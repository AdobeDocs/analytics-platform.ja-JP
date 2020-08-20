---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
translation-type: tm+mt
source-git-commit: 297ed03ff59cc8d719a6bf0984e82597e8d33392
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 69%

---


# よくある質問

| 質問 | 回答 |
| --- | --- |
| **前提条件** |  |
| Device GraphまたはDevice Coopが必要か [!UICONTROL Customer Journey Analytics]? | いいえ。 [!UICONTROL Customer Journey Analytics]. 実際、それらはまだサポートされていません。 |
| Experience CloudID(ECID)が必要か [!UICONTROL Customer Journey Analytics]? | いいえ、 [!UICONTROL Customer Journey Analytics] は、データセット内の任意のID（ECIDか、選択した他のIDか）をサポートします。 |
| Customer Journey Analyticsの前にETL（抽出、変換、読み込み）が必要な場合はどうなりますか。 | 現在、AEP に取り込む前にデータを変換する必要がある場合は、ETL パートナー（Unifi または Informatica）と連携する必要があります。データが既に取り込まれた後にETLが必要な場合、AEPクエリサービスではいくつかの制限付きオプションを提供します。 |
| **ステッチ** |  |
| 缶 [!UICONTROL Customer Journey Analytics] デバイス間またはデータセット間で「縫い合わせ」を行うか | いいえ。[!UICONTROL Customer Journey Analytics は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。]優れたステッチアプローチに対する計画は進行中です。 |
| 匿名の行動を、サポートされている認証済みの行動にステッチすることはサポートされていますか。 | いいえ、まだサポートされていません。 |
| **[!UICONTROL Customer Jeurney Analytics へのデータの取得]** |  |
| 異なるExperience Platformサンドボックスのデータを1つのCJA接続で組み合わせることはできますか。 | いいえ、サンドボックス全体のデータにアクセスすることはできません。 同じサンドボックス内にあるデータセットのみを組み合わせることができます。 [詳細情報...](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| 予想される遅延 [!UICONTROL Customer Journey Analytics] on [!UICONTROL Experience Platform]? | <ul><li>標準の負荷の場合：60分未満 <br>**注：** パイプラインを通じたデータフローが異常に多い場合は、最長 24 時間かかる場合があります。</li><li>バックフィルデータ（最大 100 億件のイベント）：4 週間未満。</li></ul> |
| オンラインデータを [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。]データセット間で人物IDが一致する限り、 [!UICONTROL Customer Journey Analytics] セグメント、アトリビューション、フロー、フォールアウトなどを接続できます。 接続できます。 |
| オフラインデータを Customer Journey Analytics に取り込む方法を教えてください。 | Customer Journey Analyticsで使用する前に、Experience Platformに任意のデータを取り込む必要があります。 Experience Platformのデータのオンボーディングチームが、必要に応じてレコメンデーションやコンサルティングを行うのに役立ちます。 |
| Analytics データを Customer Journey Analytics に取り込む方法を教えてください。 | Analyticsデータは、 [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). ほとんどの Analytics フィールドは XDM 形式で取り込まれますが、他のフィールド（マーケティングチャネルディメンションなど）はまだ使用できません。 |
| データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか。 | 開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。 |
| PII データを取り込んでデータ間の接続を確立する必要がありますか。 | いいえ。PII ではない顧客 ID のハッシュを含む、任意の ID を使用できます。 |
| **従来の Analytics コンポーネント** |  |
| 従来の Adobe Analytics 製品とは何を表していますか。 | Customer Journey Analytics は、次世代の分析製品です。現在の製品から Customer Journey Analytics に進化するには、数年の時間がかかり、多くの調整がおこなわれます。 |
| Customer Journey Analytics のセグメントを AEP や他のソリューションに共有できますか。 | まだできません。アドビでは、近い将来に、Customer Journey Analytics から AEP にセグメントを共有する新しい革新的な方法を実現できるよう検討中です。潜在的な解決策として、クエリサービスの出力を統合プロファイルに共有できます。 |
| 古い eVar 設定はどうなりましたか。 | 従来の Adobe Analytics の eVar、prop およびイベントは、Customer Journey Analytics には存在しなくなりました。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。 |
| すべてのセッションと変数の永続性の設定は、どこにありますか。 | Customer Journey Analytics では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント／計算指標はどうなりますか。 | Customer Journey Analytics は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存のセグメントや計算指標は、いずれも Customer Journey Analytics との互換性はありません。 |
| Customer Journey Analytics での `Uniques Exceeded` 制限の処理方法を教えてください。 | Customer Journey Analytics には一意の値に関する制限がないので、ご心配は不要です。 |
| 既存の [!DNL Data Workbench] のユーザーであれば、今すぐ Customer Journey Analytics に移行できますか。 | 場合によります。Unified Customer Process（UCP）を多用している場合は、ステッチが実装されるまで待つ必要があります。既に顧客認証率が高い場合や、すべてのデータを一元管理したい場合、または eVar を排除したい場合は、Customer Journey Analytics が最適です。 |

