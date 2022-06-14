---
source-git-commit: 59bb2c89c964f5b843897c40c38b11ada46f990a
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---
# 異なるスキーマを持つレポートルートの組み合わせ

## 概要

この [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) は、レポートスイートデータをAdobe AnalyticsからAdobe Experience Platformに取り込み、RTCDP や CJA などの AEP アプリケーションで使用する方法を提供します。 AEP に取り込まれる各レポートスイートは、個々のソース接続データフローとして設定され、各データフローは AEP データレイク内のデータセットとして配置されます。 （Analytics ソースコネクタは、レポートスイートごとに 1 つのデータセットを作成します）。

CJA のお客様が使用する [接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja) を使用して、AEP データレイクのデータセットを CJA のAnalysis Workspaceに統合します。 *ただし、1 つの接続内でレポートスイートを組み合わせる場合は、AEP の [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) 機能を使用して、prop や eVar などのAdobe Analytics変数が CJA で一貫した意味を持つようにします。*

## レポートスイート間のスキーマの違いに対する問題

CJA で使用するために 2 つの異なるレポートスイートのデータを AEP に取り込み、2 つのレポートスイートのスキーマに違いがあるとします。

| レポートスイート A | レポートスイート B |
| --- | --- |
| eVar1 => 検索語 | eVar1 => ビジネスユニット |
| eVar2 => 顧客カテゴリ | eVar2 => 検索語 |

簡単にするために、両方のレポートスイートに対して定義された eVar はこれらのみであると言います。

さらに、次の操作を実行するとします。

- 取り込む Analytics ソース接続の作成（データ準備を使用しない） **レポートスイート A** をとして AEP データレイクに追加します。 **データセット A**.
- 取り込む Analytics ソース接続の作成（データ準備を使用しない） **レポートスイート B** をとして AEP データレイクに追加します。 **データセット B**.
- という名前の CJA 接続を作成します。 **すべてのレポートスイート** データセット A とデータセット B を組み合わせた
- と呼ばれる CJA データビューを作成します。 **グローバル表示** すべてのレポートスイート接続に基づいている

データセット A とデータセット B のスキーマの違いを解決するために Data Prep を使用しない場合、グローバルビューのデータビューの eVar には次の値が混在します。

| CJA でのグローバルビューのデータビュー |
| --- |
| eVar1 => 検索用語とビジネスユニットの組み合わせ |
| eVar2 => 顧客カテゴリと検索語句の組み合わせ |

この状況では、eVar1 とeVar2 の無意味なレポートが生じます。

- eVarフィールドには、異なる意味を持つ値が混在して含まれます。
- 検索語句は、eVar1 とeVar2 の間に分散されます。
- 検索用語、ビジネスユニット、顧客カテゴリごとに異なるアトリビューションモデルを使用することはできません。

## AEP Data Prep を使用して、CJA で使用するためのレポートスイート間のスキーマの違いを解決する

AEP の Data Prep 機能は、Analytics Source Connector と統合され、上記のシナリオで説明したスキーマの違いの解決に使用できるので、CJA データビューで一貫した意味を持つ eVar が作成されます。 次に、これがどのように実行されるかを説明します。 以下に使用する命名規則は、ニーズに合わせてカスタマイズできます。

レポートスイート A とレポートスイート B のソース接続データフローを作成する前に、AEP でカスタムフィールドグループを作成します（これはと呼びます）。 **統合フィールド** （この例では）、次のフィールドが含まれています。

| 「統合フィールド」カスタムフィールドグループ  |
| --- |
| 検索語句 |
| ビジネスユニット |
| 顧客カテゴリ |

AEP で新しいスキーマを作成します（と呼びます）。 **統合スキーマ** （この例では）。 スキーマに次のフィールドグループを追加します。

| 「統合スキーマ」のフィールドグループ |
| --- |
| XDM エクスペリエンスイベント |
| Adobe Analytics Experience Event テンプレート |
| 統合フィールド |

のソース接続データフローを作成する場合 **レポートスイート A**&#x200B;を選択します。 **統合スキーマ** をデータフローで使用します。 次のように、カスタムマッピングを追加します。

| レポートスイート A のソースフィールド | 統合フィールドフィールドグループの宛先フィールド |
| --- | --- |
| \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
| \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

注意：宛先フィールドの XDM パスは、カスタムフィールドグループの設定方法に応じて異なります。

のソース接続データフローを作成する場合 **レポートスイート B**&#x200B;を再度選択します。 **統合スキーマ** をデータフローで使用します。 ワークフローには、2 つのフィールドに記述子名の競合があることが示されます。 これは、eVar1 とeVar2 の記述子がレポートスイート B ではレポートスイート A では記述子と異なるためです。しかし、既にこれを把握しているので、競合を安全に無視し、次のようにカスタムマッピングを使用できます。

| レポートスイート B のソースフィールド | 統合フィールドフィールドグループの宛先フィールド |
|---|---|
| \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
| _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

次に、 **すべてのレポートスイート** CJA の接続。データセット A とデータセット B を組み合わせます。

の作成 **グローバル表示** CJA でのデータ表示。 元のeVarフィールドを無視し、[ 統合フィールド ] フィールドグループのフィールドのみを含めます。

CJA でのグローバルビューのデータビュー：

| ソースフィールド | データビューに含めますか？ |
| --- | --- | 
| \_experience.analytics.customDimensions.eVars.eVar1 | × |
| \_experience.analytics.customDimensions.eVars.eVar2 | × |
| _\&lt;path>_.Search_term | ○ |
| _\&lt;path>_.Customer_category  | ○ |
| _\&lt;path>_.Business_unit | ○ |

基本的に、ソースレポートスイートから 3 つの新しいフィールドにeVar1 とeVar2 をマッピングしました。 Data Prep マッピングを使用するもう 1 つの利点は、宛先フィールドが、意味のあるeVar名 (eVar1、eVar2) ではなく、意味的に意味のある名前（検索語、ビジネスユニット、顧客カテゴリ）に基づいていることです。

注意：統合フィールドのカスタムフィールドグループと関連するフィールドマッピングは、いつでも既存の Analytics Source Connector のデータフローおよびデータセットに追加できますが、これは将来のデータにのみ影響します。

## 単なるレポートスイート以外

Data Prep でデータセットを様々なスキーマと組み合わせる機能は、Analytics レポートスイートに加えて、様々なスキーマを利用できます。 次のデータを含む 2 つのデータセットがあるとします。

| データセット A = Analytics ソースコネクタを使用した Analytics レポートスイート |
| --- |
| eVar1 => 顧客カテゴリ |

| データセット B =コールセンターデータ |
| --- |
| Some_field => 顧客カテゴリ |

Data Prep を使用すると、AnalyticseVarのデータ 1 の顧客カテゴリと、コールセンターデータの Some_field の顧客カテゴリを組み合わせることができます。 一つの方法があります この場合も、命名規則を必要に応じて変更できます。

カスタムフィールドグループの作成：

| 「顧客情報」カスタムフィールドグループ  |
| --- |
| Customer_category |

AEP でスキーマを作成します。 スキーマに次のフィールドグループを追加します。

| 「拡張スキーマ」のフィールドグループ |
| --- | 
| XDM エクスペリエンスイベント |
| Adobe Analytics Experience Event テンプレート |
| 顧客情報 |

のデータフローを作成する場合 **データセット A**&#x200B;を選択します。 **拡張スキーマ** をスキーマとして使用します。 次のように、カスタムマッピングを追加します。

| データセット A ソースフィールド | 顧客情報フィールドグループの宛先フィールド |
| --- | --- |
| \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

のデータフローを作成する場合 **データセット B**&#x200B;を再度選択します。 **拡張スキーマ** をスキーマとして使用します。 次のように、カスタムマッピングを追加します。

| データセット B ソースフィールド | 顧客情報フィールドグループの宛先フィールド |
| --- | --- |
| _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

データセット A とデータセット B を組み合わせた CJA 接続を作成します。先ほど作成した CJA 接続を使用して、CJA でデータビューを作成します。 元のeVarフィールドを無視し、「 Customer Info 」フィールドグループのフィールドのみを含めます。

CJA でのデータビュー：

| ソースフィールド | データビューに含めますか？ |
|---|---|
| \_experience.analytics.customDimensions.eVars.eVar1 | × |
| \_experience.analytics.customDimensions.eVars.eVar2 | × |
| _\&lt;path>_.Customer_category | ○ |

## データ準備とコンポーネント ID

前述のように、Data Prep では、複数のAdobe Analyticsレポートスイートをまたいで異なるフィールドをマッピングできます。 CJA は、複数のデータセットのデータを 1 つの CJA 接続に組み合わせる場合に役立ちます。 ただし、レポートスイートを別々の CJA 接続に保持する場合で、これらの接続とデータビューで 1 組のレポートを使用する場合、CJA の基になるコンポーネント ID を変更すると、スキーマが異なってもレポートに互換性を持たせることができます。 詳しくは、 [コンポーネント設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) を参照してください。

コンポーネント ID の変更は CJA のみの機能で、統合プロファイルおよび RTCDP に送信される Analytics ソースコネクタからのデータには影響しません。
