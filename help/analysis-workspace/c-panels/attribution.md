---
title: アトリビューションパネル
description: Analysis Workspace でのアトリビューションパネルの使用方法と解釈方法。
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: c89a28323c9d40a7265cd22994a0d1c484f4c7ee
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 80%

---

# アトリビューションパネル {#attribution-panel}

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_button"
>title="アトリビューション"
>abstract="任意のディメンションとコンバージョン指標を使用して、アトリビューションモデルをすばやく比較および視覚化します。"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ パネル"

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_panel"
>title="アトリビューションパネル"
>abstract="任意のディメンションとコンバージョン指標を使用して、アトリビューションモデルをすばやく比較および視覚化します。<br/><br/>**パラメーター&#x200B;**<br/>**チャネル**<br/>&#x200B;属性の対象となるディメンション。マーケティングチャネル、キャンペーン、その他のディメンションを指定できます。<br/>**モデル**<br/>&#x200B;モデルは、タッチポインへのクレジット割り当て方法を決定します。<br/>**ルックバックウィンドウ**<br/>&#x200B;この設定により、各コンバージョンに適用されるデータアトリビューションの期間が決まります。"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ パネル"


[!UICONTROL アトリビューション]パネルを使用すると、各種アトリビューションモデルの比較分析を簡単に作成できます。アトリビューションモデルの使用と比較を行うための専用のワークスペースを提供する機能です。

Customer Journey Analytics を使用すると、以下が可能になるので、アトリビューションを強化できます。

* 有料メディアに勝るアトリビューションの定義：マーケティングキャンペーンだけでなくあらゆるディメンション、指標、チャネル、イベントをモデルに適用できます（例：内部検索）。
* 無制限のアトリビューションモデル比較の利用：必要な数のモデルを動的に比較できます。
* 実装の変更を避ける：レポート時の処理とコンテキスト対応セッションを使用すると、カスタマージャーニーコンテキストを組み込み、実行時に適用できます。
* アトリビューションシナリオに最適なセッションの作成。
* アトリビューションのフィルター別分類：すべての重要なフィルターについてマーケティングチャネルのパフォーマンスを容易に比較できます（例：新規顧客とリピート顧客、製品 X と製品 Y、ロイヤルティレベル、CLV など）。
* チャネルのクロスオーバー分析およびマルチタッチ分析の調査：ベン図やヒストグラムを使用でき、アトリビューション結果のトレンドを追跡できます。
* 主要なマーケティングシーケンスの視覚的分析：コンバージョンにつながったパスをマルチノードのフローおよびフォールアウトビジュアライゼーションで視覚的に調査できます。
* 計算指標の構築：任意の数のアトリビューション割り当て方法を使用できます。

## アトリビューションパネルの作成

1. 左端のパネルアイコンをクリックします。
1. [!UICONTROL アトリビューション]パネルを Analysis Workspace プロジェクトにドラッグします。

   ![ アトリビューションパネルがハイライト表示された新規プロジェクトウィンドウ。](assets/Attribution_Panel_1.png)

1. 属性を設定する指標を追加し、属性を適用するディメンションを追加します。例としては、マーケティングチャネルや、内部プロモーションなどのカスタムディメンションがあります。

   ![ 選択した複数のディメンションと指標を表示するアトリビューションパネルウィンドウ ](assets/attribution_panel2.png)

1. 比較するアトリビューションモデルとルックバックウィンドウを選択します。

1. アトリビューションパネルは、選択したディメンションと指標のアトリビューションを比較する、豊富なデータセットとビジュアライゼーションのセットを返します。

   ![ 選択した指標とディメンションを比較するアトリビューションパネルのビジュアライゼーション ](assets/attr_panel_vizs.png)

## アトリビューションのビジュアライゼーション

* **っ合計指標**：レポート時間帯で発生したコンバージョンの合計数。これらは、選択したディメンションに関してアトリビューション分析がおこなわれたコンバージョンです。
* **アトリビューション比較バー**：選択したディメンションの各ディメンションアイテム間で、アトリビューションされたコンバージョンを視覚的に比較します。各棒の色は、個別のアトリビューションモデルを表します。
* **アトリビューション比較テーブル**：棒グラフと同じデータを表形式で表示します。この表で異なる列または行を選択すると、棒グラフに加えて、パネル内の他のビジュアライゼーションの一部がフィルターされます。このテーブルは、Workspace の他のフリーフォームテーブルと同様に機能し、指標、フィルター、分類などのコンポーネントを追加できます。
* **重なり図**：上位 3 つのディメンション項目と、それらが共同でコンバージョンに参加する頻度を示すベン図。例えば、バブルの重複のサイズは、人物が両方のディメンション項目にさらされたときにコンバージョンが発生した頻度を示します。 隣接したフリーフォームテーブルで他の行を選択すると、その選択を反映するようにビジュアライゼーションが更新されます。
* **パフォーマンスの詳細**：散布図を使用して、最大 3 つのアトリビューションモデルを視覚的に比較できます。
* **トレンドパフォーマンス**：最上位ディメンション項目の属性コンバージョンのトレンドを表示します。 隣接したフリーフォームテーブルで他の行を選択すると、その選択を反映するようにビジュアライゼーションが更新されます。
* **フロー**：ユーザーのジャーニー全体を通して、どのチャネルが最もよく使用されているか、およびその順番を確認できます。
