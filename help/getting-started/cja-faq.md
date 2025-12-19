---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: c67225619153218e3dca1eacea204f2b033dfb14
workflow-type: tm+mt
source-wordcount: '2210'
ht-degree: 98%

---

# よくある質問

Adobe Customer Journey Analytics は、次世代の分析製品です。この記事では、Customer Journey Analytics に関するよくある質問に対する回答を示します。詳しくは、[Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を参照してください。

## &#x200B;1. 前提条件 {#prerequisites}

+++**[!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスグラフ]または [!UICONTROL Device Co-op] は必要ですか？**

いいえ。[!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスのグラフ]や [!UICONTROL Device Co-op] は必要ありません。実際、それらはまだサポートされていません。

+++


+++**[!UICONTROL Customer Journey Analytics] には、[!UICONTROL Experience Cloud ID]（ECID）は必要ですか？**

いいえ。[!UICONTROL Customer Journey Analytics] では、[!UICONTROL ECID] か任意に選択した他の ID かに関わらず、データセット内の任意の ID をサポートしています。

+++


+++**[!UICONTROL Customer Journey Analytics] に先立ってデータの ETL（抽出、変換、読み込み）が必要になった場合は、どうすればよいですか？**

Customer Journey Analytics には、[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=ja)機能が含まれており、Adobe Experience Platform データレイクに取り込む前にデータを変換するのに役立ちます。データが既に取り込まれた後に ETL が必要な場合、[Adobe Experience Platform クエリサービス](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=ja#queries)がいくつかの制限付きオプションを提供しますが、追加料金がかかる場合もあります。

+++


## &#x200B;2. データのステッチ {#stitching}

+++**[!UICONTROL Customer Journey Analytics] では、様々なデバイスやデータセットにわたって「ステッチ」することはできますか？**

はい。[!UICONTROL Customer Journey Analytics] には、データセット内の認証済みイベントと未認証イベント全体で機能する[ステッチ](../stitching/overview.md)機能があります。このステッチにより、異なるレコードを単一のステッチ ID に解決し、ユーザーレベルでのクロスデバイス分析が可能になります。
さらに、共通の名前空間 ID（ユーザー ID）が[接続](/help/connections/overview.md)内のデータセット全体で使用される場合、ユーザーレベルで「ステッチされた」複数のデータセットのシームレスな組み合わせに対して分析を実行できます。

+++


+++**匿名の行動から認証済みの行動にステッチすることはサポートされていますか？**

はい。[ステッチ](../stitching/overview.md)では、認証済みセッションと未認証のセッションの両方からのユーザーデータを調べて、ステッチされた ID を生成します。

+++


+++**ステッチでは「再生」はどのように機能しますか？**

ステッチでは、学習した一意の ID に基づいてデータを「再生」します。再生は、当面、識別されたデバイスから、最初は未認証のイベントをステッチすることを目的としています。[詳細情報](../stitching/overview.md)

+++


+++**履歴データのステッチ（バックフィル）はどのように機能しますか？**

最初にオンにした際、アドビでは、選択した期間（お客様に使用権限がある Customer Journey Analytics パッケージに応じて、最大 25 か月）まで遡るステッチデータのバックフィルを提供します。このバックフィルを行うには、ステッチされていない過去のデータに一時的な ID が存在する必要があります。[詳細情報](../stitching/overview.md)

+++


+++**ステッチされていないプロファイルデータセットレコードの場合は、どのような動作が想定されますか？**

**シナリオの例**：`CRMid` をユーザー ID として使用することで、Customer Journey Analytics 接続の 2 つのデータセットを結合します。1 つは、すべてのレコードで `CRMid` を使用した web イベントデータセットです。もう 1 つのデータセットは、CRM プロファイルデータセットです。CRM データセットの 40％は、web イベントデータセットに `CRMid` が存在します。残りの 60％は、web イベントデータセットには存在しません。これらのレコードは、Analysis Workspace のレポートに表示されますか？<p> **回答**：イベントが関連付けられていないプロファイル行は、Customer Journey Analytics に保存されます。ただし、その ID に関連付けられたイベントが表示されるまでは、Analysis Workspace で表示できません。

+++

## &#x200B;3. [!UICONTROL Customer Journey Analytics] へのデータの取り込み {#ingest}

+++**異なる [!UICONTROL Adobe Experience Platform] サンドボックスのデータを 1 つの [!UICONTROL Customer Journey Analytics] 接続に結合することはできますか？**

いいえ。サンドボックス全体のデータにアクセスすることはできません。同じサンドボックス内にあるデータセットのみを組み合わせることができます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#select-sandbox-and-datasets)

+++


+++**[!UICONTROL Customer Journey Analytics] でオンラインデータをオフラインデータに接続するにはどうすればよいですか？**

データセット間でユーザー ID が一致する限り、[!UICONTROL Customer Journey Analytics] はデータセット間でセグメント、アトリビューション、フロー、フォールアウトなどを接続できます。

+++


+++**オフラインデータを [!UICONTROL Customer Journey Analytics] に取り込むにはどうすればよいですか？**

Customer Journey Analytics に対する使用権があれば、Experience Platform にデータを取り込むことができます。その後、Analysis Workspace でのレポート用に、[!UICONTROL Customer Journey Analytics] で、そのデータへの接続とデータビューを作成できます。Experience Platform のデータオンボーディングチームが、必要に応じて、レコメンデーションやコンサルティングの提供を支援します。

+++


+++**[!UICONTROL Adobe Analytics] データを [!UICONTROL Customer Journey Analytics] に取り込むにはどうすればよいですか？**

[!UICONTROL Adobe Analytics] のデータは、[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を通じて Experience Platform に接続できます。[!UICONTROL Adobe Analytics] のほとんどのフィールドは XDM 形式で取り込まれますが、それ以外のフィールドはまだ使用できません。

+++


+++**データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか？**

開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。

+++


+++**データ間の接続を確立するのに、PII データを取り込む必要がありますか？**

いいえ。例えば顧客 ID のハッシュは PII ではありませんが、こうしたものも含め、任意の ID を使用できます。

+++


+++**過去または未来の日付やタイムスタンプを Customer Journey Analytics イベントデータセットに取り込む場合、どのような制限がありますか？**

* 過去の日付／タイムスタンプの場合：最大 10 年前までのイベントデータ。
* 将来の日付／タイムスタンプの場合：最大 1 か月先のイベントデータ（予測）。

+++


## &#x200B;4. 待ち時間に関する考慮事項 {#latency}

>[!NOTE]
>
>Customer Journey Analytics のデータサイズは固定ではないので、アドビは標準的な取り込み時間を明言することはできません。アドビでは、更新プログラムの提供と取り込みの最適化を通じて、これらの待ち時間を短縮するよう積極的に取り組んでいます。

* ライブデータまたはイベント：Adobe Experience Platform でデータが使用可能になってから 90 分以内に処理して取り込みます（バッチサイズが 5,000 万行を超える場合：90 分以上）。ステッチを有効にした場合、取り込みに最大 4 時間かかることがあります。詳しくは、[ガードレール](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/technotes/guardrails)を参照してください。
* 小さなバックフィル：7 日以内
* 大きなバックフィル：30 日以内

アドビでは、最近、Customer Journey Analytics でのデータの処理方法を変更しました。

* 「現在」の日付のイベントデータは、ライブデータとしてストリーミングされます。前日の午後 11:59:59（23:59:59）より前のイベント時間を持つデータは、バックフィルとして処理されます。
* 経過時間が 24 時間以上のイベントデータは、（より新しいデータと同じバッチにある場合でも）バックフィルと見なされ、低い優先度で取り込まれます。

## &#x200B;5. [!UICONTROL 接続]データ保持ためのローリングウィンドウ（相対期間）の設定 {#data-retention}

[**[!UICONTROL 周期的なデータ期間を有効化&#x200B;]**設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#create-connection)を使用すると、Customer Journey Analytics データ保持を月単位（3 か月や 6 か月など）の周期的な期間として定義できます。これは、[!UICONTROL データセット]レベルではなく、[!UICONTROL 接続]レベルで設定されます。データ保持は、イベントデータセットのタイムスタンプに基づいており、イベントデータセットにのみ適用されます。適用可能なタイムスタンプがないので、プロファイルまたはルックアップデータセットのデータ保持設定は存在しません。

主な利点は、該当する有用なデータのみを保存またはレポートして、有用でなくなった古いデータを削除できるという点です。 契約上の上限を超えないようにし、超過コストのリスクを軽減します。

## &#x200B;6. オブジェクトまたはコンポーネントの削除の影響 {#deletion}

Customer Journey AnalyticsまたはExperience Platformのオブジェクトやコンポーネントを削除またはリセットした場合の影響の概要については、[ 削除とリセットの影響 ](/help/technotes/deletion.md) を参照してください。

<!-- Refer to deletion guide 

For data deletion, you should be concerned about six types of components: sandbox, schema, dataset, connection, data view, and Workspace project. Here are some possible scenarios around deleting any of these components:

| If you... | This happens... |
| --- | --- |
| Delete a sandbox in [!UICONTROL Adobe Experience Platform] | Deleting a sandbox stops the data flow to any [!UICONTROL Customer Journey Analytics] connections to datasets in that sandbox. Connections, data views, metrics and dimensions related to this deleted sandbox will also be deleted. |
| Delete a schema in [!UICONTROL Adobe Experience Platform], but not the dataset/s associated with this schema | [!UICONTROL Adobe Experience Platform] does not allow for the deletion of [!UICONTROL schemas] that have one or more [!UICONTROL datasets] associated with them. However, an Admin with the appropriate set of rights can delete the datasets first and then delete the schema. |
| Delete a dataset in the [!UICONTROL Adobe Experience Platform] data lake | Deleting a dataset in Adobe Experience Platform data lake stops data flow from that dataset to any Customer Journey Analytics Connections that include that dataset. Any data from that dataset is automatically deleted from the associated Customer Journey Analytics connections. |
| Delete a dataset in [!UICONTROL Customer Journey Analytics] | Contact your Adobe Account Team to set in motion the process for deleting a dataset within a connection that has been saved. |
| Delete a batch from a dataset (in [!UICONTROL Adobe Experience Platform]) | If a batch is deleted from an [!UICONTROL Adobe Experience Platform] dataset, the same batch is removed from any Customer Journey Analytics connections that contain that specific batch. Customer Journey Analytics is notified of batch deletions in [!UICONTROL Adobe Experience Platform]. |
| Delete a batch **while it is being ingested** into [!UICONTROL Customer Journey Analytics] | If there is only one batch in the dataset, no data or partial data from that batch appears in [!UICONTROL Customer Journey Analytics]. The ingestion is rolled back. For example, if there are five batches in the dataset and three of them have already been ingested when the dataset was deleted, data from those 3 batches appears in [!UICONTROL Customer Journey Analytics]. |
| Delete a connection in [!UICONTROL Customer Journey Analytics] | An error message indicates that:<ul><li>Any data views created for the deleted connection will no longer work.</li><li> Similarly, any Workspace projects that depend on data views in the deleted connection stops working.</li></ul> |
| Delete a data view in [!UICONTROL Customer Journey Analytics] | An error message indicates that any Workspace projects that depend on this deleted data view will stop working. |

-->

## &#x200B;7. レポートスイートを Customer Journey Analytics で結合する際の考慮事項 {#merge-reportsuite}

[Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を通じて Adobe Analytics データを取り込む予定がある場合は、2 つ以上の Adobe Analytics レポートスイートを結合する際に、次の影響を考慮してください。

| 問題 | 考慮事項 |
| --- | --- |
| 変数 | [!UICONTROL eVars] などの変数は、レポートスイート間で並べて使用することはできません。例えば、レポートスイート 1 の eVar1 が&#x200B;**[!UICONTROL ページ]**&#x200B;を指し、レポートスイート 2 の eVar1 が **[!UICONTROL 内部キャンペーン]** を指している場合、レポートの内容が混在したり、不正確になったりする可能性があります。 |
| [!UICONTROL セッション]と[!UICONTROL ユーザー]のカウント | 複数のレポートスイートをまたいで重複排除が行われます。その結果、カウントが一致しない場合があります。 |
| 指標の重複排除 | 複数の行に同じトランザクション ID がある場合（例：[!UICONTROL 購入 ID]）、指標のインスタンスの重複を排除します（例：[!UICONTROL 注文]）。これにより、主要指標の数が増えすぎるのを防ぎます。その結果、[!UICONTROL 注文]などの指標が複数のレポートスイートにまたがって合計されない場合があります。 |
| 通貨 | 通貨換算は、まだ Customer Journey Analytics でサポートされていません。異なる基本通貨を使用しているレポートスイートを結合すると、問題が発生する可能性があります。 |
| [!UICONTROL 永続性] | [永続性](../data-views/component-settings/persistence.md)は複数のレポートスイートにまたがって適用され、[!UICONTROL セグメント]、[!UICONTROL アトリビューション]などに影響します。数値が正しく加算されない場合があります。 |
| [!UICONTROL 分類] | [!UICONTROL 分類] は、レポートスイートを結合する際に、分類の重複が自動的に除外されないようにします。複数の分類ファイルを 1 つの[!UICONTROL ルックアップ]データセットに組み合わせると、問題が発生する場合があります。 |

## &#x200B;8. [!UICONTROL Adobe Analytics] コンポーネント

+++**[!UICONTROL オーディエンス]を [!DNL Customer Journey Analytics] から Experience Platform Real-Time CDP または他の Experience Cloud アプリケーションに共有または公開できますか？**

Adobe Experience Platform のリアルタイム顧客プロファイルに Customer Journey Analytics で識別された[オーディエンスを作成して公開](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/audiences/publish)し、顧客のターゲティングやパーソナライゼーションを実現できます。

+++

+++**以前の [!UICONTROL eVar] 設定はどうなりましたか？**

Adobe Analytics の [!UICONTROL eVar]、[!UICONTROL prop] および[!UICONTROL イベント]は、[!UICONTROL Customer Journey Analytics] にはもう存在しません。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。

+++

+++**現在、セッションと変数の永続性に関するすべての設定はどこにありますか？**

[!UICONTROL Customer Journey Analytics] では、レポート時にこれらの設定をすべて適用し、これらの設定はデータビューに反映されるようになりました。これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。

+++

+++**既存のセグメント／計算指標はどうなりますか？**

[!UICONTROL Customer Journey Analytics] では、eVar、prop またはイベントを使用しなくなりました。代わりに Experience Platform スキーマ要素を使用します。つまり、既存のセグメントや計算指標には、いずれも [!UICONTROL Customer Journey Analytics] との互換性はありません。

+++

+++**[!UICONTROL Customer Journey Analytics] では `Uniques Exceeded` 制限はどのように処理されますか？**

[!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。

+++

+++**既存の [!DNL Data Workbench] ユーザーであれば、今すぐ [!UICONTROL Customer Journey Analytics] に移行できますか？**

ユースケースによって異なります。アドビのアカウントチームにご相談ください。お客様の現在のユースケースは、Customer Journey Analytics に適している可能性があります。

+++

## &#x200B;9. 接続サイズの推定 {#estimate-size}

詳しくは、[接続の使用状況](/help/connections/manage-connections.md#usage)を参照してください。

## &#x200B;10. 使用量超過について {#overage}

使用量制限は、アドビによって定期的にモニタリングされ、適用されます。「データ行」とは、Customer Journey Analytics 内で分析に使用できる 1 日あたりの平均データ行数を意味します。

例えば、契約では 100 万行のデータを使用できるとします。Customer Journey Analytics の使用開始 1 日目に 200 万行のデータをアップロードし、2 日目に 100 万行を削除して、ライセンスの残りの期間は、許可されたデータ行の最大値（この例では、100 万行）以内に使用量を抑えたとします。この場合でも、契約条件によっては、「データ行」ライセンスの使用量制限を超えた 1 日目について、超過分の料金（日割り計算）が発生することがあります。

## &#x200B;11. データの不一致の診断 {#discrepancies}

場合によっては、接続によって取り込まれるイベントの合計数が [!UICONTROL Adobe Experience Platform] のデータセットの行数と異なることがあります。この例の場合、データセット「B2B Impression」には 7650 の行がありますが、[!UICONTROL Adobe Experience Platform] のデータセットの行数は 3830 です。不一致が発生する理由はいくつかあり、次の手順を実行して診断できます。

1. このディメンションを **[!UICONTROL Platform データセット ID]** ごとに分類すると、サイズは同じで **[!UICONTROL Platform データセット ID]** が異なる 2 つのデータセットがあることがわかります。各データセットには 3825 件のレコードがあります。つまり、[!UICONTROL Customer Journey Analytics] では、ユーザー ID またはタイムスタンプが欠落していることにより、5 件のレコードが無視されています。

   ![分類](assets/data-size2.png)

1. また、[!UICONTROL Adobe Experience Platform] にチェックインすると、ID「5f21c12b732044194bffc1d0」のデータセットがありません。つまり、他のユーザーが最初の接続の作成時に [!UICONTROL Adobe Experience Platform] からこの特定のデータセットを削除しています。その後、Customer Journey Analytics に再び追加されましたが、[!UICONTROL Adobe Experience Platform] によって異なる [!UICONTROL Platform データセット ID] が生成されました。

[!UICONTROL Customer Journey Analytics] と [!UICONTROL Adobe Experience Platform] におけるデータセットと接続の削除の影響については、[こちら](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components)を参照してください。


## &#x200B;12. 地域データ収集

Adobe Experience Cloud では、地域データ収集（RDC）を使用して、訪問者とアドビおよびアドビ以外のソリューションとの間のインタラクションが訪問者のできるだけ近くで行われるようにします。 データがデータ収集センター （DCC、Edge サイトとも呼ばれ、Platform Edge Network の一部）に地域的に収集されると、データストリームやイベント転送の設定に基づいて、安全な接続を介して関連ソリューションに転送されます。

![Edge Network を使用したデータフロー](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png?lang=ja)

地域データ収集プロセスでは、次の手順に従います。

1. DNS は、訪問者に最も近いデータ収集センターの IP アドレスに、収集のホスト名を自動で解決します。
1. 訪問者はデータをその場所に送信します。
1. データは、安全な接続を介して、データストリームまたはイベント転送設定によって定義されたソリューションに即座に転送されます。

地域データ収集を使用すると、次のような利点があります。

* **パフォーマンス**：RDC により、訪問者は最も近い DCC に接続します。この最適化により、応答時間が最速になり、追跡の精度が向上し、読み込み時間が短縮します。
* **冗長性**：DCC と DPC 間の通信が中断されると、アドビの RDC インフラストラクチャがデータをローカルに保存し、その後そのデータを通信が復旧した際に DPC に送信します。

RDC には現在、次の場所が含まれています（変更される場合があります）：


| RDC タイプ | データ収集センター |
| --- | --- |
| グローバル（デフォルト） | オレゴン州、バージニア州、アイルランド、パリ、ムンバイ、シンガポール、東京、シドニー |
| 米州のみ | オレゴン州、バージニア州 |
| ヨーロッパのみ | アイルランド、パリ |
| アジア太平洋地域のみ | ムンバイ、シンガポール、東京、シドニー |

{style="table-layout:auto"}

データが地域のデータセンターに到達すると、データストリームの設定によって、データのルーティング方法が決まります。

Customer Journey Analytics には Adobe Experience Platform からのデータセットが必要なので、データストリーム／イベント転送設定では、地域のデータセンターから Adobe Experience Platform インスタンスが配置されているデータセンターにデータをルーティングするために Adobe Experience Platform サービスが必要です。Customer Journey Analytics とそのサポートサービスおよびインフラストラクチャは、同じ Adobe Experience Platform インスタンスにデプロイされます。


Adobe Experience Platform Edge Network とその地域のデータセンターを超えたデータ収集プロセスについて詳しくは、[データ収集の概要](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html?lang=ja)を参照してください。
