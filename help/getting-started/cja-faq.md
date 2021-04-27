---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 5667e2f43873061c5350c75fdb830a95b1c9b73f
workflow-type: tm+mt
source-wordcount: '1368'
ht-degree: 60%

---

# よくある質問

[!UICONTROL Customer Journey Analytics] (CJA)は、次世代の解析製品です。以下は、CJAに関するよくある質問に対する回答です。 詳しくは、[Customer Journey Analytics 機能のサポート](/help/getting-started/cja-aa.md)を参照してください。

## 1.前提条件

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスのグラフ]または [!UICONTROL Device Co-op] は必要ですか？ | いいえ。[!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスのグラフ]や [!UICONTROL Device Co-op] は必要ありません。実際、それらはまだサポートされていません。 |
| [!UICONTROL Customer Journey Analytics] には、[!UICONTROL Experience Cloud ID]（ECID）は必要ですか？ | いいえ。[!UICONTROL Customer Journey Analytics] は、データセット内の任意の ID（[!UICONTROL ECID] か選択した他の ID かに関わらず）をサポートします。 |
| [!UICONTROL Customer Journey Analytics] の前に、データの ETL（抽出、変換、読み込み）が必要になった場合、どうしたらいいですか？ | Customer Journey Analyticsには、[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html)機能が含まれており、Adobe Experience Platformデータレークに入る前にデータを変換するのに役立ちます。 データが既に取り込まれた後にETLが必要な場合、[Adobe Experience Platformクエリサービス](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=en#queries)は、追加料金がかかる場合もありますが、いくつかの制限されたオプションを提供します。 |

{style=&quot;table-layout:auto&quot;}

## 2.データのステッチ(チャネル間分析)

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] は、デバイスやデータセットをまたいで「ステッチ」することはできますか。 | はい。[!UICONTROL 顧客ジャーニー] 分析は、 [クロスチャネル分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) (CCA)と呼ばれるステッチソリューションです。データセットのPerson IDを再キー設定できるので、複数のデータセットをシームレスに組み合わせることができます。 |
| 匿名の行動を、サポートされている認証済みの行動にステッチすることはサポートされていますか。 | はい。[クロスチャネル](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) 分析では、認証済みと未認証の両方のセッションからユーザーデータを調べ、ステッチIDを生成します。 |
| CCAでの「リプレイ」の機能 | CCAは、学習した一意の識別子に基づいてデータを「再生」します。 再生を行うと、新しいデバイスの接続がステッチされます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=en#step-1%3A-live-stitching) |
| CCAでの履歴データ(backfill)のステッチの動作 | 最初にオンにした場合、Adobeは、前月（最大60日）の初めまで遡るステッチデータのバックフィルを提供します。 このバックフィルを行うには、一時的なIDが未関連付けデータに存在し、その時点からずっと前にさかのぼる必要があります。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3.データを[!UICONTROL Customer Journey Analytics]に取り込む

| # | 質問 | 回答 |
| --- | --- | --- |
| 異なる [!UICONTROL Adobe Experience Platform] サンドボックスのデータを 1 つの [!UICONTROL Customer Journey Analytics] 接続に結合することはできますか？ | いいえ。サンドボックス全体のデータにアクセスすることはできません。同じサンドボックス内にあるデータセットのみを組み合わせることができます。[詳細情報](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| [!UICONTROL Adobe Experience Platform] の [!UICONTROL Customer Journey Analytics] では、どの程度の遅延が予想されますか？ | <ul><li>標準の負荷の場合：60 分未満 <br>**注：** パイプラインを通じたデータフローが異常に多い場合は、最長 24 時間かかる場合があります。</li><li>データのバックフィル（サイズにかかわらず、最大 13 ヶ月分のデータ）：4 週間未満</li></ul> |
| [!UICONTROL Customer Journey Analytics] でオンラインデータをオフラインデータに接続する方法を教えてください。 | データセット間で人物IDが一致する限り、[!UICONTROL Customer Journey Analytics]はフィルター、アトリビューション、フロー、フォールアウトなどを接続できます。 接続できます。 |
| オフラインデータを [!UICONTROL Customer Journey Analytics] に取り込む方法を教えてください。 | Customer Journey Analyticsに対する権利付与を使用すると、データをExperience Platformに取り込むことができます。 その後、Analysis Workspaceでのレポート用に、[!UICONTROL Customer Journey Analytics]にそのデータおよびデータ表示への接続を作成できます。 Experience Platform のデータは、オンボーディングチームが必要に応じて、レコメンデーションやコンサルティングを提供するのに役立ちます。 |
| [!UICONTROL Adobe Analytics] データを [!UICONTROL Customer Journey Analytics] に取り込む方法を教えてください。 | [!UICONTROL Adobe Analytics] のデータは、[Adobe Analytics ソースコネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/analytics.html)を通じて Experience Platform に接続できます。[!UICONTROL Adobe Analytics] のフィールドは XDM 形式で取り込まれますが、他のフィールド（[!UICONTROL マーケティングチャネル]ディメンションなど）はまだ使用できません。 |
| データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか。 | 開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。 |
| PII データを取り込んでデータ間の接続を確立する必要がありますか。 | いいえ。PII ではない顧客 ID のハッシュを含む、任意の ID を使用できます。 |

{style=&quot;table-layout:auto&quot;}

## 4.従来の[!UICONTROL Adobe Analytics]コンポーネント

| 質問 | 回答 |
| --- | --- |
| フィルター（セグメント）をCustomer Journey AnalyticsからExperience Platform統合プロファイルまたは他のExperience Cloudアプリケーションに共有/公開できますか。 | まだですが、この機能の提供に積極的に取り組んでいます。 |
| 古い eVar 設定はどうなりましたか。 | 従来の Adobe Analytics の eVar、prop およびイベントは、[!UICONTROL Customer Journey Analytics] にはもはや存在しません。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。 |
| すべてのセッションと変数の永続性の設定は、どこにありますか。 | [!UICONTROL Customer Journey Analytics] では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント／計算指標はどうなりますか。 | [!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存のセグメントや計算指標には、いずれも [!UICONTROL Customer Journey Analytics] との互換性はありません。 |
| [!UICONTROL Customer Journey Analytics] での `Uniques Exceeded` 制限の処理方法を教えてください。 | [!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。 |
| 既存の [!DNL Data Workbench] のユーザーであれば、今すぐ [!UICONTROL Customer Journey Analytics] に移行できますか。 | 使用事例によって異なります。Adobeのアカウントチームにご相談ください。 現在の使用例は、Customer Journey Analyticsにすでに適している可能性があります。 |

{style=&quot;table-layout:auto&quot;}

## 5.データ・コンポーネントの削除の影響

データ削除に関しては、次の6種類のコンポーネントが問題になります。サンドボックス、スキーマ、データセット、接続、データ表示、Workspaceプロジェクト。 次に、これらのコンポーネントを削除した場合に考えられるシナリオを示します。

| 目的 | 結果 |
| --- | --- |
| [!UICONTROL Adobe Experience Platform]のサンドボックスを削除します | サンドボックスを削除すると、そのサンドボックス内のデータセットへの [!UICONTROL Customer Journey Analytics] 接続に対するデータフローが停止します。現在、削除されたサンドボックスに関連付けられているCJA内の接続は自動的に削除されません。 |
| [!UICONTROL Adobe Experience Platform]のスキーマーを削除します。このスキーマーに関連付けられているデータセットは削除しません | [!UICONTROL Adobe Experience Platform] では、1 つ以上のデータセットが関連付けられているスキーマを削除することはできません。ただし、適切な権限を持つ管理者は、データセットを削除してからスキーマを削除できます。 |
| [!UICONTROL Adobe Experience Platform]データレークのデータセットの削除 | AEPデータレークでデータセットを削除すると、そのデータセットからそのデータセットを含むCJA接続へのデータフローが停止します。 データセットのデータは、関連付けられた CJA 接続からは自動的に削除されません。 |
| [!UICONTROL Customer Journey Analytics]内のデータセットの削除 | 現在、保存された接続内のデータセットを削除することはできません。接続全体を削除して、操作をやり直す必要があります。(ただし、CJA SKUを購入したお客様は、[!UICONTROL Adobe Experience Platform]ユーザーインターフェイスのデータセットを削除できます)。 |
| データセット([!UICONTROL Adobe Experience Platform]内)からのバッチの削除 | [!UICONTROL Adobe Experience Platform] のデータセットからバッチを削除すると、そのバッチを含む CJA 接続からも同じバッチが削除されます。  CJA には、[!UICONTROL Adobe Experience Platform] のバッチが削除されたことが通知されます。 |
| バッチ&#x200B;**を[!UICONTROL Customer Journey Analytics]に取り込まれる間に削除します** | データセットにバッチが 1 つしかない場合、そのバッチからのデータも部分的なデータも [!UICONTROL Customer Journey Analytics] には表示されません。取り込みがロールバックされます。例えば、データセットに 5 つのバッチがあり、そのうち 3 つがデータセットの削除時に既に取り込まれている場合、これら 3 つのバッチのデータは [!UICONTROL Customer Journey Analytics] に表示されます。 |
| [!UICONTROL Customer Journey Analytics]の接続を削除します | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除した接続用に作成されたデータビューは、機能しなくなります。</li><li> 同様に、削除した接続のデータビューに依存する Workspace プロジェクトは動作しなくなります。</li></ul> |
| [!UICONTROL Customer Journey Analytics]のデータ表示を削除します | この削除されたデータビューに依存する Workspace プロジェクトが動作しなくなることを示すエラーメッセージが表示されます。 |
