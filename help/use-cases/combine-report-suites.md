---
title: 異なるスキーマでレポートスイートを組み合わせる
description: Data Prep を使用して、様々なスキーマを持つレポートスイートを組み合わせる方法を説明します
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: b7446d204eab2530d188600aed7e4cc0c603bf1d
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 4%

---

# 異なるスキーマとレポートスイートを組み合わせる

この [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) は、Adobe AnalyticsからAdobe Experience Platform(AEP) に、Real-time Customer Data PlatformやCustomer Journey Analytics(CJA) などの AEP アプリケーションで使用するために、レポートスイートデータを取り込みます。 AEP に取り込まれる各レポートスイートは、個々のソース接続データフローとして設定され、各データフローは AEP データレイク内のデータセットとして配置されます。 Analytics ソースコネクタは、レポートスイートごとに 1 つのデータセットを作成します。

CJA のお客様が使用する [接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja) を使用して、AEP データレイクのデータセットを CJA のAnalysis Workspaceに統合します。 ただし、1 つの接続内でレポートスイートを組み合わせる場合は、AEP の [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) 機能。 目的は、prop や eVar などのAdobe Analytics変数が CJA で一貫した意味を持つようにすることです。

## レポートスイート間のスキーマの違いに問題がある

CJA で使用するために 2 つの異なるレポートスイートのデータを AEP に取り込み、2 つのレポートスイートのスキーマに違いがあるとします。

| レポートスイート A | レポートスイート B |
| --- | --- |
| eVar1 =検索語 | eVar1 =ビジネスユニット |
| eVar2 =顧客カテゴリ | eVar2 =検索語 |

簡潔にするために、両方のレポートスイートで定義されている eVar はこれらのみであるとします。

さらに、次の操作を実行するとします。

- 取り込む Analytics ソース接続の作成（データ準備を使用しない） **レポートスイート A** をとして AEP データレイクに追加します。 **データセット A**.
- 取り込む Analytics ソース接続の作成（データ準備を使用しない） **レポートスイート B** をとして AEP データレイクに追加します。 **データセット B**.
- の作成 [CJA 接続](/help/connections/create-connection.md) 呼び出し **すべてのレポートスイート** データセット A とデータセット B を組み合わせた
- の作成 [CJA データビュー](/help/data-views/create-dataview.md) 呼び出し **グローバル表示** すべてのレポートスイート接続に基づいている

データセット A とデータセット B のスキーマの違いを解決するために Data Prep を使用しない場合、グローバルビューのデータビューの eVar には次の値が混在します。

| CJA でのグローバルビューのデータビュー |
| --- |
| eVar1 => 検索用語とビジネスユニットの組み合わせ |
| eVar2 => 顧客カテゴリと検索語句の組み合わせ |

この状況では、eVar1 とeVar2 の無意味なレポートが生じます。

- eVarフィールドには、異なる意味を持つ値が混在しています。
- 検索語句はeVar1 とeVar2 の間に分散されます。
- 検索用語、ビジネスユニット、顧客カテゴリごとに異なるアトリビューションモデルを使用することはできません。

## AEP Data Prep を使用して、レポートスイート間のスキーマの違いを解決する

Experience Platformデータ準備機能は、Analytics ソースコネクタと統合されており、上記のシナリオで説明したスキーマの違いの解決に使用できます。 その結果、CJA データビューで一貫した意味の eVar が得られます。 （以下で使用する命名規則は、ニーズに合わせてカスタマイズできます）。

1. レポートスイート A とレポートスイート B のソース接続データフローを作成する前に、 [新しいスキーマを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.htm?lang=ja) AEP 内（と呼びます） **統合スキーマ** （この例では）。 スキーマに以下を追加します。

   | &quot;統合スキーマ&quot; |
   | --- |
   | **XDM ExperienceEvent** クラス |
   | **Adobe Analytics ExperienceEvent テンプレート** フィールドグループ |

1. 別のフィールドグループをスキーマに追加するか、 [カスタムフィールドグループの作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) スキーマに追加します。 新しいフィールドグループを作成し、という名前を付けます。 **統合フィールド**. 次に、次のフィールドを新しいフィールドグループに追加します。

   | 「統合フィールド」カスタムフィールドグループ  |
   | --- |
   | 検索語句 |
   | ビジネスユニット |
   | 顧客カテゴリ |

1. のソース接続データフローを作成 **レポートスイート A**，選択 **統合スキーマ** をデータフローで使用します。 次のように、カスタムマッピングをデータフローに追加します。

   | レポートスイート A のソースフィールド | 統合フィールドフィールドグループの宛先フィールド |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >宛先フィールドの XDM パスは、カスタムフィールドグループの構造によって異なります。

1. のソース接続データフローを作成 **レポートスイート B**、再選択 **統合スキーマ** をデータフローで使用します。 ワークフローには、2 つのフィールドに記述子名の競合があることが示されます。 これは、eVar1 とeVar2 の記述子がレポートスイート B ではレポートスイート A では記述子と異なるためです。しかし、既にこれを把握しているので、競合を無視して、次のようにカスタムマッピングを使用できます。

   | レポートスイート B のソースフィールド | 統合フィールドフィールドグループの宛先フィールド |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. 次に、 **すべてのレポートスイート** CJA の接続。データセット A とデータセット B を組み合わせます。

1. の作成 **グローバル表示** CJA でのデータ表示。 元のeVarフィールドを無視し、[ 統合フィールド ] フィールドグループのフィールドのみを含めます。

   **グローバル表示** CJA でのデータビュー：

   | ソースフィールド | データビューに含めますか？ |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | × |
   | \_experience.analytics.customDimensions.eVars.eVar2 | × |
   | _\&lt;path>_.Search_term | ○ |
   | _\&lt;path>_.Customer_category  | ○ |
   | _\&lt;path>_.Business_unit | ○ |

ソースレポートスイートのeVar1 とeVar2 を 3 つの新しいフィールドにマッピングしました。 Data Prep マッピングを使用するもう 1 つの利点は、宛先フィールドが、意味のあるeVar名 (eVar1、eVar2) ではなく、意味的に意味のある名前（検索語、ビジネスユニット、顧客カテゴリ）に基づいていることです。

>[!NOTE]
>
>統合フィールドのカスタムフィールドグループと関連するフィールドマッピングは、いつでも既存の Analytics Source Connector のデータフローおよびデータセットに追加できます。 ただし、これは将来のデータにのみ影響します。

## 単なるレポートスイート以外

Data Prep でデータセットを様々なスキーマと組み合わせる機能は、Analytics レポートスイートに加えて、様々なスキーマを利用できます。 次のデータを含む 2 つのデータセットがあるとします。

| データセット A = Analytics ソースコネクタを使用した Analytics レポートスイート |
| --- |
| `eVar1` => 顧客カテゴリ |

| データセット B =コールセンターデータ |
| --- |
| Some_field => 顧客カテゴリ |

Data Prep を使用すると、AnalyticseVarのデータ 1 の顧客カテゴリと、コールセンターデータの Some_field の顧客カテゴリを組み合わせることができます。 一つの方法があります この場合も、命名規則を必要に応じて変更できます。

1. AEP でスキーマを作成します。 スキーマに以下を追加します。

   | &quot;拡張スキーマ&quot; |
   | --- | 
   | **XDM エクスペリエンスイベント** クラス |
   | **Adobe Analytics Experience Event テンプレート** フィールドグループ |

1. 新しいフィールドグループを作成し、スキーマに追加します。 フィールドグループにフィールドを追加します。

   | 「顧客情報」カスタムフィールドグループ  |
   | --- |
   | Customer_category |

1. のデータフローの作成 **データセット A**，選択 **拡張スキーマ** をスキーマとして使用します。 次のように、カスタムマッピングをデータフローに追加します。

   | データセット A ソースフィールド | 顧客情報フィールドグループの宛先フィールド |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. のデータフローの作成 **データセット B**、再選択 **拡張スキーマ** をスキーマとして使用します。 次のように、カスタムマッピングをデータフローに追加します。

   | データセット B ソースフィールド | 顧客情報フィールドグループの宛先フィールド |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. データセット A とデータセット B を組み合わせた CJA 接続を作成します。

1. 先ほど作成した CJA 接続を使用して、CJA でデータビューを作成します。 元のeVarフィールドを無視し、「 Customer Info 」フィールドグループのフィールドのみを含めます。

   CJA でのデータビュー：

   | ソースフィールド | データビューに含めますか？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | × |
   | \_experience.analytics.customDimensions.eVars.eVar2 | × |
   | _\&lt;path>_.Customer_category | ○ |

## データ準備とコンポーネント ID

前述のように、Data Prep では、複数のAdobe Analyticsレポートスイートをまたいで異なるフィールドをマッピングできます。 CJA は、複数のデータセットのデータを 1 つの CJA 接続に組み合わせる場合に役立ちます。 ただし、レポートスイートを別々の CJA 接続に保持する場合で、これらの接続とデータビューで 1 組のレポートを使用する場合、CJA の基になるコンポーネント ID を変更すると、スキーマが異なってもレポートに互換性を持たせることができます。 詳しくは、 [コンポーネント設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) を参照してください。

コンポーネント ID の変更は CJA のみの機能で、リアルタイム顧客プロファイルおよび RTCDP に送信される Analytics ソースコネクタからのデータには影響しません。
