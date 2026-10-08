---
title: Customer Journey Analytics データフィードで使用可能なコンポーネント
description: Customer Journey Analytics データフィードを作成する際に、必須、サポートされていない、制限されている、または代用する必要があるディメンションと指標について説明します。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: d7614102d54af57a3a084c8550041f8e04f4bc37
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 43%
---
# データフィードでのコンポーネントの可用性

{{release-limited-testing}}

一部のCustomer Journey Analyticsコンポーネントは、データフィードで使用できません。 ディメンションの中には、すべてのデータフィードに含まれるものもあれば、含まれないコンポーネントもあります。また、一部の指標は代替指標に置き換える必要があります。

次の情報を使用して、[&#x200B; データフィードを作成する](/help/components/exports/cja-data-feeds/create-feed.md)際に含めることができるコンポーネントを把握します。

## 必須ディメンション {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="必須ディメンション"
>abstract="すべてのデータフィードには、ディメンション名の横に&#x200B;**必須**&#x200B;ラベルで識別される特定のディメンションを含める必要があります。 これらのディメンションは、イベントレベルの分析に必要な最小限の構造を提供します。"

<!-- markdownlint-enable MD034 -->

次のディメンションは、すべてのデータフィードにデフォルトで含まれており、削除できません。

| ディメンション名 | メモ | データフィード | その他のレポート |
|---|---|---|---|
| タイムスタンプ (UTC) | イベントが発生した日時。UTC タイムゾーンで表されます。 サブ秒（マイクロ秒）の精度をサポートします。 | 必須 | 使用不可 |
| 行 ID | データフィードに含まれる各行の一意の ID。 | 必須 | 使用不可 |
| セッション ID | データフィードに含まれる各セッションの一意の ID。 | 必須 | 使用不可 |
| ユーザー ID | データビューと接続の人物ID | 必須 | オプションの標準 |
| アカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | アカウントコンテナを使用する際のアカウント ID | 必須 | オプションの標準 |

## サポートされていないディメンション {#unsupported-dimensions}

Customer Journey Analytics標準ディメンションは、データフィードに含めることはできません。 次の表に、これらのディメンションを示します。

| ディメンション名 | メモ | データフィード |
|---|---|---|
| 5 分 | イベント発生時の5分間隔（切り捨て） | 使用不可 |
| 15 分 | イベント発生時の15分間隔（切り捨て） | 使用不可 |
| 30 分 | イベント発生時の30分間隔（切り捨て） | 使用不可 |
| 日 | イベント発生日 | 使用不可 |
| 曜日 | イベントが発生した曜日 | 使用不可 |
| 日付 | イベントが発生した月の日 | 使用不可 |
| 時間 | イベントが発生した時間（切り捨て） | 使用不可 |
| 時刻 | イベントが発生した日の時間（切り捨て） | 使用不可 |
| 分 | イベント発生分（切り捨て） | 使用不可 |
| 分 (時間) | イベントが発生した時間の分（切り捨て） | 使用不可 |
| 月 | イベントが発生した月 | 使用不可 |
| 月 | イベントが発生した年の月 | 使用不可 |
| 四半期 | イベントが発生した四半期 | 使用不可 |
| 四半期 | イベントが発生した年の四半期 | 使用不可 |
| Second | 2番目のイベントが発生しました（切り捨て） | 使用不可 |
| 週 | イベントが発生した週 | 使用不可 |
| 年間通算週 | イベントが発生した年の週 | 使用不可 |
| 年 | イベントが発生した年 | 使用不可 |

## サポートされていない指標 {#unsupported-metrics}

次のCustomer Journey Analytics標準メトリックは、データフィードに含めることはできません。

| Metric name | メモ | データフィード |
|---|---|---|
| Adobe訪問者プロファイル | | 使用不可 |
| Adobeオポチュニティユニオン | | 使用不可 |
| Adobe Opportunities Profile | | 使用不可 |
| Adobe会計組合 | | 使用不可 |
| Adobe Accounts Profile | | 使用不可 |
| Adobe購買グループ組合 | | 使用不可 |
| Adobe Buying Groups Profile | | 使用不可 |
| Adobeグローバルアカウント組合 | | 使用不可 |
| Adobeのグローバルアカウントプロファイル | | 使用不可 |
| Adobe労働組合 | | 使用不可 |
| Adobe人物プロファイル | | 使用不可 |

## 一緒に使用できないディメンション {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="ユーザーエージェントデータとデバイス参照データは、同じデータフィード設定に存在できません。"

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>特定のディメンションは、Experience Platform データセットで一緒に使用できないため、同じデータフィードに含めることはできません。
>
>**User Agent**&#x200B;または&#x200B;**Mobile ID** ディメンションのいずれかをデータフィードに含めることを選択した場合、以下に示すディメンションをデータフィードに追加することはできません。
>
>Web SDKを使用する場合、この制限は、データがExperience Platform データセットに届く前にデータストリームで適用されます。 詳しくは、データ収集ガイドの「[&#x200B; データストリームの作成と設定](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)」の「[&#x200B; デバイス検索の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure#geolocation-device-lookup)」を参照してください。

次のディメンションは、**ユーザーエージェント**&#x200B;または&#x200B;**モバイル ID** ディメンションと一緒に使用することはできません。

* ブラウザータイプ
* ブラウザー
* モバイルの製造元
* モバイルデバイスタイプ
* モバイルのオーディオ サポート
* モバイル DRM
* モバイル Java VM
* モバイル情報サービス
* モバイルの画像サポート
* モバイルの画面の色
* モバイル インターネット プロトコル
* モバイルデバイス番号
* モバイルのメール最大長
* モバイルデコレーションメール
* モバイルプッシュトゥトーク
* モバイルの画面の幅
* モバイルのブラウザー URL 最大長
* モバイルオペレーティングシステム （非推奨）
* モバイルの画面の高さ
* モバイルのビデオ サポート
* モバイルの cookie サポート
* モバイルのブックマーク最大長
* モバイルの画面のサイズ
* モバイルデバイス名
* オペレーティングシステムの種類
* オペレーティングシステム

## 代替が必要な指標 {#substitute-metrics}

次のCustomer Journey Analytics メトリクスを置き換える必要があります。

| Metric name | メモ | データフィード |
|---|---|---|
| アカウント [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 接続で指定されたアカウント IDに基づく | 使用不可。 アカウント IDで異なるカウントを使用します。 |
| 購買グループ [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 接続の購買グループ IDに基づく購買グループ | 使用不可。 購買グループ IDとは異なるカウントを使用します。 |
| イベント | 接続内のすべてのイベントデータセットからの行数 | 使用不可。 行IDとは異なるカウントを使用します。 |
| グローバルアカウント [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 接続のグローバルアカウント IDに基づく | 使用不可。 グローバルアカウント IDで異なるカウントを使用します。 |
| 商談 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 接続の商談IDに基づく商談 | 使用不可。 商談IDとは異なるカウントを使用します。 |
| People | 接続で指定された人物IDに基づく | 使用不可。 人物IDとは異なるカウントを使用します。 |
| 会話数 | 会話数 | 使用不可。 会話IDで異なるカウントを使用します。 |
| セッション終了 | セッションの最後のイベントであったイベントの数 | 使用不可 |
| セッション開始 | セッションの最初のイベントだったイベントの数 | 使用不可 |
| Sessions | データビューのセッション設定にもとづいて | 使用不可。 セッション IDで異なるカウントを使用します。 |
| 滞在時間（秒） | 2つの異なるディメンション値の間の時間を合計します | 使用不可 |

## 標準コンポーネント（任意） {#optional-standard-components}

| コンポーネント名 | タイプ | メモ | データフィード |
|---|---|---|---|
| 午前／午後 | 時間分割ディメンション | 午前または午後 | 使用不可 |
| バッチ ID | ディメンション | Experience Platform バッチの識別子 | 使用可能 |
| データセット ID | ディメンション | Experience Platform データセットの識別子 | 使用可能 |
| 日付 | 時間分割ディメンション | 1-31 | 使用不可 |
| 曜日 | 時間分割ディメンション | 月曜日～日曜日 | 使用不可 |
| 年間通算日 | 時間分割ディメンション | 1-366 | 使用不可 |
| イベント深度 | ディメンション | 連続数値（1、2、3など） セッション内の各イベントインタラクションに指定されます<p>新しい各セッションの開始時にリセット</p> | 使用可能 |
| 時刻 | 時間分割ディメンション | 0-23 | 使用不可 |
| 月 | 時間分割ディメンション | 1～12月 | 使用不可 |
| 初回セッション | 指標 | レポートウィンドウ内での個人の最初に定義されたセッション | 使用不可 |
| セッションを返す | 指標 | ユーザーの初めてのセッションではないセッション | 使用不可 |
| 人物ID名前空間 | ディメンション | 人物IDで構成されるIDのタイプ（電子メール IDやCookie IDなど） | 使用可能 |
| グローバルアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ディメンション | グローバルアカウントコンテナを使用する場合のグローバルアカウント ID | 使用可能 |
| 商談ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ディメンション | 商談コンテナの使用時の商談ID | 使用可能 |
| 購買グループ ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ディメンション | 購買グループコンテナを使用する場合の購買グループ ID | 使用可能 |
| 四半期 | 時間分割ディメンション | 第 1 四半期、第 2 四半期、第 3 四半期、第 4 四半期 | 使用不可 |
| リピートセッション | 指標 | まだセッションが始まっていない場合 | 使用不可 |
| セッションタイプ | ディメンション | 2つの値：初回または再試行 | 使用不可 |
| イベントごとの滞在時間 | ディメンション | 滞在時間指標をイベントバケットにバケット化します | 使用不可 |
| セッションごとの滞在時間 | ディメンション | 滞在時間指標をセッションバケットにバケット化します | 使用不可 |
| 1人当たりの滞在時間 | ディメンション | 滞在時間指標を個人グループにバケット化します | 使用不可 |
| 週末/平日 | 時間分割ディメンション | 週末または平日 | 使用不可 |
