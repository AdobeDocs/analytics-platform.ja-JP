---
title: 削除の影響
description: Customer Journey AnalyticsまたはExperience Platform オブジェクトの削除またはリセットの影響を理解します。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: c8b646b7e92663ed9c7e8454a336d25e34415cbe
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 11%

---

# 削除とリセットの影響

Customer Journey AnalyticsまたはExperience Platform オブジェクトの削除やリセットは、影響を与えます。 これらの影響については、この記事で概要を説明します。

## Customer Journey Analytics

Customer Journey Analyticsで接続、データビュー、またはデータセットを削除する前に、次の影響を考慮してください。

| アクション | 影響 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] の接続を削除する場合 | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除された接続用に作成されたデータビューは機能しなくなります。</li><li> 同様に、削除した接続のデータビューに依存するWorkspace プロジェクトは動作しなくなります。</li></ul>次の場合は、Customer Journey Analytics接続を削除できません。<ul><li>権限のないAdobe Experience Platform サンドボックスに関連付けられています。 これらの接続に基づいて作成されたデータビューに対する権限を持っている場合でも、基になるAdobe Experience Platform サンドボックスに対する権限が付与されるまで、接続を削除することはできません。</li><li>関連付けられているデータビューに対して、次の互換性オプションを選択します。**[!UICONTROL Adobe Journey Optimizerでデフォルトデータビューとして設定]**<p>この設定オプションについて詳しくは、[ データビューの作成または編集 ](/help/data-views/create-dataview.md#compatibility) の [ 互換性 ](/help/data-views/create-dataview.md) を参照してください</p></li></ul> |
| [!UICONTROL Customer Journey Analytics] のデータセットを削除する場合 | Customer Journey Analyticsの接続からデータセットを削除すると、そのデータセットに依存するデータビューおよびプロジェクトは機能しなくなります。 |
| [!UICONTROL Customer Journey Analytics] のデータビューを削除する場合 | Customer Journey Analyticsでデータビューを削除すると、そのデータビューを使用するWorkspace プロジェクト内のパネルが正しく機能しなくなります。 |



## Experience Platform

データセットやバッチを削除する前や、Experience Platformでサンドボックスをリセットまたは削除する際には、次の影響を考慮してください。

| アクション | 影響 |
| --- | --- |
| [!UICONTROL Experience Platform] のデータセットを削除する | Experience Platform内のそのデータセットからのデータフローは、そのデータセットを含むすべての接続を停止します。 そのデータセットのデータは、関連付けられた Customer Journey Analytics 接続から自動的に削除されます。 |
| [!UICONTROL Experience Platform] のデータセットからバッチを削除する | [!UICONTROL Adobe Experience Platform] のデータセットからバッチを削除すると、そのバッチを含む [!UICONTROL Customer Journey Analytics] 接続からも同じバッチが削除されます。 [!UICONTROL Customer Journey Analytics] には、[!UICONTROL Adobe Experience Platform] で削除されたバッチについて通知されます。 |
| [!UICONTROL Experience Platform] から **4}Customer Journey Analytics** へのバッチの取り込み中 [!UICONTROL  を削除] | データセットにバッチが 1 つしかない場合、[!UICONTROL Customer Journey Analytics] にはそのバッチからのデータも、部分的なデータも表示されません。取り込みは、ロールバックされます。例えば、データセットに 5 つのバッチがあり、4 番目のバッチが削除されたときに、それらのうち 3 つが既に取り込まれている場合、これら 3 つのバッチのデータは [!UICONTROL 0}Customer Journey Analytics} に表示されます。] |
| [!UICONTROL Experience Platform] の参照データセットを削除 | データセットの削除は、他のソースコネクタでは可能ですが、[Analytics 分類Source コネクタ ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications) のデータセットは削除できません。 誤ってそのようなデータセットを削除した場合は、カスタマーケアにお問い合わせください。 |
| Experience Platformのサンドボックスを削除またはリセット | [Experience Platform サンドボックスを削除 ](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox) すると、そのサンドボックス内のすべてのスキーマ、データセット、バッチ、ポリシーなども削除されます。 サンドボックスの識別子とサンドボックス名と同様に、サンドボックスも存在しなくなりました。<br/>Experience Platform サンドボックスを [ リセット ](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox) すると、そのサンドボックス内のすべてのスキーマ、データセット、バッチ、ポリシーなどが削除されます。 サンドボックス名と権限はそのまま残りますが、リセットが完了すると、サンドボックスの識別子が変更されます。<br/><br/>Customer Journey Analyticsは、サンドボックス識別子とサンドボックス名を使用して、接続をサンドボックスに関連付けます。 その結果、次のようになります。 <ul><li>削除またはリセットされたサンドボックスに関連付けられている接続が削除されます。</li><li>削除した接続に基づいているデータビュー（およびデータビュー内のすべてのコンポーネント定義（派生フィールドなど）が削除されます。</li><li>削除されたデータビューに依存するコンポーネントは削除されます。 例えば、セグメント、計算指標、注釈、アラート、公開済みオーディエンス、書き出しなどです。</li><li>削除されたデータビューを参照するWorkspace プロジェクトのパネルが使用できなくなる。 これらのパネルには、**[!UICONTROL 不明なデータビュー]** エラーが表示されます。 これらのパネルを削除するか、可能な場合はこれらのパネルを既存のデータビューに関連付けます。</li><li>Query Service または BI 拡張機能に依存するツールを使用して、Customer Journey Analytics内で既に使用可能な削除された接続から（履歴）データをクエリしなくなりました。 最終的に、Adobe サポートまたはエンジニアリングは、このデータをCustomer Journey Analyticsから削除します。</li></ul>Experience Platformのサンドボックスのリセットまたは削除の影響は大きいため、サンドボックスをリセットまたは削除する前に、次の点を考慮してください。<ul><li>接続を一覧表示して、どの接続がどのサンドボックスに属しているかを把握します。</li><li>データビューを一覧表示して、どのデータビューがどの接続に関連付けられているかを把握します。</li><li>重要なWorkspace プロジェクトを特定し、これらのプロジェクトがパネルで参照するデータビューを理解します。</li><li>BI 拡張機能を使用するツールとの統合を特定し、これらの統合が依存するデータビューを理解します。</li></ul> |
