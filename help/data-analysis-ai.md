---
description: Customer Journey Analyticsドキュメントのデータ分析に関する質問を行う方法
title: Customer Journey Analyticsの Data Analysis AI アシスタント
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: 7f5eddcf1ceaa6228411867f5794bfe72b2ad6ab
workflow-type: tm+mt
source-wordcount: '1537'
ht-degree: 4%

---


# Customer Journey Analyticsでの Data Analysis AI アシスタント -Alpha

Data Analysis AI Assistant は、Customer Journey Analytics内のAnalysis Workspace データに関する質問に、より迅速かつ効率的に回答するのに役立つ、インテリジェントなコンテキスト認識型の会話エージェントです。

アシスタントは、様々なタイプの指標やコンポーネントを含む、データビュー内のすべてのデータを調べ、分析に適したディメンション、指標、日付範囲にプロンプトを翻訳します。 データビューコンポーネントに慣れてから、これらのコンポーネントを最適な組み合わせでドラッグ&amp;ドロップして質問に答える代わりに、AI アシスタントに質問を入力するだけです。

## Alpha版の範囲内機能と範囲外機能

### 範囲内Alpha機能

| サポートされる機能 | 説明 |
| --- | --- |
| **ビジュアライゼーションの作成と更新** | フリーフォームテーブルおよび関連するビジュアライゼーション（線、棒、ドーナツなど）を生成します。<p>例：*2 月から 5 月の SKU での利益は何ですか？* |
| **サポートされるビジュアライゼーションタイプ** | <ul><li>行</li><li>複数行</li><li>フリーフォーム</li><li>棒グラフ</li><li>ドーナツ</li><li>概要数値</li></ul> |
| **範囲外のプロンプト検出** | 「このプロジェクトをエクスポート」など、範囲外のプロンプトを送信すると、アシスタントは、質問が範囲外であることを知らせるように応答します。 |
| **質問の明確化** | AI アシスタントが回答するのに十分なコンテキストがない、または一般的すぎる質問に対しては、AI アシスタントは明確な質問や提案されたオプションで応答します。 例： <p>**コンポーネント**<ul><li>指標：*具体的に「売上高」指標はどれですか？*</li><li>Dimension:*注目したい「地域」は以下のうちどれですか？*</li><li>フィルター：*適用した「アカウント」フィルター*</li><li>日付範囲：*「先月」では、過去 1 か月を意味していますか？それとも過去 30 日を意味していますか？*</li></ul>**Dimension項目**：どのような「ストア名」を意味しましたか？ （例：Store #5274、Store #2949 など）。 |
| **マルチターン** | AI アシスタントが、以前のプロンプトのコンテキストを含むプロンプトに応答し、ユーザーがビジュアライゼーションを更新し、フォローアップの質問をできるようにします。例： <ul><li>プロンプト 1:*3 月からのトレンドイベント*</li><li>プロンプト 2:*代わりに 3 月から 4 月のデータを表示する*</li></ul> |
| **フィードバック** | <ul><li>親指を上に向ける</li><li>サムズダウン</li><li>Flag</li></ul> |

### 範囲外のAlpha機能

| サポートされていない機能 | 説明 |
| --- | --- |
| **インラインの概要または応答** | AI アシスタントが、ユーザープロンプトの概要回答でチャットパネルのインラインで応答できません。範囲外プロンプトの例：<ul><li>*前回のプロンプトから得られたインサイトの概要を入力します。*</li><li>*折れ線グラフのビジュアライゼーションのハイライトを要約します。*</li></ul> |
| **質問の明確化** | 質問を明確にするのは、コンポーネントとディメンション項目に限られます。 AI アシスタントでは、データビュー、ビジュアライゼーション、データの精度、比較、範囲などを明確にすることはできません。 質問を明確にしない場合、アシスタントはデフォルトで要求する可能性の高い項目に設定されます。 予期しないビジュアライゼーションまたはデータの精度が返された場合は、複数回転/更新機能を使用してビジュアライゼーションとデータを調整できます。 |
| **Workspaceのアクション /機能** | AI アシスタントは、ビジュアライゼーションの作成と更新を除き、Workspaceのユーザーに対してアクションを実行することはできません。 例えば、次の操作は実行できません。<ul><li>コンテキストアクションの UI ボタン（グラフに追加、新しいパネル、新しいテーブル）</li><li>共有</li><li>書き出し</li><li>ダウンロード</li><li>ユーザー環境設定の管理</li><li>キュレート</li><li>データ表示の管理</li><li>Analytics ダッシュボードアプリ</li><li>アトリビューション</li></ul> |
| **サポートされていないビジュアライゼーションタイプ** | <ul><li>フロー</li><li>フォールアウト</li><li>コホートテーブル</li><li>面グラフ、積み重ね面グラフ</li><li>積み重ね棒グラフ</li><li>ブレット</li><li>コンボ</li><li>ヒストグラム</li><li>横棒グラフ、積み重ね横棒グラフ</li><li>主要指標の概要</li><li>散布図</li><li>変更の概要</li><li>テキスト</li><li>ツリーマップ</li><li>ベン図</li></ul> |
| **説明性及び検証性** | AI アシスタントが応答を生成する方法の説明や引用を提供し、回答が正しいことを確認する方法を提供します。 |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Data Analysis AI アシスタントへのアクセスと使用

1. [experience.adobe.com](https://experience.adobe.com/) に移動し、Adobe IDでログインします。

2. Experience Cloudのホームから **0}Customer Journey Analytics} を選択**

3. プロジェクトページ上部のバナーにある「**[!UICONTROL 空のプロジェクト]**」をクリックして、新しい空のプロジェクトを開きます。

4. パネル用に選択したデータビューが、Alphaテスト用に AI アシスタントが有効にしたデータビューであることを確認します（不明な場合は、taylorb@adobe.comまたはAlpha Slack チャンネルにお問い合わせください）

5. 右上の AI Assistant チャットアイコンをクリックします。

   ![AI アシスタント アイコン ](/help/assets/ai-asst-icon.png)

6. 下部の **[!UICONTROL Customer Journey Analyticsについて尋ねる]** ダイアログで、AI アシスタントでデータ分析の質問をします。

### 例 1

例えば、7 月にビジネスが受け取った注文に興味があるとします。

1. 「*7 月のトレンド受注」と入力します*

   ![AI プロンプト ](/help/assets/ai-asst-prompt1.png)

2. AI アシスタントは、指標やコンポーネントなど、データビューでデータを調べることでインサイトを収集するようになりました。 これにより、プロンプトが適切なディメンション、指標およびデータ範囲に変換されます。

   ご覧のように、7 月の注文を示す折れ線グラフとフリーフォームテーブルが自動的に生成されています。

   ![ プロンプトに対する回答 – 折れ線グラフとフリーフォームテーブル ](/help/assets/ai-asst-result.png)

### 例 2

次に、売上高を地域別に比較した結果を確認します。

1. プロンプトウィンドウで、「*地域ごとの売上高を表示」と入力します*。

2. AI アシスタントは、「地域」とは「顧客地域」を意味することをインテリジェントに理解しています。 次のように、地域別の売上高が最もよく表示される棒グラフが生成されます。

   ![ 棒グラフ ](/help/assets/ai-asst-result2.png)

### 例 3

次に、製品カテゴリ別の売上高について見てみましょう。

1. プロンプトウィンドウで、「製品カテゴリ別の売上高の割合 *と入力します。*

2. ここでも、データ分析 AI アシスタントは、最も適切なビジュアライゼーション（この場合は **[!UICONTROL ドーナツ]** ビジュアライゼーション）を選択して、質問に答えます。

   ![ドーナツ](/help/assets/ai-asst-result3.png)

### 例 4

最後に、最も収益性の高い SKU と、マーケティングリソースをどこに投資すべきかを把握する必要があります。

1. プロンプトウィンドウで *「2 月から 5 月までの SKU 間の利益は何ですか」と尋ねます。*

2. シンプルな **[!UICONTROL 棒]** グラフで、最も簡潔な回答を示します。

   ![ 棒グラフ ](/help/assets/ai-asst-result4.png)

## データ分析プロンプトの例

一般的なプロンプトの例と、AI 支援がそれらのプロンプトに応答するために使用するビジュアライゼーションを示します。

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

AI アシスタントは、各ユーザープロンプトによって提供されるコンテキストを処理し、フリーフォームテーブルのコンポーネントだけでなく、最も適切なビジュアライゼーションでもインテリジェントな応答を試みます。 ただし、AI アシスタントの応答は、プロンプトで使用される特定の単語やフレーズによって異なる場合があるので、言語をわずかに変更すると異なる結果になる可能性があります。 これを最大限に活用する方法を次に示します。 <ul><li>具体的：正確な用語（「先月のカリフォルニアでの売上高」など）を含めて、応答を絞り込みます。</li><li>指標とフィルターのクリアな使用：特定の指標（「売上高」など）、ディメンション（「web サイト名」など）、フィルター（「iPhone ユーザー」など）、および日付範囲（「過去 3 か月」など）を追加すると、AI アシスタントが適切なデータに集中することができます。</li><li>直接質問する：「今年の製品カテゴリ別平均売上高は何か」など、フレーズで直接質問する を使用すると、AI アシスタントが明確で関連性の高いインサイトを提供しやすくなります。</li></ul>

CJA の Data Analysis AI アシスタントでプロンプトで使用できる用語とフレーズの例を、期待できる応答のタイプと共に以下の表で確認してください。 これらの例は、特定の単語や構造が AI アシスタントの出力に与える影響を理解し、より正確で価値のあるインサイトを確保するのに役立つように設計されています。 AI アシスタントは生成 AI を使用するので、類似のプロンプト間でビジュアライゼーションや選択したデータが若干異なる場合があります。

| 望ましい結果 | 用語とフレーズの例 |
| --- | --- |
| 数値の概要ビジュアライゼーション | <ul><li>合計</li></ul> |
| コンポーネントの比較 | <ul><li>Compare</li><li>比較対象</li><li>コントラスト</li><li>週ごと</li><li>前月比</li><li>前四半期比</li><li>前年比</li></ul> |
| ドーナツグラフのビジュアライゼーション | <ul><li>割合</li><li>シェア /</li><li>配分</li><li>割合</li><li>貢献度</li><li>構成要素</li><li>部品</li></ul> |
| 折れ線グラフのビジュアライゼーション | <ul><li>トレンド</li><li>[ 時間範囲 ] の [ 指標 ]</li></ul> |
| 棒グラフのビジュアライゼーション | <ul><li>[ ディメンション ] 別の [ 指標 ]</li></ul> |

## Alphaテストの期待値とリクエストされたフィードバック

質問ごとにポーズを設定した後、アシスタントの提供した回答を注意深く確認します。 フィードバックを提供する前に、生成されたビジュアライゼーションを包括的に評価することが重要です。 AI アシスタントからの応答を評価する際は、次の点を考慮してください。

* チャットパネルの応答またはテンプレート：アシスタントから提供されたテキストの応答を評価します。 使用しているプロンプトのコンテキストに応じて、応答は適切ですか？

* ビジュアライゼーション/グラフ：ビジュアライゼーションを評価します。 このビジュアライゼーションは質問に対する適切なビジュアライゼーションか、それとも別のビジュアライゼーションを期待していたのでしょうか？

* フリーフォームテーブル：フリーフォームテーブルを評価します。 フリーフォームテーブルデータは正しいですか？ 要求された場所でデータが分類されていますか？ 適用されたフィルターは、要求した、または期待したフィルターですか？

* エラーメッセージ/範囲外：質問が範囲外であるという一般的なエラーメッセージが表示された場合は、プロンプトに対して、範囲外のメッセージが適切であると思うかどうかをフィードバックしてください。 プロンプトは実際にスコープ内にありましたか？

**回答ごとに、回答に基づいて親指を上げるか下げてください**

サムズアップ/ダウンセレクションの後に、関連する複数選択フィードバックボックスのセレクションを行ってください。 追加のフィードバックを提供する場合は、「開く」テキストボックスにメモを追加します。

## 質問と連絡先

* E メール `taylorb@adobe.com` （PM）
* AlphaSlack チャンネルで質問やフィードバックを送信：#aep-cja-ai-assistant-testers ???


