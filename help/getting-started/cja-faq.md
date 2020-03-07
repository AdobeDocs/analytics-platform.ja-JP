---
title: 顧客の遍歴分析FAQ
description: 顧客の遍歴分析 — よくある質問(FAQ)
translation-type: tm+mt
source-git-commit: cca701c2a18d094ee4b172b032c125e710b51ff0

---


# よくある質問

| 質問 | 回答 |
|---|---|
| **前提条件** |  |
| 顧客の遍歴分析にDevice GraphまたはDevice Coopが必要ですか。 | いいえ。Customer Jareny Analyticsでは、プライベートデバイスグラフまたはDevice Coopは必要ありません。 実際、まだサポートされていません。 |
| Customer Jeurney AnalyticsにExperience Cloud ID(ECID)が必要ですか。 | いいえ。Customer Jeurney Analyticsは、データセット内の任意のID（ECIDか、選択した他のIDか）をサポートします。 |
| Customer Jaurney Analyticsの前にデータをETLする必要がある場合はどうなりますか。 | 現在、AEPにデータを送信する前にデータを変換する必要がある場合は、ETLパートナー（UnifiまたはInformatica）と連携する必要があります。 データの取り込み後にETLが必要な場合、AEP Query Servicesには一部の制限付きオプションが用意されています。 |
| **ステッチ** |  |
| 顧客の遍歴分析は、デバイス間で、またはデータセット間で「縫い合わせ」できますか。 | いいえ。顧客の遍歴分析は、「独自のIDを持ち込む」分析システムです。 縫い目の良いアプローチの計画は、作品の中にあります。 |
| 匿名行動から認証された行動へのステッチはサポートされていますか？ | いいえ、まだできません。 |
| **顧客の遍歴分析へのデータの取得** |  |
| プラットフォームでの顧客の遍歴分析で予想される遅延は何ですか。 | <ul><li>標準荷重下：&lt; 60<br>**分注：**パイプラインを通じてのデータフローが異常に多い場合は、最長24時間かかります。</li><li>バックフィルデータ（最大100億イベント）:&lt; 4週間</li></ul> |
| Customer Jeurney Analyticsでオンラインデータをオフラインデータに接続する方法を教えてください。 | 顧客の遍歴分析は、「独自のIDを持ち込む」分析システムです。 データセット間で個人IDが一致する限り、Customer Jeurney Analyticsは、セグメント、アトリビューション、フロー、フォールアウトなどを接続できます。 データセット間で |
| オフラインデータをCustomer Jeurney Analyticsに取り込む方法を教えてください。 | お客様は、Customer Jareny Analyticsでデータを使用する前に、AEPにデータを持ち込む必要があります。 エクスペリエンスプラットフォームのデータは、オンボーディングチームが必要に応じて、お客様に推奨事項やコンサルティングを提供するのに役立ちます。 |
| AnalyticsデータをCustomer Jeurney Analyticsに取り込む方法を教えてください。 | 解析データは、Analytics Data Connectorを通じてAEPに接続できます。 ほとんどのAnalyticsフィールドはXDM形式で引き継がれますが、他のフィールド（マーケティングチャネルディメンションなど）はまだ使用できません。 |
| データセット要素をデータビューに組み込むのにどの程度の時間がかかりますか。 | 開始するまでに数時間かかり、過去13か月のデータをバックフィルするのに数日かかります。 |
| PIIデータを取り込んでデータ間の接続を確立する必要があるか。 | いいえ。PIIではない顧客IDのハッシュを含む、任意のIDを使用できます。 |
| **従来のAnalyticsコンポーネント** |  |
| 従来のAdobe Analytics製品の意味 | 顧客の遍歴分析は、次世代の分析製品です。 現在の製品からCustomer Jareny Analyticsに移行するには、数年かかり、多くの調整が同時に行われます。 このリリースは、多くの人々がこの方向に向けて大きな一歩を踏み出したものです。 |
| Customer Jeurney AnalyticsのセグメントをAEPや他のソリューションに共有できますか。 | まだできません。Customer Jureny AnalyticsからAEPにセグメントを共有する新しい革新的な方法を検討しています。この方法は、それほど遅れはありません。 ただし、潜在的な回避策として、Query Servicesの出力をUnified Profileに共有できます。 |
| 古いeVar設定はどうなりましたか。 | 従来のAdobe AnalyticsのeVar、propおよびイベントは、Customer Jearny Analyticsに存在しなくなりました。 スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。 したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリー時に適用されるようになりました。 |
| セッションと変数の永続性の設定は、今どこにありますか。 | Customer Jeurney Analyticsでは、これらのすべての設定がレポート時に適用され、これらの設定はデータビューに反映されます。 これらの設定に対する変更が遡及され、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント/計算指標はどうなりますか？ | 顧客の遍歴分析では、eVar、propまたはeventを使用せず、代わりにAEPスキーマを使用します。 つまり、既存のセグメントや計算指標がいずれもCustomer Jeurney Analyticsと互換性がないことを意味します。 |
| Customer Jeurney Analyticsでの制限の処理方法を教えて `Uniques Exceeded` ください。 | Customer Jeurney Analyticsには固有の値の制限がないので、心配する必要はありません。 |
| 既存のお客様の場合、 [!DNL Data Workbench] 今すぐCustomer Jargeny Analyticsに移行できますか。 | 場合によります。Unified Customer Process(UCP)を多用している場合は、ステッチが実装されるまで待つ必要があります。 顧客の認証率が高い場合、またはすべてのデータを1か所で管理したい場合や、eVarを削除したい場合は、Customer Jargeny Analyticsが適している可能性があります。 |

