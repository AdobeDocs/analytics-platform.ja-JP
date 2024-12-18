---
source-git-commit: a6f543d3b6aab06593d9fa40a5d3d6bbf4aa7c32
workflow-type: tm+mt
source-wordcount: '3977'
ht-degree: 32%

---
# スニペット

## リリース段階の限定的テスト {#release-limited-testing}

>[!AVAILABILITY]
>
>この記事で説明している機能は、リリースの限定的テスト段階にあり、お使いの環境ではまだ使用できない可能性があります。機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsリリースプロセスについて詳しくは、[Customer Journey Analytics機能リリース ](/help/release-notes/releases.md) を参照してください。

## 「リリース段階の限定的テスト」節 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>この節で説明している機能は、リリースの限定的テスト段階にあり、お使いの環境ではまだ使用できない可能性があります。機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsリリースプロセスについて詳しくは、[Customer Journey Analytics機能リリース ](/help/release-notes/releases.md) を参照してください。

## パッケージを選択 {#select-package}

>[!NOTE]
>
>この節で説明する機能を使用するには、**選択** パッケージまたはそれ以降のバージョンが必要です。 使用している Customer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。

## プライムパッケージ {#prime-package}

>[!NOTE]
>
>この節で説明している機能を使用するには、**Prime** パッケージまたはそれ以降のバージョンが必要です。 使用している Customer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。

## Ultimate パッケージ {#ultimate-package}

>[!NOTE]
>
>この節で説明する機能を使用するには、**Ultimate** パッケージが必要です。 使用している Customer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。


## データ要素のフィルター条件 {#dd-filter-criteria}

1. （オプション）**フィルター**&#x200B;アイコン ![データ要素のフィルターアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) を選択し、次のフィルターオプションのいずれかを選択して、コンポーネントのリストをフィルタリングします。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | [!UICONTROL **お気に入り**] | お気に入りのリストにあるコンポーネントのみを表示します。お気に入りのリストにコンポーネントを追加する方法については、[コンポーネントの概要](/help/components/overview.md)を参照してください。 |
   | [!UICONTROL **ディメンション**] | ディメンションであるコンポーネントのみを表示します（このオプションは、最初にデータ要素にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。 |
   | [!UICONTROL **指標**] | 指標であるコンポーネントのみを表示します（このオプションは、最初にデータ要素にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。 |
   | [!UICONTROL **フィルター**] | フィルターであるコンポーネントのみを表示します （このオプションは、最初にデータ要素にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。<!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **日付範囲**] | 日付範囲であるコンポーネントのみを表示します（このオプションは、最初にデータ要素にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。 |
   | [!UICONTROL **すべてを表示**] | すべてのコンポーネントの表示。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **未承認**] | 管理者が承認済みとしてまだマークしていないコンポーネントのみを表示します。レビューと承認が必要なコンポーネントを管理者が識別する際に役立ちます。このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **説明がありません**] | 「説明」フィールドにまだ説明がないコンポーネントのみを表示します。このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **重複の表示**] | 選択したデータビュー内の別のコンポーネントと同じ名前または同じ説明を持つコンポーネントのみを表示します。 これには、ユーザー作成のコンポーネントと、Adobe提供のコンポーネントが含まれます。 重複として表示するには、名前または説明が完全に一致している必要があります。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **最近のデータがありません**] | 過去 90 日間にデータを収集していないコンポーネントのみを表示します。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **作成者：Adobe**]<!-- I don't see this option--> | アドビが作成したコンポーネントのみを表示します。組織内の管理者または別のユーザーが作成したコンポーネントは表示しません。 |

   {style="table-layout:auto"}

## データ要素のコンポーネント情報 {#dd-component-information}

| オプション | 関数 |
|---------|----------|
| [!UICONTROL **承認済み**] | <p>コンポーネントが管理者にレビューおよび承認されたことを示します。</p><p>管理者には、「未承認 [!UICONTROL **のオプションが表示され**] す。 このオプションを選択すると、ユーザーに対してコンポーネントが「未承認」としてマークされます。</p> |
| [!UICONTROL **未承認**] | <p>コンポーネントがまだ管理者にレビューおよび承認されていないことを示します。</p><p>管理者には、「[!UICONTROL **承認**]」オプションが表示されます。このオプションを選択すると、ユーザーに対してコンポーネントが「承認済み」としてマークされます。</p> |
| [!UICONTROL **説明**] | コンポーネントの意図された機能について説明します（この情報は、[コンポーネントの説明の追加](/help/components/add-component-descriptions.md)で説明しているように、Analytics 管理者が追加します）。 |
| [!UICONTROL **次でよく使用される**] | <p>表示しているコンポーネントと最も一緒に使用されるコンポーネントを表示します。</p><p>指標、計算指標、Dimension、フィルターおよび日付範囲の 5 つの主要なコンポーネントタイプで最大 5 つのコンポーネントを表示します。</p><p>このリストは、過去 90 日間のデータに基づいています。表示するアクセス権を持つコンポーネントのみを表示します。</p><p>管理者は、「[!UICONTROL **常に含める**]」および「[!UICONTROL **常に除外**]」ドロップダウンフィールドで目的のコンポーネントを選択することにより、このセクションでユーザーに表示されるコンポーネントをキュレートできます。ユーザーに表示されるコンポーネントをキュレートする前に、最初に **すべて表示** フィルターを適用して、共有されていないコンポーネントのうち、別の管理者によって追加された可能性のあるものを表示します。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **類似**] | <p>表示しているコンポーネントと同様の名前を持つコンポーネントを表示します。</p><p>指標、計算指標、Dimension、フィルターおよび日付範囲の 5 つの主要なコンポーネントタイプで最大 5 つのコンポーネントを表示します。</p><p>表示するアクセス権を持つコンポーネントのみを表示します。</p><p>データビューで重複するコンポーネントはすべてここに表示されます。 [データ要素の正常性の監視](/help/components/data-dictionary/monitor-data-dictionary-health.md)で説明しているように、Analytics 管理者はすべての重複するコンポーネントを特定して削除する必要があります。</p><p>管理者は、「[!UICONTROL **常に含める**]」および「[!UICONTROL **常に除外**]」ドロップダウンフィールドで目的のコンポーネントを選択することにより、このセクションでユーザーに表示されるコンポーネントをキュレートできます。ユーザーに表示されるコンポーネントをキュレートする前に、最初に **すべて表示** フィルターを適用して、共有されていないコンポーネントのうち、別の管理者によって追加された可能性のあるものを表示します。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**メモ：**&#x200B;現在、「**類似**」セクションには、ユーザー作成のコンポーネントのみが含まれており、アドビ提供のコンポーネントは含まれていません。アドビ提供のコンポーネントは、今後のリリースで追加される予定です。</p> |
| [!UICONTROL **製品の互換性**] | この計算指標をCustomer Journey Analytics内で使用できる場所を示します。 <p>使用可能な値は次のとおりです。</p><ul><li>[!UICONTROL **Customer Journey Analytics内のすべての場所**]：計算指標は、Analysis WorkspaceやReport Builderなど、すべてのCustomer Journey Analyticsで使用できます。</li><li>[!UICONTROL **Customer Journey Analyticsのすべての場所（実験を除く）**]：計算指標は、実験パネルを除くすべてのCustomer Journey Analyticsで使用できます。</li> <p>計算指標が実験で使用できるかどうかを決定する条件について詳しくは、[ 実験パネル ](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) の [ 実験パネルで計算指標を使用 ](/help/analysis-workspace/c-panels/experimentation.md) を参照してください。</p></ul> |
| [!UICONTROL **タグ**] | コンポーネントに適用されているすべてのタグを表示します。管理者アクセス権を持つユーザーは、コンポーネントの編集時にタグを追加できます。 |
| [!UICONTROL **コンポーネントの種類**] | Dimension、指標、フィルター、または日付範囲のいずれかであるコンポーネントのタイプをリストします。 |
| [!UICONTROL **作成者**] | コンポーネントを作成したユーザーの名前を表示します。 |
| [!UICONTROL **プレビュー**] | Analysis Workspace でのコンポーネントの外観のプレビューを表示します。 |
| [!UICONTROL **最終変更日**] | コンポーネントの最終変更日を表示します。 このセクションは、フィルター、指標、計算指標および日付範囲を表示する際に表示されます。 |

{style="table-layout:auto"}

## コンポーネントの並べ替えオプション {#components-sort-options}

| オプション | 関数 |
|---------|----------|
| **[!UICONTROL 推奨]** | 推奨に基づいてタイプ（ディメンション、指標、フィルター、日付範囲）ごとにコンポーネントを並べ替えます。 自分や組織内の他のユーザーが最も頻繁に使用し、最近使用したコンポーネントが、各リストの上位に表示されます。 |
| **[!UICONTROL 最終変更日]** | 最終変更日に基づいて、タイプ（ディメンション、指標、フィルター、日付範囲）ごとにコンポーネントを並べ替えます。 最近変更されたコンポーネントは、各リストの上位に表示されます。 |
| **[!UICONTROL アルファベット順]** | 各タイプ（ディメンション、指標、フィルター、日付範囲）のコンポーネントをアルファベットの昇順で並べ替えます。 |
| **[!UICONTROL 分類]** | カテゴリに基づいてタイプ（ディメンション、指標、フィルター、日付範囲）ごとにコンポーネントを並べ替えます。 例えば、キュレートされたデータビューコンポーネントとキュレートされていないデータビューコンポーネントの比較です。 |

{style="table-layout:auto"}

## 時間比較 {#apply-time-comparison}

現在の期間と前の期間を比較できます。 このメニューでオプションを選択すると、すべてのデータポイントに同じような色の点線の対応物が表示されます。 この同等の指標は、選択した前の日付範囲の同じ指標を表します。 このオプションを設定すると、グラフの項目数とテーブルの行数が倍になります。

使用可能な時間比較オプションには、前期間、13 週間前、52 週間前およびカスタマイズされた日付範囲が含まれます。 「カスタマイズされた日付範囲」を選択すると、追加のオプションが表示され、数と精度を選択できます。 「なし」を選択すると、日付比較は削除されます。


## デモンストレーション用ビデオAdobe Analytics {#videoaa}

このビデオでは、Adobe Analyticsを使用した機能を説明します。 ただし、この機能はCustomer Journey Analyticsでも同様に使用できます。 用語には次の違いがあることに注意してください。

| Adobe Analytics | Customer Journey Analytics |
|:---:|:---:|
| セグメント | フィルター |
| 訪問者 | ユーザー |
| 訪問 | セッション |
| ヒット | イベント |


## フィルターパネル {#filterspanel}

1. ![ フィルター ](/help/assets/icons/Filter.svg) を選択して、フィルターパネルを開きます。 「フィルター」リストにスペースが必要な場合は、もう一度 ![ フィルター ](/help/assets/icons/Filter.svg) を選択してパネルを閉じることができます。
1. 使用可能ないずれかのフィルターセクションからフィルターを選択します。


## タグフィルターセクション {#tagfiltersection}

| タグ | 説明 |
|---|---|
| ![タグ](/help/assets/filter-tag.png){width="300"} | 「**[!UICONTROL タグ]**」セクションでは、タグに対してフィルターを適用できます。 <ul><li>![ 検索 ](/help/assets/icons/Search.svg)*タグを検索* して、フィルタリングに使用できるタグを検索できます。</li><li>複数のタグを選択できます。 使用できるタグは、フィルターパネルの他のセクションで選択した内容によって異なります。</li><li>数値は次の内容を示します。<ul><li>**（1）**：選択したタグの数（1 つ以上のタグが選択されている場合）。</li><li>**2︎⃣**：現在のフィルターによって生成された項目で使用できるタグの数。</li><li>7︎⃣：特定のタグに関連付けられている項目の数。</li></ul></li></ul> |


## データ表示フィルターセクション {#dataviewfiltersection}

| データビュー | 説明 |
|---|---|
| ![ データビュー ](/help/assets/filter-dataview.png){width="300"} | 「**[!UICONTROL データ表示]**」セクションでは、データ表示をフィルタリングできます。 <ul><li>![ 検索 ](/help/assets/icons/Search.svg)*データビューを検索* して、フィルタリングに使用できるデータビューを検索できます。</li><li>複数のデータビューを選択できます。 使用可能なデータビューは、フィルターパネルの他のセクションで選択した内容によって異なります。</li><li>数値は次の内容を示します。<ul><li>**（2）**：選択したデータビューの数（1 つ以上のデータビューが選択されている場合）。</li><li>**3︎⃣**：現在のフィルターによって生成されたアイテムで使用できるデータビューの数。</li><li>4︎⃣：特定のデータビューに関連付けられている項目の数。</li></ul></li></ul> |

## 有効化ステータスフィルターセクション {#enabledstatusfiltersection}

| 有効ステータス | 説明 |
|---|---|
| ![ 有効ステータス ](/help/assets/filter-enabledstatus.png){width="300"} | 「**[!UICONTROL 有効ステータス]**」セクションでは、有効ステータスをフィルタリングできます。 <ul><li>複数のステータスを選択できます。</li><li>数値は次の内容を示します。<ul><li>**（2）**：選択したステータスの数（1 つ以上のステータスが選択されている場合）。</li><li>**2︎⃣**：現在のフィルターによって生成されたアイテムに使用できるステータスの数。</li><li>1︎⃣：特定のステータスに関連付けられている項目の数。</li></ul></li></ul> |

## フィルターセクションを入力 {#typefiltersection}

| タイプ | 説明 |
|---|---|
| ![タイプ](/help/assets/filter-type.png){width="300"} | 「**[!UICONTROL タイプ]**」セクションでは、タイプでフィルタリングできます。 <ul><li>複数のタイプを選択できます。</li><li>数値は次の内容を示します。<ul><li>**（2）**：選択されたタイプの数（1 つ以上のタイプが選択されている場合）。</li><li>**1︎⃣**：現在のフィルターによって生成された項目で使用できるタイプの数。</li><li>3︎⃣：特定のタイプに関連付けられている項目の数。</li></ul></li></ul> |

## 所有者フィルターセクション {#ownerfiltersection}

| 所有者 | 説明 |
|---|---|
| ![ 所有者 ](/help/assets/filter-owners.png){width="300"} | **[!UICONTROL 所有者]** セクションでは、所有者をフィルタリングできます。 <ul><li>![ 検索 ](/help/assets/icons/Search.svg)*所有者を検索* して、フィルタリングに使用できる所有者を検索できます。</li><li>複数の所有者を選択できます。 使用できる所有者は、フィルターパネルの他のセクションで選択した内容によって異なります。</li><li>数値は次の内容を示します。<ul><li>**（2）**：選択された所有者の数（1 人以上の所有者が選択されている場合）。</li><li>**3︎⃣**：現在のフィルターによって生成されたアイテムで使用できる所有者の数。</li><li>4︎⃣：特定の所有者に関連付けられている項目の数。</li></ul></li></ul> |

## その他のフィルターセクション {#otherfiltersfiltersection}

| その他のフィルター | 説明 |
|---|---|
| ![その他のフィルター](/help/assets/filter-other.png){width="300"} | 「**[!UICONTROL その他のフィルター]**」セクションでは、他の定義済みフィルターでフィルタリングできます。<ul><li>次のオプションを 1 つ以上選択できます。<ul><li> **[!UICONTROL すべてを表示]**</li><li>**[!UICONTROL 自分と共有]**</li><li>**[!UICONTROL 私の]**</li><li>**[!UICONTROL 承認済み]**</li><li>**[!UICONTROL お気に入り]**</li></ul> 選択できる内容は、役割と権限によって異なります。</li><li>他の複数のフィルターを選択できます。 使用できるその他のフィルターは、フィルターパネルの他のセクションで選択した内容によって異なります。</li><li>数値は次の内容を示します。<ul><li>**（1）**：選択した他のフィルターの数（他のフィルターが 1 つ以上選択されている場合）。</li><li>**5︎⃣**：現在のフィルターから生成された項目で使用できるその他のフィルターの数。</li><li>4︎⃣：特定の他のフィルターに関連付けられている項目の数。</li></ul></li></ul> |

## 日付範囲フィルターセクション  {#daterangefiltersection}

| 適用された日付範囲 | 説明 |
|---|---|
| ![日付範囲](/help/assets/filter-daterange.png){width="300"} | 「適用された日付範囲」セクションでは、項目に適用可能な日付範囲でフィルタリングできます。<ol><li>日付範囲を選択します。</li><li>カレンダーポップアップで、日付範囲を定義するか、使用可能なプリセットの 1 つを選択します。<br> または、フィルターパネルの「日付範囲」セクションで、日付範囲を直接指定することもできます。</li></ol><ul><li>数値は次の内容を示します。<ul><li>**（1）**：デフォルトのプリセットから変更された変更済み日付範囲の数。</li><li>**5︎⃣**：現在のフィルターによって生成された項目に使用できる日付範囲の数。</li></ul> |


## アトリビューションモデル {#attribution-models-details}

アトリビューションモデルは、指標のルックバックウィンドウ内に複数の値が表示された場合に、指標のクレジットを取得するディメンション項目を決定します。 アトリビューションモデルは、ルックバックウィンドウ内に複数のディメンション項目が設定されている場合にのみ適用されます。 単一のディメンション項目のみが設定されている場合、そのディメンション項目は、使用される属性モデルに関係なく、100% のクレジットを受け取ります。

| アイコン | アトリビューションモデル | 定義 |
| :---: | :--- | --- |
| ![ラストタッチ](/help/assets/icons/AttributeLastTouch.svg) | ラストタッチ | コンバージョンの直前に発生したタッチポイントに 100% のクレジットを与えます。 このアトリビューションモデルは、通常、アトリビューションモデルが特に指定されていない指標のデフォルト値です。 内部検索キーワードの分析など、コンバージョンまでの時間が比較的短い組織では、通常、このモデルを使用します。 |
| ![ファーストタッチ](/help/assets/icons/AttributeFirstTouch.svg) | ファーストタッチ | アトリビューションのルックバックウィンドウ内で最初に確認されたタッチポイントに 100% のクレジットを与えます。 通常、組織はこのモデルを使用して、ブランド認知度や顧客獲得について理解します。 |
| ![線形](/help/assets/icons/AttributeLinear.svg) | 線形 | コンバージョンにつながるすべてのタッチポイントに対して、同等のクレジットを付与します。 これは、コンバージョンサイクルが長い場合や、より頻繁な顧客エンゲージメントが必要な場合に役立ちます。 組織は通常、モバイルアプリの通知の有効性を測定したり、購読ベースの製品で、このアトリビューションモデルを使用します。 |
| ![パーティシペーション](/help/assets/icons/AttributeParticipation.svg) | パーティシペーション | 一意のタッチポイントすべてに 100％のクレジットが与えられます。すべてのタッチポイントが 100% のクレジットを受け取るので、指標データは通常、100% を超える合計になります。 コンバージョンに至るまで、ディメンション項目が複数回別々に表示される場合、値は 100% まで重複排除されます。 このアトリビューションモデルは、顧客が最もさらされるタッチポイントを理解したい状況に最適です。 メディア組織は、通常、このモデルを使用してコンテンツベロシティを計算します。 小売組織は通常、このモデルを使用して、サイトのどの部分がコンバージョンに不可欠かを把握します。 |
| ![同じタッチ](/help/assets/icons/AttributeSameTouch.svg) | 同じタッチ | コンバージョンが発生した同じイベントに 100% のクレジットを与えます。 コンバージョンと同じイベントでタッチポイントが発生しない場合は、「なし」の下にバケット化されます。 このアトリビューションモデルは、アトリビューションモデルがまったくない場合と同等に扱われることがあります。 これは、指標がディメンション項目にクレジットを与える方法に他のイベントの値が影響を与えることを望まないシナリオで役立ちます。 製品チームまたは設計チームは、このモデルを使用して、コンバージョンが発生するページの効果を評価できます。 |
| ![U字型 ](/help/assets/icons/AttributeUShaped.svg) | U 字型 | 最初のインタラクションに 40％のクレジット、最後のインタラクションに 40％のクレジットが与えられ、残りの 20％がその間のタッチポイントに割り振られます。タッチポイントが 1 つのコンバージョンの場合、100％のクレジットが与えられます。2 つのタッチポイントを持つコンバージョンの場合、両方に 50% のクレジットが与えられます。 このアトリビューションモデルは、最初と最後のインタラクションを最も重視するが、その間の追加のインタラクションを完全に却下したくないシナリオで最適に使用されます。 |
| ![J カーブ ](/help/assets/icons/AttributeJCurve.svg) | J カーブ | 最後のインタラクションに 60％のクレジット、最初のインタラクションに 20％のクレジットが与えられ、残りの 20％がその間のタッチポイントに割り振られます。タッチポイントが 1 つのコンバージョンの場合、100％のクレジットが与えられます。2 つのタッチポイントがあるコンバージョンの場合、最後のインタラクションに 75% のクレジットが与えられ、最初のインタラクションに 25% のクレジットが与えられます。 U字型と同様に、このアトリビューションモデルは最初と最後のインタラクションを優先しますが、最後のインタラクションの方が大幅に優先されます。 |
| ![ 逆 J](/help/assets/icons/AttributeInverseJ.svg) | 逆 J 形 | 最初のタッチポイントに 60％のクレジット、最後のタッチポイントに 20％のクレジットが与えられ、残りの 20％がその間のタッチポイントに割り振られます。タッチポイントが 1 つのコンバージョンの場合、100％のクレジットが与えられます。2 つのタッチポイントがあるコンバージョンの場合、最初のインタラクションに 75% のクレジットが与えられ、最後のインタラクションに 25% のクレジットが与えられます。 J字型と同様に、このアトリビューションモデルは最初と最後のインタラクションを優先しますが、最初のインタラクションの方が大幅に優先されます。 |
| ![タイムディケイ](/help/assets/icons/AttributeTimeDecay.svg) | タイムディケイ | カスタムの半減期パラメーター（デフォルトは 7 日）で指定される指数関数的減衰に従います。各チャネルの重みは、タッチポイントの開始から最終的なコンバージョンまでの経過時間によって異なります。クレジットの決定に使用される式は `2^(-t/halflife)` です。ここで、`t` は、タッチポイントからコンバージョンまでの時間を表します。すべてのタッチポイントは、100% に正規化されます。 特定の重要なイベントに対してアトリビューションを測定するシナリオに最適です。 このイベントの後にコンバージョンが発生する時間が長いほど、与えられるクレジットは少なくなります。 |
| ![カスタム](/help/assets/icons/AttributeCustom.svg) | カスタム | ファーストタッチポイント、ラストタッチポイントおよびその間のタッチポイントに与える重みを指定できます。 指定された値は、入力したカスタムの数値の合計が 100 にならなくても、100％に正規化されます。タッチポイントが 1 つのコンバージョンの場合、100％のクレジットが与えられます。タッチポイントが 2 つのインタラクションの場合、中間のパラメーターは無視されます。その後、ファーストタッチポイントとラストタッチポイントが 100% に正規化され、それに応じてクレジットが割り当てられます。 このモデルは、アトリビューションモデルを完全に制御したいアナリストや、他のアトリビューションモデルでは実現できない特定のニーズを持つアナリストに最適です。 |
| ![アルゴリズム](/help/assets/icons/AttributeAlgorithmic.svg) | アルゴリズム | 統計的手法を使用して、選択した指標に対するクレジットの最適な配分を動的に決定します。 アトリビューションに使用されるアルゴリズムは、協同ゲーム理論のハルサニ配当に基づきます。ハルサニ配当は、結果への貢献度が等しくないゲーム内のプレーヤー間でクレジットを分配するためのシャープレイ値ソリューション（ノーベル賞受賞者のエコノミスト、ロイドシャープレイにちなんで名付けられました）の一般化です。<br> 高いレベルでは、アトリビューションは、剰余金を公平に分配する必要があるプレーヤーの連合として計算されます。 各連合体の余剰分布は、各連合体（または以前に参加したディメンション項目）が再帰的に作成した余剰に応じて決定される。 詳しくは、John Harsanii&#39;s と Lloyd Shapley&#39;s original papers:<br>Shapley, Lloyd S を参照。（1953）。 n 人用ゲームの値&#x200B;*Contributions to the Theory of Games, 2(28)*, 307-317.<br> ジョン・C・ハルサーニー（1963）。 n 人用協力ゲームのシンプル版安価モデル。*International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## 属性ルックバックウィンドウ {#attribution-lookback-window}

ルックバックウィンドウは、タッチポイントを含めるようにコンバージョンをルックバックする期間です。ディメンション項目がルックバックウィンドウ外で設定された場合、その値はアトリビューションの計算に含まれません。

* **14 日**：コンバージョンが発生した時点から最大 14 日後を遡ります。
* **30 日**：コンバージョンが発生した時点から最大 30 日後を遡ります。
* **60 日**：コンバージョンが発生した時点から最大 60 日遡ります。
* **90 日**：コンバージョンが発生した時点から最大 90 日後を遡ります。
* **セッション**：コンバージョンが発生したセッションの先頭まで遡ります。 セッションルックバックウィンドウは、データビューの変更された [ セッションタイムアウト ](/help/data-views/create-dataview.md#session-settings) を尊重します。
* **個人（レポートウィンドウ）**：現在の日付範囲の月の最初までのすべての訪問を調べます。 例えば、レポートの日付範囲が 9 月 15 日～9 月 30 日の場合、人物ルックバックの日付範囲は 9 月 1 日～9 月 30 日を含みます。 このルックバックウィンドウを使用すると、ディメンション項目がレポートウィンドウ外の日付に関連付けられていることがあります。
* **カスタム時間：** コンバージョンが発生した時点からのカスタムルックバックウィンドウを設定できます。 分、時間、日、週、月、四半期の数を指定できます。 例えば、コンバージョンが 2 月 20 日に発生した場合、5 日間のルックバックウィンドウでは、アトリビューションモデルの 2 月 15 日から 2 月 20 日までのすべてのディメンションタッチポイントが評価されます。

## アトリビューションの例 {#attribution-example}

次の例をご覧ください。

1. 9 月 15 日（PT）に、ある人物が有料検索広告を通じてサイトに到達した後、退出します。
1. 9 月 18 日（PT）、その人物は友人から取得したソーシャルメディアリンクを通じてサイトに再び到達します。 訪問者は買い物かごに複数の品目を追加しますが、何も購入しません。
1. 9 月 24 日に、マーケティングチームはこれらのユーザーに対し、買い物かご内の一部の品目に対するクーポンが記載されたメールを送信します。ユーザーはクーポンを適用しますが、他の複数のサイトを訪問して、利用可能なクーポンがあるかどうかを確認します。ディスプレイ広告で別の広告を見つけ、最終的に 50 ドルで購入します。

ルックバックウィンドウとアトリビューションモデルに応じて、チャネルは異なるクレジットを受け取ります。以下に例を示します。

* **ファーストタッチ** と **セッションルックバックウィンドウ** を使用して、アトリビューションでは 3 回目の訪問のみが表示されます。 電子メールとディスプレイ広告では、電子メールが先だったので、50 ドルの購入に対して 100％のクレジットが電子メールに与えられます。

* **ファーストタッチ** と **人物ルックバックウィンドウ** を使用して、アトリビューションは 3 回の訪問すべてを調べます。 有料検索が最初なので、50 ドルの購入に対して 100％のクレジットが与えられます。

* **線形** と **セッションルックバックウィンドウ** を使用して、クレジットをメールとディスプレイで分割します。 これらのチャンネルは両方とも 25 ドルずつクレジットを受け取っている。
**線形** と **人物ルックバックウィンドウ** を使用して、クレジットを、有料検索、ソーシャル、メール、ディスプレイに分割します。 各チャネルは、この購入に対して 12.50 ドルのクレジットを受け取ります。

* **J字型** と **人物ルックバックウィンドウ** を使用して、クレジットを、有料検索、ソーシャル、メール、ディスプレイに分割します。

   * 60％のクレジット（30 ドル）がディスプレイ広告に与えられます。
   * 20％のクレジット（10 ドル）が有料検索に与えられます。
   * 残りの 20％はソーシャルと電子メールの間で分割され、それぞれに 5 ドルが与えられます。

* **タイムディケイ** と **人物ルックバックウィンドウ** を使用して、クレジットを、有料検索、ソーシャル、メール、ディスプレイに分割します。 デフォルトである 7 日間の半減期を使用する場合：

   * 表示タッチポイントとコンバージョンの間のゼロ日のギャップ。`2^(-0/7) = 1`
   * 電子メールタッチポイントとコンバージョンの間のゼロ日のギャップ。`2^(-0/7) = 1`
   * ソーシャルタッチポイントとコンバージョンの間の 6 日間のギャップ。`2^(-6/7) = 0.552`
   * 有料検索タッチポイントとコンバージョンの間の 9 日間のギャップ。`2^(-9/7) = 0.41`
   * これらの値を正規化すると、次の結果になります。

      * ディスプレイ広告：33.8％、16.88 ドル
      * 電子メール：33.8％、16.88 ドル
      * ソーシャル：18.6％、9.32 ドル
      * 有料検索：13.8％、6.92 ドル

通常、整数を持つコンバージョンイベントは、クレジットが複数のチャネルに属する場合は分割されます。 例えば、線形アトリビューションモデルを使用して 1 つの注文に対して 2 つのチャネルが貢献している場合、両方のチャネルがその注文の 0.5 を受け取ります。 これらの部分指標は、すべてのユーザーについて合計され、レポート用に最も近い整数に丸められます。

## ジャーニービジュアライゼーションの比較 {#journey-visualization-comparisons}

顧客ジャーニー分析の様々なビジュアライゼーションは、顧客に提供するジャーニーを分析するように設計されています。

次の情報を使用して、ニーズに最適なビジュアライゼーションを選択します。

| 関数 | ジャーニーキャンバス | フォールアウト | フロー |
|---------|----------|---------|---------|
| **事前定義済みのページのシーケンス** | はい </br> 定義済みの分析と探索的分析を組み合わせます。 最終的なパスは、パス上で事前定義済みのノードを使用する際に使用されます（最終的に事前定義済みのノード間を移動する限り、訪問者がカウントされます）。 直後の（最終的ではない）次のノードも表示できます。 | はい </br> パスは、最終的なパスにすることも、次のタッチポイントに制限することもできます | × |
| **探索的なページのシーケンス（アドホック分析）** | はい </br> 定義済みの分析と探索的分析を組み合わせます。 最終的なパスは、パス上で事前定義済みのノードを使用する際に使用されます（最終的に事前定義済みのノード間を移動する限り、訪問者がカウントされます）。 直後の（最終的ではない）次のノードも表示できます。 | 制限付き </br> フリーフォームテーブルで右クリックし、即座にフォールアウトを表示できます。 | はい </br> 探索的分析のみ。 ノード間で常に 1 つの次元インスタンス内に存在します。 つまり、各ノードは、パスに沿った直近の（最終的ではない）次のタッチポイントを表示します。 |
| **ユーザーが離脱（フォールアウト）した箇所と、継続（フォールスルー）した箇所を示します** | はい </br> 事前定義済みジャーニーと探索的ジャーニーの両方で表示します | はい </br> 定義済みジャーニーを表示します | はい </br> 探索的ジャーニーを表示 |
| **線形ジャーニー** | ○ | ○ | × |
| **複数のエントリポイントとパスを持つ非線形ジャーニー** | ○ | × | ○ |
| **プライマリ指標** | 計算指標を含む任意の指標 | Only Session or Person | 発生件数のみ（パスビュー） |
| **セカンダリ指標** | ○<p>計算指標を含む任意の指標</p> | × | × |
| **ノードまたはタッチポイントでのコンポーネントのサポート** | 指標、ディメンション項目、フィルターおよび日付範囲。 | 指標、ディメンション項目、フィルターおよび日付範囲。 | ディメンション項目のみ（開始および終了タッチポイントを除く） |
| **フィルターを比較** | × | ○<p>同じレポートで異なる 2 つのフィルターを並べて比較</p> | × |
| **ドラッグ&amp;ドロップによるコンポーネントインタラクション** | ○ | ○ | × |
| **Adobe Journey Optimizer ジャーニー** | はい </br>Journey Optimizerからジャーニーを開くと、より深い分析とカスタマイズが可能になります | × | × |

{style="table-layout:auto"}
