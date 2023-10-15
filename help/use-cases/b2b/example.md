---
title: B2B プロジェクトの例
description: B2B データの設定、設定、およびレポート方法について説明します
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: c4a4dcd0e4c0d7473570c2db3aa3d99e34c2a1cf
workflow-type: tm+mt
source-wordcount: '1889'
ht-degree: 21%

---

# B2B プロジェクトの例

この記事では、例を通じて、B2B データをCustomer Journey Analyticsで設定、設定およびレポートする方法について説明します。

## 接続

接続を定義して、関連するすべての B2B データセットをExperience Platformから含めます。 これには、Experience Platform内の一般的な B2B セットアップで必要となる重要な参照データセットが含まれます。 詳しくは、 [アカウントレベルのデータをルックアップデータセットとして追加](b2b.md) を参照してください。

接続に追加できるデータセット：

| データセット | スキーマ | スキーマタイプ | 基本クラス | 説明 |
|---|---|---|---|---|
| B2B アクティビティデータセット | B2B アクティビティスキーマ | イベント | XDM ExperienceEvent | ExperienceEvent は、発生した事実の記録で、関係する個人のポイントインタイムや ID を含みます。 ExperienceEvents は、明示的（直接観察可能な人間のアクション）または暗黙的（直接人間のアクションなしで発生）に設定でき、集計や解釈なしで記録されます。特定の時間枠内で発生する変更の観察と分析、およびトレンドを追跡する複数の時間枠間の比較を可能にするので、時間ドメイン分析には非常に重要です。 |
| B2B 担当者データセット | B2B 担当者スキーマ | プロファイル | XDM 個人プロファイル | XDM 個人プロファイルは、識別された個人と部分的に識別された個人の両方の属性と関心の単数表現を形成します。 識別されにくいプロファイルには、ブラウザーの cookie などの匿名の行動シグナルのみが含まれ、高度に識別されるプロファイルには、名前、生年月日、場所、電子メールアドレスなどの詳細な個人情報が含まれます。 プロファイルが増えるにつれ、個人情報、識別情報、連絡先の詳細、個人のコミュニケーション設定の堅牢なリポジトリーになります。 |
| B2B キャンペーンメンバーデータセット | B2B キャンペーンメンバースキーマ | ルックアップ | XDM Business Campaign Members | XDM ビジネスキャンペーンメンバーは、ビジネスキャンペーンに関連付けられた連絡先またはリードを記述する標準の Experience Data Model(XDM) クラスです。 |
| B2B アカウントデータセット | B2B アカウントスキーマ | ルックアップ | XDM Business Account | XDM ビジネスアカウントは、ビジネスアカウントの最低限必要なプロパティを取得する標準の Experience Data Model(XDM) クラスです。 |
| B2B アカウント人物関係データセット | B2B アカウント人物関係スキーマ | ルックアップ | XDM Business Account Person Relation | XDM ビジネスアカウント人物関係は、ビジネスアカウントに関連付けられている人物の最小限の必要なプロパティを取得する、標準の Experience Data Model(XDM) クラスです。 |
| B2B 商談データセット | B2B 商談スキーマ | ルックアップ | XDM Business Opportunity | XDM ビジネスオポチュニティは、ビジネスオポチュニティに最低限必要なプロパティを取り込む、標準の Experience Data Model(XDM) クラスです。 |
| B2B 商談人物関係データセット | B2B 商談人物関係スキーマ | ルックアップ | XDM Business Opportunity Person Relation | XDM Business Opportunity Person Relation は、ビジネスオポチュニティに関連付けられている人物の最小限の必要なプロパティをキャプチャする、標準の Experience Data Model(XDM) クラスです。 |
| B2B キャンペーンデータセット | B2B キャンペーンスキーマ | ルックアップ | XDM Business Campaign | XDM ビジネスキャンペーンは、ビジネスキャンペーンの最低限必要なプロパティを取り込む、標準のエクスペリエンスデータモデル (XDM) クラスです。 |
| B2B マーケティングリストデータセット | B2B マーケティングリストスキーマ | ルックアップ | XDM マーケティングリスト | XDM ビジネスマーケティングリストは、マーケティングリストの最低限必要なプロパティを取り込む、標準の Experience Data Model(XDM) クラスです。 マーケティングリストを使用すると、製品を購入する可能性が最も高い見込み客を優先することができます。 |
| B2B マーケティングリストメンバーデータセット | B2B マーケティングリストメンバースキーマ | ルックアップ | XDM Marketing List Members | XDM Business Marketing List Members は、マーケティングリストに関連付けられたメンバー、人、または連絡先を記述する、標準の Experience Data Model(XDM) クラスです。 |

ルックアップスキーマ、プロファイルスキーマ、イベントスキーマ間の関係は、Experience Platform内の B2B 設定で定義されます。 詳しくは、 [Real-time Customer Data Platform B2B エディション](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html?lang=en) および [Real-time Customer Data Platform B2B Edition で 2 つのスキーマ間に多対 1 の関係を定義する](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html?lang=en) を参照してください。

![B2B スキーマ間の関係](assets/classes.png)

接続に追加する各参照データセットに対して、データセットを編集ダイアログの「キーと一致するキー」を使用して、イベントデータセットへの関係を明示的に定義する必要があります。 次に例を示します。

![キー — 一致するキー](assets/key-matchingkey.png)


次の表に、 [!UICONTROL 人物 ID], [!UICONTROL キー]、および [!UICONTROL 一致するキー] 各データセットの値。


| データセット | ユーザー ID | キー | 一致するキー（イベントデータセット内） |
|---|---|---|---|
| B2B アクティビティデータセット | `personKey.sourceKey` | | |
| B2B 担当者データセット | `b2b.personKey.sourceKey` | | |
| B2B アカウントデータセット | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B 商談データセット | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B キャンペーンデータセット | | `campaignKey.sourceKey` | *_organizationID*`.interactions.campaignKey.sourceKey` |
| B2B マーケティングリストデータセット | | `listKey.sourceKey` | `listOperations.listKey.sourceKey` |

{style="table-layout:auto"}


テーブル内 *_organizationID*`.interaction.*`「 」は、B2B アクティビティスキーマに追加したカスタムフィールドグループを参照し、B2B アカウントおよび B2B 商談スキーマとの関係を定義します。 The `listOperations.listKey.sourceKey` は、個人が特定のリストに追加されたタイミングを追跡するために、B2B アクティビティスキーマに追加された「リストに追加」フィールドグループを指します。

詳しくは、 [データセットの追加と設定](../../connections/create-connection.md) データセットの設定を構成する方法の詳細については、を参照してください。


## データビュー

Workspace プロジェクトの作成時に関連する B2B ディメンションと指標にアクセスするには、それに応じてデータビューを定義する必要があります。

この節では、 [コンポーネント](../../data-views/create-dataview.md#components) 」で指定します。

コンポーネントごとに、名前、スキーマパス、および（該当する場合）設定に関する詳細が表示されます。


### B2B アクティビティデータセット

B2B アクティビティデータセットには、関連するエクスペリエンスイベントが含まれ、接続の一部として必要です。

+++ 詳細

#### 指標

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| キャンペーンに追加 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `leadOperation.addToCampaign` |
| 商談に追加 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `opportunityEvent.addToOpportunity` |
| 終了したアプリ | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `application.close` |
| アプリケーションの起動 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `application.launch` |
| キャンペーンストリーム | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** ` leadOperation.changeCampaignStream` |
| チェックアウト | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `commerce.checkouts` |
| リードの変換 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `leadOperation.convertLead` |
| 電子メールのクリック | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `directMarketing.emailClicked` |
| メール配信済み | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `directMarketing.emailDelivered` |
| メール開封済み | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `directMarketing.emailOpened` |
| 送信済み電子メール | 文字列 | eventType | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `directMarketing.emailSent` |
| メール配信停止済み | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `directMarketing.emailUnsubscribed` |
| フォーム入力済み | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `web.formFilledOut` |
| フォーム開始 | 文字列 | `web.fillOutForm.webFormName` | |
| リード数 | 文字列 | eventType | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `leadOperation.newLead` |
| 更新された商談 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `opportunityEvent.opportunityUpdated` |
| 価格 | Double | *_organizationID*`.interactions.products.price` |  |
| 優先度 | 整数 | `leadOperation.changeScore.priority` |  |
| 製品リストの追加 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `commerce.productListAdds.value` |
| 製品リストを開く | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `commerce.productListOpens.value` |
| 製品表示 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `commerce.productViews.value` |
| 購入 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `commerce.purchases.value` |
| 商談から削除 | 文字列 | `eventType` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `opportunityEvent.removeFromOpportunity` |
| 後で使用するために保存 | 文字列 | eventType | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `commerce.productViews.value` |

{style="table-layout:auto"}


#### ディメンション

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| アカウントキー（ソースキー） | 文字列 | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| 変換済みステータス | 文字列 | `leadOperation.convertLead.convertedStatus` | |
| イベントタイプ | 文字列 | `eventType` | |
| フォーム名 | 文字列 | `leadOperation.newLead.formName` | |
| 識別子 | 文字列 | `_id` | |
| 通知を送信済み | ブール値 | `leadOperation.convertLead.isSentNotificationEmail` | |
| キーワード | 文字列 | `search.keywords` | |
| リスト ID | 文字列 | `listOperations.listID` | |
| リスト名 | 文字列 | `leadOperation.newLead.listName` | |
| ページ名 | 文字列 | `web.webPageDetails.name` | |
| 担当者キー（ソースキー） | 文字列 | `personKey.sourceKey` | |
| 作成者 | 文字列 | producedBy | |
| 製品名 | 文字列 | *_organizationID*`.Interactions.products.name` | |
| 役割 | 文字列 | `opportunityEvent.role` | |
| タイムスタンプ | Date-time | `timestamp` | 日付と時刻の形式： **[!UICONTROL 日]** |
| URL | 文字列 | `web.webPageDetails.URL` | |
| Web フォーム名 | 文字列 | `web.fillOutForm.webFormName` | |
| 製品 URL | 文字列 | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


### B2B 人物データセット

B2B Person データセットには、関連するプロファイルが含まれています。

+++ 詳細


#### 指標

このデータセットの一部として指標コンポーネントが定義されていません。


#### ディメンション

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| 最終アクティビティ日 | Date-time | `extSourceSystemAudit.lastActivityDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| ユーザー ID | 文字列 | `personID` | |

{style="table-layout:auto"}

+++ 詳細

### B2B 商談データセット

B2B 商談データセットには、関連する商談が含まれています。

+++ 詳細

#### 指標

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| 予想収益 | Double | `expectedRevenue.amount` | 動作： **[!UICONTROL 値をカウント]** |
| 商談額 | Double | `opportunityAmount.amount` | 動作： **[!UICONTROL 値をカウント]** |
| 商談ステージ — クローズ済帳簿 | 文字列 | `opportunityStage` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `Closed - Booked` |
| 商談ステージ — 見込み客 | 文字列 | `opportunityStage` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `Prospect` |
| 商談ステージ — 選定 | 文字列 | `opportunityStage` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `Opportunity Qualification` |
| オポチュニティステージ — ソリューション定義 | 文字列 | `opportunityStage` | **[!UICONTROL 値を含める/除外するを設定]**<br/>**[!UICONTROL 大文字と小文字を区別]**<br/>一致：**[!UICONTROL &#x200B;すべての条件を満たす場合]**<br/>条件： **[!UICONTROL 次と等しい]** `Solution Definition and Validation` |

{style="table-layout:auto"}


#### ディメンション

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| クローズ済みフラグ | ブール値 | `isClosed` | |
| 会社 ID | 文字列 | `opportunityID` | |
| 予測カテゴリ | 文字列 | `forecastCategoryName` | |
| 最終アクティビティ日 | Date-time | `lastActivityDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| リードソース | 文字列 | `leadSource` | |
| 商談名 | 文字列 | `opportunityName` | |
| 商談のステータス | 文字列 | `opportunityStage` | |
| 獲得フラグ | ブール値 | `isWon` | |

{style="table-layout:auto"}

+++

### B2B キャンペーンデータセット

B2B キャンペーンデータセットには、キャンペーンデータが含まれています。

+++ 詳細

#### 指標

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| キャンペーンコスト | Double | `actualCost.amount` | |

{style="table-layout:auto"}


#### ディメンション

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| キャンペーン ID | 文字列 | `campaignID` | |
| キャンペーン名 | 文字列 | `campaignName` | |
| キャンペーン開始日 | Date-time | `campaignStartDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| チャネル名 | 文字列 | `channelName` | |
| 親キャンペーン ID | 文字列 | `parentCampaignID` | |

{style="table-layout:auto"}

+++


### B2B アカウントデータセット

B2B アカウントデータセットには、アカウントデータが含まれています。

+++ 詳細

#### 指標

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| 年間売上高 | Double | `accountOrganization.annualRevenue.amount` | |
| 従業員数 | 整数 | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


#### ディメンション

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| アカウント識別子 | 文字列 | `accountID` | |
| アカウントタイプ | 文字列 | `accountType` | |
| 市区町村 | 文字列 | `accountBillingAddress.city` | |
| 国 | 文字列 | `accountBillingAddress.country` | |
| 業界 | 文字列 | `accountOrganization.industry` | |
| 領域 | 文字列 | `accountBillingAddress.region` | |
| ソース ID | 文字列 | `accountKey.sourceID` | |
| ソースインスタンス ID | 文字列 | `accountKey.sourceInstanceID` | |
| ソースキー | 文字列 | `accountKey.sourceKey` | |
| ソースタイプ | 文字列 | `accountKey.sourceType` | |

{style="table-layout:auto"}

+++


### B2B キャンペーンメンバーデータセット

B2B キャンペーンメンバーデータセットには、キャンペーンのメンバーとのやり取りが含まれます。

+++ 詳細

#### 指標

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| バウンス | Long | *_organizationID*`.campaignBounced` | 動作： **[!UICONTROL 値をカウント]** |
| クリック済み | Long | *_organizationID*`.campaignClicked` | 動作： **[!UICONTROL 値をカウント]** |
| 開封済み | Long | *_organizationID*`.CampaignOpened` | 動作： **[!UICONTROL 値をカウント]** |
| 送信済み | Long | *_organizationID*`.campaignSent` | 動作： **[!UICONTROL 値をカウント]** |
| 購読済み | Long | *_organizationID*`.campaignSubscribed` | 動作： **[!UICONTROL 値をカウント]** |
| ウェビナー登録 | Long | *_organizationID*`.Registrations` | 動作： **[!UICONTROL 値をカウント]** |

{style="table-layout:auto"}

#### ディメンション

| コンポーネント名 | スキーマデータタイプ | スキーマパス | 設定 |
|---|---|---|---|
| キャンペーン ID | 文字列 | `campaignID` | |
| キャンペーンメンバー ID | 文字列 | `campaignMemberID` | |
| キャンペーンメンバーステータス | 文字列 | `memberStatus` | |
| キャンペーンメンバーステータスの理由 | 文字列 | `memberStatusReason` | |
| 作成日 | Date-time | `extSourceSystemAudit.createdDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| 最初の応答日 | 文字列 | `firstRespondedDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| 成功に達しました | ブール値 | `hasReachedSuccess` | |
| 応答済み | ブール値 | `hasResponded` | |
| 最後のステータス | 文字列 | `lastStatus` | |
| 最終更新日 | Date-time | `extSourceSystemAudit.lastUpdatedDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| メンバーシップの日付 | Date-time | `membershipDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| 育成ケイデンス | 文字列 | `nurtureCadence` | |
| 育成トラッキング名 | 文字列 | `nurtureTrackName` | |
| ユーザー ID | 文字列 | `personID` | |
| 成功達成日 | Date-time | `reachedSuccessDate` | 日付と時刻の形式： **[!UICONTROL 日]** |
| ウェビナー登録 ID | 文字列 | `webinarRegistrationID` | |
| ウェビナー登録 URL | 文字列 | `webinarConfirmationUrl` | |
| isExhausted | ブール値 | isExhausted | |

{style="table-layout:auto"}

+++

<!--
### B2B Marketing List Member dataset

The B2B Marketing List Member dataset contains member of marketing lists.

-->

## Workspace

コンポーネントが正しく定義されたので、Workspace プロジェクトで特定の B2B ビジュアライゼーションを構築できます。

以下は、上記の接続とデータビューを使用する Workspace プロジェクトの例です。 詳しくは、各ビジュアライゼーションの説明を参照してください。

+++ 詳細

![ビジュアライゼーション](assets/visualizations.png)

+++

