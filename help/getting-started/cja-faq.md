---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
translation-type: tm+mt
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# よくある質問

| 質問 | 回答 |
|---|---|
| **前提条件** |  |
| Do you need Device Graph or Device Coop for [!UICONTROL Customer Journey Analytics]? | No, Private Device Graph or Device Coop are not required for [!UICONTROL Customer Journey Analytics]. 実際、それらはまだサポートされていません。 |
| Do you need Experience Cloud ID (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that&#39;s ECID or any other ID you choose. |
| Customer Journey Analytics の前に ETL（抽出、変換、読み込み）を実行する必要がある場合はどうなりますか。 | 現在、AEP に取り込む前にデータを変換する必要がある場合は、ETL パートナー（Unifi または Informatica）と連携する必要があります。データの取り込み後に ETL が必要となった場合、AEP クエリサービスにはいくつかの制限付きオプションが用意されています。 |
| **ステッチ** |  |
| Can [!UICONTROL Customer Journey Analytics] &quot;stitch&quot; across devices or across datasets? | いいえ。[!UICONTROL Customer Journey Analytics] は、「独自のIDを持ち込む」分析システムです。 優れたステッチアプローチに対する計画は進行中です。 |
| 匿名の行動を、サポートされている認証済みの行動にステッチすることはサポートされていますか。 | いいえ、まだサポートされていません。 |
| **データの取得[!UICONTROL Customer Journey Analytics]** |  |
| に対して予想される遅延は何 [!UICONTROL Customer Journey Analytics] です [!UICONTROL Experience Platform]か。 | <ul><li>標準の負荷の場合：&lt;60分 <br>**注：** パイプラインを通じたデータフローが異常に多い場合は、最長 24 時間かかる場合があります。</li><li>バックフィルデータ（最大 100 億件のイベント）：4 週間未満</li></ul> |
| How do you connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] は、「独自のIDを持ち込む」分析システムです。 As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect segments, attribution, flow, fallout, etc. 接続できます。 |
| オフラインデータを Customer Journey Analytics に取り込む方法を教えてください。 | お客様は、Customer Jeurney Analyticsでデータを使用する前に、エクスペリエンスプラットフォームにデータを持ち込む必要があります。 Experience Platform のデータは、オンボーディングチームが必要に応じて、お客様にレコメンデーションやコンサルティングを提供するのに役立ちます。 |
| Analytics データを Customer Journey Analytics に取り込む方法を教えてください。 | Analyticsデータは、Analytics Data Connectorを介してエクスペリエンスプラットフォームに接続できます。 ほとんどの Analytics フィールドは XDM 形式で取り込まれますが、他のフィールド（マーケティングチャネルディメンションなど）はまだ使用できません。 |
| データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか。 | 開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。 |
| PII データを取り込んでデータ間の接続を確立する必要がありますか。 | いいえ。PII ではない顧客 ID のハッシュを含む、任意の ID を使用できます。 |
| **従来の Analytics コンポーネント** |  |
| 従来の Adobe Analytics 製品とは何を表していますか。 | Customer Journey Analytics は、次世代の分析製品です。現在の製品から Customer Journey Analytics に進化するには、数年の時間がかかり、多くの調整がおこなわれます。このリリースは、この方向への大きな一歩となります。 |
| Customer Journey Analytics のセグメントを AEP や他のソリューションに共有できますか。 | まだできません。アドビでは、近い将来に、Customer Jureny Analytics から AEP にセグメントを共有する新しい革新的な方法を実現できるよう検討中です。潜在的な解決策として、クエリサービスの出力を統合プロファイルに共有できます。 |
| 古い eVar 設定はどうなりましたか。 | 従来の Adobe Analytics の eVar、prop およびイベントは、Customer Journey Analytics には存在しなくなりました。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。 |
| すべてのセッションと変数の永続性の設定は、どこにありますか。 | Customer Jaurney Analytics では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント／計算指標はどうなりますか。 | Customer Journey Analytics は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存のセグメントや計算指標は、いずれも Customer Journey Analytics との互換性はありません。 |
| Customer Journey Analytics での `Uniques Exceeded` 制限の処理方法を教えてください。 | Customer Journey Analytics には一意の値に関する制限がないので、ご心配は不要です。 |
| 既存の [!DNL Data Workbench] のユーザーであれば、今すぐ Customer Jargeny Analytics に移行できますか。 | 場合によります。Unified Customer Process（UCP）を多用している場合は、ステッチが実装されるまで待つ必要があります。既に顧客認証率が高い場合や、すべてのデータを一元管理したい場合、または eVar を排除したい場合は、Customer Jargeny Analytics が最適です。 |

