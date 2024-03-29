---
description: 計算指標ビルダーは、ディメンション、指標、フィルターおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成するためのキャンバスです。この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。
title: 指標の作成
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 60%

---

# 指標の作成

Customer Journey Analyticsには、ディメンション、指標、フィルターおよび関数をドラッグ&amp;ドロップするキャンバスがあり、コンテナ階層のロジック、ルールおよび演算子に基づいてカスタム指標を作成できます。 この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。

## 計算指標の作成を開始する

計算指標の作成は、次のいずれかの方法で開始できます。

* Analysis Workspaceで、プロジェクトを開き、「 」を選択します。 **[!UICONTROL コンポーネント]** > **[!UICONTROL 指標を作成]**.
* Analysis Workspaceで、プロジェクトを開き、 **プラス** 横のアイコン [!UICONTROL **指標**] セクションをクリックします。
* In [!DNL Customer Journey Analytics]に移動します。 **[!UICONTROL コンポーネント]** > **[!UICONTROL 計算指標]**&#x200B;を選択し、「 **[!UICONTROL +追加]** をクリックします。

## 計算指標ビルダーの領域

次の画像と付属の表は、計算指標ビルダーの主な機能と主な機能を説明しています。

![この節で説明する主な領域と機能を示す新しい計算指標ウィンドウ。](assets/cm_builder_ui.png)

| フィールド | 説明 |
| --- | --- |
| タイトル | 指標には必ず名前を付ける必要があります。名前を付けていない指標は保存できません。 |
| 説明 | 指標の用途を示し、類似した指標と区別するための、ユーザーにわかりやすい説明を入力します。 <p>この説明はレポート内にも表示されます。説明には数式を記述しないことをお勧めします。その代わりに、この指標を使うべき状況と使ってはいけない状況について記述してください（数式は、指標の作成時に「概要」という見出しの下に生成されます。そのため、この説明に数式を追加する必要はありません）。 </p> |
| 形式 | 小数、時間、割合、通貨から選択できます。 |
| 小数点以下の桁数 | レポートに表示する小数点以下の桁数を示します。指定可能な小数点以下の桁数の最大値は 10 です。 |
| 上昇傾向を次の形式で表示 | この指標の両極性の設定は、Analytics が指標の上昇傾向を良い（緑）または悪い（赤）のどちらと見なすべきかを示します。そのため、レポートのグラフは、上昇傾向の場合に緑または赤で表示されます。 |
| 通貨 | このデータビューのベース通貨。 |
| タグ | タグ付けは、指標を管理するための便利な方法です。すべてのユーザーがタグを付けることができます。指標には 1 つ以上のタグを適用できます。ただし、自分が所有しているまたは自分が共有していたフィルターに対するタグのみを表示できます。どのような種類のタグを作成する必要がありますか。次に、便利なタグのいくつかを示します。<ul><li>**チーム名**（ソーシャルマーケティング、モバイルマーケティングなど）。</li><li>**プロジェクト** （分析タグ）を使用できます。</li><li>**カテゴリ**&#x200B;例：女性用；地理。</li><li>**ワークフロー**（承認待ちなど）。（特定のビジネスユニット向けの）キュレーション。</li></ul> |
| 概要 | <p>「概要」の数式は、指標の定義を変更すると更新されます。この数式は、左側の指標レールで、指標の上にマウスポインターを置いて <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> アイコン。 </p> |
| 定義 | ここに指標や計算指標、フィルター、関数などをドラッグして、計算指標を作成します。 <ul><li>計算指標をドラッグすると、指標の定義が自動的に展開されます。 </li> <li>コンテナを使用して定義をネストできます。ただし、フィルターコンテナとは異なり、これらのコンテナは数式のように機能し、演算の順序を決定します。 </li> </ul> |
| 演算子 | 除算 ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) はデフォルトの演算子です。他にも、+、 — および x の演算子があります。 |
| プレビュー | 可能性のあるエラーについて簡単に確認できます。プレビューには過去 90 日の情報が表示されます。これは、指標に適したコンポーネントを選択したかどうかを最初に判断するための手段です。予期しない結果が生じた場合は、指標の定義を見直す必要があります。 |
| 製品の互換性 | Customer Journey Analyticsで作成する計算指標の場合、この値は常に [!UICONTROL **処理済みのデータ**]. 計算指標には、イベントデータセットのデータのみを含めることができます。 |
| 追加 | すべてのタイプの計算指標の場合、コンテナおよび静的な数値を定義に追加できます。詳細な計算指標では、フィルターと関数も追加できます。<ul><li>コンテナは数式のように機能し、演算の順序を指定します。そのため、コンテナ内の項目は、次の演算の前に処理されます。</li><li>フィルターをコンテナにドラッグすると、そのコンテナ内のすべての項目がフィルターされます。 （高度な計算指標のみ）</li><li>コンテナでは複数のフィルターを積み重ねることができます。</li></ul> |
| 歯車アイコン（指標タイプ、アトリビューション） | 指標の横にある歯車アイコンをクリックすると、指標タイプとアトリビューションモデルを指定できます。 <p>**注意：** コンポーネントのアトリビューションをデフォルト以外のアトリビューションモデルに更新する際は、次の点を考慮してください。</p><ul><li>**コンポーネントを *単一の次元*:** デフォルト以外のアトリビューションモデルが使用される場合、コンポーネントのアトリビューションは割り当てモデルを無視します。</li><li>**コンポーネントを *複数のディメンション*:** デフォルト以外のアトリビューションモデルが使用される場合、コンポーネントのアトリビューションには割り当てモデルが保持されます。</li><li>複数のディメンションは、 [クラウドへのデータのエクスポート](/help/analysis-workspace/export/export-cloud.md).</li></ul> <p>配分について詳しくは、 [永続性コンポーネントの設定](/help/data-views/component-settings/persistence.md).</p> |
| プラス (+) アイコン | 新しいフィルターなどの新しいコンポーネントを作成できます（フィルタービルダーが表示されます）。 |
| コンポーネントを検索 | この検索バーでは、ディメンション、指標、フィルター（高度な計算指標のみ）および関数（高度な計算指標のみ）を検索できます。 |
| ディメンションリスト | （フィルタービルダーで）単純なフィルター（例：「Page = Homepage」）を作成するために計算指標ビルダーから離れる代わりに、Page にドラッグして、計算指標ビルダーから直接「Homepage」を選択できます。 これにより、フィルタリングされた計算指標を作成するワークフローを効率化できます。 |
| 指標リスト | 指標は次の 3 つのカテゴリに分かれています。<ul><li>標準指標</li><li>計算指標</li><li>指標テンプレート - リストの一番下</li></ul>指標の上にカーソルを移動すると、右側に情報アイコンが表示されます。このアイコンをクリックすると、次の情報が表示されます。<ul><li>指標の計算を行うための数式。</li><li>指標の傾向のプレビュー</li><li>右上の編集（鉛筆）アイコンをクリックすると、計算指標ビルダーに移動します。このビルダーで、この計算指標を編集できます。</li></ul> |
| フィルターのリスト | （詳細な計算指標のみ）管理者の場合、ログイン会社で作成されたすべてのフィルターがこのリストに表示されます。管理者でないユーザーの場合、自分が所有するフィルターと自分に共有されたフィルターがこのリストに表示されます。 |
| 関数リスト | （高度な計算指標のみ）関数が 2 つのリストに分けて表示されます。基本的な関数（最も頻繁に使用される関数）と高度な関数。 |
| データビューセレクター | 右上のこのセレクターを使用すると、別のデータビューに切り替えることができます。 |
