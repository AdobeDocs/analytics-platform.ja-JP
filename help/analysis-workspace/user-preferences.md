---
title: Analysis Workspace でのユーザー環境設定の設定方法
description: ユーザー向けに一般環境設定とプロジェクト環境設定を設定できます。
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: de0b51096c772ceb180e759b2dd992e3cf2a009d
workflow-type: tm+mt
source-wordcount: '3947'
ht-degree: 73%

---

# ユーザー環境設定

作成するすべての新規プロジェクトまたはパネルについて、Analysis Workspace および関連コンポーネントのユーザー設定や環境設定を管理できます。既存のプロジェクトやパネルは影響を受けません。

## 環境設定を更新

環境設定は次の方法で更新できます。

- Workspace のメインインターフェイスから「![UserAdmin](/help/assets/icons/UserAdmin.svg)」、「**[!UICONTROL 環境設定を編集]**」を選択します。
- Workspace プロジェクトでの作業時に、メニューから&#x200B;**[!UICONTROL プロジェクト]**／**[!UICONTROL ユーザー環境設定]**&#x200B;を選択します。
- Customer Journey Analyticsの上部メニューバーから **[!UICONTROL コンポーネント]**/**[!UICONTROL 環境設定]** を選択します（製品管理者のみが使用できます）。

## 環境設定の設定

次の環境設定を行うことができます。

### 一般環境設定

一般環境設定は、ブラウザーの Customer Journey Analytics エクスペリエンスに適用されます。これらの環境設定へのアクセス方法について詳しくは、[環境設定の更新](#update-preferences)を参照してください。

| 環境設定 | オプション |
| --- | --- |
| **[!UICONTROL ランディングページ]** | Customer Journey Analytics にアクセスしたときにデフォルトのページとして表示するページを選択します。 <ul><li>プロジェクトリスト（デフォルト）</li><li>空のプロジェクト</li><li>空のトレンドのガイド付き分析</li><li>リストから選択された特定のプロジェクト</li></ul> |
| **[!UICONTROL ヒント]** | Analysis Workspace の右下にある青いボックスにヒントを表示します。 <p>このオプションは、デフォルトでは有効になっています。</p> |
| **[!UICONTROL 左パネルグループに表示されるコンポーネント]** | 左パネルのコンポーネントメニューに表示する各コンポーネントグループの数を選択します。 <p>コンポーネントグループに 0 を選択すると、左パネルからコンポーネントグループにアクセスできなくなります。</p><p>デフォルトでは、次の各コンポーネントグループに対して 5 つのコンポーネントが表示されます。</p> <ul><li>ディメンション</li><li>指標</li><li>セグメント</li><li>日付範囲</li></ul> <p>Analysis Workspace のコンポーネントについて詳しくは、[コンポーネントの概要](/help/components/overview.md)を参照してください。</p> |

### IMS 組織の環境設定 {#ims-organization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Workspace ユーザーとのみ共有を許可"
>abstract="有効にすると、ユーザーは Analysis Workspace プロジェクトを共有する際に、「**[!UICONTROL 任意のユーザーと共有]**」オプションを使用できなくなります。以前にこの共有オプションを通じてプロジェクトへのアクセス権を取得したユーザーは、プロジェクトにアクセスできなくなります。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Experience Cloud 認証を要求"
>abstract="有効にすると、Analysis Workspaceの「**[!UICONTROL 任意のユーザーと共有]** オプションからプロジェクトへのアクセス権を付与されたユーザーは、Experience Cloud資格情報を使用して認証する必要があります。"

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="プロジェクトへのコメントを許可"
>abstract="有効になっている場合、Analysis Workspaceの各プロジェクトの右側のパネルにコメント領域が表示されます。"

<!-- markdownlint-enable MD034 -->

組織内のすべてのユーザーとプロジェクトに適用される会社環境設定を更新できます。これらの環境設定へのアクセス方法について詳しくは、[環境設定の更新](#update-preferences)を参照してください。

| セクション | 環境設定 | オプション |
| --- | --- | --- |
| **プロジェクトの共有** | | |
| | Workspace ユーザーとのみ共有を許可 | このオプションを有効にすると、組織内のユーザーには&#x200B;**[!UICONTROL 共有]**&#x200B;メニューの「**[!UICONTROL 任意のユーザーと共有]**」オプションが表示されなくなります。つまり、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)の[任意のユーザーとのプロジェクトの共有（ログイン不要）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)で説明するように、ユーザーは組織内に Analysis Workspace アカウントがない人物とプロジェクトを共有できません。<br/>このオプションは、Healthcare Shield のライセンスを取得した顧客を除くすべての組織（つまり、ユーザーが組織外のユーザーとプロジェクトを共有できる）に対して、デフォルトで無効になっています。 <p>このオプションを有効または無効にする際は、次の点を考慮してください。<ul><li>このオプションを有効にすると、以前に「[!UICONTROL 任意のユーザーと共有]」の共有オプションを通じてプロジェクトへのアクセス権を取得したユーザーは、そのプロジェクトにアクセスできなくなります。</li><li>このオプションを有効（Workspace ユーザーとのみ共有を許可）にし、後で無効（任意のユーザーと共有を許可）にする場合、以前に「[!UICONTROL 任意のユーザーと共有]」の共有オプションを通じてプロジェクトへのアクセス権を取得した人物に対するそのプロジェクトへのアクセス権は自動的に回復しません。この場合、プロジェクトを共有するユーザーは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)の[任意のユーザーとプロジェクトを共有（ログイン不要）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)で説明するように、任意のユーザーとプロジェクトを共有する際に使用できる&#x200B;**「[!UICONTROL **&#x200B;リンクがアクティブです&#x200B;**]」オプションを有効にする必要があります（[!UICONTROL 共有]**／**[!UICONTROL 任意のユーザーと共有]**）。</li><li>**Healthcare Shield のライセンスを取得した顧客の場合**：このオプションはデフォルトで有効になっており、無効にできません。このオプションを無効にして、ユーザーが「[!UICONTROL 任意のユーザーと共有]」の共有オプションを使用できるようにするには、まず Adobe Admin Console で[!UICONTROL 任意のユーザーとプロジェクトリンクを共有]権限（[!UICONTROL レポートツール]の下にある）を追加する必要があります。権限が追加されたら、このオプションを無効にして、結果として生じる法的通知を受け入れることができます。Admin Console で権限を追加する方法について詳しくは、[Admin Console での製品権限の管理](https://helpx.adobe.com/jp/enterprise/using/manage-permissions-and-roles.html)を参照してください。</li></ul> |
| | Experience Cloud 認証を要求 | このオプションが有効な場合、Analysis Workspaceの「任意のユーザーと共有」オプションからプロジェクトへのアクセス権を付与されたユーザーは、Experience Cloud資格情報を使用して認証する必要があります。<p>このオプションを有効にすると、ユーザーが「[!UICONTROL 任意のユーザーと共有]」の共有オプションを使用してプロジェクトを共有するたびに、共有ダイアログで「[!UICONTROL Experience Cloud 認証を要求]」オプションが有効になり、プロジェクトを共有しているユーザーはこのオプションを無効にすることはできません。ユーザーがプロジェクトを任意のユーザーと共有できる方法について詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)の[任意のユーザーとプロジェクトを共有（ログイン不要）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)を参照してください。 <p> <p>このオプションを有効にする際は、次の点を考慮してください。 <ul><li>このオプションを有効にすると、以前に「[!UICONTROL 任意のユーザーと共有]」の共有オプションで共有され、「[!UICONTROL Experience Cloud 認証を要求]」オプションが有効になっていないすべてのプロジェクトが非アクティブ化されます。<p>このオプションを有効（Experience Cloud 認証を要求）にし、後で無効（プロジェクトにアクセスするリンクを持つすべてのユーザーを許可）にすると、以前に「[!UICONTROL 任意のユーザーと共有]」の共有オプションを通じてプロジェクトへのアクセス権を取得したユーザーに対して、そのプロジェクトへのアクセス権は自動的に回復しません。この場合、プロジェクトを共有するユーザーは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)の[任意のユーザーとプロジェクトを共有（ログイン不要）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)で説明するように、任意のユーザーとプロジェクトを共有する際に使用できる&#x200B;**「[!UICONTROL リンクがアクティブです]」*オプションを有効にする必要があります（[!UICONTROL 共有]**／**[!UICONTROL 任意のユーザーと共有]**／**[!UICONTROL リンクがアクティブです]**）。</li><li>このオプションは、組織に SSO が実装されている場合にのみ使用できます。システム管理者が組織の SSO を有効にする方法について詳しくは、[ID とシングルサインオンの設定](https://helpx.adobe.com/jp/enterprise/using/set-up-identity.html)を参照してください。</p><p>組織に SSO が設定されている場合は、任意の種類の自動アカウント作成がコンソールに実装されているかどうかを確認します。通常、[アカウントの自動作成の有効化](https://helpx.adobe.com/jp/enterprise/using/automatic-account-creation.html)で説明するように、システム管理者がこの設定を行います。</li><li>組織が Healthcare Shield のライセンスを取得している場合、このオプションはデフォルトで有効になっており、無効にすることはできません。</li></ul> |

{style="table-layout:auto"}

<!-- 

Add this to the table above - exchange - for pipe: (End of April, 2025 when project commenting is GA)

**Project commenting** 
- - Allow commenting on projects - When this option is enabled, a comments area is available in the right rail of each project in Analysis Workspace. <p>Project owners can disable the comments area for a given project, as described in [Create projects](/help/analysis-workspace/build-workspace-project/create-projects.md).</p> <p>For more information about commenting in Analysis Workspace projects, see [Add and manage comments in projects](/help/analysis-workspace/build-workspace-project/comment-projects.md).</p> 

-->

### プロジェクトと分析の環境設定 {#project-and-analysis-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="カテゴリ順パレット"
>abstract="Analysis Workspace およびガイド付き分析の多くのビジュアライゼーションに適用されます。各カラーは、個別のカテゴリ値を表します。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="分岐パレット"
>abstract="Analysis Workspace およびユーザーの増加率のガイド付き分析のコホートテーブルに適用されます。このパレットは、2 つの極値と中央のベースラインの数値的意味を保持します。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="順次パレット"
>abstract="頻度トレンド（積み重ね横棒グラフ）ガイド付き分析に適用されます。このパレットは、明から暗までの数値的意味を保持します。"

すべての新しい Analysis Workspace プロジェクト、新しい Analysis Workspace パネルおよび新しいガイド付き分析に対して、これらの環境設定をカスタマイズできます。これらの環境設定へのアクセス方法について詳しくは、[環境設定の更新](#update-preferences)を参照してください。

また、これらの同じ環境設定の一部は、Analysis Workspace の個々のプロジェクトに対してカスタマイズできます。詳しくは、[プロジェクトの概要](/help/analysis-workspace/build-workspace-project/freeform-overview.md)を参照してください。

| セクション | 環境設定 | オプション |
| --- | --- | --- |
| **表示** | | |
|  | [表示密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 左パネル、フリーフォームテーブル、コホートテーブルでの垂直方向のパディングを減らして、画面に表示するコンテンツの量を選択します。 <ul><li>コンパクト</li><li>快適</li><li>拡張（デフォルト）</li></ul> |
| | [カラーパレット](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Analysis Workspace とガイド付き分析で使用するビジュアライゼーションのカラーパレットを選択します。 <ul><li> カテゴリ順パレット：Analysis Workspace とガイド付き分析の多くのビジュアライゼーションに適用されます。各カラーは、個別のカテゴリ値を表します。アドビが提供するオプションから選択するか、コンマ区切りの 16 進値で定義されたカスタムパレットを入力します。</li><li> 分岐パレット：Analysis Workspace とユーザー成長ガイド付き分析のコホートテーブルに適用されます。このパレットは、2 つの極値と中央のベースラインによる数値の意味を保持します。<li> 順次パレット：頻度トレンド（積み重ね棒グラフ）のガイド付き分析に適用されます。このパレットは、明るいカラーから暗いカラーまでの数値の意味を保持します。</li></ul> |
| **データ** | | |
|  | [データビュー](/help/analysis-workspace/c-panels/panels.md#data-view) | テーブルとビジュアライゼーションがデータを導き出すデータを選択します。 <ul><li>最新（デフォルト）</li><li>リストから選択された特定のデータビュー</li></ul> |
|  | [カレンダー](/help/analysis-workspace/c-panels/panels.md#calendar) | 次のリストから選択します。 <ul><li>アドビが指定する範囲（デフォルトは今月）</li><li>「[!UICONTROL デフォルトでパネルカレンダーを基準とした日付範囲コンポーネントを作成]」を有効にすることができます。</li></ul> |
|  | [パネルタイプ](/help/analysis-workspace/c-panels/panels.md#panel-types) | <ul><li>フリーフォーム（デフォルト）</li><li>空白</li><li>クイックインサイト</li></ul> |
|  | インスタンスのカウント | 「[!UICONTROL 繰り返しインスタンスをカウント]」を有効にして、インスタンスがレポート内でカウントされるかどうかを指定します。例えば、有効にすると、同じページに対して複数の連続するページビューが複数のページビューとして扱われます。無効にすると、同じページに対する複数の連続するページビューが、単一のページビューとしてカウントされます。 <p>**メモ：**&#x200B;この設定は、特定の指標（セッションなど）にのみ影響し、フロービジュアライゼーションやフォールアウトビジュアライゼーションには適用されません。</p> |
|  | 数値の形式 | <ul><li>1,000.00（デフォルト）</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV 区切り文字 | <ul><li>コンマ（デフォルト）</li><li>セミコロン</li><li>コロン</li><li>パイプ</li><li>ピリオド</li><li>空白文字</li><li>タブ</li></ul> |
|  | 注釈を表示 | 注釈をプロジェクトに表示するかどうかを選択します。注釈について詳しくは、[注釈：概要](/help/components/annotations/overview.md)を参照してください。 |


### フリーフォームテーブルの環境設定 {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="異常値を表示"
>abstract="「**[!UICONTROL 異常を表示]**」を選択すると、時系列のフリーフォームテーブルビジュアライゼーションに追加された最初の指標列で、異常値検出が自動的に実行されるようになります。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="予測を表示"
>abstract="「**[!UICONTROL 予測を表示]**」を選択すると、時系列のフリーフォームテーブルビジュアライゼーションに追加された最初の指標列が、自動的に予測されるようになります。"


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="デフォルトのテーブル指標"
>abstract="フリーフォームテーブルに使用するデフォルトの指標を選択します。選択したデータビューに選択したデフォルトの指標が含まれていない場合、テーブルは自動的に別のプライマリ指標に切り替わります。"


Analysis Workspace で作成するすべての新しいプロジェクトについて、フリーフォームテーブルの環境設定をカスタマイズできます。これらの環境設定へのアクセス方法について詳しくは、[環境設定の更新](#update-preferences)を参照してください。

これらの同じ環境設定の一部を、個々のテーブル用にカスタマイズすることもできます。

使用可能な環境設定の詳細とコンテキストについては、リンクされた節のタイトルを選択してください。

| セクション | 環境設定 | オプション |
| --- | --- | --- |
| **テーブル** | | |
| | テーブルタイプ | <ul><li>フリーフォーム</li><li>テーブルビルダー</li></ul> |
| | デフォルトのテーブル指標 | <ul><li>発生件数</li><li>ユニーク訪問者</li><li>訪問回数</li></ul> |
| | デフォルトのテーブルディメンション | 分、時間、日、週、月、四半期、年から選択します。 |
| | 日付の整列 | このオプションを選択して各列の日付を整列させ、すべて同じ行から始まるようにすることもできます。 |
| **[列](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | ヘッダーテキストを折り返し | ヘッダーを読みやすく、またテーブルを共有しやすくするため、フリーフォームテーブルでヘッダーテキストを折り返せるようにします。これは、.pdf のレンダリングや名前の長い指標に使用すると便利です。デフォルトで有効です。 |
| | 合計を表示 | この合計数は、通常、[!UICONTROL  総計 ] と等しいか、またはそのサブセットです。 「[!UICONTROL  なしを含む ] オプションなど、フリーフォームテーブル内で適用されたすべてのテーブルセグメントが反映されます。 |
| | 総計の表示 | この合計数は、収集されたすべてのイベントを表し、*データビューの合計* と呼ばれることもあります。 セグメントがパネルレベルまたはフリーフォームテーブル内で適用されると、この合計は、セグメントの条件に一致するすべてのイベントを反映するように調整されます。 [静的な行](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)を含むテーブルや分類では、総計はサポートされません。 |
| | スパークラインを表示 | グラフの下部に折れ線グラフを表示または非表示にします。非表示にすると、凡例が変更され、折れ線が表示されなくなります。 |
| | 数値 | セルに指標の数値を表示するかどうかを決定します。例えば、指標がページビュー数の場合、数値は行項目のページ表示回数になります。 |
| | パーセント | セルに指標の割合の値を表示するかどうかを決定します。例えば、指標がページビュー数の場合、割合の値は行項目のページビュー数を列の合計ページビュー数で割った数になります。  メモ：より正確な数値を示すために、100% を超える割合を表示することができます。 また、上限を 1,000% に移動して、列の幅が大きくなりすぎないようにすることもできます。 |
| | 異常値を表示 <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | この列の値に対して異常値検出を実行するかどうかを決定します。 |
| | 予測を表示 | 作成する時系列フリーフォームテーブルの最初の指標列に、予測値を自動的に表示するかどうかを指定します。 |
| | ゼロを値なしとして解釈 | 値が 0 のセルについて、0 を表示するか空白にするかを決定します。この設定は、まだ終わっていない月の日ごとのデータを確認する際に便利です。将来の日付のセルに 0 を表示するのではなく、空にすることができます。グラフもこの設定に従います（例えば、この設定をオンにすると、買い物かごに値 0 の線や棒が表示されません）。 |
| | 背景 | セルのすべての書式（棒グラフや条件付き書式など）をセルに表示するかどうかを決定します <ul><li>棒グラフ</li> 列の合計を最大値としてセルの値を示す横棒グラフを表示します。 <li>条件付き書式</li>条件付き書式について詳しくは、[列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)の「条件付き書式」を参照してください。</ul> |
| | セルのプレビュー | 現在選択されている書式オプションが適用されると各セルがどのように表示されるかを示すプレビューが表示されます。 |
| **[行](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | 位置で分類 | 項目自体ではなく項目の位置に分類を保持する場合は、このオプションを選択します。分類について詳しくは、[ディメンションの分類](/help/components/dimensions/t-breakdown-fa.md)を参照してください。 |
| | パーセンテージ計算 | <ul><li>列</li><li>行</li></ul> |
| | 列の合計（静的行のみ） | <ul><li>行の合計を表示：個々の行項目の合計を表示します </li><li>総計を表示：重複を排除した行の合計を表示します。</li></ul> |

### ビジュアライゼーションの環境設定 {#visalization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultflowcontainer"
>title="デフォルトのコンテナ"
>abstract="[!UICONTROL フロー]ビジュアライゼーションに使用するデフォルトのコンテナを選択します。選択したデータビューに選択したデフォルトコンテナが含まれていない場合、[!UICONTROL  フロー ] ビジュアライゼーションは自動的に別のプライマリコンテナに切り替わります。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultfalloutcontainer"
>title="デフォルトのコンテナ"
>abstract="[!UICONTROL フォールアウト]ビジュアライゼーションに使用するデフォルトのコンテナを選択します。選択したデータビューに選択したデフォルトコンテナが含まれていない場合、[!UICONTROL  フォールアウト ] ビジュアライゼーションは自動的に別のプライマリコンテナに切り替わります。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulthistogramcountingmethod"
>title="デフォルトのカウント方法"
>abstract="[!UICONTROL ヒストグラム]ビジュアライゼーションに使用するデフォルトのカウント方法を選択します。選択したデータビューに選択したデフォルトのカウント方法が含まれていない場合、[!UICONTROL  ヒストグラム ] ビジュアライゼーションは別のプライマリアカウント方法に自動的に切り替わります。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultjourneycanvascontainer"
>title="デフォルトのコンテナ"
>abstract="[!UICONTROL ジャーニーキャンバス]ビジュアライゼーションに使用するデフォルトのコンテナを選択します。選択したデータビューに選択したデフォルトコンテナが含まれていない場合、[!UICONTROL  プライマリキャンバス ] ビジュアライゼーションは別のジャーニーコンテナに自動的に切り替わります。"


Analysis Workspace で作成するすべての新しいプロジェクトについて、ビジュアライゼーション環境設定を更新できます。これらの環境設定へのアクセス方法について詳しくは、[環境設定の更新](#update-preferences)を参照してください。

これらの同じ環境設定の一部は、個々のビジュアライゼーション用にカスタマイズすることもできます。

使用可能な環境設定の詳細とコンテキストについては、リンクされた節のタイトルを選択してください。

| セクション | 環境設定 | オプション |
| --- | --- | --- |
| **一般的なデフォルト** | | |
| | 割合 | すべてのビジュアライゼーションの値をパーセンテージで表示します。 |
| | 凡例を表示 | すべてのビジュアライゼーションで詳細な凡例テキストを非表示にできます。 |
| | 項目数の上限を設定 | すべてのビジュアライゼーションで X 軸の項目数を減らします。この環境設定は、大きなデータセットがある場合に役立ちます。 |
| | 2 軸を表示（該当する場合） | 2 つの指標がある場合にのみ適用されます。（ある指標の）Y 軸を左側に、（他の指標の）Y 軸を右側に表示できます。この環境設定は、プロットされた指標のスケールが大きく異なる場合に役立ちます。 |
| | 正規化（該当する場合） | 指標を均等な比率にします。この環境設定は、プロットされた指標のスケールが大きく異なる場合に役立ちます。 |
| | Y 軸をゼロに固定 | グラフにプロットされるすべての値がゼロを大幅に上回る場合、グラフのデフォルトは Y 軸の一番下をゼロ以外に更新します。 このチェックボックスをオンにすると、Y 軸が強制的にゼロになります（グラフが再描画されます）。 |
| | 異常値で Y 軸のスケールの設定を固定 | Y 軸は、異常値を使用してスケーリングされます。 |
| **[行](/help/analysis-workspace/visualizations/line.md)** | | |
| | 割合 | 折れ線グラフビジュアライゼーションの値をパーセンテージで表示します。 |
| | 凡例を表示 | 折れ線グラフビジュアライゼーションの詳細な凡例テキストを非表示にできます。 |
| | 項目数の上限を設定 | 折れ線グラフのビジュアライゼーションの X 軸の項目数を減らします。この環境設定は、大きなデータセットがある場合に役立ちます。 |
| | 2 軸を表示（該当する場合） | 2 つの指標がある場合にのみ適用されます。（ある指標の）Y 軸を左側に、（他の指標の）Y 軸を右側に表示できます。この環境設定は、プロットされた指標のスケールが大きく異なる場合に役立ちます。 |
| | 正規化（該当する場合） | 指標を均等な比率にします。この環境設定は、プロットされた指標のスケールが大きく異なる場合に役立ちます。 |
| | X 軸を表示 | 折れ線グラフに X 軸を表示します。 |
| | Y 軸を表示 | 折れ線グラフに Y 軸を表示します。 |
| | Y 軸を固定 | グラフにプロットされるすべての値がゼロを大幅に上回る場合、グラフのデフォルトでは、Y 軸の一番下がゼロ以外になります。 このチェックボックスをオンにすると、Y 軸が強制的にゼロになります（グラフが再描画されます）。 |
| | 異常値で Y 軸のスケールの設定を許可 | グラフに複数の指標がある場合、各異常値の上にマウスポインターを置いて、その指標の信頼帯を表示する必要があります。ビジュアライゼーションを見やすくするために、異常値検出の信頼区間では、Y 軸は自動的に拡大・縮小されません。この設定を使用すると、信頼区間でビジュアライゼーションを拡大・縮小できます。 <p>詳しくは、[Analysis Workspace での異常値の表示](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md)を参照してください。</p> |
| | 予測で Y 軸のスケールの設定を許可 | 履歴値の上限および下限を超える予測値がある場合、y 軸はこれらの予測値を自動的にスケールしません。 このオプションをオンにすると、予測値の Y 軸が適切にスケールされます。 |
| | 最小値を表示 | 最小値のラベルをオーバーレイして、指標内の谷をすばやく強調表示します。 メモ：最小値は、ディメンション内のすべての値ではなく、ビジュアライゼーション内に表示されたデータポイントから得られます。 |
| | 最大値を表示 | 最大値のラベルをオーバーレイして、指標のピークをすばやく強調表示します。 メモ：最大値は、ディメンション内のすべての値ではなく、ビジュアライゼーション内に表示されたデータポイントから得られます。 |
| | 近似曲線を表示 | 回帰または移動平均の近似曲線を線系列に表示します。近似曲線は、データにより明確なパターンを表現するのに役立ちます。 |
| **[コホート](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>Container | アカウントベースの [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} 接続を使用している場合は、コホート分析用の優先コンテナを選択します。 <p>次のオプションがあります。</p> <ul><li>グローバル アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>購買グループ [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>商談 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>ユーザー</li></ul> |
| | 精度 | トレンドのビジュアライゼーションでは、このドロップダウンから時間の精度（日、週、月など）を。この変更は、データソーステーブルにも適用されます。 |
| | 割合のみを表示 | 数値を削除し、パーセンテージのみを表示します。 |
| | 割合を整数に四捨五入 | パーセント値を、小数値ではなく、最も近い整数に丸めます。 |
| | 割合の平均行を表示 | テーブルの先頭に新しい行を挿入し、各列の値の平均を加算します。 |
| **[コンビネーショングラフ](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | X 軸を表示 | 複合グラフに X 軸を表示します。 |
| | Y 軸を表示 | 複合グラフに Y 軸を表示します。 |
| | 行にバーベルを表示 | 複合グラフの線にバーベルを表示します。 |
| **[主要指標の概要](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | 概要表示タイプ | <ul><li>変化率を強調</li><li>数値を強調</li></ul> |
| | スパークラインを表示 | グラフの下部で折れ線グラフを表示または非表示にします。非表示にすると、凡例が変更され、折れ線が表示されなくなります。 |
| | スパークラインに最大値と最小値を表示 | プライマリ折れ線グラフと比較折れ線グラフの最小値と最大値を表示または非表示します。 |
| | 比較を表示 | 比較データを表示します。非表示の場合、比較折れ線グラフと変更概要オブジェクトの両方が非表示になります。 |
| | 数値オプション | [!UICONTROL **主要指標の概要**]&#x200B;セクション内 <ul><li>変化率を表示</li><li>生の差異を表示</li>プライマリ日付範囲とセカンダリ日付範囲で、指標の合計値の生の差異を表示または非表示</ul> |
| **[フォールアウト](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | コンテナ | パスを分析するコンテナを選択します。 優先コンテナは、様々な B2B コンテナレベル [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} でのアカウントエンゲージメント、ユーザーレベル（複数のセッションにわたる）でのユーザーエンゲージメント、または分析を 1 つのセッションに制限するのに役立ちます。 <p>次のオプションがあります。</p> <ul><li>グローバル アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>購買グループ [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>商談 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>セッション</li><li>ユーザー</li></ul> |
| **[フロー](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | コンテナ | 分析する優先コンテナを選択します。 優先コンテナは、様々な B2B コンテナレベル [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} でのアカウントエンゲージメント、ユーザーレベル（複数のセッションにわたる）でのユーザーエンゲージメント、または分析を 1 つのセッションに制限するのに役立ちます。 <p>次のオプションがあります。</p> <ul><li>グローバル アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>購買グループ [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>商談 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>セッション</li><li>ユーザー</li></ul> |
| | ラベルの折り返し | 通常、フロー要素のラベルは、画面の領域を節約するために切り捨てられます。しかし、このチェックボックスをオンにすることで完全なラベルを表示できます（デフォルト = オフ）。 |
| | 繰り返しインスタンスを含める | フロービジュアライゼーションは、ディメンションのインスタンスに基づいています。この設定により、ページのリロードなど、繰り返し発生するインスタンスを含めるか除外するかを選択できます。ただし、listVar、listProp、s.product、マーチャンダイジング eVar など複数の値を持つディメンションを含むフロービジュアライゼーションから、繰り返しを削除することはできません。（デフォルト = オフ）。 |
| | ツールチップを表示 | フロービジュアライゼーション内の個々のノードにカーソルを合わせたときに、ノードデータを含むツールチップを表示するかどうかを決定します。 |
| | 列の数 | フロー図で必要な列数を決定します。 |
| | 列ごとに展開される項目数 | 各列に必要な項目数。 |
| **[ジャーニーキャンバス](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)** | | |
| | コンテナ | パスを分析するコンテナを選択します。 優先コンテナは、様々な B2B コンテナレベル [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} でのアカウントエンゲージメント、ユーザーレベル（複数のセッションにわたる）でのユーザーエンゲージメント、または分析を 1 つのセッションに制限するのに役立ちます。 <p>次のオプションがあります。</p> <ul><li>グローバル アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>アカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>購買グループ [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>商談 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}</li><li>セッション</li><li>ユーザー</li></ul> |
| **積み重ねグラフ** | | |
| | 100% の積み重ね | 積み上げ面、積み上げ棒、または積み上げ横棒のビジュアライゼーションのこの設定は、グラフを「100 % の積み上げ」のビジュアライゼーションに変更します。 <p>詳しくは、[ 棒グラフおよび積み重ね棒グラフ ](/help/analysis-workspace/visualizations/bar.md) を参照してください。</p> |
| **[ヒストグラム](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | バケット数 | ビジュアライゼーション内の日付範囲（バケット）の数を選択します。グループの最大数は 50 です。 <p>詳しくは、[ヒストグラム](/help/analysis-workspace/visualizations/histogram.md)を参照してください。</p> |
| | カウント方法 | 次のオプションから選択します。 <ul><li>ヒット</li><li>セッション</li><li>ユーザー</li></ul> <p>例えば、ページビューと共に使用する場合、1 人あたりのページビュー、訪問のページビュー、またはイベントごとのページビューを選択できます。 ヒットの場合、フリーフォームテーブルの y 軸指標として、「回数」が使用されます。</p> |
| **[変更の概要](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 値 | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>パーセントの変更</li><li>生の差異</li></ul> |
| | 割合 | 変更の概要ビジュアライゼーションの値をパーセンテージで表示します。 |
| | 凡例を表示 | 変更の概要ビジュアライゼーションの詳細な凡例テキストを非表示にできます。 |
| **[数値の概要](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 割合 | 数値の概要ビジュアライゼーションの値をパーセンテージで表示します。 |
| | 凡例を表示 | 数値の概要ビジュアライゼーションの詳細な凡例テキストを非表示にできます。 |
| | 概要値の基準 | 「最大」、「最小」、「平均」、「中央値」、「合計」から選択します。 |
| | 値を短縮 | **[!UICONTROL 数値の概要]**&#x200B;セクション内 |
| **[ツリーマップ](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | 割合 | ツリーマップビジュアライゼーションの値をパーセンテージで表示します。 |
| | 項目数の上限を設定 | ツリーマップビジュアライゼーションの X 軸の項目数を減らします。この環境設定は、大きなデータセットがある場合に役立ちます。 |
| **[ベン図](/help/analysis-workspace/visualizations/venn.md)** | | |
| | 凡例を表示 | ベン図ビジュアライゼーションの詳細な凡例テキストを非表示にできます。 |
| **[散布図](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | 割合 | 散布図のビジュアライゼーションの値をパーセンテージで表示します。 |
| | 凡例を表示 | 散布図ビジュアライゼーションの詳細な凡例テキストを非表示にできます。 |
| | 項目数の上限を設定 | 散布図ビジュアライゼーションの X 軸の項目数を減らします。  この環境設定は、大きなデータセットがある場合に役立ちます。 |
| | Y 軸をゼロに固定 | グラフにプロットされるすべての値がゼロを大幅に上回る場合、グラフのデフォルトでは、Y 軸の一番下がゼロ以外になります。 このチェックボックスをオンにすると、Y 軸が強制的にゼロになります（グラフが再描画されます）。 |

## デフォルトの環境設定を復元

すべてのユーザー設定をシステムのデフォルトに戻すことができます。この環境設定は、「会社」タブの管理者の環境設定には影響しません

このアクションは取り消しできません。

1. Customer Journey Analytics で、上部のメニューから&#x200B;[!UICONTROL **コンポーネント**]**／**[!UICONTROL **環境設定**]&#x200B;を選択します。または、Workspace メニューから&#x200B;**[!UICONTROL プロジェクト]**／**[!UICONTROL ユーザー設定]**&#x200B;を選択します。

1. 右上で、「**[!UICONTROL デフォルトに戻す]**」を選択します。

1. **[!UICONTROL システムのデフォルト設定を復元]** で **[!UICONTROL デフォルトに戻す]** を選択します。

## [!UICONTROL ダークテーマ]

Customer Journey Analytics ユーザーインターフェイスの背景を暗くする場合は、[!UICONTROL ダークテーマ]に切り替えることができます。

1. 右上の Experience Cloud ユーザーアイコンを選択します。

   ![ダークテーマ](assets/dark-theme.png)

1. **[!UICONTROL ダークテーマ]** を有効にします。

