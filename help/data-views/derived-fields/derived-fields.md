---
title: 派生フィールド
description: 派生フィールドは、使用可能な関数や関数テンプレートのセットを介して、スキーマフィールドや標準コンポーネントのレポート時間操作を指定します。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
exl-id: 1ba38aa6-7db4-47f8-ad3b-c5678e5a5974
badgeDerivedFields: label="New Feature" type="Positive"
source-git-commit: f9aafab436fa1f26be9ed2e433ded046bbb1135a
workflow-type: tm+mt
source-wordcount: '3218'
ht-degree: 9%

---


# 派生フィールド

{{release-limited-testing}}

派生フィールドは、Customer Journey Analytics(CJA) のリアルタイムレポート機能の重要な側面です。 派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。その派生フィールドを、 [Workspace](../../analysis-workspace/home.md) または、派生フィールドを [データビュー](../data-views.md).

派生フィールドを使用すると、CJA 以外の他の場所でデータを変換または操作する場合と比べて、大幅な時間と労力を節約できます。 例： [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja), [データDistiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)または独自の変換読み込みの抽出 (ETL)/読み込み変換の抽出 (ELT) プロセス内で実行できます。

派生フィールドは、 [データビュー](../data-views.md)は、ルールとして定義された一連の関数に基づき、使用可能な標準フィールドやスキーマフィールドに適用されます。

使用例を次に示します。

- 収集された不適切なページ名の値を修正し、ページ名の値を正しく修正する、派生した「ページ名」フィールドを定義します。

- 1 つ以上の条件（URL パラメーター、ページ URL、ページ名など）に基づいて適切なマーケティングチャネルを決定する、派生マーケティングチャネルフィールドを定義します。

## 派生フィールドインターフェイス

派生フィールドを作成または編集する場合、派生フィールドインターフェイスを使用します。

![派生フィールドダイアログ](assets/derived-field-dialog.png)


|  | 名前 | 説明 |
|---------|----------|--------|
| 1 | **セレクター** | セレクター領域を使用して、関数、関数テンプレート、スキーマフィールドまたは標準フィールドを選択し、ルールビルダーにドラッグ&amp;ドロップします。 <br/>ドロップダウンを使用して、次の中から選択します。 <br/>![関数](assets/Smock_Function_18_N.svg) [!UICONTROL 関数]  — 使用可能なリスト [関数](#function-reference), </br>![関数テンプレートアイコン](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL 関数テンプレート]  — 使用可能なリスト [関数テンプレート](#function-templates), <br/>![スキーマフィールドアイコン](assets/Smock_Folder_18_N.svg)  [!UICONTROL スキーマフィールド]  — データセットカテゴリ（イベント、プロファイル、ルックアップ）や以前に定義した派生フィールドから使用できるフィールドを一覧表示し、 <br/>![標準フィールドアイコン](assets/Smock_DragHandle_18_N.svg) [!UICONTROL 標準フィールド]  — 標準の使用可能フィールド（プラットフォームデータセット ID など）。 セレクターには、文字列および数値の標準フィールドのみが表示されます。 関数が他のデータ型をサポートしている場合、ルールインターフェイス内の値やフィールドに対して、これらの他のデータ型を持つ標準フィールドを選択できます。<br/>関数、関数テンプレート、スキーマ、標準フィールドは、 ![検索アイコン](assets/Smock_Search_18_N.svg) 検索ボックス。 <br/>選択したオブジェクトのリストをフィルタするには、 ![フィルターアイコン](assets/Smock_Filter_18_N.svg) フィルターを設定し、 [!UICONTROL 次の条件でフィールドをフィルター] ダイアログ。 フィルターを簡単に削除するには、 ![閉じるアイコン](assets/CrossSize75.svg) フィルターごとに |
| 2 | **ルールビルダー** | 派生フィールドは、1 つ以上のルールを使用して順番に作成します。 ルールは、関数の特定の実装なので、常に 1 つの関数にのみ関連付けられます。 ルールを作成するには、関数をルールビルダーにドラッグ&amp;ドロップします。 関数の型によって、ルールのインターフェイスが決まります。<br/>詳しくは、 [ルールインターフェイス](#rule-interface) を参照してください。 <br/>関数は、ルールビルダーで既に使用可能なルールの開始、終了または中間に挿入できます。 ルールビルダーの最後のルールによって、派生フィールドの最終出力が決まります。 |
| 3 | **[!UICONTROL **&#x200B;フィールド設定&#x200B;**]** | 派生フィールドに名前を付け、説明し、そのフィールドタイプを調べることができます。 |
| 4 | **[!UICONTROL **&#x200B;最終出力&#x200B;**]** | この領域には、過去 30 日間のデータと、ルールビルダーの派生フィールドに加えた変更に基づき、出力値のプレビューがその場で表示されます。 |

{style="table-layout:auto"}

## フィールドテンプレートウィザード

派生フィールドのインターフェイスに初めてアクセスした場合、 [!UICONTROL フィールドテンプレートから開始] ウィザードが表示されます。

1. 作成しようとしているフィールドのタイプに最も適したテンプレートを選択します。
2. を選択します。 **[!UICONTROL **&#x200B;選択&#x200B;**]** ボタンをクリックして続行します。

派生フィールドダイアログには、選択したフィールドのタイプに必要なルール（および関数）が入力されます。また、このルールは、選択したフィールドのタイプに役立ちます。 詳しくは、 [関数テンプレート](#function-templates) を参照してください。

## ルールインターフェイス

ルールビルダーでルールを定義する場合、ルールインターフェイスを使用します。

![ルールインターフェイス](assets/rule-interface.png)

|  | 名前 | 説明 |
|---------|----------|--------|
| A | **ルール名** | デフォルトでは、ルール名は **ルール X** （X はシーケンス番号を参照）。 ルールの名前を編集するには、ルールの名前を選択し、新しい名前を入力します（例： ）。 `Query Parameter`. |
| B | **関数名** | ルールの選択された関数名（例： ）。 [!UICONTROL URL 解析]. 関数が関数のシーケンスの最後で、最終的な出力値を決定する場合、関数名の後に [!UICONTROL  — 最終出力]例： [!UICONTROL URL 解析 — 最終出力]. <br/>関数の詳細情報を含むポップアップを表示するには、 ![ヘルプアイコン](assets/Smock_HelpOutline_18_N.svg). |
| C | **ルールの説明** | オプションで、ルールに説明を追加できます。<br/>選択 ![その他のアイコン](assets/More.svg)を選択し、「 **[!UICONTROL **&#x200B;説明を追加&#x200B;**]** 説明を追加するには、または **[!UICONTROL **&#x200B;説明を編集&#x200B;**]** 既存の説明を編集する場合。<br/>説明を入力するには、エディターを使用します。 ツールバーを使用して、テキストの書式設定（スタイルセレクター、太字、斜体、下線、右、左、中央揃え、色、番号リスト、箇条書きリストを使用）や、外部情報へのリンクの追加を行うことができます。 <br/>説明の編集を終了するには、エディターの外側をクリックします。 |
| D | **機能領域** | 関数のロジックを定義します。 インターフェイスは、関数のタイプによって異なります。 のドロップダウン [!UICONTROL フィールド] または [!UICONTROL 値] は、関数が想定する入力のタイプに基づいて、使用可能なフィールド（ルール、標準フィールド、フィールド）のすべてのカテゴリを表示します。 詳しくは、 [関数リファレンス](#function-reference) を参照してください。 |

{style="table-layout:auto"}

## 派生フィールドの作成

1. 既存のデータビューを選択するか、データビューを作成します。 詳しくは、 [データビュー](../data-views.md) を参照してください。

2. を選択します。 **[!UICONTROL **&#x200B;コンポーネント&#x200B;**]** 」タブをクリックします。

3. 選択 **[!UICONTROL **&#x200B;派生フィールドを作成&#x200B;**]** をクリックします。

4. 派生フィールドを定義するには、 [!UICONTROL 派生フィールドを作成] インターフェイス。 詳しくは、 [派生フィールドインターフェイス](#derived-field-interface).

   新しい派生フィールドを保存するには、「 」を選択します。 **[!UICONTROL **&#x200B;保存&#x200B;**]**.

5. 新しい派生フィールドが [!UICONTROL 派生フィールド >] コンテナ、 **[!UICONTROL **&#x200B;スキーマフィールド&#x200B;**]** をクリックします。


## 派生フィールドの編集

1. 既存のデータビューを選択します。 詳しくは、 [データビュー](../data-views.md) を参照してください。

2. を選択します。 **[!UICONTROL **&#x200B;コンポーネント&#x200B;**]** 」タブをクリックします。

3. 選択 **[!UICONTROL **&#x200B;スキーマフィールド&#x200B;**]** 」タブをクリックします。 [!UICONTROL 接続] 」パネルを開きます。

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


## 関数テンプレート

特定の使用例に対して派生フィールドをすばやく作成するために、関数テンプレートを使用できます。 これらの関数テンプレートは、派生フィールドインターフェイスのセレクター領域からアクセスできます。また、 [!UICONTROL フィールドテンプレートから開始] ウィザード。


### マーケティングチャネル

このテンプレートは、 [Url 解析](#dnl-url-parse) および [例：](#dnl-case-when) は複数回関数を使用して、URL から適切な値を取得します。 次に、これらの値にロジックが適用され、URL が特定のマーケティングチャネルに関連付けられます。

+++ 詳細

このテンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、 [関数リファレンス](#function-reference) を参照してください。

![マーケティングチャネルテンプレートのルールビルダー](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## 関数リファレンス

サポートされる各関数について、以下の詳細を確認します。

- 仕様：
   - 入力データタイプ：サポートされるデータのタイプ
   - 入力：入力に指定可能な値
   - 含まれる演算子：この関数でサポートされる演算子（存在する場合）
   - 制限事項：この特定の関数に適用される制限
   - 出力。

- 次のような使用例です。
   - 派生フィールドを定義する前のデータ
   - 派生フィールドの定義方法、
   - データを更新しました。

- 制約（該当する場合）


<!-- Concatenate -->

### 連結

2 つ以上のフィールド、派生フィールド、またはユーザーが入力した値を、定義済みの区切り文字で 1 つのフィールドに結合します。

+++ 詳細

## 仕様 {#concatenate-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <p>文字列</p> | <ul><li>各 [!UICONTROL 値]:<ul><li>規則</li><li>標準フィールド</li><li>フィールド</li><li>ユーザー入力</li></ul></li><li>各 [!UICONTROL 区切り]:<ul><li>ユーザー入力</li></ul></li> </ul> | <p>該当なし</p> | <p>派生フィールドあたり 2 つの関数</p> | <p>新しい派生フィールド</p> |

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


### 次より前のデータ {#concatenate-uc-databefore}

| 接触チャネル | 宛先 |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 派生フィールド {#concatenate-derivedfield}

新しい [!UICONTROL Origin - Destination] 派生フィールド。 次を使用する [!UICONTROL 連結] 関数を使用して [!UICONTROL オリジナル] および [!UICONTROL 宛先] を使用するフィールド `-` [!UICONTROL 区切り].

![連結ルール](assets/concatenate.png)

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

<!-- CASE WHEN -->

### Case When

1 つ以上のフィールドの定義された条件に基づいて条件を適用します。 次に、これらの条件を使用して、条件の順序に基づいて新しい派生フィールドの値を定義します。

+++ 詳細

## 仕様 {#casewhen-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>各 [!UICONTROL If], [!UICONTROL Else If] コンテナ：</p><ul><li>[!UICONTROL 値]</li><ul><li>規則</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL 条件] （選択した値のタイプに基づく、含まれる演算子を参照）</li></ul></li><li>各 [!UICONTROL 次に、値を], [!UICONTROL それ以外の場合は、値をに設定します。]:</p><ul><li>[!UICONTROL 値]</li><ul><li>規則</li><li>標準フィールド</li><li>フィールド</li></ul></ul></li></ul> | <p>文字列</p><ul><li>次と等しい</li><li>いずれかの語句と等しい</li><li>フレーズを含む</li><li>いずれかの語句を含む</li><li>すべての語句を含む</li><li>次の語句で始まる</li><li>任意の語句で始まる</li><li>次の語句で終わる</li><li>任意の語句で終わる</li><li>次と等しくない</li><li>いずれの語句も含まない</li><li>このフレーズを含まない</li><li>いずれの語句も含まない</li><li>すべての語句を含まない</li><li>次で始まらない</li><li>どの用語でも始まらない</li><li>次で終わらない</li><li>次の語句で終わらない</li><li>設定済み</li><li>未設定</li></ul><p>数値</p><ul><li>次と等しい</li><li>次と等しくない</li><li>次より大きい</li><li>次よりも大きいか等しい</li><li>次より小さい</li><li>次よりも小さいか等しい</li><li>設定済み</li><li>未設定</li></ul><p>日付</p><ul><li>次と等しい</li><li>次と等しくない</li><li>次より後</li><li>次より後または等しい</li><li>次の値より前</li><li>次より前または等しい</li><li>設定済み</li><li>未設定</li></ul> | <ul><li>派生フィールドあたり 5 個の関数</li><li>派生フィールドあたり 200 個の演算子。 例えば、「参照ドメインに Google が含まれる」などが 1 つの演算子です。 </li></ul> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## 使用例 1 {#casewhen-uc1}

様々なマーケティングチャネルを識別するルールを定義するには、カスケードロジックを適用してマーケティングチャネルフィールドを適切な値に設定します。

- リファラーが検索エンジンからのもので、ページにクエリー文字列値が含まれている場合、 `cid` 次を含む `ps_`に値を指定する場合、マーケティングチャネルは [!DNL *有料検索*].
- リファラーが検索エンジンからのもので、ページにクエリ文字列がない場合 `cid`に値を指定する場合、マーケティングチャネルは [!DNL *自然検索*].
- ページにクエリー文字列値がある場合、 `cid` 次を含む `em_`に値を指定する場合、マーケティングチャネルは [!DNL *電子メール*].
- ページにクエリー文字列値がある場合、 `cid` 次を含む `ds_`に値を指定する場合、マーケティングチャネルは [!DNL *ディスプレイ広告*].
- ページにクエリー文字列値がある場合、 `cid` 次を含む `so_`に値を指定する場合、マーケティングチャネルは [!DNL *有料ソーシャル*].
- リファラーがの参照ドメインからのものである場合 [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com]または [!DNL tiktok.com]に値を指定する場合、マーケティングチャネルは [!DNL *自然社会*].
- 上記のルールがいずれも一致しない場合は、マーケティングチャネルを [!DNL *その他のリファラー*].

サイトが以下のサンプルイベントを受け取った場合、 [!UICONTROL リファラー] および [!UICONTROL ページ URL]に設定する場合、これらのイベントは次のように識別する必要があります。

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 |  | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### 次より前のデータ {#casewhen-uc1-databefore}

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

新しい `Marketing Channel` 派生フィールド。 次を使用する [!UICONTROL 次の場合にケース] 関数を使用して、両方の `Page URL` および `Referring URL` フィールドに入力します。

関数の使用に注意してください [!UICONTROL URL 解析] 値を取得するルールを定義するには `Page Url` および `Referring Url` の前 [!UICONTROL 次の場合にケース] ルールが適用されます。

![ルール 1 の場合](assets/case-when-1.png)

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

サイトで [!DNL Product Finding Methods] ディメンション。 最後に、これらの値はすべて検索を示します。

| 収集された値 | 実際の値 |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes ] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### 次より前のデータ {#casewhen-uc2-databefore}

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

次の項目を定義します。 `Product Finding Methods (new)` 派生フィールド。 次を作成します [!UICONTROL 次の場合にケース] ルールビルダーのルール。 これらのルールは、古い [!UICONTROL 製品検索方法] フィールド値 `search` および `browse` の使用 [!UICONTROL フレーズを含む] 条件

![ルール 2 の場合](assets/case-when-2.png)

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

### 次より前のデータ {#casewhen-uc3-databefore}

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

次の項目を定義します。 `Trip Duration (bucketed)` 派生フィールド。 次を作成します [!UICONTROL 次の場合にケース] ルールビルダーのルール。 このルールは、古い [!UICONTROL 旅行期間] フィールドの値を 3 つの値に変換します。 `short trip`, `medium  trip`、および `long trip`.

![ルール 3 の場合](assets/case-when-3.png)


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


## 制約

CJA は、Adobe Experience Platformの [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja) （エクスペリエンスデータモデル）。 詳しくは、 [コンテナ](../create-dataview.md#containers) および [フィルターコンテナ](../../components/filters/filters-overview.md#filter-containers) を参照してください。 このコンテナモデルは、本来は柔軟ですが、ルールビルダーを使用する際に一部の制約が課されます。

CJA は、次のデフォルトのコンテナモデルを使用します。

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>



次の制約が適用され、適用されるのは *選択* および *設定* 値。

|  | 制約 |
|:---:|----|
| **<span style='color: red'>A</span>** | 値 *選択* 同じ内部で [!UICONTROL If], [!UICONTROL Else If] 構文 ( [!UICONTROL および] または [!UICONTROL または]) ルール内では、同じコンテナから始まる必要があり、任意のタイプ（文字列）を指定できます ![文字列](assets/Smock_ABC_18_N.svg)，数値 ![数値](assets/Smock_123_18_N.svg)など ) を含める必要があります。 <br/>![依存関係 A](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | すべての値 *設定* ルールの間は、同じコンテナに属し、同じタイプまたは同じタイプの派生値を持つ必要があります。 <br/> ![依存関係 B](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | 指定した値 *選択* 横 [!UICONTROL If], [!UICONTROL Else If] ルール内の構成では、次の処理が行われます *not* 同じコンテナから派生し、同じコンテナから派生する必要がある *not* 同じタイプである必要があります。 <br/> ![依存関係 C](assets/dependency-c.png) |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### 検索と置換

選択したフィールド内のすべての値を検索し、新しい派生フィールド内の別の値に置き換えます。

+++ 詳細

## 仕様 {#findreplace-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <p>文字列</p> | <ul><li>条件の場合：<ul><li>[!UICONTROL 値]<ul><li>規則</li><li>標準フィールド</li><li>フィールド</li></ul></li></ul></li><li>各 [!UICONTROL すべて検索], [!UICONTROL を置き換え、すべてを]:<ul><li>[!UICONTROL 値]</li><ul><li>ユーザー入力</li></ul></li></ul></ul> | <p>文字列</p><ul><li>[!UICONTROL すべて検索], [!UICONTROL を置き換え、すべてを]</li></ul> | <p>派生フィールドあたり 5 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース {#findreplace-uc}

外部マーケティングチャネルレポートの値の形式が正しくありません。例： `email%20 marketing` の代わりに `email marketing`. これらの不正な値により、レポートが破壊され、E メールのパフォーマンスがより難しくなります。 置き換えますか？ `email%20marketing` と `email marketing`.

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


### 次より前のデータ {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### 派生フィールド {#findreplace-uc-derivedfield}

次を定義します。 `Email Marketing (updated)` 派生フィールド。 次を使用する [!UICONTROL 検索と置換] 関数を使用して、 `email%20marketing` と `email marketing`.

![検索と置換のルール](assets/find-and-replace.png)

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

対応する値に置き換えられる参照値のセットを定義します。

+++ 詳細


## 仕様 {#lookup-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>の場合 [!UICONTROL ルックアップを適用するフィールド]:<ul><li>規則</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>の場合 [!UICONTROL 値が] および [!UICONTROL 値の置換文字列]:</p><ul><li>ユーザー入力</li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 5 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## 使用例 1 {#lookup-uc1}

次のキー列を含む CSV ファイルがあります： `hotelID` および `hotelID`: `city`, `rooms`, `hotel name`.
収集しています [!DNL Hotel ID] ディメンション内で、 [!DNL Hotel Name] から派生したディメンション `hotelID` を CSV ファイルに追加します。

**CSV ファイルの構造とコンテンツ**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |

{style="table-layout:auto"}

**現在のレポート**

| [!DNL Hotel ID] | 製品表示 |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |

{style="table-layout:auto"}


**目的のレポート**

| [!DNL Hotel Name] | 製品表示 |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### 次より前のデータ {#lookup-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |

{style="table-layout:auto"}


### 派生フィールド {#lookup-uc1-derivedfield}

次の項目を定義します。 `Hotel Name` 派生フィールド。 次を使用する [!UICONTROL 参照] 関数を使用して、 [!UICONTROL ホテル ID] フィールドに値を入力し、新しい値に置き換えます。

![参照ルール 1](assets/lookup-1.png)

### 後のデータ {#lookup-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## 使用例 2 {#lookup-uc2}

複数のページのわかりやすいページ名の代わりに URL を収集した。 この値の組み合わせコレクションは、レポートを壊します。

### 次より前のデータ {#lookup-uc2-databefore}

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

### 派生フィールド {#lookup-uc2-derivedfield}

次の項目を定義します。 `Page Name (updated)` 派生フィールド。 次を使用する [!UICONTROL 参照] 関数を使用して、既存の [!UICONTROL ページ名] フィールドに入力し、更新された正しい値に置き換えます。

![ルックアップルール 2](assets/lookup-2.png)

### 後のデータ {#lookup-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |

+++

<!-- URL PARSE -->

### URL の解析

プロトコル、ホスト、パス、クエリーのパラメーターを含む、URL の様々な部分を解析します。

+++ 詳細

## 仕様 {#urlparse-io}

| データタイプを入力 | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>の場合 [!UICONTROL フィールド]:</li><ul><li>規則</li><li>標準フィールド</li><li>フィールド</li></ul><li>の場合 [!UICONTROL オプション]:<ul><li>[!UICONTROL プロトコルを取得]</li><li>[!UICONTROL ホストを取得]</li><li>[!UICONTROL パスを取得]</li><li>[!UICONTROL クエリ文字列値を取得]<ul><li>[!UICONTROL クエリーパラメーター]:<ul><li>ユーザー入力</li></ul></li></ul></li><li>[!UICONTROL ハッシュ値を取得]</li></ul></li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドあたり 5 個の関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## 使用例 1 {#urlparse-uc1}

マーケティングチャネルのルールセットの一部として、参照 URL からの参照ドメインのみを使用する必要がある場合。

### 次より前のデータ {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 派生フィールド {#urlparse-uc1-derivedfield}

次の項目を定義します。  `Referring Domain` 派生フィールド。 次を使用する [!UICONTROL URL 解析] 関数を使用して、 [!UICONTROL 参照 URL] フィールドに格納し、新しい派生フィールドに格納します。

![ URL 解析ルール 1](assets/url-parse-1.png)

### 後のデータ {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## 使用例 2 {#urlparse-uc2}

次の `cid` 内のクエリー文字列のパラメーター [!DNL Page URL] 派生トラッキングコードレポートの出力の一部として。

### 次より前のデータ {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 派生フィールド {#urlparse-uc2-derivedfield}

次の項目を定義します。 `Query String CID` 派生フィールド。 次を使用する [!UICONTROL URL 解析] 関数を使用して、 [!UICONTROL ページ URL] フィールド、指定 `cid` をクエリパラメーターとして使用します。 出力値は、新しい派生フィールドに格納されます。

![URL 解析ルール 2](assets/url-parse-2.png)

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

- 派生フィールドのルールを定義する場合、最大 100 個の異なるスキーマフィールド（標準フィールドを除く）を使用できます。
- CJA 接続あたり最大 100 個の派生フィールドを持つことができます。
