---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: b66aed675153af3a2a0fbb77569d5c4c90d48022
workflow-type: tm+mt
source-wordcount: '2199'
ht-degree: 72%

---

# よくある質問

Adobe Customer Journey Analyticsは次世代の分析製品です。 次に、Customer Journey Analyticsに関するよくある質問に対する回答を示します。 詳しくは、[Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を参照してください。

## 1. 前提条件 {#prerequisites}

+++**[!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスグラフ]または [!UICONTROL Device Co-op] は必要ですか？**

いいえ。[!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスのグラフ]や [!UICONTROL Device Co-op] は必要ありません。実際、それらはまだサポートされていません。

+++


+++**[!UICONTROL Customer Journey Analytics] には、[!UICONTROL Experience Cloud ID]（ECID）は必要ですか？**

いいえ。[!UICONTROL Customer Journey Analytics] では、[!UICONTROL ECID] か任意に選択した他の ID かに関わらず、データセット内の任意の ID をサポートしています。

+++


+++**[!UICONTROL Customer Journey Analytics] に先立ってデータの ETL（抽出、変換、読み込み）が必要になった場合は、どうすればよいですか？**

Customer Journey Analytics には、[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=ja)機能が含まれており、Adobe Experience Platform データレイクに取り込む前にデータを変換するのに役立ちます。データが既に取り込まれた後に ETL が必要な場合、[Adobe Experience Platform クエリサービス](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=ja#queries)がいくつかの制限付きオプションを提供しますが、追加料金がかかる場合もあります。

+++


## 2. データのステッチ（クロスチャネル分析） {#stitching}

+++**[!UICONTROL Customer Journey Analytics] では、様々なデバイスやデータセットにわたって「ステッチ」することはできますか？**

はい。[!UICONTROL Customer Journey Analytics] には、[クロスチャネル分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ja)（CCA）と呼ばれるステッチソリューションがあります。データセットのユーザー ID を再入力できるので、複数のデータセットをシームレスに組み合わせることができます。

+++


+++**匿名の行動から認証済みの行動にステッチすることはサポートされていますか？**

はい。[クロスチャネル分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ja)では、認証済みセッションと未認証セッションの両方からのユーザーデータを調べて、ステッチされた ID を生成します。

+++


+++**CCA では「再生」はどのように機能しますか？**

CCA（クロスチャネル分析）では、学習した一意の ID に基づいてデータを「再生」します。再生を行うと、接続の新しいデバイスがステッチされます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=ja#step-1%3A-live-stitching)

+++


+++**CCA では履歴データのステッチ（バックフィル）はどのように機能しますか？**

初めてオンにしたとき、前月の初め（最大 60 日前）まで遡ってステッチデータのバックフィルが行われます。このバックフィルを行うには、ステッチされていない過去のデータに一時的な ID が存在する必要があります。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ja#enable-cross-channel-analytics)

+++


+++**未関連付けプロファイルデータセットレコードに対して期待される動作は何ですか？**

**シナリオの例**:を使用して、Customer Journey Analytics接続で 2 つのデータセットを結合する `CRMid` をユーザー ID として設定します。 1 つは、すべてのレコードで `CRMid` を使用した web イベントデータセットです。他のデータセットは、CRM プロファイルデータセットです。 CRM データセットの 40%に `CRMid` が Web イベントデータセットに存在する。 残りの 60％は、web イベントデータセットには存在しません。これらのレコードは、Analysis Workspace のレポートに表示されますか。<p> **回答**:イベントが関連付けられていないプロファイル行は、Customer Journey Analyticsに保存されます。 ただし、その ID に関連付けられたイベントが表示されるまでは、Analysis Workspace で表示できません。

+++

## 3. [!UICONTROL Customer Journey Analytics] へのデータの取り込み {#ingest}

+++**異なる [!UICONTROL Adobe Experience Platform] サンドボックスのデータを 1 つの [!UICONTROL Customer Journey Analytics] 接続に結合することはできますか？**

いいえ。サンドボックス全体のデータにアクセスすることはできません。同じサンドボックス内にあるデータセットのみを組み合わせることができます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#select-sandbox-and-datasets)

+++


+++**[!UICONTROL Customer Journey Analytics] でオンラインデータをオフラインデータに接続するにはどうすればよいですか？**

データセット間でユーザー ID が一致する限り、[!UICONTROL Customer Journey Analytics] は、フィルター、アトリビューション、フロー、フォールアウトなどを接続できます。接続できます。

+++


+++**オフラインデータを [!UICONTROL Customer Journey Analytics] に取り込むにはどうすればよいですか？**

Customer Journey Analytics に対する使用権があれば、Experience Platform にデータを取り込むことができます。その後、Analysis Workspace でのレポート用に、[!UICONTROL Customer Journey Analytics] で、そのデータへの接続とデータビューを作成できます。Experience Platform のデータオンボーディングチームが、必要に応じて、レコメンデーションやコンサルティングの提供を支援します。

+++


+++**[!UICONTROL Adobe Analytics] データを [!UICONTROL Customer Journey Analytics] に取り込むにはどうすればよいですか？**

[!UICONTROL Adobe Analytics] データは、[Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を通じて Experience Platform に接続できます。[!UICONTROL Adobe Analytics] のほとんどのフィールドは XDM 形式で取り込まれますが、それ以外のフィールドはまだ使用できません。

+++


+++**データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか？**

開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。

+++


+++**データ間の接続を確立するのに、PII データを取り込む必要がありますか？**

いいえ。例えば顧客 ID のハッシュは PII ではありませんが、こうしたものも含め、任意の ID を使用できます。

+++


+++**過去または将来の日付/タイムスタンプをCustomer Journey Analyticsイベントデータセットに取り込む際の制限は何ですか。**

<ul><li>過去の日付／タイムスタンプの場合：最大 10 年前までのイベントデータ。</li><li>将来の日付／タイムスタンプの場合：最大 1 か月先のイベントデータ（予測）。</li></ul>

+++


## 4. 待ち時間に関する考慮事項 {#latency}

>[!NOTE]
>Customer Journey Analyticsには固定データサイズがないので、Adobeは標準の取り込み時間にコミットできません。 アドビでは、更新プログラムの提供と取り込みの最適化を通じて、これらの待ち時間を短縮するよう積極的に取り組んでいます。

+++**の予想遅延 [!UICONTROL Customer Journey Analytics] データ [!UICONTROL Adobe Experience Platform]?**

<ul><li>ライブデータまたはイベント：データがAdobe Experience Platformで使用可能になったら、90 分以内に処理および取り込みます。 （バッチサイズが 5,000 万行を超える場合：90 分以上）。</li><li>小さなバックフィル：七日以内に<li>大きなバックフィル：30 日以内に</li></ul>

最近、Customer Journey Analyticsのデータ処理方法を変更しました。

<ul><li>タイムスタンプが 24 時間未満のイベントデータは、でストリーミングされます。</li><li>タイムスタンプが 24 時間以上のイベントデータ（新しいデータと同じバッチにある場合でも）はバックフィルと見なされ、より低い優先度で取り込まれます。</li></ul>

+++

## 5. [!UICONTROL 接続]データ保持ためのローリングウィンドウ（相対期間）の設定 {#data-retention}

この [**[!UICONTROL 周期データウィンドウを有効にする&#x200B;]**設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#create-connection) を使用すると、Customer Journey Analyticsデータの保持を周期的な期間（3 か月、6 か月など）として月単位で定義できます。 これは、[!UICONTROL データセット]レベルではなく、[!UICONTROL 接続]レベルで設定されます。データ保持は、イベントデータセットのタイムスタンプに基づいており、イベントデータセットにのみ適用されます。適用可能なタイムスタンプがないので、プロファイルまたはルックアップデータセットのデータ保持設定は存在しません。

主な利点は、該当する有用なデータのみを保存またはレポートして、有用でなくなった古いデータを削除できるという点です。契約上の上限を超えないようにし、超過コストのリスクを軽減します。

## 6. データコンポーネントの削除の影響 {#deletion}

データの削除に関しては、サンドボックス、スキーマ、データセット、接続、データビュー、ワークスペースプロジェクトの 6 種類のコンポーネントを考慮する必要があります。次に、これらのコンポーネントを削除した場合に考えられるシナリオを示します。

| 目的 | 結果 |
| --- | --- |
| [!UICONTROL Adobe Experience Platform] のサンドボックスを削除する場合 | サンドボックスを削除すると、そのサンドボックス内のデータセットへの [!UICONTROL Customer Journey Analytics] 接続に対するデータフローが停止します。現在、 [!UICONTROL 接続] 削除されたサンドボックスに関連付けられているCustomer Journey Analytics内は、自動的には削除されません。 |
| [!UICONTROL Adobe Experience Platform] のスキーマを削除し、このスキーマに関連付けられているデータセットを削除しない場合 | [!UICONTROL Adobe Experience Platform] では、1 つ以上の[!UICONTROL データセット]が関連付けられている[!UICONTROL スキーマ]を削除することはできません。ただし、適切な権限を持つ管理者は、データセットを削除してからスキーマを削除できます。 |
| [!UICONTROL Adobe Experience Platform] データレイクのデータセットを削除する場合 | Adobe Experience Platformデータレイクのデータセットを削除すると、そのデータセットから、そのデータセットを含むすべてのCustomer Journey Analytics接続へのデータフローが停止します。 データセットのデータは、関連付けられたCustomer Journey Analytics接続から自動的に削除されます。 |
| [!UICONTROL Customer Journey Analytics] のデータセットを削除する場合 | 保存したAdobe内のデータセットの削除プロセスを運用中に設定するには、接続アカウントチームに連絡してください。 |
| （[!UICONTROL Adobe Experience Platform] の）データセットからバッチを削除する場合 | バッチが [!UICONTROL Adobe Experience Platform] データセットの場合、同じバッチが、その特定のバッチを含むCustomer Journey Analytics接続から削除されます。  Customer Journey Analyticsに、 [!UICONTROL Adobe Experience Platform]. |
| [!UICONTROL Customer Journey Analytics] への&#x200B;**取り込み中**&#x200B;にバッチを削除する場合 | データセットにバッチが 1 つしかない場合、そのバッチからのデータも部分的なデータも [!UICONTROL Customer Journey Analytics] には表示されません。取り込みがロールバックされます。例えば、データセットに 5 つのバッチがあり、そのうち 3 つがデータセットの削除時に既に取り込まれている場合、これら 3 つのバッチのデータは、 [!UICONTROL Customer Journey Analytics]. |
| [!UICONTROL Customer Journey Analytics] の接続を削除する場合 | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除した接続用に作成されたデータビューは、機能しなくなります。</li><li> 同様に、削除した接続のデータビューに依存するワークスペースプロジェクトは動作しなくなります。</li></ul> |
| [!UICONTROL Customer Journey Analytics] のデータビューを削除する場合 | この削除されたデータビューに依存する Workspace プロジェクトが動作しなくなることを示すエラーメッセージが表示されます。 |

## 7.レポートスイートをCustomer Journey Analyticsで結合する際の考慮事項 {#merge-reportsuite}

[Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja) を通じて Adobe Analytics データを取り込む予定がある場合は、2 つ以上の Adobe Analytics レポートスイートを結合する際に、次の影響を考慮してください。

| 問題 | 考慮事項 |
| --- | --- |
| 変数 | [!UICONTROL eVars] などの変数は、レポートスイート間で並べて使用することはできません。例えば、レポートスイート 1 の eVar1 が&#x200B;**[!UICONTROL ページ]**&#x200B;を指し、レポートスイート 2 の eVar1 が **[!UICONTROL 内部キャンペーン]** を指している場合、レポートの内容が混在したり、不正確になったりする可能性があります。 |
| [!UICONTROL セッション]と[!UICONTROL ユーザー]のカウント | 複数のレポートスイートをまたいで重複排除が行われます。その結果、カウントが一致しない場合があります。 |
| 指標の重複排除 | 複数の行に同じトランザクション ID がある場合（例：[!UICONTROL 購入 ID]）、指標のインスタンスの重複を排除します（例：[!UICONTROL 注文]）。これにより、主要指標の数が増えすぎるのを防ぎます。その結果、[!UICONTROL 注文]などの指標が複数のレポートスイートにまたがって合計されない場合があります。 |
| 通貨 | 通貨換算は、まだCustomer Journey Analyticsでサポートされていません。 異なる基本通貨を使用しているレポートスイートを結合すると、問題が発生する可能性があります。 |
| [!UICONTROL 永続性] | [永続性](../data-views/component-settings/persistence.md)は複数のレポートスイートにまたがって適用され、[!UICONTROL フィルター]、[!UICONTROL アトリビューション]などに影響します。数値が正しく加算されない場合があります。 |
| [!UICONTROL 分類] | [!UICONTROL 分類] は、レポートスイートを結合する際に、分類の重複が自動的に除外されないようにします。複数の分類ファイルを 1 つに組み合わせる場合 [!UICONTROL 参照] データセットに含めると、問題が発生する場合があります。 |

## 8. [!UICONTROL Adobe Analytics] コンポーネント

+++**共有/公開できますか [!UICONTROL フィルター] から [!DNL Customer Journey Analytics] Real-Time CDPやその他のExperience Cloud・アプリケーションに**

現在はできませんが、アドビではこの機能を提供できるように鋭意取り組んでいます。

+++

+++**以前の [!UICONTROL eVar] 設定はどうなりましたか？**

[!UICONTROL eVar], [!UICONTROL prop]、および [!UICONTROL イベント] Adobe Analyticsの意味では～にはもはや存在しない [!UICONTROL Customer Journey Analytics]. スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。

+++

+++**現在、セッションと変数の永続性に関するすべての設定はどこにありますか？**

[!UICONTROL Customer Journey Analytics] では、レポート時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。 これらの設定に対する変更が遡及的になり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。

+++

+++**既存のセグメント／計算指標はどうなりますか？**

[!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに、Adobe Experience Platformスキーマを使用します。 つまり、既存のセグメントや計算指標には、いずれも [!UICONTROL Customer Journey Analytics] との互換性はありません。

+++

+++**[!UICONTROL Customer Journey Analytics] では `Uniques Exceeded` 制限はどのように処理されますか？**

[!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。

+++

+++**既存の [!DNL Data Workbench] ユーザーであれば、今すぐ [!UICONTROL Customer Journey Analytics] に移行できますか？**

ユースケースによって異なります。アドビアカウントチームにご相談ください。お客様の現在のユースケースは、既に Customer Journey Analytics に適している可能性があります。

+++

## 9. 接続サイズの推定 {#estimate-size}

[使用状況の推定と管理](/help/admin/estimate-usage.md)を参照してください。

## 10. 使用量超過について {#overage}

使用量制限は、アドビによって定期的にモニタリングされ、適用されます。「データ行」とは、Customer Journey Analytics 内で分析に使用できる 1 日あたりの平均データ行数を意味します。

例えば、契約によって 100 万行のデータを使用できるとしましょう。Customer Journey Analytics の使用開始 1 日目に 200 万行のデータをアップロードし、2 日目に 100 万行を削除して、ライセンスの残りの期間は、許可されたデータ行の最大値（この例では、100 万行）以内に使用量を抑えたとします。この場合でも、契約条件によっては、「データ行」ライセンスの使用量制限を超えた 1 日目について、超過分の料金（日割り計算）が発生することがあります。

## 11. データの不一致の診断 {#discrepancies}

場合によっては、接続によって取り込まれるイベントの合計数が [!UICONTROL Adobe Experience Platform] のデータセットの行数と異なることがあります。この例の場合、データセット「B2B Impression」には 7650 の行がありますが、[!UICONTROL Adobe Experience Platform] のデータセットの行数は 3830 です。不一致が発生する理由はいくつかあり、次の手順を実行して診断できます。

1. このディメンションを次の項目で分類 **[!UICONTROL プラットフォームデータセット ID]** サイズは同じでもサイズが異なる 2 つのデータセットがあることがわかります。 **[!UICONTROL プラットフォームデータセット ID]**. 各データセットには 3825 件のレコードがあります。つまり、[!UICONTROL Customer Journey Analytics] では、ユーザー ID またはタイムスタンプが欠落していることにより、5 件のレコードが無視されています。

   ![分類](assets/data-size2.png)

2. また、 [!UICONTROL Adobe Experience Platform]、ID が「5f21c12b732044194bffc1d0」のデータセットがないので、他のユーザーがこの特定のデータセットを次から削除しました： [!UICONTROL Adobe Experience Platform] 最初の接続が作成された時点。 その後、再びCustomer Journey Analyticsに追加されましたが、異なる [!UICONTROL プラットフォームデータセット ID] が次の場所で生成された： [!UICONTROL Adobe Experience Platform].

[!UICONTROL Customer Journey Analytics] と [!UICONTROL Adobe Experience Platform] におけるデータセットと接続の削除の影響については、[こちら](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components)を参照してください。
