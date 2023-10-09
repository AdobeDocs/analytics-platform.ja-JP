---
title: 派生フィールド
description: 派生フィールドは、使用可能な関数や関数テンプレートのセットを介して、スキーマフィールドや標準コンポーネントのレポート時間操作を指定します。
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
source-git-commit: 4ec48fcdd62781720f7d648a0ec2169d2af03d23
workflow-type: tm+mt
source-wordcount: '5431'
ht-degree: 15%

---

# 派生フィールド

派生フィールドは、Adobe Customer Journey Analyticsのリアルタイムレポート機能の重要な側面です。 派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。その派生フィールドを、 [Workspace](../../analysis-workspace/home.md) または、派生フィールドを [データビュー](../data-views.md).

派生フィールドを使用すると、Customer Journey Analyticsの外部にある他の場所でデータを変換または操作する場合と比べて、大幅な時間と労力を節約できます。 例： [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)または独自の変換読み込みの抽出 (ETL)/読み込み変換の抽出 (ELT) プロセス内で実行できます。

派生フィールドは、 [データビュー](../data-views.md)は、ルールとして定義された一連の関数に基づき、使用可能な標準フィールドやスキーマフィールドに適用されます。

使用例を次に示します。

- 収集された不適切なページ名の値を修正し、ページ名の値を正しく修正する、派生した「ページ名」フィールドを定義します。

- 1 つ以上の条件（URL パラメーター、ページ URL、ページ名など）に基づいて適切なマーケティングチャネルを決定する、派生マーケティングチャネルフィールドを定義します。

## 派生フィールドインターフェイス

派生フィールドを作成または編集する場合、派生フィールドインターフェイスを使用します。

![派生フィールドダイアログのスクリーンショット](assets/derived-field-dialog.png)


|  | 名前 | 説明 |
|---------|----------|--------|
| 1 | **セレクター** | セレクター領域を使用して、関数、関数テンプレート、スキーマフィールドまたは標準フィールドを選択し、ルールビルダーにドラッグ&amp;ドロップします。 <br/>ドロップダウンを使用して、次の中から選択します。 <br/>![関数](assets/Smock_Function_18_N.svg) [!UICONTROL 関数]  — 使用可能なリスト [関数](#function-reference), </br>![関数テンプレートアイコン](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL 関数テンプレート]  — 使用可能なリスト [関数テンプレート](#function-templates), <br/>![スキーマフィールドアイコン](assets/Smock_Folder_18_N.svg)  [!UICONTROL スキーマフィールド]  — データセットカテゴリ（イベント、プロファイル、参照）および以前に定義した派生フィールドから使用できるフィールドを一覧表示します。 <br/>![標準フィールドアイコン](assets/Smock_DragHandle_18_N.svg) [!UICONTROL 標準フィールド]  — 標準の使用可能フィールド（プラットフォームデータセット ID など）。 セレクターには、文字列および数値の標準フィールドのみが表示されます。 関数が他のデータ型をサポートしている場合、ルールインターフェイス内の値やフィールドに対して、これらの他のデータ型を持つ標準フィールドを選択できます。<br/>関数、関数テンプレート、スキーマ、標準フィールドは、 ![検索アイコン](assets/Smock_Search_18_N.svg) 検索ボックス。 <br/>選択したオブジェクトのリストをフィルタするには、 ![フィルターアイコン](assets/Smock_Filter_18_N.svg) フィルターを設定し、 [!UICONTROL 次の条件でフィールドをフィルター] ダイアログ。 フィルターを簡単に削除するには、 ![閉じるアイコン](assets/CrossSize75.svg) フィルターごとに |
| 2 | **ルールビルダー** | 派生フィールドは、1 つ以上のルールを使用して順番に作成します。 ルールは、関数の特定の実装なので、常に 1 つの関数にのみ関連付けられます。 ルールを作成するには、関数をルールビルダーにドラッグ&amp;ドロップします。 関数の型によって、ルールのインターフェイスが決まります。<br/>詳しくは、 [ルールインターフェイス](#rule-interface) を参照してください。 <br/>関数は、ルールビルダーで既に使用可能なルールの開始、終了または中間に挿入できます。 ルールビルダーの最後のルールによって、派生フィールドの最終出力が決まります。 |
| 3 | **[!UICONTROL **&#x200B;フィールド設定&#x200B;**]** | 派生フィールドに名前を付け、説明し、そのフィールドタイプを調べることができます。 |
| 4 | **[!UICONTROL **&#x200B;最終出力&#x200B;**]** | この領域には、過去 30 日間のデータと、ルールビルダーの派生フィールドに加えた変更に基づき、出力値のプレビューがその場で表示されます。 |

{style="table-layout:auto"}

## フィールドテンプレートウィザード

派生フィールドのインターフェイスに初めてアクセスしたとき、 [!UICONTROL フィールドテンプレートから開始する] ウィザードが表示されます。

1. 作成しようとしているフィールドのタイプに最も適したテンプレートを選択します。
2. を選択します。 **[!UICONTROL **&#x200B;選択&#x200B;**]** ボタンをクリックして続行します。

派生フィールドダイアログには、選択したフィールドのタイプに必要なルール（および関数）が入力されます。また、このルールは、選択したフィールドのタイプに役立ちます。 詳しくは、 [関数テンプレート](#function-templates) を参照してください。

## ルールインターフェイス

ルールビルダーでルールを定義する場合、ルールインターフェイスを使用します。

![派生フィールドルールインターフェイスのスクリーンショット](assets/rule-interface.png)

|  | 名前 | 説明 |
|---------|----------|--------|
| A | **ルール名** | デフォルトでは、ルール名は **ルール X** （X はシーケンス番号を参照）。 ルールの名前を編集するには、ルールの名前を選択し、新しい名前を入力します（例： ）。 `Query Parameter`. |
| B | **関数名** | ルールの選択された関数名（例： ）。 [!UICONTROL URL 解析]. 関数が関数のシーケンスの最後の関数で、最終的な出力値を決定する場合、関数名の後に [!UICONTROL  — 最終出力]例： [!UICONTROL URL 解析 — 最終出力]. <br/>関数の詳細情報を含むポップアップを表示するには、 ![ヘルプアイコン](assets/Smock_HelpOutline_18_N.svg). |
| C | **ルールの説明** | オプションで、ルールに説明を追加できます。<br/>選択 ![その他のアイコン](assets/More.svg)を選択し、「 **[!UICONTROL **&#x200B;説明を追加&#x200B;**]** 説明を追加するには、または **[!UICONTROL **&#x200B;説明を編集&#x200B;**]** 既存の説明を編集する場合。<br/>説明を入力するには、エディターを使用します。 ツールバーを使用して、テキストの書式設定（スタイルセレクター、太字、斜体、下線、右、左、中央揃え、色、番号リスト、箇条書きリストを使用）や、外部情報へのリンクの追加を行うことができます。 <br/>説明の編集を終了するには、エディターの外側をクリックします。 |
| D | **機能領域** | 関数のロジックを定義します。 インターフェイスは、関数のタイプによって異なります。 次のドロップダウン： [!UICONTROL フィールド] または [!UICONTROL 値] は、関数が想定する入力のタイプに基づいて、使用可能なフィールド（ルール、標準フィールド、フィールド）のすべてのカテゴリを表示します。 または、スキーマおよび標準フィールドセレクターからフィールドまたは値にフィールドをドラッグ&amp;ドロップできます。 ドラッグしたフィールドがルックアップデータセットから取得された場合、定義した関数の前に、ルックアップ関数が自動的に挿入されます。 <br/>詳しくは、 [関数リファレンス](#function-reference) を参照してください。 |

{style="table-layout:auto"}

## 派生フィールドの作成

1. 既存のデータビューを選択するか、データビューを作成します。 詳しくは、 [データビュー](../data-views.md) を参照してください。

2. を選択します。 **[!UICONTROL **&#x200B;コンポーネント&#x200B;**]** 」タブをクリックします。

3. 選択 **[!UICONTROL **&#x200B;派生フィールドを作成&#x200B;**]** をクリックします。

4. 派生フィールドを定義するには、 [!UICONTROL 派生フィールドを作成] インターフェイス。 詳しくは、 [派生フィールドインターフェイス](#derived-field-interface).

   新しい派生フィールドを保存するには、「 」を選択します。 **[!UICONTROL **&#x200B;保存&#x200B;**]**.

5. 新しい派生フィールドが [!UICONTROL 派生フィールド >] コンテナ、の一部 **[!UICONTROL **&#x200B;スキーマフィールド&#x200B;**]** をクリックします。


## 派生フィールドの編集

1. 既存のデータビューを選択します。 詳しくは、 [データビュー](../data-views.md) を参照してください。

2. を選択します。 **[!UICONTROL **&#x200B;コンポーネント&#x200B;**]** 」タブをクリックします。

3. 選択 **[!UICONTROL **&#x200B;スキーマフィールド&#x200B;**]** 」タブをクリックします。 [!UICONTROL 接続] ウィンドウの左側に表示されます。

4. 選択 **[!UICONTROL **&#x200B;派生フィールド >**]** コンテナ。

5. 編集する派生フィールドの上にマウスポインターを置いて、「 」を選択します。 ![編集アイコン](assets/Smock_Edit_18_N.svg).

6. 派生フィールドを編集するには、 [!UICONTROL 派生フィールドを編集] インターフェイス。 詳しくは、 [派生フィールドインターフェイス](#derived-field-interface).

   - 選択 **[!UICONTROL **&#x200B;保存&#x200B;**]** 更新した派生フィールドを保存します。

   - 選択 **[!UICONTROL **&#x200B;キャンセル&#x200B;**]** をクリックして、派生フィールドに加えた変更をキャンセルします。

   - 選択 **[!UICONTROL **&#x200B;名前を付けて保存&#x200B;**]** をクリックして、派生フィールドを新しい派生フィールドとして保存します。 新しい派生フィールドは、編集元の派生フィールドと同じ名前で、 `(copy)` を追加しました。

## 派生フィールドの削除

1. 既存のデータビューを選択します。 詳しくは、 [データビュー](../data-views.md) を参照してください。

2. を選択します。 **[!UICONTROL **&#x200B;コンポーネント&#x200B;**]** 」タブをクリックします。

3. 選択 **[!UICONTROL **&#x200B;スキーマフィールド&#x200B;**]** タブ [!UICONTROL 接続] ウィンドウ

4. 選択 **[!UICONTROL **&#x200B;派生フィールド >**]** コンテナ。

5. 削除する派生フィールドの上にマウスポインターを置いて、「 」を選択します。 ![編集アイコン](assets/Smock_Edit_18_N.svg).

6. 使用中 **[!UICONTROL **&#x200B;派生フィールドを編集&#x200B;**]** インタフェースで、「削除」を選択します。

   A [!UICONTROL コンポーネントを削除] 削除を確認するダイアログが表示されます。 データビューの外部にある派生フィールドに対する外部参照が存在する可能性があるとします。

   - 選択 **[!UICONTROL **&#x200B;続行&#x200B;**]** をクリックして、派生フィールドを削除します。

>[!NOTE]
>
>派生フィールドは、接続の接続レベルでCustomer Journey Analyticsで管理されます。 その接続に関連付けられたデータビューの派生フィールドに対して行われた変更は、関連付けられたすべてのデータビューに適用されます。



## 関数テンプレート

特定の使用例に対して派生フィールドをすばやく作成するために、関数テンプレートを使用できます。 これらの関数テンプレートは、派生フィールドインターフェイスのセレクター領域からアクセスできます。また、 [!UICONTROL フィールドテンプレートから開始する] ウィザード。


### マーケティングチャネル

このテンプレートは、 [Url 解析](#dnl-url-parse) および [次の場合](#dnl-case-when) は複数回関数を使用して、URL から適切な値を取得します。 次に、これらの値にロジックが適用され、URL が特定のマーケティングチャネルに関連付けられます。

+++ 詳細

このテンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、 [関数リファレンス](#function-reference) を参照してください。

![マーケティングチャネルテンプレートルールビルダーのスクリーンショット](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## 関数リファレンス

{{select-package}}

サポートされる各関数について、以下の詳細を確認します。

- 仕様：
   - 入力データタイプ：サポートされるデータのタイプ。
   - 入力：入力に使用できる値
   - 含まれる演算子：この関数でサポートされる演算子（存在する場合）、
   - 制限事項：この関数に適用される制限事項
   - 出力。

- 次のような使用例があります。
   - 派生フィールドを定義する前のデータ
   - 派生フィールドの定義方法、
   - データを更新しました。

- 制約（該当する場合）

>[!NOTE]
>
>Lookup 関数の名前は、「 [分類](#classify). 詳しくは、 [分類](#classify) 関数を参照してください。

<!-- CASE WHEN -->

### Case When

1 つ以上のフィールドの定義された条件に基づいて条件を適用します。 次に、これらの条件を使用して、条件の順序に基づいて、新しい派生フィールドの値を定義します。

+++ 詳細

## 仕様 {#casewhen-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL 次の場合], [!UICONTROL Else If] コンテナ：</p><ul><li>[!UICONTROL 値]</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL 条件] （選択した値のタイプに基づく、含まれる演算子を参照）</li></ul></li><li>[!UICONTROL 次に、値をに設定します。], [!UICONTROL それ以外の場合は、値をに設定します。]:</p><ul><li>[!UICONTROL 値]</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></ul></li></ul> | <p>文字列</p><ul><li>次と等しい</li><li>いずれかの語句と等しい</li><li>フレーズを含む</li><li>いずれかの語句を含む</li><li>すべての語句を含む</li><li>次の語句で始まる</li><li>任意の語句で始まる</li><li>次の語句で終わる</li><li>任意の用語で終わる</li><li>次と等しくない</li><li>いずれの語句も含まない</li><li>このフレーズを含まない</li><li>いずれの語句も含まない</li><li>すべての語句を含まない</li><li>次で始まらない</li><li>どの用語でも始まらない</li><li>次で終わらない</li><li>次の語句で終わらない</li><li>設定済み</li><li>未設定</li></ul><p>数値</p><ul><li>次と等しい</li><li>次と等しくない</li><li>次より大きい</li><li>次よりも大きいか等しい</li><li>次より小さい</li><li>次よりも小さいか等しい</li><li>設定済み</li><li>未設定</li></ul><p>日付</p><ul><li>次と等しい</li><li>次と等しくない</li><li>次より後</li><li>次より後または等しい</li><li>次より前</li><li>次より前または等しい</li><li>設定済み</li><li>未設定</li></ul> | <ul><li>派生フィールドあたり 5 個の関数</li><li>派生フィールドあたり 200 個の演算子。 例えば、「参照ドメインに Google が含まれる」などが 1 つの演算子です。 </li></ul> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## 使用例 1 {#casewhen-uc1}

様々なマーケティングチャネルを識別するルールを定義するには、カスケードロジックを適用してマーケティングチャネルフィールドを適切な値に設定します。

- リファラーが検索エンジンからのもので、ページにクエリー文字列値が含まれている場合、 `cid` 次を含む `ps_`に値を指定する場合、マーケティングチャネルは [!DNL *有料検索*].
- リファラーが検索エンジンからのもので、ページにクエリ文字列がない場合。 `cid`に値を指定する場合、マーケティングチャネルは [!DNL *自然検索*].
- ページにクエリー文字列値がある場合、 `cid` 次を含む `em_`に値を指定する場合、マーケティングチャネルは [!DNL *電子メール*].
- ページにクエリー文字列値がある場合、 `cid` 次を含む `ds_`に値を指定する場合、マーケティングチャネルは [!DNL *ディスプレイ広告*].
- ページにクエリー文字列値がある場合、 `cid` 次を含む `so_`に値を指定する場合、マーケティングチャネルは [!DNL *ペイドソーシャル*].
- リファラーがの参照ドメインからのものである場合 [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com]または [!DNL tiktok.com]に値を指定する場合、マーケティングチャネルは [!DNL *自然社会*].
- 上記のルールがいずれも一致しない場合は、マーケティングチャネルを [!DNL *その他のリファラー*].

サイトが以下のサンプルイベントを受け取った場合、 [!UICONTROL リファラー] および [!UICONTROL ページ URL]に設定する場合、これらのイベントは次のように識別する必要があります。

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### 次より前のデータ： {#casewhen-uc1-databefore}

| [!DNL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### 派生フィールド {#casewhen-uc1-derivedfield}

新しい `Marketing Channel` 派生フィールド。 次を使用します。 [!UICONTROL 次の場合にケース：] 関数を使用して、両方の `Page URL` および `Referring URL` フィールドに入力します。

関数の使用に注意してください [!UICONTROL URL 解析] 値を取得するルールを定義するには `Page Url` および `Referring Url` の前に [!UICONTROL 次の場合にケース：] ルールが適用されます。

![ルール 1 のケースのスクリーンショット](assets/case-when-1.png)

### 後のデータ {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## 使用例 2 {#casewhen-uc2}

検索の様々なバリエーションを [!DNL Product Finding Methods] ディメンション。 検索と参照の全体的なパフォーマンスを理解するには、結果を手動で組み合わせるのに非常に時間を費やす必要があります。

サイトで、 [!DNL Product Finding Methods] ディメンション。 最後に、これらの値はすべて検索を示します。

| 収集された値 | 実際の値 |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### 次より前のデータ： {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] |
| [!DNL search p13_yes] |
| [!DNL browse] |
| [!DNL search refine p13_no] |
| [!DNL search refine p13_yes] |
| [!DNL browse] |
| [!DNL search redirect p13_yes] |
| [!DNL search-redirect] |
| [!DNL browse] |

{style="table-layout:auto"}

### 派生フィールド {#casewhen-uc2-derivedfield}

次の項目を定義します。 `Product Finding Methods (new)` 派生フィールド。 次を作成します。 [!UICONTROL 次の場合にケース：] ルールビルダーのルール。 これらのルールは、古い [!UICONTROL 製品検索方法] フィールド値 `search` および `browse` の使用 [!UICONTROL 次のフレーズを含む] 条件

![ルール 2 のケースのスクリーンショット](assets/case-when-2.png)

### 後のデータ {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## 使用例 3 {#casewhen-uc3}

旅行会社の場合、予約済みのトリップのトリップ期間をバケット化して、トリップのグループ長をレポートできます。

前提条件：

- 組織は、数値フィールドに対してトリップ期間を収集しています。
- 1 ～ 3 日の期間を「 」という名前のバケットにグループ化する必要があります。[!DNL short trip]&#39;
- 4 ～ 7 日の期間を「 」という名前のバケットにグループ化する必要があります。[!DNL medium trip]&#39;
- 8 日以上の期間を「 」という名前のバケットにグループ化します。[!DNL long trip]&#39;
- 132 回の旅行は 1 日間予約されていた
- 110 回の旅行が 2 日間の予約を受けていた
- 105 回の旅行は 3 日間の予約を受けていた
- 99 回の旅行は 4 日間の予約を受けていた
- 92 回の旅行は 5 日間予約されていた
- 85 回の旅行は 6 日間予約されていた
- 82 回の旅行は、7 日間の予約を受けていた
- 78 回の旅行は 8 日間予約されていた
- 50 回の旅行は 9 日間予約されていた
- 44 回の旅行は 10 日間の予約を受けていた
- 38 回の旅行は 11 日間の予約を受けていた
- 31 回の旅行は 12 日間予約されていた

目的のレポートは次のようになります。

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### 次より前のデータ： {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### 派生フィールド {#casewhen-uc3-derivedfield}

次の項目を定義します。 `Trip Duration (bucketed)` 派生フィールド。 次を作成します。 [!UICONTROL 次の場合にケース：] ルールビルダーのルール。 このルールは、古い [!UICONTROL 旅行期間] フィールドの値を 3 つの値に変換します。 `short trip`, `medium  trip`、および `long trip`.

![ルール 3 のケースのスクリーンショット](assets/case-when-3.png)


### 後のデータ {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## 詳細情報

Customer Journey Analyticsは、Adobe Experience Platformの [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja) （エクスペリエンスデータモデル）。 詳しくは、 [コンテナ](../create-dataview.md#containers) および [フィルターコンテナ](../../components/filters/filters-overview.md#filter-containers) を参照してください。 このコンテナモデルは、本来は柔軟ですが、ルールビルダーを使用する際に一部の制約が課されます。

Customer Journey Analyticsは、次のデフォルトのコンテナモデルを使用します。

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

次の制約が適用され、適用されるのは *選択* および *設定* 値。

|  | 制約 |
|:---:|----|
| **<span style='color: red'>A</span>** | 値 *選択* 同じ内部で [!UICONTROL 次の場合], [!UICONTROL Else If] 構文 ( [!UICONTROL および] または [!UICONTROL または]) ルール内では、同じコンテナから始まる必要があり、任意のタイプ（文字列）を指定できます ![文字列](assets/Smock_ABC_18_N.svg)，数値 ![数値](assets/Smock_123_18_N.svg)など ) を含める必要があります。 <br/>![依存関係 A のスクリーンショット](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | すべての値 *設定* ルールの間は、同じコンテナに属し、同じタイプまたは同じタイプの派生値を持つ必要があります。 <br/> ![依存関係 B のスクリーンショット](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | 指定した値 *選択* 横 [!UICONTROL 次の場合], [!UICONTROL Else If] ルール内の構成では、次の処理が実行されます。 *not* 同じコンテナから派生し、同じコンテナから派生する必要がある *not* 同じタイプである必要があります。 <br/> ![依存関係 C のスクリーンショット](assets/dependency-c.png) |

{style="table-layout:auto"}

+++

<!-- CLASSIFY -->

### 分類

新しい派生フィールドの対応する値に置き換わる値のセットを定義します。

+++ 詳細

>[!NOTE]
>
>この関数は、もともとは Lookup という名前でしたが、異なる機能を備えた今後の Lookup 関数に対応するように、 Classify という名前に変更されました。

## 仕様 {#classify-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL 分類するフィールド]:<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>[!UICONTROL 値がと等しい場合] および [!UICONTROL 値の置換文字列]:</p><ul><li>文字列</li></ul><li>元の値を表示<ul><li>ブール値</li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 5 個の関数<br/>1 関数あたり 100 行</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## 使用例 1 {#classify-uc1}

次のキー列を含む CSV ファイルがあります： `hotelID` および `hotelID`: `city`, `rooms`, `hotel name`.
収集しています [!DNL Hotel ID] ディメンション内で、を作成します。 [!DNL Hotel Name] から派生したディメンション `hotelID` を CSV ファイルに追加します。

**CSV ファイルの構造とコンテンツ**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |
| [!DNL AMS789] | [!DNL Amsterdam] | 50 | [!DNL Okura] |

{style="table-layout:auto"}

**現在のレポート**

| [!DNL Hotel ID] | 製品表示 |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |
| [!DNL AMS789] | 150 |

{style="table-layout:auto"}


**目的のレポート**

| [!DNL Hotel Name] | 製品表示 |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### 次より前のデータ： {#classify-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |
| [!DNL AMS789] |

{style="table-layout:auto"}


### 派生フィールド {#classify-uc1-derivedfield}

次の項目を定義します。 `Hotel Name` 派生フィールド。 次を使用します。 [!UICONTROL 分類] 関数を使用して、 [!UICONTROL ホテル ID] フィールドに値を入力し、新しい値に置き換えます。

分類する値の一部として定義していない元の値を含める場合（例：Hotel ID AMS789）、必ず「 」を選択します。 **[!UICONTROL 元の値を表示]**. これにより、AMS789 が派生フィールドの出力の一部となりますが、その値は分類されません。

![ルール分類 1 のスクリーンショット](assets/classify-1.png)

### 後のデータ {#classify-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## 使用例 2 {#classify-uc2}

複数のページのわかりやすいページ名の代わりに URL を収集した。 この値の組み合わせコレクションは、レポートを壊します。

### 次より前のデータ： {#classify-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### 派生フィールド {#classify-uc2-derivedfield}

次の項目を定義します。 `Page Name (updated)` 派生フィールド。 次を使用します。 [!UICONTROL 分類] 関数を使用して、既存の [!UICONTROL ページ名] フィールドに入力し、更新された正しい値に置き換えます。

![Classify ルール 2 のスクリーンショット](assets/classify-2.png)

### 後のデータ {#classify-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |


## 詳細情報 {#classify-moreinfo}

以下の追加機能が「ルールを分類」インターフェイスで使用できます。

- すべてのテーブル値をすばやくクリアするには、 ![消去](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Erase_18_N.svg) **[!UICONTROL すべてのテーブル値をクリア]**.
- の元の値を含む CSV ファイルをアップロードするには、「値が等しい場合に値を置き換える」で「新しい値」を選択します。 ![CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL CSV をアップロード]**.
- アップロードする元の値と新しい値を含む CSV ファイルを作成するためのテンプレートをダウンロードするには、「 ![ダウンロード](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL CSV テンプレートをダウンロード]**.
- すべての元の値と新しい値がルールインターフェイスに入力された CSV ファイルをダウンロードするには、 ![ダウンロード](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL CSV 値のダウンロード]**.


+++

<!-- CONCATENATE -->

### 連結

フィールドの値を、定義された区切り文字で単一の新しい派生フィールドに組み合わせます。

+++ 詳細

## 仕様 {#concatenate-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL 値]:<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li><li>文字列</li></ul></li><li>[!UICONTROL 区切り]:<ul><li>文字列</li></ul></li> </ul> | <p>該当なし</p> | <p>派生フィールドあたり 2 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース {#concatenate-uc}

現在、オリジンおよび目的地の空港コードを別々のフィールドとして収集しています。 2 つのフィールドを結合して、ハイフン (-) で区切られた 1 つのディメンションにします。 したがって、接触チャネルと宛先の組み合わせを分析して、予約済みの上位ルートを特定できます。

前提条件：

- 同じテーブル内の別々のフィールドで、接触チャネルと宛先の値が収集されます。
- ユーザーは、値の間に区切り文字「 — 」を使用することを決定します。

次の予約が発生するとします。

- お客様 ABC123 は、Salt Lake City(SLC) と Orlando(MCO) 間のフライトを予約しています
- 顧客 ABC456 は、Salt Lake City(SLC) と Los Angeles(LAX) 間のフライトを予約しています
- お客様 ABC789 は、Salt Lake City(SLC) と Seattle(SEA) 間のフライトを予約しています
- お客様 ABC987 は、Salt Lake City(SLC) と San Jose(SJO) 間のフライトを予約しています
- お客様 ABC654 は、Salt Lake City(SLC) と Orlando(MCO) 間のフライトを予約しています

目的のレポートは次のようになります。

| 起源/宛先 | 予約 |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### 次より前のデータ： {#concatenate-uc-databefore}

| 接触チャネル | 宛先 |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 派生フィールド {#concatenate-derivedfield}

新しい [!UICONTROL Origin - Destination] 派生フィールド。 次を使用します。 [!UICONTROL 連結] 関数を使用して、 [!UICONTROL オリジナル] および [!UICONTROL 宛先] を使用するフィールド `-` [!UICONTROL 区切り].

![連結ルールのスクリーンショット](assets/concatenate.png)

### 後のデータ {#concatenate-dataafter}

| Origin - Destination<br/>（派生フィールド） |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- FIND AND REPLACE -->

### 検索と置き換え

選択したフィールド内のすべての値を検索し、新しい派生フィールド内の別の値に置き換えます。

+++ 詳細

## 仕様 {#findreplace-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL 値]<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>[!UICONTROL すべて検索], [!UICONTROL を置き換え、すべてを]:<ul><li>文字列</li></ul></li></ul></ul> | <p>文字列</p><ul><li>[!UICONTROL すべて検索], [!UICONTROL を置き換え、すべてを]</li></ul> | <p>派生フィールドあたり 5 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース {#findreplace-uc}

外部マーケティングチャネルレポートの値の形式が正しくありません。例： `email%20 marketing` の代わりに `email marketing`. これらの不正な値により、レポートが破壊され、E メールのパフォーマンスがより難しくなります。 置き換えますか？ `email%20marketing` 次を使用 `email marketing`.

**元のレポート**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**優先レポート**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### 次より前のデータ： {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### 派生フィールド {#findreplace-uc-derivedfield}

次の項目を定義します。 `Email Marketing (updated)` 派生フィールド。 次を使用します。 [!UICONTROL 検索と置換] 関数を使用して、 `email%20marketing` 次を使用 `email marketing`.

![「検索と置換」ルールのスクリーンショット](assets/find-and-replace.png)

### 後のデータ {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### ルックアップ

ルックアップデータセットのフィールドを使用して値をルックアップし、新しい派生フィールドに値を返す、またはその他のルール処理をおこなうために値を返します。

+++ 詳細

## 仕様 {#lookup-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL 参照を適用するフィールド]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL ルックアップデータセット]</li><ul><li>データセット</li></ul><li>[!UICONTROL 一致するキー]<ul><li>ルール</li><li>フィールド</li></ul></li><li>戻す値<ul><li>ルール</li><li>フィールド</li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 3 つの関数</p> | <p>次のルールでさらに処理するための新しい派生フィールドまたは値</p> |

{style="table-layout:auto"}

## ユースケース {#lookup-uc}

顧客がAdobe Targetを通じて表示されるパーソナライズされたバナーをクリックした際に収集されたアクティビティ ID を使用して、アクティビティ名を検索します。 アクティビティ ID とアクティビティ名を含む Analytics for Target(A4T) アクティビティでルックアップデータセットを使用する場合。

### A4T ルックアップデータセット {#lookup-uc-lookup}

| アクティビティ ID | アクティビティ名 |
|---|---|
| 415851 | MVT テストカテゴリページ |
| 415852 | Luma - Campaign Max 2022 |
| 402922 | ホームページバナー |

{style="table-layout:auto"}

### 派生フィールド {#lookup-uc-derivedfield}

次の項目を定義します。 `Activity Name` 派生フィールド。 次を使用します。 [!UICONTROL 参照] 関数を使用して、 [!UICONTROL ルックアップを適用するフィールド] フィールド ( 例： **[!DNL ActivityIdentifier]**) をクリックします。 ルックアップデータセットは、 [!UICONTROL ルックアップデータセット] リスト ( 例： **[!DNL New CJA4T Activities]**) をクリックします。 次に、識別子フィールド ( 例えば、 **[!DNL ActivityIdentifier]**) を [!UICONTROL 一致するキー] リストと、 [!UICONTROL 返す値] リスト ( 例： **[!DNL ActivityName]**) をクリックします。

![小文字ルールのスクリーンショット](assets/lookup.png)

## 詳細情報

次の項目を簡単に挿入できます。 [!UICONTROL 参照] 関数内に含まれている必要があります。

1. 選択 **[!UICONTROL スキーマフィールド]** を選択します。
1. 選択 ![スキーマフィールドアイコン](assets/Smock_Folder_18_N.svg) **[!UICONTROL 参照データセット]**.
1. ルックアップデータセットを選択し、ルックアップに使用するフィールドを見つけます。
1. 関数で使用可能な任意の入力フィールド（例えば、「Case When」）にルックアップフィールドをドラッグ&amp;ドロップします。 有効な場合は、青いボックスで、ラベル付き **[!UICONTROL +追加]**を使用すると、フィールドをドロップし、ルックアップフィールドをドロップした関数の前に、ルックアップ関数を自動的に挿入できます。 挿入されたルックアップ関数は、すべてのフィールドに関連する値を自動的に設定します。
   ![ルックアップドラッグ](assets/lookup-drag.png)

+++


<!-- LOWERCASE -->

### 小文字

値をフィールドから小文字に変換し、新しい派生フィールドに保存します。

+++ 詳細

## 仕様 {#lowercase-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL フィールド]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 2 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース {#lowercase-uc}

レポートを適切に作成するために、収集されたすべての製品名を小文字に変換します。

### 次より前のデータ： {#lowercase-uc-databefore}

| 収集された製品名 | 製品表示 |
|---|---:|
| テニスラケット | 35 |
| テニスラケット | 33 |
| テニスラケット | 21 |
| 野球用バット | 15 |
| 野球バット | 12 |
| 野球のバット | 10 |

{style="table-layout:auto"}

### 派生フィールド {#lowercase-uc-derivedfield}

次の項目を定義します。 `Product Names` 派生フィールド。 次を使用します。 [!UICONTROL 小文字] 関数を使用して、 [!UICONTROL 収集された製品名] フィールドを小文字に変換し、新しい派生フィールドに格納します。

![小文字ルールのスクリーンショット](assets/lowercase.png)


### 後のデータ {#lowercase-uc-dataafter}

| 製品名 | 製品表示 |
|---|---|
| テニスラケット | 89 |
| 野球のバット | 37 |

{style="table-layout:auto"}

+++

<!-- MERGE FIELDS -->

### フィールドを結合

2 つの異なるフィールドの値を新しい派生フィールドに結合します。

+++ 詳細

## 仕様 {#merge-fields-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL フィールド]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 5 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース {#merge-fields-uc}

チャネルをまたいでジャーニーを分析する目的で、ページ名フィールドと呼び出し理由フィールドから構成されるディメンションを作成したい場合。

### 次より前のデータ： {#merge-fields-uc-databefore}

| ページ名 | セッション | 訪問者 |
|---|--:|--:|
| ヘルプページ | 250 | 200 |
| home page | 500 | 250 |
| 製品の詳細ページ | 300 | 200 |

{style="table-layout:auto"}

| 通話理由 | セッション | 訪問者 |
|---|--:|--:|
| 注文に関する質問 | 275 | 250 |
| 注文を変更する | 150 | 145 |
| 注文の問題 | 100 | 95 |

{style="table-layout:auto"}

### 派生フィールド {#merge-fields-uc-derivedfield}

次の項目を定義します。 `Cross Channel Interactions` 派生フィールド。 次を使用します。 [!UICONTROL フィールドのマージ] 関数を使用して、 [!UICONTROL ページ名] フィールドと [!UICONTROL 通話理由] フィールドに格納し、新しい派生フィールドに格納します。

![結合フィールドルールのスクリーンショット](assets/merge-fields.png)

### 後のデータ {#merge-fields-uc-dataafter}

| クロスチャネルインタラクション | セッション数 | 訪問者 |
|---|--:|--:|
| home page | 500 | 250 |
| 製品の詳細ページ | 300 | 200 |
| 注文に関する質問 | 275 | 250 |
| ヘルプページ | 250 | 200 |
| 注文を変更する | 150 | 145 |
| 注文の問題 | 100 | 95 |

{style="table-layout:auto"}

## 詳細情報 {#merge-fields-moreinfo}

[ フィールドの結合 ] ルール内で同じタイプのフィールドを選択する必要があります。 例えば、日付フィールドを選択した場合、結合する他のすべてのフィールドは、日付フィールドである必要があります。

![結合フィールドに対する制約のスクリーンショット](assets/merge-fields-constraint.png)

+++


<!-- REGEX REPLACE -->

### 正規表現による置換

正規表現を使用して新しい派生フィールドに値を置き換えます。

+++ 詳細

## 仕様 {#regex-replace-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li></ul> | <ul><li>[!UICONTROL フィールド]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></ul><ul><li>[!UICONTROL 正規表現]:</li><ul><li>文字列</li></ul></li><li>[!UICONTROL 出力形式]:<ul><li>文字列</li></ul></ul><ul><li>大文字と小文字を区別</li><ul><li>ブール値</li></ul></li></ul></li> | <p>該当なし</p> | <p>派生フィールドあたり 1 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース {#regex-replace-uc}

URL の一部を取得し、それを一意のページ識別子として使用してトラフィックを分析したいとします。 次を使用する： `[^/]+(?=/$|$)` を返します。 `$1` を出力パターンとして使用します。

### 次より前のデータ： {#regex-replace-uc-databefore}

| ページ URL |
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### 派生フィールド {#regex-replace-uc-derivedfield}

次の項目を作成します。 `Page Identifier` 派生フィールド。 次を使用します。 [!UICONTROL 正規表現の置換] 関数を使用して、 [!UICONTROL 参照 URL] を使用するフィールド [!UICONTROL Regex] / `[^/]+(?=/$|$)` および [!UICONTROL 出力形式] / `$1`.

![正規表現の置き換えルールのスクリーンショット](assets/regex-replace.png)


### 後のデータ {#regex-replace-uc-dataafter}

| ページ識別子 |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## 詳細情報

Customer Journey Analyticsは、Perl 正規表現構文のサブセットを使用します。 次の式がサポートされています。

| 式 | 説明 |
| --- | --- |
| `a` | 単一の文字 `a`。 |
| `a\|b` | 単一の文字 `a` または `b`。 |
| `[abc]` | 単一の文字 `a`、`b` または `c`。 |
| `[^abc]` | `a`、`b` または `c` を除く任意の単一の文字。 |
| `[a-z]` | `a` ～ `z` の範囲の任意の単一の文字。 |
| `[a-zA-Z0-9]` | `a` ～ `z`、`A` ～ `Z` または数字 `0` ～ `9` の範囲の任意の単一の文字。 |
| `^` | 行の先頭に一致します。 |
| `$` | 行の末尾に一致します。 |
| `\A` | 文字列の開始。 |
| `\z` | 文字列の終わり。 |
| `.` | 任意の文字に一致します。 |
| `\s` | 空白文字。 |
| `\S` | 空白以外の文字。 |
| `\d` | 数字。 |
| `\D` | 数字以外。 |
| `\w` | 文字、数字、アンダースコア。 |
| `\W` | 単語以外の文字。 |
| `\b` | 単語の境界。 |
| `\B` | 単語の境界以外の文字。 |
| `\<` | 単語の始まり。 |
| `\>` | 単語の終わり。 |
| `(...)` | 囲まれている内容をすべてキャプチャ。 |
| `(?:...)` | マーキングのないキャプチャ。出力文字列で一致を参照できないようにします。 |
| `a?` | 0 または 1 個の `a`。 |
| `a*` | 0 個以上の `a`。 |
| `a+` | 1 個以上の `a`。 |
| `a{3}` | 厳密に 3 個の `a`。 |
| `a{3,}` | 3 個以上の `a`。 |
| `a{3,6}` | 3 ～ 6 個の `a`。 |

[!UICONTROL 出力形式]では、目的の文字列出力を実現するために、これらのシーケンスを何回でも、どのような順序でも使用できます。

| 出力プレースホルダーシーケンス | 説明 |
| --- | --- |
| `$&` | 式全体に一致したものを出力します。 |
| `$n` | n 番目のサブ式に一致する値を出力します。 例： `$1` 最初のサブ式を出力します。 |
| ``$` `` | 最後に見つかった一致の終わり（前に一致が見つからなかった場合は、テキストの始まり）から、現在の一致の始まりまでのテキストを出力します。 |
| `$+` | 正規表現で最後にマークされたサブ式に一致するものを出力します。 |
| `$$` | 文字列文字 `"$"` を出力します。 |

{style="table-layout:auto"}

+++

<!-- SPLIT -->

### Split

フィールドの値を新しい派生フィールドに分割します。

+++ 詳細

## 仕様 {#split-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li></ul> | <ul><li>[!UICONTROL フィールド]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></ul><ul><li>[!UICONTROL 方法]:</li><ul><li>左から</li><li>右から</li><li>配列に変換</li></ul></li><li>区切り文字の場合：<ul><li>文字列</li></ul><li>インデックスの場合：<ul><li>数値</li></ul></li> | <p>該当なし</p> | <p>派生フィールドあたり 5 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## 使用例 1 {#split-uc1}

ボイスアプリの応答を、単一のディメンションの区切りリストに収集します。 リスト内の各値を回答レポート内の一意の値にしたいとします。

### 次より前のデータ： {#split-uc1-databefore}

| ボイスアプリの応答 | イベント |
|---|--:|
| それは素晴らしく、完璧な意味を持ち、他の人に勧められる | 1 |
| それは大きく、いくぶん混乱し、他の人に勧めるだろう | 1 |
| それは、大きくはなく、非常に混乱し、他の人に勧められなかった | 1 |

{style="table-layout:auto"}

### 派生フィールド {#split-u1-derivedfield}

次の項目を作成します。 `Responses` 派生フィールド。 次を使用します。 [!UICONTROL SPLIT] 関数を使用して、  [!UICONTROL 配列に変換] 次の値を変換する方法 [!UICONTROL ボイスアプリの応答] フィールド使用 `,` として [!UICONTROL 区切り].

![分割ルール 1 のスクリーンショット](assets/split-1.png)

### 後のデータ {#split-uc1-dataafter}

| 応答 | イベント |
|---|--:|
| それは素晴らしかった | 2 |
| 他の人に勧める | 2 |
| それは素晴らしくなかった | 1 |
| 完璧な意味を持つ | 1 |
| ややややこしい | 1 |
| 非常に混乱している | 1 |
| 他人に勧めない | 1 |

{style="table-layout:auto"}

## 使用例 2 {#split-uc2}

ボイスアプリの応答を、単一のディメンションの区切りリストに収集します。 リストの最初の値からの応答を、独自のディメンションに格納したい場合。 リストの最後の値を独自のディメンションに配置します。

### 次より前のデータ： {#split-uc2-databefore}

| 応答 | イベント |
|---|--:|
| それは素晴らしく、完全な意味を持ち、他の人々に勧められた | 1 |
| それは大きく、いくぶん混乱し、他の人に勧めるだろう | 1 |
| それは、大きくはなく、非常に混乱し、他の人に勧められなかった | 1 |

{style="table-layout:auto"}

### 派生フィールド {#split-u2-derivedfield}

次の項目を作成します。  `First Response` 派生フィールド。 次を使用します。 [!UICONTROL SPLIT] 関数を使用して、 [!UICONTROL 応答] 応答の左側のフィールド `,` を区切り文字として使用します。

![分割ルールのスクリーンショット — 最初の値](assets/split-2.png)

次の項目を作成します。 `Second Response` から最後の値を取得する派生フィールド [!UICONTROL 応答] フィールドで、右から、1 を区切り文字として、1 をインデックスとして選択します。

![分割ルールのスクリーンショット — 最後の値](assets/split-3.png)

### 後のデータ {#split-uc2-dataafter}

| 最初の応答 | イベント |
|---|--:|
| それは素晴らしかった | 2 |
| それは素晴らしくなかった | 1 |

{style="table-layout:auto"}

| 2 番目の応答 | イベント |
|---|--:|
| 他の人に勧める | 2 |
| 他人に勧めない | 1 |

{style="table-layout:auto"}

+++


<!-- TRIM -->

### トリミング

フィールド値の先頭または末尾から、空白文字、特殊文字、または文字数を新しい派生フィールドにトリミングします。

+++ 詳細

## 仕様 {#trim-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL フィールド]<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>空白をトリミング</li><li>特殊文字をトリミング<ul><li>特殊文字の入力</li></ul></li><li>左からトリミング<ul><li>送信元 <ul><li>文字列の開始</li><li>位置<ul><li>位置 #</li></ul></li><li>文字列<ul><li>文字列値</li><li>インデックス</li><li>文字列を含めるフラグ</li></ul></li></ul></li><li>設定値<ul><li>文字列の終了</li><li>位置<ul><li>位置 #</li></ul></li><li>文字列<ul><li>文字列値</li><li>インデックス</li><li>文字列を含めるフラグ</li></ul></li><li>長さ</li></ul></li></ul></li><li>右からトリミング<ul><li>送信元 <ul><li>文字列の終了</li><li>位置<ul><li>位置 #</li></ul></li><li>文字列<ul><li>文字列値</li><li>インデックス</li><li>文字列を含めるフラグ</li></ul></li></ul></li><li>設定値<ul><li>文字列の開始</li><li>位置<ul><li>位置 #</li></ul></li><li>文字列<ul><li>文字列値</li><li>インデックス</li><li>文字列を含めるフラグ</li></ul></li><li>長さ</li></ul></li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 1 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## 使用例 1 {#trim-uc1}

製品データを収集しますが、そのデータにはフラグメントレポートに含まれない空白文字が含まれます。 余分な空白を簡単にトリミングしたい

### 次より前のデータ： {#trim-uc1-databefore}

| 製品 ID | イベント |
|---|--:|
| `"prod12356 "` | 1 |
| `"prod12356"` | 1 |
| `" prod12356"` | 1 |

{style="table-layout:auto"}

### 派生フィールド {#trim-u1-derivedfield}

次の項目を作成します。 `Product Identifier` 派生フィールド。 次を使用します。 [!UICONTROL トリミング] 関数を使用して、 **[!UICONTROL 空白をトリミング]** から **[!UICONTROL 製品 ID]** フィールドに入力します。

![分割ルール 1 のスクリーンショット](assets/trim-1.png)

### 後のデータ {#trim-uc1-dataafter}

| 製品識別子 | イベント |
|---|--:|
| `"prod12356"` | 3 |

{style="table-layout:auto"}

## 使用例 2 {#trim-uc2}

収集されたページ名のデータに、削除する必要があるページ名の末尾に、誤った特殊文字が含まれています。

### 次より前のデータ： {#trim-uc2-databefore}

| 名前 | イベント |
|---|--:|
| home page# | 1 |
| home page? | 1 |
| home page% | 1 |
| home page&amp; | 1 |
| home page/ | 1 |

{style="table-layout:auto"}

### 派生フィールド {#trim-u2-derivedfield}

次の項目を作成します。  `Page Name` 派生フィールド。 次を使用します。 [!UICONTROL トリミング] 関数を使用して、 [!UICONTROL 特殊文字をトリミングする] から [!UICONTROL 名前] を使用するフィールド [!UICONTROL 特殊文字] `#?%&/`.

![分割ルールのスクリーンショット — 最初の値](assets/trim-2.png)

### 後のデータ {#trim-uc2-dataafter}

| ページ名 | イベント |
|---|--:|
| home page | 5 |

{style="table-layout:auto"}


## 使用例 3 {#trim-uc3}

storeID を含むデータを収集します。 storeID には、省略された米国の状態コードが最初の 2 文字として含まれます。 レポートでは、その状態コードのみを使用する必要があります。

### 次より前のデータ： {#trim-uc3-databefore}

| storeID | イベント |
|---|--:|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| OR234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### 派生フィールド {#trim-u3-derivedfield}

次の項目を作成します。  `Store Identifier` 派生フィールド。 次を使用します。 [!UICONTROL トリミング] 関数を使用して、 [!UICONTROL 右から切り捨て] の [!UICONTROL storeID] 文字列の終わりから位置までのフィールド `3`.

![分割ルールのスクリーンショット — 最初の値](assets/trim-3.png)

### 後のデータ {#trim-uc3-dataafter}

| ストア識別子 | イベント |
|---|--:|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| または | 1 |
| NV | 1 |

{style="table-layout:auto"}
+++


<!-- URL PARSE -->

### URL の解析

プロトコル、ホスト、パス、クエリーのパラメーターを含む、URL の様々な部分を解析します。

+++ 詳細

## 仕様 {#urlparse-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL フィールド]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL オプション]:<ul><li>[!UICONTROL プロトコルを取得]</li><li>[!UICONTROL ホストを取得]</li><li>[!UICONTROL パスを取得]</li><li>[!UICONTROL クエリ文字列値を取得]<ul><li>[!UICONTROL クエリーパラメーター]:<ul><li>文字列</li></ul></li></ul></li><li>[!UICONTROL ハッシュ値を取得]</li></ul></li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 5 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## 使用例 1 {#urlparse-uc1}

マーケティングチャネルのルールセットの一部として、参照 URL からの参照ドメインのみを使用する必要がある場合。

### 次より前のデータ： {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 派生フィールド {#urlparse-uc1-derivedfield}

次の項目を定義します。  `Referring Domain` 派生フィールド。 次を使用します。 [!UICONTROL URL 解析] 関数を使用して、 [!UICONTROL 参照 URL] フィールドに格納し、新しい派生フィールドに格納します。

![URL 解析ルール 1 のスクリーンショット](assets/url-parse-1.png)

### 後のデータ {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## 使用例 2 {#urlparse-uc2}

この値を `cid` 内のクエリー文字列のパラメーター [!DNL Page URL] 派生トラッキングコードレポートの出力の一部として。

### 次より前のデータ： {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 派生フィールド {#urlparse-uc2-derivedfield}

次の項目を定義します。 `Query String CID` 派生フィールド。 次を使用します。 [!UICONTROL URL 解析] 関数を使用して、 [!UICONTROL ページ URL] フィールド、指定する `cid` をクエリパラメーターとして使用します。 出力値は、新しい派生フィールドに格納されます。

![URL 解析ルール 2 のスクリーンショット](assets/url-parse-2.png)

### 後のデータ {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++

## 制限事項

派生フィールドの一般的な機能には、次の制限が適用されます。

- 派生フィールドのルールを定義する場合、最大 10 個の異なるスキーマフィールド（標準フィールドを除く）を使用できます。
   - この最大 10 個の異なるスキーマフィールドから、最大 3 つのルックアップスキーマまたはプロファイルスキーマフィールドのみを使用できます。
- 1 つのCustomer Journey Analytics接続につき最大 100 個の派生フィールドを指定できます。

## 詳細情報

- [データを最大限に活用する：Customer Journey Analyticsで派生フィールドを使用するためのフレームワーク](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)

- [Customer Journey Analytics用の派生フィールドの使用例](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)
