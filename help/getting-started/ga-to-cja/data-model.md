---
title: GA4 データモデルとCustomer Journey Analyticsのマッピング
description: GA4のイベントベースのデータモデルが、Customer Journey AnalyticsでXDM スキーマやデータセットにどのように変換されるのかを理解できます。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# GA4 データモデルとCustomer Journey Analyticsのマッピング

GA4とCustomer Journey Analyticsはどちらもイベントベースの基盤であるため、両者のデータモデルの変換は、Universal Analyticsよりも直接的なものになります。 GA4のイベントとパラメーターが、Customer Journey AnalyticsのXDM フィールドとデータセットとどのように対応しているかを把握することで、レポートの解釈や実装チームとのコラボレーションが容易になります。

## GA4のイベントベースデータモデル

GA4のすべてのインタラクションは&#x200B;**イベント**&#x200B;です。コンテキストを提供する&#x200B;**パラメーター**&#x200B;のオプションのセットを持つ名前付きアクションです。 ページビュー、セッション、目標に特化したオブジェクトタイプは存在せず、すべてイベントです。

| GA4 イベントタイプ | 例 |
|---|---|
| 自動収集 | `page_view`, `session_start`, `first_visit`, `scroll` |
| 拡張測定 | `file_download`, `video_start`, `form_submit` |
| 推奨 | `purchase`, `add_to_cart`, `sign_up` |
| カスタム | 定義したイベント名 |

各イベントは最大25個のパラメーターを含めることができます。 例えば、`purchase` イベントには、通常、`transaction_id`、`value`、`currency`および`items`がパラメーターとして含まれます。

## Customer Journey Analyticsにおけるデータの保存方法

Customer Journey Analyticsは、**Adobe Experience Platform**&#x200B;からデータを取得します。 Platformのデータは&#x200B;**データセット**&#x200B;に保存され、それぞれが&#x200B;**Experience Data Model （XDM）**&#x200B;を使用して構築された&#x200B;**スキーマ**&#x200B;に準拠しています。 XDMは、顧客体験データを表現するための、Adobeのオープンスタンダードです。

Customer Journey Analyticsでは、次の3つのデータセットタイプを使用します。

| CJAのデータセットタイプ | GA4当量 | What it holds |
|---|---|---|
| [!UICONTROL &#x200B; イベントデータセット &#x200B;] | GA4 イベントストリーム | 時系列のインタラクション（ページビュー、クリック、購入） |
| [!UICONTROL &#x200B; プロファイルデータセット &#x200B;] | GA4 ユーザーのプロパティ | 個人レベルの属性（CRM フィールド、ロイヤルティステータス、デモグラフィック） |
| [!UICONTROL ルックアップデータセット] | 参照テーブルとして使用されるGA4 カスタムディメンション | キー値参照データ（製品カタログ、キャンペーン名） |

Customer Journey Analyticsには、eVar、prop、Success イベントがありません。 あらゆるディメンションと指標は、XDM スキーマフィールドから直接取得されています。 一意のディメンション値の数に制限はありません。

## 自動収集されたイベント

SDKを通じて、一連のイベントを自動的に収集します。 次の表は、これらのイベントをXDMまたはCustomer Journey Analyticsに対応するイベントにマッピングします。

| GA4自動収集イベント | XDM/Customer Journey Analytics版 |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` （標準XDM フィールド） |
| `session_start` | セッション開始（自動、データビューセッション定義ごと） |
| `first_visit` | [!UICONTROL 最初のセッション &#x200B;] セグメント |
| `scroll` | カスタムイベント（明示的な実装マッピングが必要） |
| `click` | `xdm.web.webInteraction` フィールド （実装が必要） |
| `video_start` / `video_complete` | Media Collection スキーマフィールド（Adobe ストリーミングメディアサービスを使用） |
| `purchase` | `xdm.commerce.purchases`、`xdm.commerce.order` （標準XDM コマーススキーマ） |
| `add_to_cart` | `xdm.commerce.productListAdds` （標準XDM コマーススキーマ） |

>[!NOTE]
>
>Web SDKを使用して実装する場合、GA4の強化された測定イベント（スクロール、ファイルダウンロード、動画など）のいくつかは、XDM フィールドへの明示的なマッピングを必要とします。 GA4のSDKで処理するのと同じように自動収集されることはありません。

## カスタムイベントとパラメーター

GA4では、カスタムイベントには名前と最大25個のパラメーターがあります。 Customer Journey Analyticsでは、カスタムイベントは、実装中に定義されたカスタム XDM スキーマフィールドにマッピングされます。

* **イベント名**&#x200B;は、XDM フィールドのフィールド値になります（通常は[`xdm.eventType`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent)）。
* 各&#x200B;**パラメーター**&#x200B;は個別のXDM スキーマフィールドになります。 任意のXDM フィールドは、[&#x200B; データビューの設定](/help/data-views/component-settings/overview.md)時に、ディメンションまたは指標として公開できます。

>[!NOTE]
>
>組織のカスタムイベントの特定のXDM フィールドパスは、Web SDKの実装中に決定されます。 レポートを作成する前に、実装チームと協力して特定のフィールドマッピングを理解しましょう。 詳しくは、[&#x200B; スキーマの構築](../cja-upgrade/cja-upgrade-schema-architect.md)を参照してください。

## ユーザープロパティ

GA4 ユーザープロパティは、ユーザーに設定された永続的な属性です（例：`membership_tier`または`account_type`）。 Customer Journey Analyticsでは、これらはPlatformの&#x200B;**プロファイルデータセット**&#x200B;にマッピングされます。

プロファイルデータセットは、イベントデータとは別に取り込まれ、Customer Journey Analyticsで共有人物IDを使用して結合されます。 このコンテキストで使用される一般的な人物IDには、顧客IDまたはメールハッシュが含まれます。 結合されると、これらのプロファイル属性は、Analysis Workspaceのディメンションとしてイベントレベルのデータと共に利用できるようになります。

このアプローチにより、Customer Journey AnalyticsはGA4のユーザープロパティモデルよりも柔軟性が高まります。GA4では、SDKで定義されたユーザープロパティに制限が設けられていますが、Customer Journey Analyticsプロファイルデータセットには、結合可能なIDを共有する限り、あらゆるシステム（CRM、ロイヤルティプラットフォーム、サポートレコード）の任意の属性を含めることができます。

組織が引き続きAdobe Experience PlatformにGA データを取り込む必要がある場合は、管理者向けの設定ガイドについては、[Google Analyticsの履歴データの取り込み](/help/use-cases/third-party/ga/backfill.md)および[&#x200B; ストリーミング Google Analytics データの設定](/help/use-cases/third-party/ga/streaming.md)を参照してください。
