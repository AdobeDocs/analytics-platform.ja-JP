---
title: メディア分平均オーディエンスパネル
description: Analysis Workspace のメディア分平均オーディエンスパネルを使用および解釈する方法。
feature: Panels
role: User, Admin
source-git-commit: 907a627720910794d77f016d797f1b95d2d3ce13
workflow-type: tm+mt
source-wordcount: '1656'
ht-degree: 31%

---

# メディア分平均オーディエンスパネル

>[!NOTE]
>
>メディアの分平均オーディエンスパネルは、Customer Journey Analytics用に Media Analytics アドオンを購入したお客様のみ利用できます。
>
>Media Analytics を購入するには、Adobeの営業担当者またはAdobeのアカウントチームにお問い合わせください。

Analysis Workspace での分平均オーディエンスは、メディアストリームを視聴した時間をコンテンツの期間（または選択した期間や精度の合計値）で割った値です。

メディアの分平均オーディエンスパネルでは、あらゆる長さやジャンルのプログラムを比較することで、コンテンツの平均消費量をより深く把握できます。 例えば、30 分のサイトコムと 3 時間のスポーツイベントを比較する場合の平均消費量を把握できます。

さらに、メディアの分平均オーディエンスパネルを使用して、このデジタル平均分オーディエンスを、線形 TV の分平均指標と比較または追加できます。

メディアの分平均オーディエンスパネルには、分平均オーディエンス指標に対する次のメリットがあります。

* カスタム期間をサポート

* 表示が処理された後（表示が存在しなかった場合や修正が必要な場合）、期間の分類を更新できます。

  指標を使用する際にこれをおこなった場合は、存在しないか（分類が存在しなかった場合）、古くなっています（分類が存在し、正しくない場合）。

## メディアの平均分オーディエンスパネルにアクセスします

1. Analysis Workspaceで、Media Analytics コンポーネントが有効になっているレポートスイートに移動します。

1. 左側のナビゲーションで、 **パネル** アイコン。

   ![左側のナビゲーションのパネルアイコン](assets/panels-icon.png)

1. 次の項目をドラッグ： [!UICONTROL **メディア分平均オーディエンス**] パネルをAnalysis Workspaceのキャンバスに移動します。

1. パネルを設定するには、次に進みます。 [パネル入力](#panel-inputs).

## パネル入力 {#Input}

この節で説明する入力設定を使用して、メディアの分平均オーディエンスパネルを設定します。

1. メディアの分平均オーディエンスパネルの作成を開始します ( [メディアの平均分オーディエンスパネルにアクセスします](#access-the-media-average-minute-audience-panel).

1. 次の入力設定を指定します。

   | 設定 | 説明 |
   |---------|------------|
   | **パネルの日付範囲** | パネルの日付範囲のデフォルトは [!UICONTROL **今月**]. 編集して、1 日または数ヶ月を一度に表示できます。 <br></br>このビジュアライゼーションは、1440 行のデータ（例えば、分単位の精度で 24 時間）に制限されています。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。 |
   | [!UICONTROL **ここにセグメント（または他のコンポーネント）をドロップ**] | 他のパネルと同様に、この設定では、作成したセグメントに基づいて選択内容がフィルタリングされます。 これは、特定のプラットフォーム、ライブストリームまたはその他の一般的なメディアセグメントを調べる優れた方法です。 |
   | [!UICONTROL **次の指標を計算：**] | 特定のコンテンツ部分の分平均オーディエンスを表示するか、カスタム期間の分平均オーディエンスを表示するかを選択します。<ul><li>**特定のコンテンツ：** この機能は、期間が分類を使用して更新されている場合にのみ使用できます。 期間を指定できない場合、または（ライブストリーム中やイベント中などに）特定の期間を指定せずに、複数のコンテンツやコンテンツを含む時系列の分平均オーディエンスを表示する場合は、 [!UICONTROL **カスタム期間**]. （期間は、処理時間の前後に分類を使用して設定できます）。</li><li>**カスタム期間：** この期間は、分類を使用して期間を有効にするかどうかに関係なく、使用できます。</li></ul> <p>この設定により、ワークフローとレポートの出力が変更されます。</p> |

1. 次で続行 [特定のコンテンツ](#specific-content) または [カスタム期間](#custom-time-period)( [!UICONTROL **次の指標を計算：**] ドロップダウンメニュー。

### 特定のコンテンツ

1. 次を選択した場合： [!UICONTROL **特定のコンテンツ**] （内） [!UICONTROL **次の指標を計算：**] 次の場合のドロップダウンメニュー [パネル入力の設定](#panel-inputs)で、次の設定オプションを指定します。

   | 設定 | 説明 |
   |---------|------------|
   | [!UICONTROL **レポートディメンション**] | 特定のコンテンツを選択する場合、レポート出力を選択して、ビデオ名またはコンテンツ ID フィールドを使用し、選択した期間に対するコンテンツとそれに関連する分平均オーディエンスを表示できます。 |
   | [!UICONTROL **次の条件でコンテンツをフィルター（オプション）**] | 目的の表示やデータの構造に応じて、特定のコンテンツをフィルタリングする方法を選択します。 <ul>[!UICONTROL **表示、シーズン、エピソード**]：使用可能な番組をドロップダウンに表示します。検索を使用してフィルタリングできます（または、左の列から番組名をドラッグ&amp;ドロップします）。 そこで選択を終了して、番組のすべてのシーズンを表示するか、個々のシーズン、次に個々のエピソードでフィルタリングできます。この設定では、選択した期間の番組、シーズンまたはエピソードのデータを表示します。</li><li>[!UICONTROL **カスタムディメンション**]：番組名がカスタムディメンションの下にある場合は、ディメンション（オプション）ドロップダウンで検索するか、左列の検索を使用して、見つけることができます。 ディメンション項目は、その選択に基づいて自動的に入力され、エピソードとして扱われます。</li><li>[!UICONTROL **なし**]：選択した選択範囲の分平均オーディエンスデータを持つすべてのビデオ名を表示します。 （このオプションはデフォルトで選択されています）。</li></ul> |

1. 次で続行 [特定のコンテンツの詳細設定](#specific-content-advanced-settings) をクリックして詳細設定を構成します。

### 特定のコンテンツの詳細設定

1. を使用 [!UICONTROL **特定のコンテンツ**] 選択された [!UICONTROL **次の指標を計算：**] ドロップダウンメニューで、「 [!UICONTROL **詳細設定を表示**]&#x200B;次に、次の設定オプションを指定します。

   | 設定 | 説明 |
   |---------|------------|
   | テーブル設定 | デフォルト設定では、テーブル内の計算値が表示され、分平均オーディエンスの分子と分母がテーブルの前の列として表示されます。このオプションの選択を解除すると、2 つの列が削除され、ビデオ名またはコンテンツ ID の横の分平均オーディエンスのみが残ります。 |
   | 滞在時間指標 | デフォルトのコンテンツ視聴時間（コンテンツ視聴時間のみを含む）を選択するか、メディア視聴時間（コンテンツ時間と広告時間を含む）を分平均オーディエンスの分子の計算に使用することを選択できます。 |

1. 選択 [!UICONTROL **ビルド**] メディアの分平均オーディエンスパネルの作成を完了するため。

1. 次で続行 [パネル出力](#panel-output) メディアの分平均オーディエンスパネルの使用方法に関する情報を参照してください。

### カスタム期間

1. 次を選択した場合： [!UICONTROL **カスタム期間**] （内） [!UICONTROL **次の指標を計算：**] 次の場合のドロップダウンメニュー [パネル入力の設定](#panel-inputs)で、次の設定オプションを指定します。

   | 設定 | 説明 |
   |---------|------------|
   | 精度 | デフォルトの精度は次のとおりです。 [!UICONTROL **5 分**]&#x200B;を選択できますが、カレンダーの選択でおこなわれた全期間選択内の時系列の分母として使用される任意の精度を選択できます。 例えば、精度を 5 分にして午後 12:00 ～ 12:30 に設定した場合、30 分間の平均分オーディエンスと、各 5 分間の平均分オーディエンスを持つ 6 行が返されます。 これらの行は、時系列グラフのデータポイントとして使用されます。 |
   | [!UICONTROL **次の条件でコンテンツをフィルター（オプション）**] | 目的の表示やデータの構造に応じて、特定のコンテンツをフィルタリングする方法を選択します。 <ul>[!UICONTROL **表示、シーズン、エピソード**]：使用可能な番組をドロップダウンに表示します。検索を使用してフィルタリングできます（または、左の列から番組名をドラッグ&amp;ドロップします）。 そこで選択を終了して、番組のすべてのシーズンを表示するか、個々のシーズン、次に個々のエピソードでフィルタリングできます。この設定では、選択した期間の番組、シーズンまたはエピソードのデータを表示します。</li><li>[!UICONTROL **カスタムディメンション**]：番組名がカスタムディメンションの下にある場合は、ディメンション（オプション）ドロップダウンで検索するか、左列の検索を使用して、見つけることができます。 ディメンション項目は、その選択に基づいて自動的に入力され、エピソードとして扱われます。</li><li>[!UICONTROL **なし**]：選択した選択範囲の分平均オーディエンスデータを持つすべてのビデオ名を表示します。 （このオプションはデフォルトで選択されています）。</li></ul> |

1. 次で続行 [カスタム期間の詳細設定](#custom-time-period-advanced-settings) をクリックして詳細設定を構成します。

### カスタム期間の詳細設定

1. を使用 [!UICONTROL **カスタム期間**] 選択された [!UICONTROL **次の指標を計算：**] ドロップダウンメニューで、「 [!UICONTROL **詳細設定を表示**]&#x200B;次に、次の設定オプションを指定します。

   | 設定 | 説明 |
   |---------|------------|
   | テーブル設定 | デフォルト設定では、テーブル内の計算値が表示され、分平均オーディエンスの分子と分母がテーブルの前の列として表示されます。このオプションの選択を解除すると、2 つの列が削除され、期間の横の分平均オーディエンスのみが残ります。 |

1. 選択 [!UICONTROL **ビルド**] メディアの分平均オーディエンスパネルの作成を完了するため。

1. 次で続行 [パネル出力](#panel-output) メディアの分平均オーディエンスパネルの使用方法に関する情報を参照してください。

## パネル出力

パネルの出力は、選択した内容によって異なります [!UICONTROL **特定のコンテンツ**] または [!UICONTROL **カスタム期間**] （内） [!UICONTROL **次の指標を計算：**] 次の場合のドロップダウンメニュー [パネル入力の設定](#panel-inputs).

### 特定のコンテンツ

メディアの分平均オーディエンスパネルは、次の値を返します。

* 選択期間全体の合計分平均オーディエンス
* テーブルに表示される個々のビデオのフィルターおよび分平均オーディエンス
* 詳細設定が選択されている場合は、コンテンツ視聴時間とビデオの長さ（期間）

パネルを編集および再構築するには、右上の編集（鉛筆）アイコンを選択します。

![デフォルトのビュー](assets/specific-content-panel-output.png)

### 特定のコンテンツデータソース

メディアの分平均オーディエンスパネルでは、分平均オーディエンス指標のみを使用してデータを収集します。 分類やその他の指標は、パネルでは使用できません。

| 指標 | 説明 |
|--------|-------------|
| 分平均オーディエンス | メディアストリームの視聴に費やした時間を、分類で提供されたビデオの長さ（期間）で割った値です。 |

### カスタム期間 {#custom-time-period-output}

メディアの分平均オーディエンスパネルは、次の値を返します。

* 選択範囲全体の合計分平均オーディエンス

* 分単位の最大オーディエンスと最小平均オーディエンス

* 選択範囲全体の分平均オーディエンスを示す線系列グラフ。

* 精度のフィルターと平均分オーディエンス、および各期間のコンテンツ滞在時間と精度を表示するテーブル

  このテーブルは、「詳細設定」で「 [!UICONTROL **テーブルに計算値を表示**] が選択されている。

パネルを編集および再構築するには、右上の編集（鉛筆）アイコンを選択します。

![同時視聴者数出力](assets/custom-time-period-panel-output.png)

### カスタム期間データソース

メディアの分平均オーディエンスパネルでは、分平均オーディエンス指標のみを使用してデータを収集します。 分類やその他の指標は、パネルでは使用できません。

| 指標 | 説明 |
|---|---|
| 分平均オーディエンス | メディアストリームの視聴に費やした時間を、選択期間全体または選択した精度（分単位）で割った値です。 |
