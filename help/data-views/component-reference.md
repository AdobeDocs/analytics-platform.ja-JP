---
title: 標準コンポーネントリファレンス
description: 任意のデータビューに追加できるすべての標準コンポーネントの詳細と情報。
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 65b4339b4a1b27c41cfe442482a54661989d704b
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 77%

---

# 標準コンポーネントリファレンス

Customer Journey Analytics のほとんどのディメンションと指標は、Adobe Experience Platform データセットのスキーマ要素に基づいています。ただし、使用する接続に関係なく、データビューに追加できるコンポーネントがいくつかあります。

[!UICONTROL 標準] コンポーネントとは、データセットスキーマフィールドから生成されるのではなく、システムによって生成されるコンポーネントを指します。Analysis Workspace でのレポート機能を強化するために必要なシステムコンポーネントもあれば、オプションのシステムコンポーネントもあります。

![標準コンポーネント](assets/dataview-standard-components.png)

## 必要な標準コンポーネント {#required}

これら必須の標準コンポーネントは、デフォルトで各データビューに追加されます。これらは、Customer Journey Analytics が提供するレポート機能に不可欠です。

### 標準寸法

{{standard-dimensions}}


### 標準指標

{{standard-metrics}}


## 標準コンポーネント（任意） {#optional}

オプションの標準コンポーネントは、 **[!UICONTROL データビュー]**／ **[!UICONTROL データビューを編集]**／ **[!UICONTROL コンポーネント]**&#x200B;タブ／ **[!UICONTROL 標準コンポーネント]** タブにあります。

| コンポーネント名 | ディメンションまたは指標 | メモおよび値 |
| --- | --- | --- |
| [!UICONTROL 午前／午後] | 時間分割ディメンション | 午前または午後 |
| [!UICONTROL バッチ ID] | ディメンション | [!UICONTROL &#x200B; イベント &#x200B;] が含まれていたExperience Platform バッチの識別子。 |
| [!UICONTROL データセット ID] | ディメンション | [!UICONTROL &#x200B; イベント &#x200B;] が含まれていたExperience Platform データセットの識別子。 |
| [!UICONTROL 日付] | 時間分割ディメンション | 1 ～ 31 |
| [!UICONTROL 曜日] | 時間分割ディメンション | 月曜日、火曜日、水曜日、木曜日、金曜日、土曜日、日曜日 |
| [!UICONTROL 年間通算日] | 時間分割ディメンション | 1 ～ 366 |
| [!UICONTROL 時刻] | 時間分割ディメンション | 0 ～ 23 |
| [!UICONTROL 月] | 時間分割ディメンション | 1 月 ～ 12 月 |
| [!UICONTROL 初回セッション] | 指標 | レポートウィンドウ内での個人の定義された最初のセッション。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ja#new-repeat) |
| [!UICONTROL セッションを返す] | 指標 | 個人の初めてのセッションではなかったセッションの数。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ja#new-repeat) |
| [!UICONTROL ユーザー ID] | ディメンション | Experience Platform で定義された各データセットスキーマは、1 つ以上の定義済み ID のセットを持つことができ、ID 名前空間に関連付けられます。これら ID のいずれかをユーザー ID として使用できます。 例えば、cookie ID、関連付け ID、ユーザー ID、トラッキングコードなどがあります。[!UICONTROL ユーザー ID] ディメンションは、データセットを組み合わせ、Customer Journey Analytics での一意のユーザーを識別する際の基礎となります。<p>考えられるユースケースは次のとおりです。<ul><li>特定のユーザー ID 値にセグメントを作成して、そのユーザーの行動に至るまですべてをセグメント化します。</li><li>デバッグ：特定の cookie ID（または特定の顧客 ID）のデータが存在することを確認します。</li><li>コールセンターに電話をかけたユーザーを特定します。</li></ul> |
| [!UICONTROL ユーザー ID 名前空間] | ディメンション | [!UICONTROL ユーザー ID] を構成している ID のタイプ。例：`email address`、`cookie ID`、`Analytics ID` |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>[!UICONTROL &#x200B; グローバルアカウント ID] | ディメンション | 接続でグローバルアカウントコンテナを使用する場合の [!UICONTROL &#x200B; グローバルアカウント ID]。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>[!UICONTROL &#x200B; アカウント ID] | ディメンション | 接続でアカウントコンテナを使用する場合の [!UICONTROL &#x200B; アカウント ID]。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>[!UICONTROL &#x200B; オポチュニティ ID] | ディメンション | 接続で商談コンテナを使用する場合の [!UICONTROL &#x200B; 商談 ID]。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>[!UICONTROL &#x200B; 購入グループ ID] | ディメンション | 接続で購入グループコンテナを使用する場合の [!UICONTROL &#x200B; 購入グループ ID]。 |
| [!UICONTROL 四半期] | 時間分割ディメンション | 第 1 四半期、第 2 四半期、第 3 四半期、第 4 四半期 |
| [!UICONTROL リピートセッション] | 指標 | 個人の初めてのセッションではなかったセッションの数。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ja#new-repeat) |
| [!UICONTROL セッションタイプ] | ディメンション | このディメンションには次の 2 つの値があります。1. [!UICONTROL &#x200B; 初回 &#x200B;] と 2. 再来訪。 [!UICONTROL 初回]行項目には、個人の定義された最初のセッションと判断されたセッションのすべての動作（このディメンションに対する指標）が含まれます。その他すべては、[!UICONTROL 再来訪]行項目に含まれます（すべてがセッションに属すると仮定）。指標がどのセッションにも含まれていない場合、このディメンションの「該当なし」バケットに入ります。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ja#new-repeat) |
| [!UICONTROL イベント別滞在時間] | ディメンション | [!UICONTROL 滞在時間] 指標を [!UICONTROL イベント] グループ別にまとめたものです。 |
| [!UICONTROL セッション別滞在時間] | ディメンション | [!UICONTROL 滞在時間] 指標を [!UICONTROL セッション] 別にまとめたものです。 |
| [!UICONTROL ユーザー別滞在時間] | ディメンション | [!UICONTROL 滞在時間] 指標を [!UICONTROL 個人] グループ別にまとめたものです。 |
| [!UICONTROL 週末]／[!UICONTROL 平日] | 時間分割ディメンション | 週末または平日 |

{style="table-layout:auto"}
