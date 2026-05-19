---
title: レポートスイートを様々なスキーマと組み合わせる
description: データ準備を使用してレポートスイートを様々なスキーマと組み合わせる方法を説明します
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
autotag-review: '2026-05-19T09:35:22.411Z'
TQID: 'https://experienceleague.adobe.com/La2B-Yvc3-OHQsgmr5EPILZQBcm6zKCAAcKPLZ3PbIQ'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1390
ht-degree: 55%

---

# レポートスイートを様々なスキーマと組み合わせる

[Analytics ソースコネクタ ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)は、Adobe AnalyticsのレポートスイートデータをAdobe Experience Platformに取り込み、Real-time Customer Data PlatformやCustomer Journey Analytics（Customer Journey Analytics）などのAdobe Experience Platform アプリケーションで使用します。 Adobe Experience Platformに取り込まれた各レポートスイートは、個々のソース接続データフローとして設定され、各データフローはAdobe Experience Platform データレイク内のデータセットとして格納されます。 Analytics ソースコネクタは、レポートスイートごとに1つのデータセットを作成します。

Customer Journey Analyticsのお客様は、[connections](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja)を使用して、Adobe Experience Platform データレイクからCustomer Journey Analytics Analysis Workspaceにデータセットを統合します。 ただし、接続内でレポートスイートを組み合わせる場合、Adobe Experience Platform [ データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)機能を使用してレポートスイート間のスキーマの違いを解決する必要があります。 その目的は、propやeVarなどのAdobe Analytics変数がCustomer Journey Analyticsで一貫した意味を持つようにすることです。

## レポートスイート間のスキーマの違いが問題

Customer Journey Analyticsで使用するために、2つの異なるレポートスイートからAdobe Experience Platformにデータを取り込み、2つのレポートスイートのスキーマに違いがあると仮定します。

| レポートスイート A | レポートスイート B |
| --- | --- |
| eVar1 = 検索語句 | eVar1 = ビジネスユニット |
| eVar2 = 顧客カテゴリ | eVar2 = 検索語句 |

簡素化のために、両方のレポートスイートに対して、これらは唯一の定義されたeVarであると仮定します。

さらに、次のアクションを実行するとします。

- **Report Suite A**&#x200B;を&#x200B;**データセット A**&#x200B;としてAdobe Experience Platform データレイクに取り込むAnalytics ソース接続を（データ準備を使用せずに）作成します。
- **Report Suite B**&#x200B;を&#x200B;**データセット B**&#x200B;としてAdobe Experience Platform データレイクに取り込むAnalytics ソース接続を（データ準備を使用せずに）作成します。
- データセット Aとデータセット Bを組み合わせた&#x200B;**すべてのレポートスイート**&#x200B;という[Customer Journey Analytics接続](/help/connections/create-connection.md)を作成します。
- すべてのレポートスイート接続に基づく&#x200B;**グローバルビュー**&#x200B;という[Customer Journey Analytics データビュー](/help/data-views/create-dataview.md)を作成します。

データセット A とデータセット B の間のスキーマの違いを解決するためにデータ準備を使用しない場合、グローバル表示データビューの eVar には、次の値が混在することになります。

| Customer Journey Analyticsのグローバルビューデータビュー |
| --- |
| eVar1 => 検索語句とビジネスユニットの混在 |
| eVar2 => 顧客カテゴリと検索語句の混在 |

このような状況では、eVar1 と eVar2 について意味のないレポートが作成されることになります。

- eVar フィールドには、様々な意味論的意味を含む値が混在します。
- 検索語句は、eVar1 と eVar2 の間で分散されます。
- 検索語句、ビジネスユニット、顧客カテゴリごとに異なるアトリビューションモデルを使用することはできません。

## Adobe Experience Platform Data Prepを使用して、レポートスイート間のスキーマの違いを解決します

Experience Platform Data Prep機能は、Analytics ソースコネクタと統合されており、上記のシナリオで説明したスキーマの違いを解決するために使用できます。 これにより、Customer Journey Analytics データビューで一貫した意味を持つeVarが作成されます。 （次に使用する命名規則は、必要に応じてカスタマイズできます。）

1. レポートスイート Aおよびレポートスイート Bのソース接続データフローを作成する前に、[Adobe Experience Platformで新しいスキーマ ](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja)を作成します（この例では&#x200B;**統合スキーマ**&#x200B;と呼びます）。 スキーマに次を追加します。

   | 「統合スキーマ」 |
   | --- |
   | **XDM ExperienceEvent** クラス |
   | 「**Adobe Analytics ExperienceEvent テンプレート**」フィールドグループ |

1. スキーマに別のフィールドグループを追加するか、[カスタムフィールドグループを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail)してスキーマに追加します。 ここでは、新しいフィールドグループを作成し、**Unified Fields** と呼ぶことにします。 次に、この新しいフィールドグループに次のフィールドを追加します。

   | 「Unified Fields」カスタムフィールドグループ  |
   | --- |
   | 検索語句 |
   | ビジネスユニット |
   | 顧客カテゴリ |

1. データフローで使用する&#x200B;**統合スキーマ**&#x200B;を選択して、**レポートスイート A** のソース接続データフローを作成します。 次のように、データフローにカスタムマッピングを追加します。

   | レポートスイート A ソースフィールド | 「Unified Fields」フィールドグループからの宛先フィールド |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >宛先フィールドの XDM パスは、カスタムフィールドグループの構造によって異なります。

1. データフローで使用する&#x200B;**統合スキーマ**&#x200B;を選択して、**レポートスイート B** のソース接続データフローを作成します。 このワークフローでは、2 つのフィールドの記述子名が競合していることが表示されます。 これは、eVar1 と eVar2 の記述子がレポートスイート B とレポートスイート A で異なっているからです。しかし、これは既にわかっていることなので、問題なく競合を無視でき、次のようにカスタムマッピングを使用できます。

   | レポートスイート B ソースフィールド | 「Unified Fields」フィールドグループからの宛先フィールド |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. 次に、データセット Aとデータセット Bを組み合わせて、Customer Journey Analyticsの&#x200B;**すべてのレポートスイート**&#x200B;接続を作成します。

1. Customer Journey Analyticsで&#x200B;**グローバルビュー** データビューを作成します。 元の eVar フィールドを無視して、「Unified Fields」フィールドグループからのフィールドのみを含めます。

   Customer Journey Analyticsの&#x200B;**グローバルビュー** データビュー：

   | ソースフィールド | データビューに含める？ |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | いいえ |
   | \_experience.analytics.customDimensions.eVars.eVar2 | いいえ |
   | _\&lt;path>_.Search_term | はい |
   | _\&lt;path>_.Customer_category  | はい |
   | _\&lt;path>_.Business_unit | はい |

これで、ソースレポートスイートの eVar1 および eVar2 が 3 つの新しいフィールドにマッピングされました。 データ準備のマッピングを使用するもう 1 つの利点は、宛先フィールドが、意味のない eVar 名（eVar1、eVar2）ではなく、意味論的に意味のある名前（検索語句、ビジネスユニット、顧客カテゴリ）に基づいていることです。

>[!NOTE]
>
>統合フィールドのカスタムフィールドグループ、および関連するフィールドマッピングは、いつでも既存のAnalytics ソースコネクタのデータフローとデータセットに追加できます。 ただし、これは、将来のデータにのみ影響します。

## 単なるレポートスイート以上

データセットを様々なスキーマと組み合わせるデータ準備の機能は、Analytics レポートスイートを超えたものです。 次のデータを含む 2 つのデータセットがあるとします。

| データセット A = Analytics ソースコネクタを介したAnalytics レポートスイート |
| --- |
| `eVar1` => 顧客カテゴリ |

| データセット B = コールセンターデータ |
| --- |
| Some_field => 顧客カテゴリ |

データ準備を使用すると、Analytics データの eVar 1 の顧客カテゴリとコールセンターデータの Some_field の顧客カテゴリを組み合わせることができます。 次に、その方法のひとつを示します。 ここでも、命名規則は必要に応じて変更できます。

1. Adobe Experience Platformでスキーマを作成します。 スキーマに次を追加します。

   | 「拡張スキーマ」 |
   | --- |
   | **XDM エクスペリエンスイベント**&#x200B;クラス |
   | 「**Adobe Analytics エクスペリエンスイベントテンプレート**」フィールドグループ |

1. 新しいフィールドグループを作成して、スキーマに追加します。 フィールドグループにフィールドを追加します。

   | 「Customer Info」カスタムフィールドグループ  |
   | --- |
   | Customer_category |

1. **データセット A** のデータフローを作成し、スキーマとして **Extended Schema** を選択します。 次のように、データフローにカスタムマッピングを追加します。

   | データセット A ソースフィールド | 「Customer Info」フィールドグループからの宛先フィールド |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. **データセット B** のデータフローを作成し、スキーマとして **Extended Schema** を選択します。 次のように、データフローにカスタムマッピングを追加します。

   | データセット B ソースフィールド | 「Customer Info」フィールドグループからの宛先フィールド |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. データセット Aとデータセット Bを組み合わせたCustomer Journey Analytics接続を作成します。

1. 先ほど作成したCustomer Journey Analytics接続を使用して、Customer Journey Analyticsでデータビューを作成します。 元の eVar フィールドを無視して、「Customer Info」フィールドグループからのフィールドのみを含めます。

   Customer Journey Analyticsのデータビュー：

   | ソースフィールド | データビューに含める？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | いいえ |
   | \_experience.analytics.customDimensions.eVars.eVar2 | いいえ |
   | _\&lt;path>_.Customer_category | はい |

## データ準備とコンポーネント ID の比較

前述のように、データ準備を使用すると、複数の Adobe Analytics レポートスイートをまたいで異なるフィールドを一緒にマッピングできます。 これは、複数のデータセットのデータを1つのCustomer Journey Analytics接続に結合する場合にCustomer Journey Analyticsで役立ちます。 ただし、レポートスイートを個別のCustomer Journey Analytics接続に保持する場合に、これらの接続とデータビュー全体で1つのレポートセットを使用する場合は、Customer Journey Analyticsで基になるコンポーネント IDを変更すると、スキーマが異なる場合でもレポートを互換性のあるものにすることができます。 詳しくは、[コンポーネント設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html)を参照してください。

コンポーネント IDの変更はCustomer Journey Analyticsのみの機能であり、Real-time Customer ProfileおよびRTCDPに送信されるAnalytics ソースコネクタのデータには影響しません。
