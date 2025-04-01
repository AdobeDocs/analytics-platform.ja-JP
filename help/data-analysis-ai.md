---
description: Customer Journey Analytics ドキュメントのデータ分析に関する質問を行う方法
title: Customer Journey Analyticsの Data Insights Agent を使用したデータの視覚化
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: bc0573b2d75a18aaaac4f5d171579e9763f2f8e0
workflow-type: tm+mt
source-wordcount: '1703'
ht-degree: 3%

---

# Customer Journey Analyticsの Data Insights Agent を使用したデータの視覚化

Customer Journey Analyticsの AI アシスタントに含まれる Data Insights Agent は、データに関する質問に迅速かつ効率的に回答するジェネレーティブ AI コンバージョンエージェントです。 データビューのコンポーネントと実際のデータを使用して、Analysis Workspaceで関連するビジュアライゼーションを作成します。

Data Insights Agent を使用してAnalysis Workspaceのデータ中心の質問に回答すると、Analysis Workspaceでビジュアライゼーションを手動で構築し、データビューコンポーネントに慣れるまでに費やす可能性のある、膨大な時間を節約できます。

![AI アシスタント内の Data Insights エージェント ](assets/cja-ai-asst-da.gif)

## Alpha バージョンの範囲内機能と範囲外機能

### Alphaの範囲内機能

| サポートされる機能 | 説明 |
| --- | --- |
| **ビジュアライゼーションの作成と更新** | フリーフォームテーブルおよび関連するビジュアライゼーション（線、棒グラフ、ドーナツなど）を生成します。<p>例：*2 月から 5 月の SKU での利益は何ですか？* |
| **サポートされるビジュアライゼーションタイプ** | <ul><li>行</li><li>複数行</li><li>フリーフォームテーブル</li><li>棒グラフ</li><li>ドーナツ</li><li>概要番号</li></ul> |
| **範囲外のプロンプト検出** | 「このプロジェクトをエクスポートする」など、範囲外のプロンプトを送信すると、アシスタントは、質問が範囲外であることを知らせるように応答します。 |
| **質問の明確化** | データインサイトエージェントが回答するのに十分なコンテキストがない質問や、一般的すぎる質問については、データインサイトエージェントが、明確な質問や提案されたオプションで応答します。 例： <p>**コンポーネント**<ul><li>指標：*具体的に「売上高」指標はどれですか？*</li><li>Dimension:*注目したい「地域」は、以下のうちどれですか？*</li><li>フィルター：*適用した「アカウント」フィルター*</li><li>日付範囲：*「先月」とは、過去 1 か月を意味していますか？過去 30 日を意味していますか？*</li></ul>**Dimension商品**：店舗名はどちらですか？ （例えば、Store #5274、Store #2949 など）。 |
| **マルチターン** | データインサイトエージェントは、以前のプロンプトからのコンテキストでプロンプトに応答し、ユーザーはビジュアライゼーションを更新し、フォローアップの質問をすることができます。 例： <ul><li>プロンプト 1:*3 月からのトレンドイベント*</li><li>プロンプト 2:*代わりに 3 月から 4 月のデータを表示する*</li></ul> |
| **検証可能性** | データの検証可能性と正確性は、生成されたフリーフォームテーブルとデータビジュアライゼーションで確認できます。 例えば、ユーザーが *先月のトレンド注文* と尋ねた場合、新しく生成されたパネル、データビジュアライゼーションおよびフリーフォームテーブルで正しい指標（「注文」）と日付範囲（「先月」）が選択されたことを確認できます。 |
| **フィードバック** | <ul><li>親指を上に向ける</li><li>サムズダウン</li><li>Flag</li></ul> |

### Betaの範囲外の機能

| サポートされていない機能 | 説明 |
| --- | --- |
| **インラインの概要または応答** | データインサイトエージェントが、ユーザープロンプトの概要回答でチャットパネルのインラインで応答できません。 範囲外プロンプトの例：<ul><li>*前回のプロンプトから得られたインサイトの概要を入力します。*</li><li>*折れ線グラフのビジュアライゼーションのハイライトを要約します。*</li></ul> |
| **質問の明確化** | 質問を明確にするのは、コンポーネントとディメンション項目に限られます。 データインサイトエージェントは、データビュー、ビジュアライゼーション、データの精度、比較、範囲などを明確にすることはできません。 質問を明確にできない場合、アシスタントはデフォルトで要求する可能性が最も高い質問に設定されます。 予期しないビジュアライゼーションまたはデータの精度が返された場合は、複数回転/更新機能を使用してビジュアライゼーションとデータを調整できます。 |
| **Workspaceのアクション/機能** | データインサイトエージェントは、Workspace内のユーザーに対して、ビジュアライゼーションの作成と更新を除き、アクションを実行することはできません。 例えば、次の操作は実行できません。<ul><li>コンテキストアクションの UI ボタン（グラフに追加、新しいパネル、新しいテーブル）</li><li>共有</li><li>書き出し</li><li>ダウンロード</li><li>ユーザー環境設定の管理</li><li>キュレート</li><li>データ表示の管理</li><li>Analytics ダッシュボードアプリ</li><li>アトリビューション</li></ul> |
| **サポートされていないビジュアライゼーションタイプ** | <ul><li>フロー</li><li>フォールアウト</li><li>コホートテーブル</li><li>面グラフ、積み重ね面グラフ</li><li>積み重ね棒グラフ</li><li>ブレット</li><li>コンボ</li><li>ヒストグラム</li><li>横棒グラフ、積み重ね横棒グラフ</li><li>主要指標の概要</li><li>散布図</li><li>変更の概要</li><li>テキスト</li><li>ツリーマップ</li><li>ベン図</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## AI アシスタントでのアクセスおよびデータインサイトエージェント

1. [experience.adobe.com](https://experience.adobe.com/) に移動し、Adobe IDでログインします。

2. Experience Cloud ホームから **0}Customer Journey Analytics} を選択します。**

3. プロジェクトページ上部のバナーで **[!UICONTROL 空のプロジェクト]** を選択して、新しい空のプロジェクトを開きます。

4. パネル用に選択したデータビューが、Beta テスト用に Data Insights Agent で使用できるようになったデータビューと同じであることを確認します。

   不明な場合は、Beta Slackにお問い合わせください。

5. ページの右上にある AI Assistant チャットアイコンを選択します。

   チャットアイコンが表示されない場合は、管理者に問い合わせて、管理者が Admin Console で次の機能を有効にできるようにします。

   * **[!UICONTROL AI アシスタント：製品に関する知識]**

   * **[!UICONTROL AI アシスタント：データ分析]**

   詳細については、管理者は [ 以下の手順 ](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access) を参照してください。

   ![AI アシスタント アイコン ](/help/assets/ai-asst-icon.png)

6. ページ下部の **[!UICONTROL Customer Journey Analyticsについて尋ねる]** ダイアログで、AI アシスタントでデータビジュアライゼーションに関する質問をします。

   詳しくは、次の例を参照してください。

### 例 1

例えば、7 月にビジネスが受け取った注文に興味があるとします。

**プロンプト：** 「7 月のトレンド受注 *を入力します*。

![AI プロンプト ](/help/assets/ai-asst-prompt1.png)

**応答：** AI アシスタントの Data Insights エージェントは、指標やコンポーネントなど、データビューのデータを調べることでインサイトを収集します。 これにより、プロンプトがデータ範囲内の適切なディメンションと指標に変換されます。

ご覧のように、7 月の注文を表示する折れ線グラフとフリーフォームテーブルが自動的に生成されました。

![ プロンプトに対する回答 – 折れ線グラフとフリーフォームテーブル ](/help/assets/ai-asst-result.png)

### 例 2

次に、売上高を地域別に比較した結果を確認します。

**プロンプト：** プロンプトウィンドウで、「*地域ごとの売上高を表示」と入力します*。

**回答：** AI アシスタントの Data Insights エージェントは、「地域」とは「顧客地域」を意味することをインテリジェントに理解しています。 次のように、地域別の売上高が最もよく表示される棒グラフが生成されます。

![ 棒グラフ ](/help/assets/ai-asst-result2.png)

### 例 3

次に、地域別の売上高を把握するだけでなく、地域別の利益のデータも確認する必要があります。 前のプロンプトを繰り返す代わりに、AI アシスタントに最新のビジュアライゼーションとフリーフォームテーブルの更新を依頼することができます。

**プロンプト：** プロンプトウィンドウに *「Add profit.」と入力します*

**応答：** **[!UICONTROL 棒グラフ]** は引き続き最も簡潔な回答を提供しますが、利益指標はフリーフォームテーブルの列として追加されています。

![ 棒グラフ ](/help/assets/ai-asst-result4.png)

### 例 4

最後に、売上高を製品カテゴリ別に見てみましょう。

**プロンプト：** プロンプトウィンドウで、「*製品カテゴリ別売上高の割合」と入力します。*

**応答：** ここでも、AI アシスタントのデータインサイトエージェントは、最も適切なビジュアライゼーション（この場合は **[!UICONTROL ドーナツ]** ビジュアライゼーション）を選択して質問に回答します。

![ドーナツ](/help/assets/ai-asst-result3.png)

## データビジュアライゼーションプロンプトの例

以下に、一般的なプロンプトと、それらのプロンプトに応答するためにデータインサイトエージェントで使用されるビジュアライゼーションの例を示します。

| プロンプトの例 | 期待されるビジュアライゼーション |
| --- | --- |
| [ 月 ] の利益を表示する | 行<p>デフォルトでは、特定の期間内のトレンドや指標を尋ねると、折れ線グラフのビジュアライゼーションが返されます。 |
| [ 月 ] の注文のトレンド | 行 |
| 地域別の収益を [ 月 ] に表示 | 棒グラフ |
| 製品カテゴリ別売上高のシェア | ドーナツ |
| 1 月から 5 月までの曜日ごとの注文 | 棒グラフ |
| 3 月から 6 月の間、性別ごとに注文を表示 | 棒グラフ |
| 2 月から 5 月の SKU での利益 | 棒グラフ |
| [ 月 ] の店舗名別の売上高 | 棒グラフ |
| [ 月 ] の利益別の上位 10 個の SKU は何でしたか？ | 棒グラフ |
| 月別の購入率 | ドーナツ |
| [ 月 ] の合計利益 | 概要数値<p>特定の時間範囲にわたる指標の「合計」を求めると、数値の概要ビジュアライゼーションが返されます。 |


## プロンプトのベストプラクティス

データインサイトエージェントは、各ユーザープロンプトから提供されるコンテキストを処理し、フリーフォームテーブル内の最も適切なビジュアライゼーションとコンポーネントでインテリジェントな応答を試みます。

回答は、プロンプトで使用された特定の単語やフレーズによって異なる場合があり、言語がわずかに変更されただけで結果が異なる場合があります。

最適な結果を得るには、次のガイドラインを考慮してください。

* 具体的：応答を絞り込むために正確な用語を含めます。 次に、「カリフォルニアでの先月の売上」という特定のプロンプトの例を示します

* 明確な指標とフィルターの使用：特定の指標（「売上高」など）、ディメンション（「web サイト名」など）、フィルター（「iPhone ユーザー」など）、日付範囲（「過去 3 か月」など）を追加すると、データインサイトエージェントが適切なデータに焦点を当てることができます。

* 直接質問する：質問を直接言い換えると、データインサイトエージェントが明確で関連性の高いインサイトを提供しやすくなります。 次に、「今年の製品カテゴリ別平均売上高は何ですか？」というプロンプトで直接質問した例を示します。

AI アシスタントのデータインサイトエージェントを使用して、プロンプトで使用できる用語とフレーズの例を、期待できる応答のタイプと共に次の表で確認します。

これらの例は、特定の単語や構造が AI アシスタントの出力に与える影響を理解し、より正確で価値のあるインサイトを確保するのに役立つように設計されています。 AI アシスタントのデータインサイトエージェントは、生成 AI を使用するので、類似のプロンプト間でビジュアライゼーションや選択したデータが若干異なる場合があります。

| 望ましい結果 | 用語とフレーズの例 |
| --- | --- |
| 数値の概要ビジュアライゼーション | <ul><li>合計</li></ul> |
| コンポーネントの比較 | <ul><li>Compare</li><li>比較対象</li><li>コントラスト</li><li>週ごと</li><li>前月比</li><li>前四半期比</li><li>前年比</li></ul> |
| ドーナツグラフのビジュアライゼーション | <ul><li>割合</li><li>シェア /</li><li>配分</li><li>割合</li><li>貢献度</li><li>構成要素</li><li>部品</li></ul> |
| 折れ線グラフビジュアライゼーション | <ul><li>トレンド</li><li>[ 時間範囲 ] の [ 指標 ]</li></ul> |
| 棒グラフビジュアライゼーション | <ul><li>[ 指標 ] （[Dimension] による）</li></ul> |

## Beta テストの期待値とリクエストされたフィードバック

質問ごとにポーズを設定した後、アシスタントの提供した回答を注意深く確認します。 フィードバックを提供する前に、生成されたビジュアライゼーションを包括的に評価することが重要です。

AI Assistant で Data Insights Agent からの応答を評価する際は、以下の点を考慮してください。

* チャットパネルの応答またはテンプレート：アシスタントから提供されたテキストの応答を評価します。 プロンプトのコンテキストに基づいて応答は適切か

* ビジュアライゼーション/グラフ：ビジュアライゼーションを評価します。 これは質問に対する適切な、または期待されるビジュアライゼーションですか？それとも、別のビジュアライゼーションを期待していますか？

* フリーフォームテーブル：フリーフォームテーブルを評価します。 フリーフォームテーブルデータは正しいですか？ 要求された場所でデータが分類されていますか？ 適用されたフィルターは、要求した、または期待したフィルターですか？

* エラーメッセージ/範囲外：質問が範囲外であることを示す一般的なエラーメッセージが表示された場合は、プロンプトに対して、範囲外のメッセージが適切であると思うかどうかに関するフィードバックを提供します。 あなたのプロンプトは本当にスコープに入っていたのですか？

**すべての応答に対して、応答に基づいてサムズアップまたはサムズダウンを行います。**

サムズアップまたはサムズダウンの選択に続いて、関連する複数選択フィードバックボックスの選択を行ってください。 追加のフィードバックを提供する場合は、「開く」テキストボックスにメモを追加します。

## 質問と連絡先

* Alpha Slack チャネルで質問やフィードバックを送信：#cja-assistant-data-alpha
