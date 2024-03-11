---
title: レポートスイートを様々なスキーマと組み合わせる
description: データ準備を使用してレポートスイートを様々なスキーマと組み合わせる方法を説明します
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 57%

---

# レポートスイートを様々なスキーマと組み合わせる

The [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) は、Adobe AnalyticsからAdobe Experience Platformにレポートスイートデータを取り込み、Real-time Customer Data PlatformやCustomer Journey Analytics(Customer Journey Analytics) などのAdobe Experience Platformアプリケーションで使用できるようにします。 Adobe Experience Platformに取り込まれる各レポートスイートは、個々のソース接続データフローとして設定され、各データフローは、Adobe Experience Platformデータレイク内のデータセットとして配置されます。 Analytics ソースコネクタは、レポートスイートごとに 1 つのデータセットを作成します。

Customer Journey Analyticsのお客様が [接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja) を使用して、Adobe Experience PlatformデータレイクのデータセットをCustomer Journey AnalyticsAnalysis Workspaceに統合します。 ただし、1 つの接続内でレポートスイートを組み合わせる場合は、Adobe Experience Platformを使用してレポートスイート間のスキーマの違いを解決する必要があります [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) 機能。 目的は、prop や eVar などのAdobe Analytics変数がCustomer Journey Analyticsで一貫した意味を持つようにすることです。

## レポートスイート間のスキーマの違いが問題

Customer Journey Analyticsで使用する 2 つの異なるレポートスイートのデータをAdobe Experience Platformに取り込み、2 つのレポートスイートのスキーマに違いがあるとします。

| レポートスイート A | レポートスイート B |
| --- | --- |
| eVar1 = 検索語句 | eVar1 = ビジネスユニット |
| eVar2 = 顧客カテゴリ | eVar2 = 検索語句 |

簡潔にするために、両方のレポートスイートで定義されている eVar はこれらのみということにします。

さらに、次のアクションを実行するとします。

- 取り込む Analytics ソース接続の作成（データ準備を使用しない） **レポートスイート A** をAdobe Experience Platformデータレイクに **データセット A**.
- 取り込む Analytics ソース接続の作成（データ準備を使用しない） **レポートスイート B** をAdobe Experience Platformデータレイクに **データセット B**.
- の作成 [Customer Journey Analytics接続](/help/connections/create-connection.md) 呼び出し **すべてのレポートスイート** データセット A とデータセット B を組み合わせた
- の作成 [Customer Journey Analyticsのデータビュー](/help/data-views/create-dataview.md) 呼び出し **グローバル表示** すべてのレポートスイート接続に基づいている

データセット A とデータセット B の間のスキーマの違いを解決するためにデータ準備を使用しない場合、グローバル表示データビューの eVar には、次の値が混在することになります。

| Customer Journey Analyticsのグローバルビューデータビュー |
| --- |
| eVar1 => 検索語句とビジネスユニットの混在 |
| eVar2 => 顧客カテゴリと検索語句の混在 |

このような状況では、eVar1 と eVar2 について意味のないレポートが作成されることになります。

- eVar フィールドには、様々な意味論的意味を含む値が混在します。
- 検索語句は、eVar1 と eVar2 の間で分散されます。
- 検索語句、ビジネスユニット、顧客カテゴリごとに異なるアトリビューションモデルを使用することはできません。

## Adobe Experience Platform Data Prep を使用して、レポートスイート間のスキーマの違いを解決する

Experience Platformデータ準備機能は、Analytics ソースコネクタと統合されており、上記のシナリオで説明したスキーマの違いの解決に使用できます。 その結果、Customer Journey Analyticsデータビューで一貫した意味の eVar が生成されます。 （次に使用する命名規則は、必要に応じてカスタマイズできます。）

1. レポートスイート A とレポートスイート B のソース接続データフローを作成する前に、 [新しいスキーマを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja) ADOBE EXPERIENCE PLATFORM( **統合スキーマ** （この例では）。 スキーマに次を追加します。

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

1. 次に、 **すべてのレポートスイート** Customer Journey Analytics用の接続。データセット A とデータセット B を組み合わせます。

1. の作成 **グローバル表示** Customer Journey Analyticsのデータビュー。 元の eVar フィールドを無視して、「Unified Fields」フィールドグループからのフィールドのみを含めます。

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
>統合フィールドのカスタムフィールドグループと関連するフィールドマッピングは、いつでも既存の Analytics ソースコネクタのデータフローとデータセットに追加できます。 ただし、これは、将来のデータにのみ影響します。

## 単なるレポートスイート以上

データセットを様々なスキーマと組み合わせるデータ準備の機能は、Analytics レポートスイートを超えたものです。次のデータを含む 2 つのデータセットがあるとします。

| データセット A = Analytics ソースコネクタを使用した Analytics レポートスイート |
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

1. データセット A とCustomer Journey Analyticsセット B を組み合わせたデータ接続を作成します。

1. 先ほど作成したCustomer Journey Analytics接続を使用して、Customer Journey Analyticsでデータビューを作成します。 元の eVar フィールドを無視して、「Customer Info」フィールドグループからのフィールドのみを含めます。

   Customer Journey Analyticsのデータビュー：

   | ソースフィールド | データビューに含める？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | × |
   | \_experience.analytics.customDimensions.eVars.eVar2 | × |
   | _\&lt;path>_.Customer_category | ○ |

## データ準備とコンポーネント ID の比較

前述のように、データ準備を使用すると、複数の Adobe Analytics レポートスイートをまたいで異なるフィールドを一緒にマッピングできます。これは、複数のCustomer Journey Analyticsセットのデータを 1 つのデータ接続に組み合わせる場合にCustomer Journey Analyticsに役立ちます。 ただし、レポートスイートを別々のCustomer Journey Analytics接続に維持する場合で、これらの接続とデータビューをまたいで 1 組のレポートを使用する場合、Customer Journey Analyticsの基になるコンポーネント ID を変更すると、異なるスキーマでもレポートに互換性を持たせることができます。 詳しくは、[コンポーネント設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html)を参照してください。

コンポーネント ID の変更はCustomer Journey Analyticsのみの機能で、リアルタイム顧客プロファイルおよび RTCDP に送信される Analytics ソースコネクタからのデータには影響しません。
