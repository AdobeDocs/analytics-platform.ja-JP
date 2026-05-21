---
title: 削除の影響
description: Customer Journey AnalyticsまたはExperience Platform オブジェクトの削除またはリセットの意味を理解します。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
TQID: https://experienceleague.adobe.com/95ZvIc4JM3aNY2zO6ypn-KmLrIdZ8DZga4vrOcl9Yzs
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 965
ht-degree: 9%

---

# 削除とリセットの影響

Customer Journey AnalyticsまたはExperience Platform オブジェクトの削除またはリセットには影響があります。 これらの意味については、この記事で概説しています。

## Customer Journey Analytics

Customer Journey Analyticsで接続、データビューまたはデータセットを削除する前に、次の点を考慮してください。

| アクション | 影響 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] の接続を削除する場合 | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除された接続に対して作成されたデータビューは機能しなくなります。</li><li> 同様に、削除された接続のデータビューに依存するWorkspace プロジェクトも機能しなくなります。</li></ul><p>以下のCustomer Journey Analytics接続は削除できないことに注意してください。</p><ul><li>権限がないAdobe Experience Platform サンドボックスに関連付けられます。 これらの接続で構築されたデータビューに対する権限がある場合でも、基になるAdobe Experience Platform サンドボックスに対する権限が付与されるまで、接続を削除することはできません。</li><li>接続に関連付けられているデータビューに対して、次の互換性オプションを選択します。**[!UICONTROL Adobe Journey Optimizerのデフォルトのデータビューとして設定]**<p>この設定オプションについて詳しくは、[&#x200B; データビューの作成または編集](/help/data-views/create-dataview.md)の[互換性](/help/data-views/create-dataview.md#compatibility)を参照してください。</p></li><li>次のいずれかのサービスの設定で使用されます。<ul><li>[&#x200B; オーディエンス分析](/help/connections/audience-analysis/audience-analysis-overview.md)：詳細な分析のためにCustomer Journey Analyticsにオーディエンスデータを提供します</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md): コンテンツの使用状況とCustomer Journey Analyticsへの影響に関するデータを提供します</li></ul><p>接続を削除する前に、まずこの接続を使用する設定を削除または編集する必要があります。</p></li></ul> |
| [!UICONTROL Customer Journey Analytics] のデータセットを削除する場合 | Customer Journey Analyticsの接続からデータセットを削除すると、そのデータセットに依存するデータビューとプロジェクトは機能しなくなります。 |
| [!UICONTROL Customer Journey Analytics] のデータビューを削除する場合 | Customer Journey Analyticsでデータビューを削除すると、そのデータビューに依存するWorkspace プロジェクト内のパネルが正しく機能しなくなります。<p>次のいずれかのサービスの設定で使用されているCustomer Journey Analytics データビューは削除できないことに注意してください。</p><ul><li>[&#x200B; オーディエンス分析](/help/connections/audience-analysis/audience-analysis-overview.md)：詳細な分析のためにCustomer Journey Analyticsにオーディエンスデータを提供します</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md): コンテンツの使用状況とCustomer Journey Analyticsへの影響に関するデータを提供します</li></ul><p>データビューを削除する前に、まずこのデータビューを使用する設定を削除または編集する必要があります。</p></li></ul> |



## Experience Platform

データセットやバッチを削除する前、またはExperience Platformでサンドボックスをリセットまたは削除する前に、次の点を考慮してください。

| アクション | 影響 |
| --- | --- |
| [!UICONTROL Experience Platform]のデータセットを削除 | Experience Platformのデータセットからのデータフローは、そのデータセットを含むあらゆる接続に停止します。 そのデータセットのデータは、関連付けられた Customer Journey Analytics 接続から自動的に削除されます。 |
| [!UICONTROL Experience Platform]のデータセットからバッチを削除します | バッチが[!UICONTROL Adobe Experience Platform] データセットから削除された場合、そのバッチを含む[!UICONTROL Customer Journey Analytics]接続から同じバッチが削除されます。 [!UICONTROL Customer Journey Analytics] には、[!UICONTROL Adobe Experience Platform] で削除されたバッチについて通知されます。 |
| [!UICONTROL Experience Platform] **から[!UICONTROL Customer Journey Analytics]に取り込まれているバッチを削除します** | データセットにバッチが 1 つしかない場合、[!UICONTROL Customer Journey Analytics] にはそのバッチからのデータも、部分的なデータも表示されません。 取り込みは、ロールバックされます。 例えば、データセットに5つのバッチがあり、そのうちの3つが4番目のバッチが削除されたときに既に取り込まれている場合、それらの3つのバッチのデータは[!UICONTROL Customer Journey Analytics]に表示されます。 |
| [!UICONTROL Experience Platform]のルックアップデータセットを削除 | 他のソースコネクタではデータセットの削除は可能ですが、[Analytics Classifications Source コネクタ &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications)のデータセットの削除はサポートされていません。 誤ってそのようなデータセットを削除した場合は、カスタマーケアにお問い合わせください。 |
| Experience Platformでのサンドボックスの削除またはリセット | Experience Platform サンドボックス [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox)を削除すると、そのサンドボックス内のすべてのスキーマ、データセット、バッチ、ポリシーなどが削除されます。 サンドボックスは、サンドボックス IDおよびサンドボックス名と同様に、もう存在しません。<br/>Experience Platform サンドボックスを[&#x200B; リセットすると](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox)、そのサンドボックス内のすべてのスキーマ、データセット、バッチ、ポリシーなどが削除されます。 サンドボックス名と権限は変更されませんが、リセットが完了すると、サンドボックス識別子が変更されます。<br/><br/>Customer Journey Analyticsは、サンドボックス IDとサンドボックス名を使用して、接続をサンドボックスに関連付けます。 これにより、 <ul><li>削除またはリセットされたサンドボックスに関連付けられている接続は削除されます。</li><li>削除された接続に基づくデータビュー（およびデータビュー内の派生フィールドなど、すべてのコンポーネント定義）は削除されます。</li><li>削除されたデータビューに依存しているコンポーネントは削除されます。 Adobe Analyticsのレポート機能では、セグメント、計算指標、注釈、アラート、公開オーディエンス、書き出しなどの機能を利用できます。</li><li>削除されたデータビューを参照するWorkspace プロジェクトのパネルは使用できなくなります。 これらのパネルには、**[!UICONTROL 不明なデータビュー]**&#x200B;のエラーが表示されます。 これらのパネルを削除するか、可能であれば、これらのパネルを既存のデータビューに関連付けます。</li><li>Customer Journey Analytics内で既に使用可能な削除された接続の（履歴）データを、クエリサービスまたはBI拡張機能に依存するツールを使用してクエリする必要はありません。 最終的に、Adobe サポートまたはエンジニアリングは、このデータをCustomer Journey Analyticsから削除します。</li></ul>Experience Platformのサンドボックスのリセットまたは削除の影響は大きいため、サンドボックスをリセットまたは削除する前に、次の点を考慮してください。<ul><li>どの接続がどのサンドボックスに属しているかを理解するために、接続をリストアップします。</li><li>データビューを一覧表示して、どのデータビューがどの接続に関連付けられているかを把握できます。</li><li>重要なWorkspace プロジェクトを特定し、これらのプロジェクトがパネルで参照するデータビューを理解します。</li><li>BI拡張機能を使用するツールとの統合を特定し、その統合がどのデータビューに依存しているかを把握します。</li></ul> |
