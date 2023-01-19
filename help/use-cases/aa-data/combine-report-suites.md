---
title: レポートスイートを様々なスキーマと組み合わせる
description: データ準備を使用してレポートスイートを様々なスキーマと組み合わせる方法を説明します
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 69356510596d047d80af63338fccca71e8af53cd
workflow-type: ht
source-wordcount: '1335'
ht-degree: 100%

---

# レポートスイートを様々なスキーマと組み合わせる

[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)は、AEP アプリケーション（Real-time Customer Data Platform や Customer Journey Analytics（CJA）など）で使用するために、Adobe Analytics から Adobe Experience Platform（AEP）にレポートスイートデータを取り込みます。AEP に取り込まれる各レポートスイートは、個別のソース接続データフローとして設定され、各データフローは AEP データレイク内のデータセットとして取得されます。Analytics ソースコネクタは、レポートスイートごとに 1 つのデータセットを作成します。

CJA のお客様は、[接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja)を使用して、AEP データレイクから CJA の Analysis Workspace にデータセットを統合します。ただし、接続内でレポートスイートを組み合わせる場合、レポートスイート間のスキーマの違いは、AEP の[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)機能を使用して解決される必要があります。その目的は、Adobe Analytics 変数（prop や eVar など）が CJA 内で一貫した意味を持つのを保証することです。

## レポートスイート間のスキーマの違いが問題

あなたの会社が、CJA で使用するために 2 つの異なるレポートスイートから AEP にデータを取り込みたいと想定し、2 つのレポートスイートのスキーマに違いがあると仮定します。

| レポートスイート A | レポートスイート B |
| --- | --- |
| eVar1 = 検索語句 | eVar1 = ビジネスユニット |
| eVar2 = 顧客カテゴリ | eVar2 = 検索語句 |

簡潔にするために、両方のレポートスイートで定義されている eVar はこれらのみということにします。

さらに、次のアクションを実行するとします。

- **レポートスイート A** を&#x200B;**データセット A** として AEP データレイクに取り込む Analytics ソース接続を作成（データ準備を使用しない）。
- **レポートスイート B** を&#x200B;**データセット B** として AEP データレイクに取り込む Analytics ソース接続を作成（データ準備を使用しない）。
- データセット A とデータセット B を組み合わせた、**すべてのレポートスイート**&#x200B;と呼ばれる [CJA 接続](/help/connections/create-connection.md)を作成。
- すべてのレポートスイート接続に基づいた、**グローバル表示**&#x200B;と呼ばれる [CJA データビュー](/help/data-views/create-dataview.md)を作成。

データセット A とデータセット B の間のスキーマの違いを解決するためにデータ準備を使用しない場合、グローバル表示データビューの eVar には、次の値が混在することになります。

| CJA のグローバル表示データビュー |
| --- |
| eVar1 => 検索語句とビジネスユニットの混在 |
| eVar2 => 顧客カテゴリと検索語句の混在 |

このような状況では、eVar1 と eVar2 について意味のないレポートが作成されることになります。

- eVar フィールドには、様々な意味論的意味を含む値が混在します。
- 検索語句は、eVar1 と eVar2 の間で分散されます。
- 検索語句、ビジネスユニット、顧客カテゴリごとに異なるアトリビューションモデルを使用することはできません。

## AEP データ準備を使用したレポートスイート間のスキーマの違いの解決

Experience Platform データ準備機能は、Analytics ソースコネクタと統合されており、前述のシナリオで説明したスキーマの違いを解決するのに使用できます。これにより、CJA データビューで一貫した意味を持つ eVar になります（次に使用する命名規則は、必要に応じてカスタマイズできます。）

1. レポートスイート A とレポートスイート B のソース接続データフローを作成する前に、AEP で[新しいスキーマを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja)します（この例では、**Unified Schema** と呼ぶことにします）。スキーマに次を追加します。

   | 「Unified Schema」 |
   | --- |
   | **XDM ExperienceEvent** クラス |
   | 「**Adobe Analytics ExperienceEvent テンプレート**」フィールドグループ |

1. スキーマに別のフィールドグループを追加するか、[カスタムフィールドグループを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=ja#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail)してスキーマに追加します。ここでは、新しいフィールドグループを作成し、**Unified Fields** と呼ぶことにします。次に、この新しいフィールドグループに次のフィールドを追加します。

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

1. ここで、データセット A とデータセット B を組み合わせる、CJA の&#x200B;**すべてのレポートスイート**&#x200B;接続を作成します。

1. CJA の&#x200B;**グローバル表示**&#x200B;データビューを作成します。元の eVar フィールドを無視して、「Unified Fields」フィールドグループからのフィールドのみを含めます。

   CJA の&#x200B;**グローバル表示**&#x200B;データビュー：

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
>「Unified Fields」カスタムフィールドグループと、関連するフィールドマッピングは、既存の Analytics ソースコネクタデータフローおよびデータセットにいつでも追加できます。ただし、これは、将来のデータにのみ影響します。

## 単なるレポートスイート以上

データセットを様々なスキーマと組み合わせるデータ準備の機能は、Analytics レポートスイートを超えたものです。次のデータを含む 2 つのデータセットがあるとします。

| データセット A = Analytics ソースコネクタを介した Analytics レポートスイート |
| --- |
| `eVar1` => 顧客カテゴリ |

| データセット B = コールセンターデータ |
| --- |
| Some_field => 顧客カテゴリ |

データ準備を使用すると、Analytics データの eVar 1 の顧客カテゴリとコールセンターデータの Some_field の顧客カテゴリを組み合わせることができます。次に、その方法のひとつを示します。ここでも、命名規則は必要に応じて変更できます。

1. AEP でスキーマを作成します。スキーマに次を追加します。

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

1. データセット A とデータセット B を組み合わせる CJA 接続を作成します。

1. 作成したばかりの CJA 接続を使用して、CJA でデータビューを作成します。元の eVar フィールドを無視して、「Customer Info」フィールドグループからのフィールドのみを含めます。

   CJA のデータビュー：

   | ソースフィールド | データビューに含める？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | × |
   | \_experience.analytics.customDimensions.eVars.eVar2 | × |
   | _\&lt;path>_.Customer_category | ○ |

## データ準備とコンポーネント ID の比較

前述のように、データ準備を使用すると、複数の Adobe Analytics レポートスイートをまたいで異なるフィールドを一緒にマッピングできます。これは、CJA で、複数のデータセットから単一の CJA 接続にデータを組み合わせたい場合に便利です。ただし、レポートスイートを別々の CJA 接続のままにするつもりでも、それらの接続やデータビューで 1 セットのレポートを使用したい場合、CJA で基盤となるコンポーネント ID を変更すると、スキーマが異なる場合でもレポートの互換性を維持する手段が提供されます。詳しくは、[コンポーネント設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=ja)を参照してください。

コンポーネント ID の変更は、CJA のみの機能であり、リアルタイム顧客プロファイルおよび RTCDP に送信される Analytics ソースコネクタのデータには影響しません。
