---
title: フィルターの作成
description: フィルター作成ユーザーインターフェイスについて説明します。
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 38%

---


# フィルターの作成

フィルタービルダーのキャンバスに指標、ディメンション、フィルターおよびイベントをドラッグ＆ドロップすると、コンテナ階層の論理、ルールおよび演算子に基づいて訪問者をフィルタリングできます。この統合開発ツールを使用すると、訪問やページヒットを対象として訪問者の属性やアクションを識別する、簡単なフィルターや複雑なフィルターを作成して保存できます。

コンポーネントタイプ(ディメンション、ディメンション項目、イベント、指標、セグメント、セグメントテンプレート、日付範囲)をパネルの上部にあるフィルタードロップゾーンにドロップすると、インスタントフィルターを作成できます。

コンポーネントタイプはフィルターに自動変換されます。 Alternatively, you can click the &quot;+&quot; sign in the **[!UICONTROL Add Filter]** drop box.

次の点に注意してください。

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* フルディメンションおよびイベントの場合、Analysis Workspaceは「存在する」ヒットフィルターを作成します。 例：「eVar1 が存在するヒット」または「event1 が存在するヒット」
* フィルタードロップゾーンに「未指定」または「なし」が含まれない場合は、正しく処理されるように、自動的に「存在しない」フィルターに変換されます。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>この方法で作成されたフィルターは、プロジェクトの内部にあります。

次の手順に従って、これらのフィルターを公開（グローバル）できます。

1. ドロップゾーンのフィルターの上にマウスポインターを置き、「i」アイコンをクリックします。
1. 表示される情報パネルで、「**[!UICONTROL 公開する]**」をクリックします。

   ![](assets/segment-info.png)

## フィルターを適用するその他の方法

プロジェクトにフィルターを適用するには、他にもいくつかの方法があります。

| アクション | 説明 |
|--- |--- |
| 選択範囲からフィルタを作成 | インラインフィルターを作成します。 行を選択し、選択範囲を右クリックして、インラインフィルターを作成します。 このフィルターは、開いているプロジェクトにのみ適用され、CJAフィルターとしては保存されません。 1. 行を選択します。2. 選択範囲を右クリックします。3. Click *Create filter from selection*. |
| コンポーネント/新しいフィルター | フィルタビルダを表示します。 See [Filter Builder](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about filtering. |
| 共有／プロジェクトを共有または共有／プロジェクトデータをキュレート | In [Curate and Share](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how filters that you apply to the project are available in shared analysis for the recipient. |
| フィルターをディメンションとして使用 | ビデオ：[Analysis Workspace でセグメントをディメンションとして使用する](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
