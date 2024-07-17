---
title: 派生フィールド
description: 派生フィールドは、使用可能な関数および関数テンプレートのセットを使用して、スキーマフィールドや標準コンポーネントのレポート時間操作を指定します。
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
source-git-commit: 0a046a89e1742d3470a78ebad4f93cb3b4ea7f4c
workflow-type: tm+mt
source-wordcount: '8366'
ht-degree: 12%

---

# 派生フィールド

派生フィールドは、Adobe Customer Journey Analyticsのリアルタイムレポート機能の重要な側面になります。 派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。その派生フィールドを [Workspaceのコンポーネント （指標またはディメンション）として使用したり ](../../analysis-workspace/home.md) さらに派生フィールドを [ データビュー ](../data-views.md) のコンポーネントとして定義したりできます。

派生フィールドを使用すると、Customer Journey Analytics外の他の場所でデータを変換または操作する場合と比較して、大幅な時間と労力を節約できます。 [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)、[Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)、独自の ETL （Extract Transform Load）/ELT （Extract Load Transform）プロセスなど。

派生フィールドは、[ データビュー ](../data-views.md) 内で定義され、ルールとして定義された一連の関数に基づいており、使用可能な標準フィールドやスキーマフィールドに適用されます。

例えば、次のようなユースケースがあります。

- 収集した不適切なページ名の値を修正してページ名の値を修正する、派生ページ名フィールドを定義します。

- 1 つ以上の条件（例：URL パラメーター、ページ URL、ページ名）に基づいて適切なマーケティングチャネルを決定する、派生マーケティングチャネルフィールドを定義します。

## 派生フィールドインターフェイス

派生フィールドを作成または編集する場合は、派生フィールドインターフェイスを使用します。

![ 派生フィールドダイアログのスクリーンショット ](assets/derived-field-dialog.png)


|  | 名前 | 説明 |
|---------|----------|--------|
| 1 | **セレクター** | セレクター領域を使用して、関数、関数テンプレート、スキーマフィールド、または標準フィールドを選択してルールビルダーにドラッグ&amp;ドロップします。 <br/> ドロップダウンを使用して、次のいずれかを選択します。<br/>![ 関数 ](assets/Smock_Function_18_N.svg) [!UICONTROL  関数 ] – 使用可能なリスト [ 関数 ](#function-reference)、</br>![ 関数テンプレートアイコン ](assets/Smock_FileTemplate_18_N.svg)[!UICONTROL  関数テンプレート ] – 使用可能なリスト [ 関数テンプレート ](#function-templates)、<br/>![ スキーマフィールドアイコン ](assets/Smock_Folder_18_N.svg)[!UICONTROL  スキーマフィールド ] - データセットカテゴリ（イベント、プロファイル、ルックアップ）および以前定義した派生フィールドから使用可能なフィールド、<br/>![ 標準フィールドアイコン ](assets/Smock_DragHandle_18_N.svg)  – 標準の使用可能なフィールド（Platform データセット ID など）。 文字列および数値の標準フィールドのみがセレクターに表示されます。 関数が他のデータタイプをサポートしている場合、これらの他のデータタイプを持つ標準フィールドを、値またはルールインターフェイス内のフィールドに選択できます。<br/> 関数、関数テンプレート、スキーマおよび標準フィールドは、「![ 検索アイコン ](assets/Smock_Search_18_N.svg) 検索ボックスを使用して検索できます。 <br/> 選択したオブジェクトリストをフィルタリングするには、「![ フィルターアイコン ](assets/Smock_Filter_18_N.svg)」を選択し、「[!UICONTROL  フィールドのフィルター ]」ダイアログでフィルターを指定します。 フィルターごとに ![ 閉じるアイコン ](assets/CrossSize75.svg) を使用して、フィルターを簡単に削除できます。 |
| 2 | **ルールビルダー** | 1 つ以上のルールを使用して、派生フィールドを順番に作成します。 ルールは関数の特定の実装なので、常に 1 つの関数にのみ関連付けられます。 ルールを作成するには、関数をルールビルダーにドラッグ&amp;ドロップします。 関数タイプは、ルールのインターフェイスを決定します。<br/> 詳しくは、[ ルールインターフェイス ](#rule-interface) を参照してください。 <br/> 関数は、ルールビルダーで既に使用可能なルールの先頭、末尾、またはその間に挿入できます。 ルールビルダーの最後のルールによって、派生フィールドの最終的な出力が決定されます。 |
| 3 | **[!UICONTROL ** フィールド設定 **]** | 派生フィールドに名前を付けて説明し、そのフィールドタイプを調べることができます。 |
| 4 | **[!UICONTROL ** 最終出力 **]** | この領域には、過去 30 日間のデータと、ルールビルダーで派生フィールドに加えた変更に基づいて、出力値を即座に更新したプレビューが表示されます。 |

{style="table-layout:auto"}

## フィールドテンプレートウィザード

派生フィールドインターフェイスに初めてアクセスすると、[!UICONTROL  フィールドテンプレートで開始 ] ウィザードが表示されます。

1. 作成しようとしているフィールドのタイプに最も近いテンプレートを選択します。
2. 「**[!UICONTROL ** 選択 **]**」ボタンを選択して続行します。

派生フィールドダイアログには、選択したフィールドのタイプに必須または便利なルール（および関数）が入力されます。 使用可能なテンプレートについて詳しくは、[ 関数テンプレート ](#function-templates) を参照してください。

## ルールインターフェイス

ルールビルダーでルールを定義する場合は、ルールインターフェイスを使用します。

![ 派生フィールドルールインターフェイスのスクリーンショット ](assets/rule-interface.png)

|  | 名前 | 説明 |
|---------|----------|--------|
| A | **ルール名** | デフォルトでは、ルール名は **Rule X** （X はシーケンス番号を表します）です。 ルールの名前を編集するには、ルールの名前を選択し、新しい名前（例：`Query Parameter`）を入力します。 |
| B | **関数名** | ルール用に選択された関数名（例：[!UICONTROL URL PARSE]）。 関数が関数のシーケンスの最後にあり、最終的な出力値を決定する場合、関数名の後に [!UICONTROL - FINAL OUTPUT] が続きます。例：[!UICONTROL URL PARSE - FINAL OUTPUT]。 <br/> 関数の詳細をポップアップに表示するには、![ ヘルプアイコン ](assets/Smock_HelpOutline_18_N.svg) を選択します。 |
| C | **ルールの説明** | オプションで、ルールに説明を追加できます。<br/> 詳細アイコン ![ を選択して ](assets/More.svg) 説明を追加するには **[!UICONTROL ** 説明を追加 **]** を選択し、既存の説明を編集するには **[!UICONTROL ** 説明を編集 **]** を選択します。<br/> エディターを使用して説明を入力します。 ツールバーを使用して、テキストの書式を設定したり（スタイルセレクター、太字、斜体、アンダーライン、右、左、中央、カラー、番号リスト、箇条書きを使用）、外部情報へのリンクを追加したりできます。 <br/> 説明の編集を終了するには、エディターの外側をクリックします。 |
| D | **関数領域** | 関数のロジックを定義します。 インターフェイスは、関数のタイプによって異なります。 [!UICONTROL  フィールド ] または [!UICONTROL  値 ] のドロップダウンには、関数で想定される入力のタイプに基づいて、使用可能なすべてのフィールドのカテゴリ（ルール、標準フィールド、フィールド）が表示されます。 または、スキーマと標準フィールド セレクターからフィールドをフィールドまたは値にドラッグ&amp;ドロップすることもできます。 ドラッグされたフィールドがルックアップデータセットから派生している場合、ルックアップ関数は、定義した関数の前に自動的に挿入されます。 <br/> サポートされる各関数の詳細については、[ 関数リファレンス ](#function-reference) を参照してください。 |

{style="table-layout:auto"}

## 派生フィールドの作成

1. 既存のデータビューを選択するか、データビューを作成します。 詳しくは、[ データビュー ](../data-views.md) を参照してください。

2. データビューの **[!UICONTROL ** コンポーネント **]** タブを選択します。

3. 左パネルから「**[!UICONTROL ** 派生フィールドを作成 **]**」を選択します。

4. 派生フィールドを定義するには、[!UICONTROL  派生フィールドを作成 ] インターフェイスを使用します。 [ 派生フィールドインターフェイス ](#derived-field-interface) を参照してください。

   新しい派生フィールドを保存するには、「**[!UICONTROL ** 保存 **]**」を選択します。

5. 新しい派生フィールドが、データビューの左側のパネルにある [!UICONTROL  スキーマフィールド **]** の一部として、**[!UICONTROL ** 派生フィールド/] コンテナに追加されます。


## 派生フィールドの編集

1. 既存のデータビューを選択します。 詳しくは、[ データビュー ](../data-views.md) を参照してください。

2. データビューの **[!UICONTROL ** コンポーネント **]** タブを選択します。

3. 左側の **[!UICONTROL ** 接続 **]** パネルにある [!UICONTROL  スキーマフィールド ] タブを選択します。

4. **[!UICONTROL ** 派生フィールド/**]** コンテナを選択します。

5. 編集する派生フィールドの上にマウスポインターを置いて、「編集アイコン ![ を選択し ](assets/Smock_Edit_18_N.svg) す。

6. 派生フィールドを編集するには、「[!UICONTROL  派生フィールドを編集 ] インターフェイスを使用します。 [ 派生フィールドインターフェイス ](#derived-field-interface) を参照してください。

   - 「**[!UICONTROL ** 保存 **]**」を選択して、更新した派生フィールドを保存します。

   - 派生フィールドに加えた変更をキャンセルするには、「**[!UICONTROL ** キャンセル **]**」を選択します。

   - 「**[!UICONTROL ** 名前を付けて保存 **]**」を選択して、派生フィールドを新しい派生フィールドとして保存します。 新しい派生フィールドの名前は、編集した元の派生フィールドと同じで、`(copy)` が追加されています。

または、派生フィールドをデータビューのディメンションまたは指標のコンポーネントとして使用した場合は、次のようになります。

1. コンポーネントを選択します。 コンポーネントは、派生フィールドとは異なる名前を持つ場合があることに注意してください。

1. コンポーネントパネルで、スキーマフィールド名の下の派生フィールドの横にある ![ 編集アイコン ](assets/Smock_Edit_18_N.svg) を選択します。

1. 派生フィールドを編集するには、「[!UICONTROL  派生フィールドを編集 ] インターフェイスを使用します。 [ 派生フィールドインターフェイス ](#derived-field-interface) を参照してください。

   - 「**[!UICONTROL ** 保存 **]**」を選択して、更新した派生フィールドを保存します。

   - 派生フィールドに加えた変更をキャンセルするには、「**[!UICONTROL ** キャンセル **]**」を選択します。

   - 「**[!UICONTROL ** 名前を付けて保存 **]**」を選択して、派生フィールドを新しい派生フィールドとして保存します。 新しい派生フィールドの名前は、編集した元の派生フィールドと同じで、`(copy)` が追加されています。



## 派生フィールドの削除

1. 既存のデータビューを選択します。 詳しくは、[ データビュー ](../data-views.md) を参照してください。

2. データビューの **[!UICONTROL ** コンポーネント **]** タブを選択します。

3. **[!UICONTROL ** 接続 **]** ペインの「[!UICONTROL  スキーマフィールド ]」タブを選択します。

4. **[!UICONTROL ** 派生フィールド/**]** コンテナを選択します。

5. 削除する派生フィールドの上にマウスポインターを置いて、「編集アイコン ![ を選択し ](assets/Smock_Edit_18_N.svg) す。

6. [!UICONTROL  派生フィールドを編集 ] インターフェイスで、「**[!UICONTROL 削除]**」を選択します。

   削除を確認する [!UICONTROL  コンポーネントを削除 ] ダイアログが表示されます。 データビューの外部の派生フィールドに外部参照が存在する可能性があることを考慮してください。

   - 「**[!UICONTROL ** 続行 **]**」を選択して、派生フィールドを削除します。

または、派生フィールドをデータビューのディメンションまたは指標のコンポーネントとして使用した場合は、次のようになります。

1. コンポーネントを選択します。 コンポーネントは、派生フィールドとは異なる名前を持つ場合があることに注意してください。

1. コンポーネントパネルで、スキーマフィールド名の下の派生フィールドの横にある ![ 編集アイコン ](assets/Smock_Edit_18_N.svg) を選択します。

1. [!UICONTROL  派生フィールドを編集 ] インターフェイスで、「**[!UICONTROL 削除]**」を選択します。

   削除を確認する [!UICONTROL  コンポーネントを削除 ] ダイアログが表示されます。 データビューの外部の派生フィールドに外部参照が存在する可能性があることを考慮してください。

   - 「**[!UICONTROL ** 続行 **]**」を選択して、派生フィールドを削除します。

>[!NOTE]
>
>派生フィールドは、Customer Journey Analyticsの接続レベルで管理されます。 その接続に関連付けられたいずれかのデータビューの派生フィールドに加えられた変更は、関連付けられたすべてのデータビューに適用されます。



## 関数テンプレート

特定のユースケースの派生フィールドをすばやく作成するために、関数テンプレートを使用できます。 これらの関数テンプレートは、派生フィールドインターフェイスのセレクター領域からアクセスすることも、[!UICONTROL  フィールドテンプレートで開始 ] ウィザードで初めて使用するときに表示することもできます。


### マーケティングチャネル

この関数テンプレートは、ルールのコレクションを使用してマーケティングチャネルを作成します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ マーケティングチャネルテンプレートルールビルダーのスクリーンショット ](assets/function-template-marketing-channel-template.png)

+++

### バウンス数

この関数テンプレートは、ルールのコレクションを使用して、サイトバウンスを識別します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ バウンスルールビルダーのスクリーンショット ](assets/function-template-bounces.png)

+++

### マルチディメンション結合

この関数テンプレートは、2 つの値を 1 つに結合します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ 複数Dimensionの結合ルールビルダーのスクリーンショット ](assets/function-template-multi-dimension-combine.png)

+++

### わかりやすいデータセット名

この関数テンプレートは、読み取り可能なデータセット名を提供します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ わかりやすいデータセット名ルールビルダーのスクリーンショット ](assets/function-template-friendly-dataset-name.png)

+++

### URL からのページ名

この関数テンプレートは、単純なページ名を作成します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![URL ルールビルダーからのページ名のスクリーンショット ](assets/function-template-page-name-from-url.png)

+++

### ホリデーシーズン

この関数テンプレートは、年の主な時期を分類します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ ホリデーシーズンルールビルダーのスクリーンショット ](assets/function-template-holiday-season.png)

+++

### 月間目標

この関数テンプレートは、カスタムの月次目標を設定します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ 月別目標ルールビルダーのスクリーンショット ](assets/function-template-monthly-goals.png)

+++

### 区切りリストのすべての値を取得

この関数テンプレートは、制限リストを配列に変換します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ 区切りリストルールビルダーですべての値を取得のスクリーンショット ](assets/function-template-get-all-values-in-delimited-list.png)

+++

### 区切りリストの最初の値を取得

この関数はテンプレート区切り文字リスト内の最初の値を取得します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは [関数リファレンス](#function-reference) を参照してください。

![区切り文字で区切られたリスト ルールビルダーの「Get First 値」のスクリーンショット](assets/function-template-get-first-value-in-delimited-list.png)

+++

### 区切りリストの最後の値を取得

この関数テンプレートは、区切られたリストの最後の値を取得します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ 区切りリストルールビルダーでの最後の値の取得のスクリーンショット ](assets/function-template-get-last-value-in-delimited-list.png)

+++

### ドメイン名

この関数テンプレートは、正規表現を使用してドメイン名を抽出します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ ドメイン名ルールビルダーのスクリーンショット ](assets/function-template-domain-name.png)

+++

### クエリ文字列パラメーターを取得

この関数テンプレートは、クエリ文字列値を抽出します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ クエリ文字列を取得パラメータールールビルダーのスクリーンショット ](assets/function-template-get-query-string-parameter.png)

+++

### 移行フィールド

この関数テンプレートは、あるフィールドから別のフィールドにレポートを移行します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ トランジションフィールドルールビルダーのスクリーンショット ](assets/function-template-transition-field.png)

+++

### シンプルなボット検出

この関数テンプレートは、ライトボットの識別を実装します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ シンプルなボット検出ルールビルダーのスクリーンショット ](assets/function-template-simple-bot-detection.png)

+++

### 離脱リンク

この関数テンプレートは、セッションで最後にクリックされたリンクを識別します。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ 離脱リンクのルールビルダーのスクリーンショット ](assets/function-template-exit-link.png)

+++

### ダウンロードリンク

この関数テンプレートは、一般的なダウンロードリンクにフラグを立てます。

+++ 詳細

テンプレートを使用するには、テンプレートのルールの一部としてリストされている各関数に対して正しいパラメーターを指定する必要があります。 詳しくは、[ 関数リファレンス ](#function-reference) を参照してください。

![ ダウンロードリンクのルールビルダーのスクリーンショット ](assets/function-template-download-link.png)

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

サポートされている各関数について、次の点で詳細を確認してください。

- 仕様：
   - 入力データタイプ：サポートされるデータのタイプ
   - input：入力に使用可能な値
   - 含まれる演算子：この関数でサポートされる演算子（ある場合）、
   - 制限事項：この特定の関数に適用される制限事項
   - 出力。

- 次のような使用例
   - 派生フィールドを定義する前のデータ。
   - 派生フィールドの定義方法
   - 派生フィールドを定義した後のデータ。

- 制約（該当する場合）。


<!-- CASE WHEN -->

### Case When

1 つ以上のフィールドから定義された条件に基づいて、条件を適用します。 これらの条件は、条件のシーケンスに基づいて、新しい派生フィールドの値を定義するために使用します。

+++ 詳細

## 仕様 {#casewhen-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL If], [!UICONTROL Else If] コンテナ：</p><ul><li>[!UICONTROL 値]</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL  条件 ] （選択した値のタイプに基づく含まれる演算子を参照してください）</li></ul></li><li>[!UICONTROL  次に値をに設定 ]、[!UICONTROL  それ以外の場合は値をに設定 ]:</p><ul><li>[!UICONTROL 値]</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></ul></li></ul> | <p>文字列</p><ul><li>次と等しい</li><li>が次のいずれかの語句に等しい</li><li>フレーズを含む</li><li>いずれかの語句を含む</li><li>すべての語句を含む</li><li>次の語句で始まる</li><li>任意の語句で始まる</li><li>次の語句で終わる</li><li>任意の語句で終わる</li><li>次と等しくない</li><li>が次のいずれの語句にも等しくない</li><li>このフレーズを含まない</li><li>いずれの語句も含まない</li><li>が次のすべての語句を含まない</li><li>次で始まらない</li><li>いずれの語句でも開始しない</li><li>次で終わらない</li><li>いずれの語句も含まない</li><li>設定済み</li><li>未設定</li></ul><p>数値</p><ul><li>次と等しい</li><li>次と等しくない</li><li>次より大きい</li><li>次よりも大きいか等しい</li><li>次より小さい</li><li>次よりも小さいか等しい</li><li>設定済み</li><li>未設定</li></ul><p>日付</p><ul><li>次と等しい</li><li>次と等しくない</li><li>が次よりも後</li><li>が次以降</li><li>次より前</li><li>が次以前</li><li>設定済み</li><li>未設定</li></ul> | <ul><li>派生フィールドごとに 5 つの関数</li><li>派生フィールドあたり 200 [ 演算子 ](#operators)。 単一のオペレーターの例としては、「参照ドメインに google が含まれる」などがあります。 </li></ul> | <p>派生フィールド新規</p> |

{style="table-layout:auto"}

## 使用例 1 {#casewhen-uc1}

カスケードロジックを適用してマーケティングチャネルフィールドを適切な値に設定することにより、さまざまなマーケティングチャネルを識別するルールを定義します。

- 転送者が検索エンジンからのものであり、ページにクエリー文字列値が含まれ、 `cid` に `ps_`が含まれている場合、マーケティングチャネルは [!DNL *有料Search*]&#x200B;として識別する必要があります。
- リファラーが検索エンジンからのもので、ページにクエリ文字列 `cid` がない場合、マーケティングチャネルは [!DNL *自然検索*] として識別される必要があります。
- ページに `em_` を含むクエリ文字列値が `cid` る場合、マーケティングチャネルは [!DNL *メール*] として識別される必要があります。
- ページに `ds_` を含むクエリ文字列値が `cid` る場合、マーケティングチャネルは [!DNL *ディスプレイ広告*] として識別される必要があります。
- ページに `so_` を含むクエリ文字列値が `cid` る場合、マーケティングチャネルは [!DNL *有料ソーシャル*] として識別される必要があります。
- リファラーが [!DNL twitter.com]、[!DNL facebook.com]、[!DNL linkedin.com] または [!DNL tiktok.com] の参照ドメインからの場合、マーケティングチャネルは [!DNL *ナチュラルソーシャル*] として識別される必要があります。
- 上記のルールのいずれも一致しない場合、マーケティングチャネルは [!DNL *その他のリファラー*] として識別される必要があります。

サイトが [!UICONTROL  リファラー ] と [!UICONTROL  ページ URL] を含む次のサンプルイベントを受け取った場合、これらのイベントは次のように識別される必要があります。

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### 前のデータ {#casewhen-uc1-databefore}

| [!DNL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` | |

{style="table-layout:auto"}

### 派生フィールド {#casewhen-uc1-derivedfield}

`Marketing Channel` の派生フィールドを定義します。 [!UICONTROL CASE WHEN] 関数を使用して、「`Page URL`」フィールドと「`Referring URL`」フィールドの両方の既存の値に基づいての値を作成するルールを定義します。

[!UICONTROL CASE WHEN] ルールが適用される前に `Page Url` と `Referring Url` の値を取得するルールを定義するための関数 [!UICONTROL URL PARSE] の使用に注意してください。

![ ルール 1 の場合のケースのスクリーンショット ](assets/case-when-1.png)

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


## ユースケース 2 {#casewhen-uc2}

[!DNL Product Finding Methods] ディメンション内の複数の異なるバリエーションの検索を収集しました。 検索と参照の全体的なパフォーマンスを理解するには、結果を手動で組み合わせることに多くの時間を費やす必要があります。

サイトは、[!DNL Product Finding Methods] ディメンションに対して次の値を収集します。 最後に、これらの値はすべて検索を示します。

| 収集された値 | 実際の値 |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### 前のデータ {#casewhen-uc2-databefore}

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

`Product Finding Methods (new)` の派生フィールドを定義します。 次の [!UICONTROL CASE WHEN] ルールをルールビルダーで作成します。 これらのルールは、「[!UICONTROL  フレーズを含む ]」条件を使用して `search` と `browse` の古い ] 製品検索方法 [!UICONTROL  フィールド値のすべての可能なバリエーションにロジックを適用します。

![ ルール 2 の場合のスクリーンショット ](assets/case-when-2.png)

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


## ユースケース 3 {#casewhen-uc3}

旅行会社として、記帳済トリップのバケット・トリップ期間をレポートして、トリップのバケット長をレポートできるようにします。

前提：

- 組織が、旅行期間を数値フィールドに収集しています。
- 1～3 日の期間を「[!DNL short trip]」というバケットにバケット化したいと考えています
- 期間が 4～7 日のバケットを「[!DNL medium trip]」というバケットに入れたいと考えています
- 8 日以上の期間を「[!DNL long trip]」というバケットにバケット化したいとします
- 132 回の旅行が 1 日間の期間で予約されました
- 2 日間で 110 回の旅行が予約されました
- 3 日間で 105 回の旅行が予約されました
- 99 回の旅行が 4 日間にわたって予約された
- 92 回の旅行が 5 日間にわたって予約された
- 6 日間で 85 回の旅行が予約されました
- 7 日間で 82 回の旅行が予約されました
- 78 回の旅行が 8 日間にわたって予約された
- 9 日間で 50 回の旅行が予約されました
- 44 回の旅行が 10 日間にわたって予約された
- 38 回の旅行が 11 日間にわたって予約された
- 31 回の旅行が 12 日間にわたって予約された

目的のレポートは次のようになります。

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### 前のデータ {#casewhen-uc3-databefore}

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

`Trip Duration (bucketed)` の派生フィールドを定義します。 次の [!UICONTROL CASE WHEN] ルールをルールビルダーで作成します。 このルールは、古い [!UICONTROL  トリップ期間 ] フィールド値を `short trip`、`medium  trip` および `long trip` の 3 つの値にバケット化するロジックを適用します。

![ ルール 3 を採用した場合のスクリーンショット ](assets/case-when-3.png)


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


## 詳細情報 {#casewhen-more-info}

Customer Journey Analyticsでは、Adobe Experience Platform [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja) （エクスペリエンスデータモデル）に倣ってモデル化された、ネストされたコンテナ構造を使用します。 背景の情報について詳しくは、[ コンテナ ](../create-dataview.md#containers) および [ フィルターコンテナ ](../../components/filters/filters-overview.md#filter-containers) を参照してください。 このコンテナモデルは、本質的に柔軟性がありますが、ルールビルダーを使用する際にいくつかの制約を課します。

Customer Journey Analyticsでは、次のデフォルトのコンテナモデルを使用します。

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

次の制約が適用され、値 *選択* および *設定* 時に適用されます。

|  | 制約 |
|:---:|----|
| **A** | ルール内の同じ *If*、[!UICONTROL Else If[!UICONTROL  の同じ ]And] または [!UICONTROL Or] を使用する）コンストラクト内の [!UICONTROL  選択 ] 値は、同じコンテナから生成され、任意のタイプ（文字列 ![String](assets/Smock_ABC_18_N.svg)、数値 ![Numeric](assets/Smock_123_18_N.svg) など）にする必要があります。 <br/>![ 依存関係 A のスクリーンショット ](assets/dependency-a.png) |
| **B** | ルール全体にわたって *設定* する値は、同じコンテナから得られ、同じタイプまたは同じタイプの派生値を持つ必要があります。<br/> ![ 依存関係 B のスクリーンショット ](assets/dependency-b.png) |
| **C** | ルール内の [!UICONTROL If]、[!UICONTROL Else If] 構成全体で *選択* した値は、同じコンテナから生成される必要はなく *ありません* また、同じタイプである必要も *ありません*。<br/> ![ 依存関係 C のスクリーンショット ](assets/dependency-c.png) |

{style="table-layout:auto"}

+++

<!-- CLASSIFY -->

### 分類

新しい派生フィールドで対応する値に置き換えられる値のセットを定義します。

+++ 詳細

## 仕様 {#classify-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL  分類するフィールド ]:<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>[!UICONTROL  値がに等しい場合 ] および [!UICONTROL  値をで置き換える ]:</p><ul><li>文字列</li></ul><li>元の値を表示<ul><li>ブール値</li></ul></li></ul> | <p>該当なし</p> | <ul><li>派生フィールドごとに 5 つの関数</li><li>派生フィールドあたり 200 [ 演算子 ](#operators)。 [!UICONTROL  値が元の値と等しい場合 ][!UICONTROL  値を新しい値に置き換える ] のすべてのエントリは操作と見なされます。</li></ul> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース 1 {#classify-uc1}

`hotelID` のキー列と、`hotelID` に関連付けられた 1 つ以上の追加の列（`city`、`rooms`、`hotel name`）を含む CSV ファイルがあります。
ディメンションの [!DNL Hotel ID] を収集していますが、CSV ファイルの `hotelID` から派生した [!DNL Hotel Name] ディメンションを作成したいと考えています。

**CSV ファイル構造とコンテンツ**

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

### 前のデータ {#classify-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |
| [!DNL AMS789] |

{style="table-layout:auto"}


### 派生フィールド {#classify-uc1-derivedfield}

`Hotel Name` の派生フィールドを定義します。 [!UICONTROL CLASSIFY] 関数を使用して、「[!UICONTROL  ホテル ID]」フィールドの値を分類し、新しい値に置き換えることができるルールを定義します。

分類する値の一部として定義していない元の値（例：ホテル ID AMS789）を含める場合は、「元の値を表示 **[!UICONTROL を選択していることを確認し]** す。 これにより、値が分類されていないにもかかわらず、AMS789 が派生フィールドの出力の一部になります。

![ 分類ルール 1 のスクリーンショット ](assets/classify-1.png)

### 後のデータ {#classify-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## ユースケース 2 {#classify-uc2}

複数のページのわかりやすいページ名の代わりに URL を収集しました。 この値の混在コレクションにより、レポートが中断されます。

### 前のデータ {#classify-uc2-databefore}

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

`Page Name (updated)` の派生フィールドを定義します。 [!UICONTROL CLASSIFY] 関数を使用して、既存の [!UICONTROL  ページ名 ] フィールドの値を分類し、更新された正しい値に置き換えることができるルールを定義します。

![ 分類ルールのスクリーンショット 2](assets/classify-2.png)

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

分類ルールインターフェイスでは次の追加機能を使用できます。

- すべてのテーブル値をすばやくクリアするには、「![ 消去 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Erase_18_N.svg)**[!UICONTROL すべてのテーブル値をクリア]** を選択します。
- 「値が等しい場合」の元の値と「値を置き換える」の新しい値を含む CSV ファイルをアップロードするには、「![CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg)**[!UICONTROL CSV をアップロード]**」を選択します。
- アップロードする元の値と新しい値を含む CSV ファイルを作成するためのテンプレートをダウンロードするには、「![ ダウンロード ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg)**[!UICONTROL CSV テンプレートをダウンロード]**」を選択します。
- ルールインターフェイスに入力された元の値と新しい値をすべて含む CSV ファイルをダウンロードするには、「![ ダウンロード ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg)**[!UICONTROL CSV 値をダウンロード]**」を選択します。


+++

<!-- CONCATENATE -->

### 連結

フィールド値を、定義済みの区切り文字を使用して単一の新しい派生フィールドに結合します。

+++ 詳細

## 仕様 {#concatenate-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL  値 ]:<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li><li>文字列</li></ul></li><li>[!UICONTROL  区切り文字 ]:<ul><li>文字列</li></ul></li> </ul> | <p>該当なし</p> | <p>派生フィールドごとに 2 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース {#concatenate-uc}

現在、出発地と目的地の空港コードを別のフィールドとして収集しています。 2 つのフィールドを取り込み、ハイフン（–）で区切られた単一のディメンションに結合する場合。 そのため、接触チャネルと宛先の組み合わせを分析して、予約された上位のルートを特定できます。

前提：

- 起源と宛先の値は、同じテーブルの別々のフィールドに収集されます。
- ユーザーは、値の間に区切り文字「–」を使用することを決定します。

次の予約が発生すると仮定します。

- お客様 ABC123 様がソルトレイクシティ（SLC）とオーランド（MCO）間のフライトを予約
- お客様の ABC456 がソルトレイクシティ（SLC）とロサンゼルス（LAX）間のフライトを予約
- お客様 ABC789 がソルトレイクシティ（SLC）とシアトル（SEA）間のフライトを予約
- お客様 ABC987 がソルトレイクシティ（SLC）とサンノゼ（SJO）間のフライトを予約
- お客様 ABC654 がソルトレイクシティ（SLC）とオーランド（MCO）間のフライトを予約

目的のレポートは次のようになります。

| 接触チャネル/移動先 | Bookings |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC 海 | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### 前のデータ {#concatenate-uc-databefore}

| 複製元 | 宛先 |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | 海 |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 派生フィールド {#concatenate-derivedfield}

`Origin - Destination` 派生フィールドを定義します。 [!UICONTROL CONCATENATE] 関数を使用すると、`-` [!UICONTROL Delimiter] を使用して「[!UICONTROL Original]」フィールドと「[!UICONTROL Destination]」フィールドを連結するルールを定義できます。

![ 連結ルールのスクリーンショット ](assets/concatenate.png)

### 後のデータ {#concatenate-dataafter}

| 接触チャネル – 宛先 <br/> （派生フィールド） |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC 海 |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++


### 重複排除

値を複数回数えるのを防ぎます。

+++ 詳細


## 仕様 {#deduplicate-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li></ul> | <ul><li>[!UICONTROL  値 ]:<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li><li>文字列</li></ul></li><li>[!UICONTROL  範囲 ]:<ul><li>ユーザー</li><li>セッション</li></ul></li><li>[!UICONTROL  重複排除 ID]:<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li><li>文字列</li></ul><li>[!UICONTROL  保持する値 ]:<ul><li>最初のインスタンスを維持</li><li>最後のインスタンスを維持</li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 5 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース 1 {#deduplicate-uc1}

ユーザーが予約確認ページをリロードする際に、重複売上高がカウントされないようにする必要がある。 同じイベントで受信した収益を再度カウントしないように、識別子で予約確認 ID を使用します。

### 前のデータ {#deduplicate-uc1-databefore}

| 予約確認 ID | 売上高 |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 359 |
| ABC123456789 | 359 |

{style="table-layout:auto"}

### 派生フィールド {#deduplicate-uc1-derivedfield}

`Booking Confirmation` の派生フィールドを定義します。 [!UICONTROL DEDUPLICATE] 関数を使用すると、[!UICONTROL  重複排除 ID][!UICONTROL  予約確認 ID] を使用して [!UICONTROL  範囲 ][!DNL Person] の [!UICONTROL  値 ][!DNL Booking] の重複排除を行うルールを定義できます。 [!UICONTROL  最初のインスタンスを保持 ] を [!UICONTROL  保持する値 ] として選択します。

![ 連結ルールのスクリーンショット ](assets/deduplicate-1.png)

### 後のデータ {#deduplicate-uc1-dataafter}

| 予約確認 ID | 売上高 |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 0 |
| ABC123456789 | 0 |

{style="table-layout:auto"}

## ユースケース 2 {#deduplicate-uc2}

イベントを、外部マーケティングキャンペーンでのキャンペーンのクリックスルーのプロキシとして使用します。 リロードとリダイレクトが原因で、イベント指標が水増しされる。 トラッキングコードディメンションの重複を排除して、最初のディメンションのみが収集されるようにし、イベントのオーバーカウントを最小限に抑えたいと考えています。

### 前のデータ {#deduplicate-uc2-databefore}

| 訪問者 ID | マーケティングチャネル | イベント |
|----|---|---:|
| ABC123 | 有料検索 | 1 |
| ABC123 | 有料検索 | 1 |
| ABC123 | 有料検索 | 1 |
| DEF123 | メール | 1 |
| DEF123 | メール | 1 |
| JKL123 | 自然検索 | 1 |
| JKL123 | 自然検索 | 1 |

{style="table-layout:auto"}

### 派生フィールド {#deduplicate-uc2-derivedfield}

新しい `Tracking Code (deduplicated)` 派生フィールドを定義します。 [!UICONTROL DEDUPLICATE] 関数を使用すると、[!UICONTROL  トラッキングコード ] の重複を除外するルールを、[!UICONTROL  重複排除範囲 ] の [!UICONTROL  セッション ] と、[!UICONTROL  最初のインスタンスを保持 ] を保持する値 [!UICONTROL  として定義できます ]。

![ 連結ルールのスクリーンショット ](assets/deduplicate-2.png)

### 後のデータ {#deduplicate-uc2-dataafter}

| 訪問者 ID | マーケティングチャネル | イベント |
|----|---|---:|
| ABC123 | 有料検索 | 1 |
| DEF123 | メール | 1 |
| JKL123 | 自然検索 | 1 |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### 検索と置換

選択したフィールド内のすべての値を検索し、それらの値を新しい派生フィールド内の別の値に置き換えます。

+++ 詳細

## 仕様 {#findreplace-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL 値]<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>[!UICONTROL  すべてを検索 ]、[!UICONTROL  すべてを次に置換 ]:<ul><li>文字列</li></ul></li></ul></ul> | <p>文字列</p><ul><li>[!UICONTROL Find all], [!UICONTROL and replace all with]</li></ul> | <p>派生フィールドごとに 5 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース {#findreplace-uc}

外部マーケティングチャネルレポートに不正な値（例：`email marketing` ではなく `email%20 marketing`）が一部届いています。 これらの不正な値によりレポートが破損するため、メールのパフォーマンスを確認するのが難しくなります。 `email%20marketing` を `email marketing` に置き換えます。

**原本報告書**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**優先するレポート**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### 前のデータ {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### 派生フィールド {#findreplace-uc-derivedfield}

`Email Marketing (updated)` 派生フィールドを定義します。 [!UICONTROL FIND AND REPLACE] 関数を使用して、`email%20marketing` のすべての出現箇所を検索して `email marketing` に置換するルールを定義します。

![ 検索と置換ルールのスクリーンショット ](assets/find-and-replace.png)

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

ルックアップデータセットのフィールドを使用して値をルックアップし、新しい派生フィールドまたは追加のルール処理のための値を返します。

+++ 詳細

## 仕様 {#lookup-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL  ルックアップを適用するフィールド ]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL  データセットを検索 ]</li><ul><li>データセット</li></ul><li>[!UICONTROL 一致するキー]<ul><li>ルール</li><li>フィールド</li></ul></li><li>戻す値<ul><li>ルール</li><li>フィールド</li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 3 つの関数</p> | <p>次のルールでさらに処理するための新しい派生フィールドまたは値</p> |

{style="table-layout:auto"}

## ユースケース {#lookup-uc}

Adobe Targetを通じて表示されるパーソナライズされたバナーを顧客がクリックしたときに収集されたアクティビティ ID を使用して、アクティビティ名を参照したいと考えています。 アクティビティ ID とアクティビティ名を含む Analytics for Target （A4T）アクティビティでルックアップデータセットを使用する。

### A4T ルックアップデータセット {#lookup-uc-lookup}

| アクティビティ Id | アクティビティ名 |
|---|---|
| 415851 | MVT テストカテゴリページ |
| 415852 | Luma - Campaign Max 2022 |
| 402922 | ホーム ページ バナー |

{style="table-layout:auto"}

### 派生フィールド {#lookup-uc-derivedfield}

`Activity Name` 派生フィールドを定義します。 [!UICONTROL LOOKUP] 関数を使用すると、収集したデータから値を検索するルールを定義できます。このルールは、[!UICONTROL  ルックアップを適用するフィールド ] フィールド（**[!DNL ActivityIdentifier]** など）で指定します。 [!UICONTROL  ルックアップデータセット ] リストからルックアップデータセットを選択します（例：**[!DNL New CJA4T Activities]**）。 次に、「[!UICONTROL  一致するキー ]」リストから識別子フィールド（例：**[!DNL ActivityIdentifier]**）を選択し、「[!UICONTROL  返す値 ]」リストから返すフィールド（例：**[!DNL ActivityName]**）を選択します。

![Lowercase ルールのスクリーンショット ](assets/lookup.png)

## 詳細情報 {#lookup-more-info}

ルックアップ関数は、接続の一部として設定したルックアップデータセットからCustomer Journey Analyticsによって取得されたデータに、レポート時に適用されます。

既に 1 つ以上の他の関数が含まれている [!UICONTROL  ルックアップ ] 関数を、ルールビルダーにすばやく挿入できます。

1. セレクターから **[!UICONTROL スキーマフィールド]** を選択します。
1. ![ スキーマフィールドアイコン ](assets/Smock_Folder_18_N.svg)**[!UICONTROL ルックアップデータセット]** を選択します。
1. ルックアップデータセットを選択し、ルックアップに使用するフィールドを見つけます。
1. 関数に使用可能な入力フィールドのいずれかにルックアップフィールドをドラッグ&amp;ドロップします（例：Case When）。 有効な場合、**[!UICONTROL +追加]** というラベルの付いた青いボックスを使用して、フィールドをドロップし、ルックアップ フィールドをドロップした関数の前にルックアップ関数を自動的に挿入できます。 挿入されたルックアップ関数は、すべてのフィールドの関連する値に自動的に設定されます。
   ![ 参照ドラッグ ](assets/lookup-drag.png)

+++


<!-- LOWERCASE -->

### 小文字

フィールドの値を小文字に変換して、新しい派生フィールドに格納します。

+++ 詳細

## 仕様 {#lowercase-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL  フィールド ]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 2 つの関数</p> | <p>派生フィールド新規</p> |

{style="table-layout:auto"}

## ユースケース {#lowercase-uc}

適切なレポートのために、収集したすべての製品名をすべて小文字に変換するする必要があります。

### データ前 {#lowercase-uc-databefore}

| 収集された製品名 | 製品表示 |
|---|---:|
| テニスラケット | 35 |
| テニスラケット | 33 |
| テニスラケット | 21 |
| 野球バット | 15 |
| 野球バット | 12 |
| 野球バット | 10 |

{style="table-layout:auto"}

### 派生フィールド {#lowercase-uc-derivedfield}

`Product Names` の派生フィールドを定義します。 [!UICONTROL LOWERCASE] 関数を使用して、「[!UICONTROL  収集された製品名 ]」フィールドの値を小文字に変換し、新しい派生フィールドに保存するルールを定義します。

![Lowercase ルールのスクリーンショット ](assets/lowercase.png)


### 後のデータ {#lowercase-uc-dataafter}

| 製品名 | 製品表示 |
|---|---|
| テニスラケット | 89 |
| 野球バット | 37 |

{style="table-layout:auto"}

+++

<!-- MATH -->

### Math

数値フィールドに対して基本的な数学演算子（加算、減算、乗算、除算、累乗）を使用します。

+++ 詳細

## 仕様 {#math-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>数値</li></ul> | <ul><li>1 つまたは複数の数値フィールド</li><li>1 つまたは複数の演算子（加算、減算、乗算、除算、累乗）</li><li>ユーザー入力値</li></ul> | <ul><li>`+` （追加）</li><li>`-` （減算）</li><li>`*` （multiply）</li><li>`/` （除算）</li><li>`^` （累乗）</li></ul> | <ul><li>派生フィールドあたり 25 操作</li><li>派生フィールドごとに 5 つの数学関数</li></ul> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース {#math-uc}

インフレが原因で、取り込んだ CRM データの収益数を 5% のインフレで修正する必要があります。

### 前のデータ {#math-uc-databefore}

| CRM ID | 年間売上高 |
|---|---:|
| 1234 | 35,070,000 |
| 4133 | 7,500,000 |
| 8110 | 10,980 |
| 2201 | 42,620 |

{style="table-layout:auto"}

### 派生フィールド {#math-uc-derivedfield}

`Corrected Annual Revenue` の派生フィールドを定義します。 [!UICONTROL MATH] 関数を使用して、元の年間売上高の数値に 1.05 を乗算するルールを定義します。

![ 数学ルールのスクリーンショット ](assets/math.png)


### 後のデータ {#math-uc-dataafter}

| CRM ID | 修正済み年間収益 |
|---|---:|
| 1234 | 36,823,500 |
| 4133 | 7,875,000 |
| 8110 | 11,529,00 |
| 2201 | 44,751 |

{style="table-layout:auto"}

## 詳細情報 {#math-more-info}

式を作成するには、次の手順に従います。

1. 数式フィールドと入力した値に一致する数値フィールドに入力するだけで、ポップアップメニューに表示されます。 または、左側のペインの使用可能なフィールドから数値フィールドをドラッグ&amp;ドロップすることもできます。
   ![ 算術詳細情報 1](assets/math-more-info-1.png)

1. オペランド（乗算する場合は `*`）の後に別のフィールドまたは静的な値を追加します。 括弧を使用すると、より複雑な式を定義できます。

1. 静的な値（`1.05` など）を挿入するには、値を入力し、ポップアップメニューから「**[!UICONTROL 静的な値として *x* を追加]** または「**[!UICONTROL -*x* 負の静的な値を追加]**」を選択します。
   ![ 算術詳細情報 2](assets/math-more-info-2.png)

1. 緑のチェックマーク ![ チェックマーク ](./assets/checkmark.svg)</span> は、数式が有効かどうかを示します。それ以外の場合は、警告 ![ アラート ](./assets/alert.svg) とメッセージ [!UICONTROL  数式が無効です ] が表示されます。
   ![ 算術詳細情報 3](assets/math-more-info-3.png)

[!UICONTROL MATH] 関数で静的な数値を使用する場合は、いくつかの重要な考慮事項があります。

- 静的値はフィールドに関連付ける必要があります。 例えば、静的フィールドのみで [!UICONTROL MATH] 関数を使用することはできません。
- 静的値に raise to power 演算子（`ˆ`）を使用することはできません。
- 数式内で複数の静的値を使用している場合、数式を有効にするには、これらの静的値を括弧で囲む必要があります。 次に例を示します。

   - この式はエラーを返します。
     ![ 算術詳細情報 4](assets/math-more-info-4.png)

   - この式は有効です。
     ![ 算術詳細情報 5](assets/math-more-info-5.png)

ヒットレベルに基づく計算には、数学関数を使用します。 イベント、セッション、またはユーザー範囲に基づく計算には、[Summarize](#summarize) 関数を使用します。

+++


<!-- MERGE FIELDS -->

### フィールドを結合

2 つの異なるフィールドの値を新しい派生フィールドに結合します。

+++ 詳細

## 仕様 {#merge-fields-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL  フィールド ]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 5 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース {#merge-fields-uc}

チャネルをまたいでジャーニーを分析する目的で、ページ名フィールドと問い合わせ理由フィールドから構成されるディメンションを作成したいと考えています。

### 前のデータ {#merge-fields-uc-databefore}

| ページ名 | セッション | 訪問者 |
|---|--:|--:|
| ヘルプページ | 250 | 200 |
| ホームページ | 500 | 250 |
| 製品詳細ページ | 300 | 200 |

{style="table-layout:auto"}

| 通話理由 | セッション | 訪問者 |
|---|--:|--:|
| 注文に関する質問 | 275 | 250 |
| 注文を変更する | 150 | 145 |
| 順序付けに関する問題 | 100 | 95 |

{style="table-layout:auto"}

### 派生フィールド {#merge-fields-uc-derivedfield}

`Cross Channel Interactions` の派生フィールドを定義します。 [!UICONTROL MERGE FIELDS] 関数を使用して、「[!UICONTROL  ページ名 ]」フィールドと「[!UICONTROL  問い合わせ理由 ]」フィールドの値を結合して新しい派生フィールドに保存するルールを定義します。

![ 結合フィールドルールのスクリーンショット ](assets/merge-fields.png)

### 後のデータ {#merge-fields-uc-dataafter}

| クロスチャネルインタラクション | セッション数 | 訪問者 |
|---|--:|--:|
| ホームページ | 500 | 250 |
| 製品詳細ページ | 300 | 200 |
| 注文に関する質問 | 275 | 250 |
| ヘルプページ | 250 | 200 |
| 注文を変更する | 150 | 145 |
| 順序付けに関する問題 | 100 | 95 |

{style="table-layout:auto"}

## 詳細情報 {#merge-fields-moreinfo}

結合フィールドルール内で同じタイプのフィールドを選択する必要があります。 例えば、日付フィールドを選択した場合、結合する他のすべてのフィールドは日付フィールドである必要があります。

![ 結合フィールドに対する制約のスクリーンショット ](assets/merge-fields-constraint.png)

+++


<!-- NEXT OR PREVIOUS -->

### 次または前

フィールドを入力として受け取り、セッションまたは使用の範囲内で、そのフィールドの次または前の値を解決します。 これは、訪問およびイベント テーブルのフィールドにのみ適用されます。

+++ 詳細

## 仕様 {#prevornext-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>[!UICONTROL  フィールド ]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL  メソッド ]:<ul><li>前の値</li><li>次の値</li></ul></li><li>[!UICONTROL  範囲 ]:<ul><li>ユーザー</li><li>セッション</li></ul></li><li>[!UICONTROL  指数 ]:<ul><li>数値</li></ul><li>[!UICONTROL  繰り返しを含める ]:<ul><li>ブール値</li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 3 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース {#prevornext-uc1}

受け取ったデータの **次** または **前** の値を、繰り返し値を考慮して理解する必要があります。

### データ {#prevornext-uc1-databefore}

**例 1 – 繰り返しを含む処理**

| 受信データ | 次の値 <br/>Session<br/>Index = 1<br/> 繰り返しを含める | 次の値 <br/>Session<br/>Index = 1<br/> 繰り返しを含まない | 前の値 <br/>Session<br/>Index = 1<br/>Include Repeats | 前の値 <br/>Session<br/>Index = 1<br/> 繰り返しを含まない |
|---|---|---|---|---|
| ホーム | ホーム | 検索 | *値なし* | *値なし* |
| ホーム | 検索 | 検索 | ホーム | *値なし* |
| 検索 | 検索 | 製品の詳細 | ホーム | ホーム |
| 検索 | 製品の詳細 | 製品の詳細 | 検索 | ホーム |
| 製品の詳細 | 検索 | 検索 | 検索 | 検索 |
| 検索 | 製品詳細 | 製品の詳細 | 製品の詳細 | 製品の詳細 |
| 製品の詳細 | 検索 | 検索 | 検索 | 検索 |
| 検索 | 検索 | *値なし* | 製品の詳細 | 製品の詳細 |
| 検索 | *値なし* | *値なし* | 検索 | 製品の詳細 |

{style="table-layout:auto"}

**例 2 – 処理には、受信したデータに空白の値を使用して繰り返しが含まれる**

| 受信データ | 次の値 <br/>Session<br/>Index = 1<br/> 繰り返しを含める | 次の値 <br/>Session<br/>Index = 1<br/> 繰り返しを含まない | 前の値 <br/>Session<br/>Index = 1<br/>Include Repeats | 前の値 <br/>Session<br/>Index = 1<br/> 繰り返しを含まない |
|---|---|---|---|---|
| ホーム | ホーム | 検索 | *値なし* | *値なし* |
| ホーム | ホーム | 検索 | ホーム | *値なし* |
| ホーム | 検索 | 検索 | ホーム | *値なし* |
| 検索 | 検索 | 製品の詳細 | ホーム | ホーム |
|   |   |   |   |   |
| 検索 | 検索 | 製品の詳細 | 検索 | ホーム |
| 検索 | 製品の詳細 | 製品の詳細 | 検索 | ホーム |
| 製品の詳細 | *値なし* | *値なし* | 検索 | 検索 |
|   |   |   |   |   |

{style="table-layout:auto"}

### 派生フィールド {#prevnext-uc1-derivedfield}

`Next Value` または `Previous value` の派生フィールドを定義します。 [!UICONTROL NEXT OR PREVIOUS] 関数を使用すると、[!UICONTROL Data received] フィールドを選択するルールを定義し、[!UICONTROL Next value] または [!UICONTROL Previous value] を [!UICONTROL Method] として選択し、[!UICONTROL Session] を Scope として選択し、[!UICONTROL Index] の値を `1` に設定することができます。

![ 結合フィールドルールのスクリーンショット ](assets/prevnext-next.png)

## 詳細情報 {#prevnext-moreinfo}

選択できるのは、「訪問」または「イベント」テーブルに属するフィールドのみです。

[!UICONTROL  繰り返しを含める ] [!UICONTROL NEXT または PREVIOUS] 関数の繰り返し値の処理方法を指定します。

- 繰り返しのルックと、次または前の値を含めます。 [!UICONTROL  繰り返しを含める ] が選択されている場合、現在のヒットから次または前の値の連続した繰り返しが無視されます。

- 選択したフィールドに値がない（空白の）行は、[!UICONTROL NEXT OR PREVIOUS] 関数出力の一部として返される次の値または前の値を持ちません。

+++

<!-- REGEX REPLACE -->

### 正規表現による置換

正規表現を使用してフィールドの値を新しい派生フィールドに置き換えます。

+++ 詳細

## 仕様 {#regex-replace-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li></ul> | <ul><li>[!UICONTROL  フィールド ]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></ul><ul><li>[!UICONTROL  正規表現 ]:</li><ul><li>文字列</li></ul></li><li>[!UICONTROL  出力形式 ]:<ul><li>文字列</li></ul></ul><ul><li>大文字と小文字を区別</li><ul><li>ブール値</li></ul></li></ul></li> | <p>該当なし</p> | <p>派生フィールドごとに 1 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース {#regex-replace-uc}

URL の一部を取得し、それを一意のページ識別子として使用してトラフィックを分析します。 正規表現に `[^/]+(?=/$|$)` を使用して、URL の末尾を取得し、出力パターンとして `$1` を使用します。

### 前のデータ {#regex-replace-uc-databefore}

| ページ URL |
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### 派生フィールド {#regex-replace-uc-derivedfield}

`Page Identifier` の派生フィールドを作成します。 [!UICONTROL REGEX REPLACE] 関数を使用して、`[^/]+(?=/$|$)` の [!UICONTROL Regex] と `$1` の [!UICONTROL  出力形式 ] を使用して「[!UICONTROL  参照 URL]」フィールドの値を置換するルールを定義します。

![ 正規表現置換ルールのスクリーンショット ](assets/regex-replace.png)


### 後のデータ {#regex-replace-uc-dataafter}

| ページ識別子 |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## 詳細情報 {#regex-replace-more-info}

Customer Journey Analyticsでは、Perl 正規表現構文のサブセットを使用します。 次の式がサポートされています。

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
| `$n` | n 番目のサブ式に一致したものを出力します。 例えば、`$1` は、最初のサブ式を出力します。 |
| ``$` `` | 最後に見つかった一致の終わり（前に一致が見つからなかった場合は、テキストの始まり）から、現在の一致の始まりまでのテキストを出力します。 |
| `$+` | 正規表現で最後にマークされたサブ式に一致するものを出力します。 |
| `$$` | 文字列文字 `"$"` を出力します。 |

{style="table-layout:auto"}

+++

<!-- SPLIT -->

### Split

フィールドから新しい派生フィールドに値を分割します。

+++ 詳細

## 仕様 {#split-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li></ul> | <ul><li>[!UICONTROL  フィールド ]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></ul><ul><li>[!UICONTROL  メソッド ]:</li><ul><li>左から</li><li>右から</li><li>配列に変換</li></ul></li><li>区切り文字の場合：<ul><li>文字列</li></ul><li>インデックスの場合：<ul><li>数値</li></ul></li> | <p>該当なし</p> | <p>派生フィールドごとに 5 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}

## ユースケース 1 {#split-uc1}

音声アプリの応答を、1 つのディメンションで区切られたリストに収集します。 リスト内の各値を、応答レポート内で一意の値にする必要があります。

### 前のデータ {#split-uc1-databefore}

| 音声アプリの応答 | イベント |
|---|--:|
| それは素晴らしく、完璧に理にかなっていて、他の人に推薦します | 1 |
| それは素晴らしく、やや混乱していて、他の人に推奨されます | 1 |
| それは素晴らしくなく、非常に混乱していて、他の人に勧められません | 1 |

{style="table-layout:auto"}

### 派生フィールド {#split-u1-derivedfield}

`Responses` の派生フィールドを作成します。 [!UICONTROL SPLIT] 関数を使用して、[!UICONTROL  配列に変換 ] メソッドを使用し、`,` を [!UICONTROL  区切り文字 ] として使用して [!UICONTROL  音声アプリの応答 ] フィールドの値を変換するルールを定義します。

![ 分割ルール 1 のスクリーンショット ](assets/split-1.png)

### 後のデータ {#split-uc1-dataafter}

| 応答 | イベント |
|---|--:|
| 素晴らしかった | 2 |
| 他のユーザーにをレコメンデーションします | 2 |
| それは素晴らしくなかった | 1 |
| 完全に理解した | 1 |
| やや混乱させる | 1 |
| 非常に混乱させる | 1 |
| 他のユーザーにお勧めしません | 1 |

{style="table-layout:auto"}

## ユースケース 2 {#split-uc2}

音声アプリの応答を、1 つのディメンションで区切られたリストに収集します。 リストの最初の値からの応答を、独自のディメンションに変換します。 リストの最後の値を、独自のディメンションに配置する必要があります。

### 前のデータ {#split-uc2-databefore}

| 応答 | イベント |
|---|--:|
| それは素晴らしく、完全に理にかなっていて、他の人に勧められるでしょう | 1 |
| それは素晴らしく、やや混乱していて、他の人に推奨されます | 1 |
| それは素晴らしくなく、非常に混乱していて、他の人に勧められません | 1 |

{style="table-layout:auto"}

### 派生フィールド {#split-u2-derivedfield}

`First Response` の派生フィールドを作成します。 [!UICONTROL SPLIT] 関数を使用して、応答 `,` の左側の [!UICONTROL Responses] フィールドから最初の値を区切り文字として取得するルールを定義します。

![ 分割ルールのスクリーンショット – 最初の値 ](assets/split-2.png)

[!UICONTROL Responses] フィールドから最後の値を取得するための `Second Response` 派生フィールドを作成するには、右側から「From」を選択し、区切り文字として「1」、インデックスとして「1」を選択します。

![ 分割ルールのスクリーンショット – 最後の値 ](assets/split-3.png)

### 後のデータ {#split-uc2-dataafter}

| 最初の応答 | イベント |
|---|--:|
| 素晴らしかった | 2 |
| それは素晴らしくなかった | 1 |

{style="table-layout:auto"}

| 2 番目の応答 | イベント |
|---|--:|
| 他のユーザーにをレコメンデーションします | 2 |
| 他のユーザーにお勧めしません | 1 |

{style="table-layout:auto"}

+++

<!-- SUMMARIZE -->

### 要約

イベント、セッションおよびユーザーレベルで指標またはディメンションに集計タイプ関数を適用します。

+++ 詳細

## 仕様 {#summarize-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li><li>数値</li><li>日付</li></ul> | <ul><li>値<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>要約方法</li><li>範囲<ul><li>イベント</li><li>セッション</li><li>ユーザー</li></ul></li></ul> | <ul><li>数値<ul><li>MAX – 値のセットから最大値を返します</li><li>MIN – 値のセットから最小値を返します</li><li>MEDIAN – 一連の値の中央値を返します</li><li>MEAN – 一連の値の平均を返します。</li><li>SUM - セットの値の合計を返します</li><li>COUNT – 受信した値の数を返します</li><li>DISTINCT - ユニーク値のセットを返します。</li></ul></li><li>文字列<ul><li>DISTINCT - ユニーク値のセットを返します。</li><li>COUNT DISTINCT – 個別の値の数を返します</li><li>MOST COMMON – 最も頻繁に受信された文字列値を返します</li><li>LEAST COMMON – 最も頻度が低い文字列値を返します</li><li>FIRST – 受け取った最初の値。セッションテーブルとイベントテーブルにのみ適用されます。</li><li>LAST – 最後に受け取った値。セッションテーブルとイベントテーブルにのみ適用できます。</li></ul></li><li>日付<ul><li>DISTINCT - ユニーク値のセットを返します。</li><li>COUNT DISTINCT – 個別の値の数を返します</li><li>MOST COMMON – 最も頻繁に受信された文字列値を返します</li><li>LEAST COMMON – 最も頻度が低い文字列値を返します</li><li>FIRST – 受け取った最初の値。セッションテーブルとイベントテーブルにのみ適用されます。</li><li>LAST – 最後に受け取った値。セッションテーブルとイベントテーブルにのみ適用できます。</li><li>最早値 – 最も早く受け取った値（時間によって決定）。セッションおよびイベント表にのみ適用されます。</li><li>LATEST – 受信した最新の値（時間によって決定）。セッションテーブルとイベントテーブルにのみ適用されます</li></ul></li></ul> | 派生フィールドごとに 3 つの関数 | 新しい派生フィールド |

{style="table-layout:auto"}

## ユースケース {#summarize-uc}

買い物かごに追加売上高は、小、Medium、大の 3 つの異なるカテゴリに分類したいとします。 これにより、価値の高い顧客の特性を分析および特定できます。

### 前のデータ {#summarize-uc-databefore}

前提：

- 買い物かごに追加する売上高は、数値フィールドとして収集されます。

シナリオ：

- CustomerABC123 は、ProductABC の買い物かごに 35 ドルを追加し、その後、75 ドルで ProductDEF を買い物かごに個別に追加します。
- CustomerDEF456 は、ProductGHI の買い物かごに 50 ドルを追加し、その後 275 ドルで ProductJKL を買い物かごに個別に追加します。
- CustomerGHI789 は、ProductMNO のために買い物かごに 500 ドルを追加します。

ロジック :

- 訪問者の「買い物かごに追加する売上高の合計」が 150 ドル未満の場合は、「小」に設定します。
- 訪問者の「買い物かごに追加する売上高の合計」が 150 ドルを超え、500 ドル未満の場合は、Mediumに設定します。
- 訪問者の買い物かごへの合計 追加の売上高が $500 以上の場合は、大 に設定します。

業績：

- 合計 追加 to CustomerABC123 の $110 の売上高。
- 買い物かごへの合計 追加の売上高は CustomerDEF456 の場合 $325 です。
- 買い物かごへの合計 追加の売上高は 500 ドルで、CustomerGHI789 が支払われます。

### 派生フィールド {#summarize-uc-derivedfield}

`Add To Cart Revenue Size` 派生フィールドを作成します。 [!UICONTROL SUMMARIZE] 関数と [!UICONTROL Sum] [!UICONTROL Summarize メソッド ] を使用し、[!UICONTROL Scope] を [!UICONTROL Person] に設定すると、[!UICONTROL cart_add] フィールドの値を合計できます。 次に、2 つ目の [!UICONTROL CASE WHEN] ルールを使用して、結果をツリーカテゴリサイズに分割します。

![Summarize rule 1 のスクリーンショット ](assets/summarize.png)



### 後のデータ {#summarize-uc-dataafter}

| 買い物かごに追加の売上高サイズ | 訪問者 |
|---|--:|
| 小 | 1 |
| メディア | 1 |
| 大 | 1 |

{style="table-layout:auto"}

## 詳細情報 {#summarize-more-info}

イベント、セッションまたはユーザー範囲に基づく計算に要約関数を使用します。 ヒットレベルに基づく計算には、[Math](#math) 関数を使用します。

+++

<!-- TRIM -->

### トリミング

フィールド値の先頭または末尾の空白、特殊文字または文字数を新しい派生フィールドにトリミングします。

+++ 詳細

## 仕様 {#trim-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL フィールド]<ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul></li><li>空白をトリミング</li><li>特殊文字をトリミング<ul><li>特殊文字の入力</li></ul></li><li>左からトリミング<ul><li>送信元 <ul><li>文字列の開始</li><li>位置<ul><li>位置#</li></ul></li><li>文字列<ul><li>文字列値</li><li>索引</li><li>文字列を含めるフラグ</li></ul></li></ul></li><li>設定値<ul><li>文字列の終了</li><li>位置<ul><li>位置#</li></ul></li><li>文字列<ul><li>文字列値</li><li>索引</li><li>文字列を含めるフラグ</li></ul></li><li>長さ</li></ul></li></ul></li><li>右からトリミング<ul><li>送信元 <ul><li>文字列の終了</li><li>位置<ul><li>位置#</li></ul></li><li>文字列<ul><li>文字列値</li><li>索引</li><li>文字列を含めるフラグ</li></ul></li></ul></li><li>設定値<ul><li>文字列の開始</li><li>位置<ul><li>位置#</li></ul></li><li>文字列<ul><li>文字列値</li><li>索引</li><li>文字列を含めるフラグ</li></ul></li><li>長さ</li></ul></li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 1 つの関数</p> | <p>新しい派生フィールド</p> |


## ユースケース 1 {#trim-uc1}

製品データは収集しますが、そのデータには、フラグメントレポート用の非表示の空白文字が含まれています。 余分な空白を簡単にトリミングしたい場合

### 前のデータ {#trim-uc1-databefore}

| 製品 ID | イベント |
|---|--:|
| `"prod12356 "` | 1 |
| `"prod12356"` | 1 |
| `" prod12356"` | 1 |

{style="table-layout:auto"}

### 派生フィールド {#trim-u1-derivedfield}

`Product Identifier` の派生フィールドを作成します。 [!UICONTROL TRIM] 関数を使用して、「**[!UICONTROL 製品 ID]**」フィールドから **[!UICONTROL 空白をトリミング]** するルールを定義します。

![ 分割ルール 1 のスクリーンショット ](assets/trim-1.png)

### 後のデータ {#trim-uc1-dataafter}

| 商品識別子 | イベント |
|---|--:|
| `"prod12356"` | 3 |

{style="table-layout:auto"}

## ユースケース 2 {#trim-uc2}

収集されたページ名のデータで、ページ名の末尾に誤った特殊文字が含まれています。この特殊文字は削除する必要があります。

### 前のデータ {#trim-uc2-databefore}

| 名前 | イベント |
|---|--:|
| ホームページ# | 1 |
| ホーム ページ？ | 1 |
| ホームページ % | 1 |
| ホームページ&amp; | 1 |
| ホームページ/ | 1 |

{style="table-layout:auto"}

### 派生フィールド {#trim-u2-derivedfield}

`Page Name` の派生フィールドを作成します。 [!UICONTROL TRIM] 関数を使用すると、「特殊文字 [!UICONTROL `#?%&/` を使用して「[!UICONTROL  名前 ] フィールドから  特殊文字をトリミング ] するルールを定義できます。

![ 分割ルールのスクリーンショット – 最初の値 ](assets/trim-2.png)

### 後のデータ {#trim-uc2-dataafter}

| ページ名 | イベント |
|---|--:|
| ホームページ | 5 |

{style="table-layout:auto"}


## ユースケース 3 {#trim-uc3}

storeID を含むデータを収集します。 storeID には、最初の 2 文字として略語の US 状態コードが含まれます。 レポートでその状態コードのみを使用したい場合。

### 前のデータ {#trim-uc3-databefore}

| storeID | イベント |
|---|--:|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| または 234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### 派生フィールド {#trim-u3-derivedfield}

`Store Identifier` の派生フィールドを作成します。 [!UICONTROL TRIM] 関数を使用して、文字列の末尾から位置の `3` まで ][!UICONTROL storeID] フィールドを「右から切り捨て [!UICONTROL 」するルールを定義します。

![ 分割ルールのスクリーンショット – 最初の値 ](assets/trim-3.png)

### 後のデータ {#trim-uc3-dataafter}

| ストア識別子 | イベント |
|---|--:|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| OR | 1 |
| NV | 1 |

{style="table-layout:auto"}
+++


<!-- URL PARSE -->

### URL の解析

プロトコル、ホスト、パス、クエリパラメーターなど、URL の様々な部分を解析します。

+++ 詳細

## 仕様 {#urlparse-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>文字列</li></ul> | <ul><li>[!UICONTROL  フィールド ]:</li><ul><li>ルール</li><li>標準フィールド</li><li>フィールド</li></ul><li>[!UICONTROL  オプション ]:<ul><li>[!UICONTROL  プロトコルを取得 ]</li><li>[!UICONTROL  ホストを取得 ]</li><li>[!UICONTROL  パスを取得 ]</li><li>[!UICONTROL  クエリ文字列値を取得 ]<ul><li>[!UICONTROL  クエリパラメーター ]:<ul><li>文字列</li></ul></li></ul></li><li>[!UICONTROL  ハッシュ値を取得 ]</li></ul></li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 5 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース 1 {#urlparse-uc1}

マーケティングチャネルのルールセットの一部として、参照 URL の参照ドメインのみを使用できます。

### 前のデータ {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 派生フィールド {#urlparse-uc1-derivedfield}

`Referring Domain` の派生フィールドを定義します。 [!UICONTROL URL PARSE] 関数を使用して、「[!UICONTROL  参照 URL]」フィールドからホストを取得し、新しい派生フィールドに保存するルールを定義します。

![Url 解析ルール 1 のスクリーンショット ](assets/url-parse-1.png)

### 後のデータ {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## ユースケース 2 {#urlparse-uc2}

クエリ文字列の `cid` パラメーターの値を、派生トラッキングコードレポートの出力の一部として [!DNL Page URL] で使用する場合。

### 前のデータ {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 派生フィールド {#urlparse-uc2-derivedfield}

`Query String CID` の派生フィールドを定義します。 [!UICONTROL URL PARSE] 関数を使用して、「[!UICONTROL  ページ URL]」フィールドのクエリ文字列パラメーターの値を取得するルールを定義し、`cid` をクエリパラメーターとして指定します。 出力値は新しい派生フィールドに保存されます。

![Url 解析ルール 2 のスクリーンショット ](assets/url-parse-2.png)

### 後のデータ {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++

## 制限事項

派生フィールド機能全般に次の制限が適用されます。

- 派生フィールドのルールを定義する際には、（標準フィールドを除く）最大 10 個の異なるスキーマフィールドを使用できます。
   - この最大 10 個の異なるスキーマフィールドから、最大 3 個のルックアップスキーマまたはプロファイルスキーマフィールドのみを使用できます。
- Customer Journey Analytics接続ごとに最大 100 個の派生フィールドを設定できます。


### 関数の制限事項の概要

| 関数 | 制限事項 |
|---|---|
| <p>Case When</p> | <ul><li>派生フィールドごとに関数が 5 つの場合</li><li>派生フィールドあたり 200 [ 演算子 ](#operators)</li></ul> |
| <p>分類</p> | <ul><li>派生フィールドごとに 5 つの分類関数</li><li>派生フィールドあたり 200 [ 演算子 ](#operators)</li></ul> |
| <p>連結</p> | <ul><li>派生フィールドごとに 2 つの関数を連結</li></ul> |
| <p>重複排除</p> | <ul><li>派生フィールドごとに 5 つの重複排除関数</li></ul> |
| <p>検索と置換</p> | <ul><li>派生フィールドごとに 2 つの検索と置換関数</li></ul> |
| <p>ルックアップ</p> | <ul><li>派生フィールドごとに 5 つのルックアップ関数</li></ul> |
| <p>小文字</p> | <ul><li>派生フィールドごとに 2 つの小文字の関数</li></ul> |
| <p>Math</p> | <ul><li>派生フィールドあたり 25 操作</li><li>派生フィールドごとに 5 つの数学関数</li></ul> |
| <p>フィールドを結合</p> | <ul><li>派生フィールドごとに 2 つの結合フィールド関数</li></ul> |
| <p>次または前</p> | <ul><li>派生フィールドごとに 3 つの次または前の関数</li></ul> |
| <p>正規表現による置換</p> | <ul><li>派生フィールドごとに 1 つの正規表現置換関数</li></ul> |
| <p>Split</p> | <ul><li>派生フィールドごとに 5 つの分割関数</li></ul> |
| <p>要約</p> | <ul><li>3 派生フィールドごとの要約関数</li></ul> |
| <p>トリミング</p> | <ul><li>派生フィールドごとに 1 つの Trim 関数</li></ul> |
| <p>URL の解析</p> | <ul><li>派生フィールドごとに 5 つの URL 解析関数</li></ul> |

{style="table-layout:auto"}

### 演算子

Case When 関数内の If または Else If 構文の演算子は、条件と **1** 値の組み合わせです。 条件に値を追加するたびに、演算子の数が加算されます。

例えば、以下の条件では、13 個の演算子を使用しています。

![ サンプル演算子 ](assets/operators-sample.png)

分類関数の演算子は、[!UICONTROL  値が元の値と等しい場合 ][!UICONTROL  値を新しい値に置き換える ] の単一のエントリです。

例えば、以下の分類ルールでは、3 つの演算子を使用します。

![分類ルール 1 のスクリーンショット](assets/classify-1.png)


## 詳細情報 {#trim-more-info}

[`Trim`](#trim) と [`Lowercase`](#lowercase) は、 [データ ビューのコンポーネント設定で既に使用できる機能です](../component-settings/overview.md)。 派生フィールドを使用すると、これらの関数を組み合わせて、より複雑なデータ変換を Customer Journey Analytics で直接実行できます。 たとえば、 `Lowercase` を使用してイベント フィールドの大文字と小文字の区別を削除し、 [`Lookup`](#lookup) を使用して、新しいすべて小文字 フィールドを、すべて小文字 にルックアップ キーのみを持つルックアップ データセットと一致させることができます。 または、新しいフィールドに`Lookup`を設定する前に、`Trim`を使用して文字を削除することもできます。

派生フィールドでの参照およびプロファイルフィールドのサポートにより、イベントの参照とプロファイル属性に基づいてデータを変換できます。 これは、ルックアップまたはプロファイルデータセットにアカウントレベルのデータが含まれている B2B シナリオで特に役立ちます。 また、このサポートは、ルックアップデータ（キャンペーン情報やオファータイプなど）やプロファイルデータ（メンバー層やアカウントタイプなど）の共通フィールドでデータを操作する場合に役立ちます。

派生フィールドの背景情報については、を参照してください。

- [ データを最大限に活用：Customer Journey Analyticsで派生フィールドを使用するためのフレームワーク ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)

- [ 派生フィールドのCustomer Journey Analyticsのユースケース ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)
