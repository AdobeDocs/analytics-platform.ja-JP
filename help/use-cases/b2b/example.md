---
title: B2B プロジェクトの例
description: B2B データを設定、設定、レポートする方法について説明します
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 1bfebb53fbe056ed6320380178c8b1ce8f7079f1
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 13%

---

# ユーザーベースの B2B プロジェクトの例

この記事では、一般的なユーザーベースの B2B 設定のコンテキスト内で、人物データに関してCustomer Journey Analyticsで適切にレポートする使用例を説明します。 このような設定は、[Real-Time CDP B2B edition](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview) で容易に行えます。  このユースケースでは、Customer Journey Analyticsでプロファイル（ユーザー）レベルの B2B データに基づいて設定、設定、レポートを行う方法を説明します。

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} アカウントベースのレポートのユースケースに関する別の節が、[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) のリリースで公開されました。

## 接続

接続を定義して、Experience Platformのすべての関連する B2B データセットを含めます。 接続に追加することを検討できるデータセット：

| データセット | スキーマ | スキーマタイプ | 基本クラス | 説明 |
|---|---|---|---|---|
| B2B アクティビティデータセット | B2B アクティビティスキーマ | イベント | XDM ExperienceEvent | ExperienceEvent は、発生した事実（特定の時点や個人の ID など）の記録したものです。 ExperienceEvents は、明示的（直接観察可能な人間のアクション）または暗黙的（直接人間のアクションなしで発生）に設定でき、集計や解釈なしで記録されます。エクスペリエンスイベントは、特定の期間内に発生する変更の観察や分析、およびトレンドを追跡するための複数の時間枠間の比較を可能にするので、タイムドメイン分析にとって重要です。 |
| B2B 人物データセット | B2B 人物スキーマ | プロファイル | XDM 個人プロファイル | XDM 個人プロファイルは、識別された個人と部分的に識別された個人の両方の属性と興味の単一の表現を形成します。 識別されていないプロファイルには、ブラウザー cookie などの匿名の行動シグナルのみが含まれる場合がありますが、識別されたプロファイルには、名前、生年月日、場所、メールアドレスなどの詳細な個人情報が含まれる場合があります。 プロファイルが増えるにつれ、個人情報、識別情報、連絡先の詳細、個人のコミュニケーション設定の堅牢なリポジトリーになります。 |
| B2B アカウントデータセット | B2B アカウントスキーマ | ルックアップ | XDM Business Account | XDM ビジネスアカウントは、ビジネスアカウントに必要な最小限のプロパティをキャプチャする、標準のエクスペリエンスデータモデル（XDM）クラスです。 この XDM クラスは、B2B または B2P Edition を使用する顧客のプロファイルにのみ含めることができます。 |
| B2B 商談データセット | B2B オポチュニティスキーマ | ルックアップ | XDM Business Opportunity | XDM Business Opportunity は、ビジネスオポチュニティに必要な最小限のプロパティをキャプチャする、標準のエクスペリエンスデータモデル（XDM）クラスです。 この XDM クラスは、B2B または B2P Edition を使用する顧客のプロファイルにのみ含めることができます。 |
| B2B キャンペーンデータセット | B2B キャンペーンスキーマ | ルックアップ | XDM Business Campaign | XDM ビジネスキャンペーンは、ビジネスキャンペーンに必要な最小限のプロパティをキャプチャする、標準のエクスペリエンスデータモデル（XDM）クラスです。 この XDM クラスは、B2B または B2P Edition を使用する顧客のプロファイルにのみ含めることができます。 |
| B2B マーケティングリストデータセット | B2B マーケティングリストスキーマ | ルックアップ | XDM Business Marketing List | XDM ビジネスマーケティングリストは、マーケティングリストに必要な最小限のプロパティをキャプチャする、標準のエクスペリエンスデータモデル（XDM）クラスです。 マーケティングリストを使用すると、商品を購入する可能性が最も高い見込み客を優先することができます。 この XDM クラスは、B2B または B2P Edition を使用する顧客のプロファイルにのみ含めることができます。 |
| B2B アカウント人物関係データセット | B2B アカウント人物関係スキーマ | ルックアップ | XDM Business Account Person Relation | XDM ビジネスアカウントユーザー関係は、ビジネスアカウントに関連付けられたユーザーの最低限必要なプロパティをキャプチャする、標準のエクスペリエンスデータモデル（XDM）クラスです。 |
| B2B オポチュニティ人物関係データセット | B2B オポチュニティ人物関係スキーマ | ルックアップ | XDM Business Opportunity Person Relation | XDM Business Opportunity ユーザー関係は、ビジネスオポチュニティに関連付けられたユーザーの最低限必要なプロパティをキャプチャする、標準のエクスペリエンスデータモデル（XDM）クラスです。 |
| B2B マーケティングリストメンバーデータセット | B2B マーケティングリストメンバースキーマ | ルックアップ | XDM マーケティングリストメンバー | XDM ビジネスマーケティングリストメンバーは、マーケティングリストに関連付けられたメンバー、人物または連絡先を記述する、標準のエクスペリエンスデータモデル（XDM）クラスです。 |
| B2B キャンペーンメンバーデータセット | B2B キャンペーンメンバースキーマ | ルックアップ | XDM Business Campaign Members | XDM ビジネスキャンペーンメンバーは、ビジネスキャンペーンに関連付けられた連絡先またはリードを記述する標準のエクスペリエンスデータモデル（XDM）クラスです。 |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


B2B ルックアップスキーマ、プロファイルスキーマおよびイベントスキーマ間の関係は、Experience Platform内の B2B 設定で定義されます。 [Real-Time Customer Data Platform B2B editionのスキーマおよび &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/schemas/b2b)Real-Time Customer Data Platform B2B editionの 2 つのスキーマ間の多対 1 の関係の定義 [&#x200B; を参照してください &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/relationship-b2b)


B2B データのユーザーベースの検索をサポートする接続を適切に設定するには、概要について次の図を使用し、次の手順に従います。

注釈付きの ![B2B スキーマ &#x200B;](assets/b2b-schemas-annotated.svg)

1. 上記のテーブルから接続にデータセットを追加します。
1. 接続に追加する各ルックアップデータセットについて、**[!UICONTROL データセットを編集]** ダイアログで **[!UICONTROL キー]** と **[!UICONTROL 一致するキー]** を使用して、イベントデータセットへの関係を明示的に定義する必要があります。
1. ユーザーベースの B2B 検索で変換する各検索データセットについて、**[!UICONTROL データセットを変換]** を有効にして、ユーザーベースの検索でデータが確実に変換されるようにします。 詳しくは、[B2B ルックアップ用のデータセットの変換 &#x200B;](/help/connections/transform-datasets-b2b-lookups.md) を参照してください。

   ![&#x200B; キー – 一致するキー &#x200B;](assets/key-matchingkey.png)

   次の表に、各データセットの [!UICONTROL &#x200B; ユーザー ID]、[!UICONTROL &#x200B; キー &#x200B;] および [!UICONTROL &#x200B; 一致するキー &#x200B;] 値の概要例を示します。

   | データセット | ユーザー ID | キー | 一致するキー <br/> （イベントデータセット内） |
   |---|---|---|---| 
   | B2B アクティビティデータセット | SourceKey <br/>**personKey.sourceKey** | | |
   | B2B 人物データセット | SourceKey <br/>**b2b.personKey.sourceKey** | | |
   | B2B アカウントデータセット | | SourceKey <br/>**accountKey.sourceKey**&#x200B;❶ | SourceKey<br> （B2B Person Dataset） <br/>**b2b.accountKey.sourceKey**&#x200B;❶ |
   | B2B 商談データセット | | Source Key <br/>**opportunityKey.sourceKey**&#x200B;❷ | SourceKey<br/> （B2B 商談関係データセット） <br/>**opportunityKey.sourceKey**&#x200B;❷ |
   | B2B キャンペーンデータセット | | SourceKey <br/>**campaignKey.sourceKey**&#x200B;❸ | SourceKey<br/> （B2B キャンペーンメンバーデータセット） <br/>**campaignKey.sourceKey**&#x200B;❸<br/> |
   | B2B マーケティングリストデータセット | | SourceKey <br/>**marketingListKey.sourceKey**&#x200B;❹ | SourceKey<br/> （B2B マーケティングリストメンバーデータセット） <br/>**marketingListKey.sourceKey**&#x200B;❹ |
   | B2B アカウント人物関係データセット | | SourceKey <br/>**personKey.sourceKey**&#x200B;❺ | Source Key<br/> （イベントデータセット） <br/>**personKey.sourceKey**&#x200B;❺ |
   | B2B オポチュニティ人物関係データセット | | SourceKey <br/>**personKey.sourceKe** y❻ | Source Key<br/> （イベントデータセット） <br/>**personKey.sourceKey**&#x200B;❻ |
   | B2B キャンペーンメンバーデータセット | | SourceKey <br/>**personKey.sourceKey**&#x200B;❼ | Source Key<br/> （イベントデータセット） <br/>**personKey.sourceKey**&#x200B;❼ |
   | B2B マーケティングリストメンバーデータセット | | SourceKey <br/>**personKey.sourceKey**&#x200B;❽ | Source Key<br/> （イベントデータセット） <br/>**personKey.sourceKey**&#x200B;❽ |

{style="table-layout:auto"}

データセットの設定を構成する方法について詳しくは、[&#x200B; データセットの追加と構成 &#x200B;](../../connections/create-connection.md) を参照してください。


## データビュー

Workspace プロジェクトを作成する際に、関連する B2B ディメンションと指標にアクセスできるようにするには、それに応じてデータビューを定義する必要があります。

例えば、次のコンポーネントをデータビューに追加して、B2B データに基づいてユーザーベースのレベルでレポートできるようにします。 コンポーネント名は、元のスキーマ名がわかりやすいように変更される場合があります。

+++指標 

| コンポーネント名 | データセット | データタイプ | スキーマパス |
|---|---|---|---|
| 年収 | B2B アカウントデータセット | Double | accountOrganization.annualRevenue.amount |
| 従業員数 | B2B アカウントデータセット | 整数 | accountOrganization.numberOfEmployees |
| 実際のキャンペーンコスト | B2B キャンペーンデータセット | Double | actualCost.amount |
| 予算計上キャンペーンコスト | B2B キャンペーンデータセット | Double | budgetedCost.amount |
| 見込み商談収益 | B2B 商談データセット | Double | expectedRevenue.amount |
| 予想されるキャンペーン収益 | B2B キャンペーンデータセット | Double | expectedRevenue.amount |
| オポチュニティの金額 | B2B 商談データセット | Double | opportunityAmount.amount |

+++

+++ディメンション

| コンポーネント名 | データセット | データタイプ | スキーマパス |
|---|---|---|---|
| アカウント名 | B2B アカウントデータセット | 文字列 | accountName |
| キャンペーン名 | B2B キャンペーンデータセット | 文字列 | campaignName |
| チャネル名 | B2B キャンペーンデータセット | 文字列 | channelName |
| 国 | B2B アカウントデータセット | 文字列 | accountBillingAddress.country |
| 予測カテゴリ名 | B2B 商談データセット | 文字列 | forecastCategoryName |
| 業界 | B2B アカウントデータセット | 文字列 | accountOrganization.industry |
| 姓 | B2B 人物データセット | 文字列 | person.name.lastName |
| マーケティングリスト名 | B2B マーケティングリストデータセット | 文字列 | marketingListName |
| 商談名 | B2B 商談データセット | 文字列 | opportunityName |
| 商談ステージ | B2B 商談データセット | 文字列 | opportunityStage |
| 商談タイプ | B2B 商談タイプデータセット | 文字列 | opportunityType |
| ウェビナーセッション名 | B2B キャンペーンデータセット | 文字列 | webinarSessionName |

+++

## Workspace

データビューでコンポーネントを適切に定義すれば、Workspace プロジェクトで特定の B2B レポートおよびビジュアライゼーションを作成できるようになります。

以下は、上記の接続とデータビューに依存するサンプルプロジェクトのスクリーンショットです。 ビジュアライゼーションの説明では、変換された B2B ルックアップデータに依存するフリーフォームテーブルビジュアライゼーションについて説明します。

![&#x200B; サンプルプロジェクト &#x200B;](assets/sample-workspace-project.png)

