---
title: フィルターの作成
description: フィルター作成ユーザーインターフェイスについて説明します。
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
source-git-commit: 7013237e11cb173d54dcbe236967b49d89810975
workflow-type: ht
source-wordcount: '371'
ht-degree: 100%

---

# フィルターの作成

フィルタービルダーのキャンバスに指標、ディメンション、フィルターおよびイベントをドラッグ＆ドロップすると、コンテナ階層の論理、ルールおよび演算子に基づいて訪問者をフィルタリングできます。この統合開発ツールを使用すると、訪問やページヒットを対象として訪問者の属性やアクションを識別する、簡単なフィルターや複雑なフィルターを作成して保存できます。

任意のコンポーネントタイプ（ディメンション、ディメンション項目、イベント、指標、フィルター、フィルターテンプレート、日付範囲）をパネルの上部にあるフィルタードロップゾーンにドロップすることで、フィルターを即座に作成できます。

コンポーネントタイプはフィルターに自動変換されます。また、「**[!UICONTROL フィルターを追加]**」ドロップボックスの「+」記号をクリックすることもできます。

次の点に注意してください。

* フィルターを作成できない計算指標およびディメンション／指標のコンポーネントタイプをフィルターゾーンにドロップすることは&#x200B;**できません**。
* Analysis Workspace では、すべてのディメンションおよびイベントに対して、「存在する」ヒットフィルターを作成します。例：「eVar1 が存在するヒット」または「event1 が存在するヒット」。
* 「未指定」または「なし」がフィルタードロップゾーンにドロップされると、フィルターで正しく扱えるように、自動的に「存在しない」フィルターに変換されます。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>この方法で作成されたフィルターは、プロジェクト内部にあります。

次の手順に従うことで、これらのフィルターを公開（グローバル）できます。

1. ドロップゾーンのフィルターの上にマウスポインターを置いて、「i」アイコンをクリックします。
1. 表示される情報パネルで、「**[!UICONTROL 公開する]**」をクリックします。

   ![](assets/segment-info.png)

## フィルターを適用するその他の方法

プロジェクトにフィルターを適用するには、他にもいくつかの方法があります。

| アクション | 説明 |
| --- | --- |
| 選択範囲からフィルターを作成 | インラインフィルターを作成します。このフィルターは、オープンプロジェクトにのみ適用し、CJA フィルターとして保存されません。<p> 1. フィルターの対象とするテーブル行を選択します。2. 選択範囲を右クリックします。3. 「*選択内容からフィルターを作成*」をクリックします。 |
| ワークスペース[!UICONTROL コンポーネント]／[!UICONTROL 新しいフィルター] | フィルタービルダーを表示します。フィルタリングについて詳しくは、[フィルタービルダー](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=ja)を参照してください。 |
| 共有／プロジェクトを共有または共有／プロジェクトデータをキュレート | [キュレーションおよび共有](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=ja#concept_4A9726927E7C44AFA260E2BB2721AFC6)では、プロジェクトに適用するフィルターを、受信者に共有された分析で使用する方法について学習します。 |
| フィルターをディメンションとして使用 | ビデオ「Analysis ワークスペースでフィルターをディメンションとして使用する」をご覧ください |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
