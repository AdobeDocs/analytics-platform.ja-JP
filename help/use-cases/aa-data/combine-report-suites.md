---
title: レポートスイートを様々なスキーマと組み合わせる
description: データ準備を使用してレポートスイートを様々なスキーマと組み合わせる方法を説明します
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 55%

---

# レポートスイートを様々なスキーマと組み合わせる

[Analytics ソースコネクタ ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) は、Real-time Customer Data PlatformやCustomer Journey Analytics（Customer Journey Analytics）などのAdobe Experience Platform アプリケーションで使用するために、Adobe AnalyticsからAdobe Experience Platformにレポートスイートデータを取り込みます。 Adobe Experience Platformに取り込まれる各レポートスイートは、個々のソース接続データフローとして設定され、各データフローはAdobe Experience Platform データレイク内のデータセットとして取得されます。 Analytics ソースコネクタは、レポートスイートごとに 1 つのデータセットを作成します。

Customer Journey Analyticsのお客様は、[ 接続 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja) を使用して、Adobe Experience Platform データレイクからCustomer Journey Analytics Analysis Workspaceにデータセットを統合します。 ただし、接続内でレポートスイートを組み合わせる場合、レポートスイート間のスキーマの違いは、Adobe Experience Platform[ データ準備 ](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) 機能を使用して解決される必要があります。 その目的は、prop や eVar などのAdobe Analytics変数のCustomer Journey Analyticsにおいて、一貫性のある意味を持たせることです。

## レポートスイート間のスキーマの違いが問題

あなたの会社が、Customer Journey Analyticsで使用するために 2 つの異なるレポートスイートからAdobe Experience Platformにデータを取り込みたいと想定し、2 つのレポートスイートのスキーマに違いがあると仮定します。

| レポートスイート A | レポートスイート B |
| --- | --- |
| eVar1 = 検索語句 | eVar1 = ビジネスユニット |
| eVar2 = 顧客カテゴリ | eVar2 = 検索語句 |

説明を簡単にするために、両方のレポートスイートで定義されている eVar はこれらのみであると仮定します。

さらに、次のアクションを実行するとします。

- **レポートスイート A** を（データセット A **としてAdobe Experience Platform データレイクに取り込む Analytics ソース接続を作成** データ準備を使用しない）。
- **レポートスイート B** を（データセット B **としてAdobe Experience Platform データレイクに取り込む Analytics ソース接続を作成（データ準備を使用しない**。
- データセット A とデータセット B を組み合わせた [&#128279;](/help/connections/create-connection.md) すべてのレポートスイート **と呼ばれる** 0&rbrace;Customer Journey Analytics接続を作成。
- すべてのレポートスイートCustomer Journey Analyticsに基づいた [&#128279;](/help/data-views/create-dataview.md) グローバルビュー **と呼ばれる** 0&rbrace; 接続データビューを作成します。

データセット A とデータセット B の間のスキーマの違いを解決するためにデータ準備を使用しない場合、グローバル表示データビューの eVar には、次の値が混在することになります。

| Customer Journey Analyticsのグローバル表示データビュー |
| --- |
| eVar1 => 検索語句とビジネスユニットの混在 |
| eVar2 => 顧客カテゴリと検索語句の混在 |

このような状況では、eVar1 と eVar2 について意味のないレポートが作成されることになります。

- eVar フィールドには、様々な意味論的意味を含む値が混在します。
- 検索語句は、eVar1 と eVar2 の間で分散されます。
- 検索語句、ビジネスユニット、顧客カテゴリごとに異なるアトリビューションモデルを使用することはできません。

## Adobe Experience Platform Data Prep を使用したレポートスイート間のスキーマの違いの解決

Experience Platformのデータ準備機能は、Analytics ソースコネクタと統合されており、前述のシナリオで説明したスキーマの違いを解決するのに使用できます。 これにより、Customer Journey Analyticsデータビューで一貫した意味を持つ eVar になります。 （次に使用する命名規則は、必要に応じてカスタマイズできます。）

1. レポートスイート A とレポートスイート B のソース接続データフローを作成する前に、Adobe Experience Platformで [ 新しいスキーマを作成 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja) します（この例では、**Unified Schema** と呼ぶことにします）。 スキーマに次を追加します。

   | 「Unified Schema」 |
   | --- |
   | **XDM ExperienceEvent** クラス |
   | 「**Adobe Analytics ExperienceEvent テンプレート**」フィールドグループ |

1. スキーマに別のフィールドグループを追加するか、[カスタムフィールドグループを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail)してスキーマに追加します。ここでは、新しいフィールドグループを作成し、**Unified Fields** と呼ぶことにします。次に、この新しいフィールドグループに次のフィールドを追加します。

   | 「Unified Fields」カスタムフィールドグループ |
   | --- |
   | 検索語句 |
   | ビジネスユニット |
   | 顧客カテゴリ |

1. データフローで使用する **Unified Schema** を選択して、**レポートスイート A** のソース接続データフローを作成します。次のように、データフローにカスタムマッピングを追加します。

   | レポートスイート A ソースフィールド | 「Unified Fields」フィールドグループからの宛先フィールド |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >宛先フィールドの XDM パスは、カスタムフィールドグループの構造によって異なります。

1. データフローで使用する **Unified Schema** を選択して、**レポートスイート B** のソース接続データフローを作成します。このワークフローでは、2 つのフィールドの記述子名が競合していることが表示されます。これは、eVar1 と eVar2 の記述子がレポートスイート B とレポートスイート A で異なっているからです。しかし、これは既にわかっていることなので、問題なく競合を無視でき、次のようにカスタムマッピングを使用できます。

   | レポートスイート B ソースフィールド | 「Unified Fields」フィールドグループからの宛先フィールド |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. ここで、データセット A とデータセット B を組み合わせる、Customer Journey Analytics用の **すべてのレポートスイート** 接続を作成します。

1. Customer Journey Analyticsで **グローバル表示** データビューを作成します。 元の eVar フィールドを無視して、「Unified Fields」フィールドグループからのフィールドのみを含めます。

   **グローバル表示** Customer Journey Analyticsのデータビュー：

   | ソースフィールド | データビューに含める？ |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | × |
   | \_experience.analytics.customDimensions.eVars.eVar2 | × |
   | _\&lt;path>_.Search_term | ○ |
   | _\&lt;path>_.Customer_category  | ○ |
   | _\&lt;path>_.Business_unit | ○ |

これで、ソースレポートスイートの eVar1 および eVar2 が 3 つの新しいフィールドにマッピングされました。データ準備のマッピングを使用するもう 1 つの利点は、宛先フィールドが、意味のない eVar 名（eVar1、eVar2）ではなく、意味論的に意味のある名前（検索語句、ビジネスユニット、顧客カテゴリ）に基づいていることです。

>[!NOTE]
>
>「Unified Fields」カスタムフィールドグループと、関連するフィールドマッピングは、既存の Analytics ソースコネクタデータフローおよびデータセットにいつでも追加できます。 ただし、これは、将来のデータにのみ影響します。

## 単なるレポートスイート以上

データセットを様々なスキーマと組み合わせるデータ準備の機能は、Analytics レポートスイートを超えたものです。次のデータを含む 2 つのデータセットがあるとします。

| データセット A = Analytics ソースコネクタを介した Analytics レポートスイート |
| --- |
| `eVar1` => 顧客カテゴリ |

| データセット B = コールセンターデータ |
| --- |
| Some_field => 顧客カテゴリ |

データ準備を使用すると、Analytics データの eVar 1 の顧客カテゴリとコールセンターデータの Some_field の顧客カテゴリを組み合わせることができます。次に、その方法のひとつを示します。ここでも、命名規則は必要に応じて変更できます。

1. Adobe Experience Platformでスキーマを作成します。 スキーマに次を追加します。

   | 「Extended Schema」 |
   | --- | 
   | **XDM Experience Event** クラス |
   | 「**Adobe Analytics Experience Event テンプレート**」フィールドグループ |

1. 新しいフィールドグループを作成して、スキーマに追加します。フィールドグループにフィールドを追加します。

   | 「Customer Info」カスタムフィールドグループ |
   | --- |
   | Customer_category |

1. **データセット A** のデータフローを作成し、スキーマとして **Extended Schema** を選択します。次のように、データフローにカスタムマッピングを追加します。

   | データセット A ソースフィールド | 「Customer Info」フィールドグループからの宛先フィールド |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. **データセット B** のデータフローを作成し、スキーマとして **Extended Schema** を選択します。次のように、データフローにカスタムマッピングを追加します。

   | データセット B ソースフィールド | 「Customer Info」フィールドグループからの宛先フィールド |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. データセット A とデータセット B を組み合わせるCustomer Journey Analytics接続を作成します。

1. 作成したCustomer Journey Analytics接続を使用して、Customer Journey Analyticsでデータビューを作成します。 元の eVar フィールドを無視して、「Customer Info」フィールドグループからのフィールドのみを含めます。

   Customer Journey Analyticsのデータビュー：

   | ソースフィールド | データビューに含める？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | × |
   | \_experience.analytics.customDimensions.eVars.eVar2 | × |
   | _\&lt;path>_.Customer_category | ○ |

## データ準備とコンポーネント ID の比較

前述のように、データ準備を使用すると、複数の Adobe Analytics レポートスイートをまたいで異なるフィールドを一緒にマッピングできます。これは、複数のデータセットのデータを 1 つのCustomer Journey AnalyticsCustomer Journey Analyticsに組み合わせる場合に便利です。 ただし、レポートスイートを別々のCustomer Journey Analytics接続のままにするつもりでも、それらの接続やデータビューで 1 セットのレポートを使用したい場合、Customer Journey Analyticsで基になるコンポーネント ID を変更すると、スキーマが異なる場合でもレポートの互換性を維持する手段が提供されます。 詳しくは、[コンポーネント設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html)を参照してください。

コンポーネント ID の変更は、Customer Journey Analyticsのみの機能であり、リアルタイム顧客プロファイルおよび RTCDP に送信される Analytics ソースコネクタのデータには影響しません。
