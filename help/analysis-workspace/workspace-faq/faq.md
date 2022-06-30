---
description: Workspace に関する FAQ とトラブルシューティングのヒント。
title: よくある質問
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '379'
ht-degree: 100%

---

# よくある質問

| 質問 | 回答 |
|--- |--- |
| **Analysis Workspace を使用するための前提条件を教えてください。** | Analysis Workspace を使用するには、動作する Customer Journey Analytics 実装が必要です。ツールを使用する前に、組織が Adobe Experience Platform にデータを送信していることを確認します。 |
| **Analysis Workspace の管理およびアクセスの要件を教えてください。** | [管理要件](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。 |
| **Analysis Workspace を使用するとデータ収集に影響がありますか？** | Analysis Workspace はレポート作成ツールなので、データ収集には影響しません。何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。様々なディメンションと指標の組み合わせをワークスペースプロジェクトにドラッグして、利用可能な項目を確認してください。無効なコンポーネントを誤ってワークスペースプロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。左上のメニューで&#x200B;*[!UICONTROL プロジェクト]／[!UICONTROL 新規]*&#x200B;をクリックして、新しいスレートから始めることもできます。 |
| **Analysis Workspace を実装するにはどうすればよいですか？** | 特別な実装は必要ありません。Analysis Workspace は、あらゆる企業の Customer Journey Analytics で利用できます。 ただし、コンテンツ（プロジェクトコンポーネントなど）へのアクセスやプロジェクトのキュレーションおよび共有には、標準の権限が適用されます。[管理およびアクセス要件](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md) を参照してください。 |
| **Analysis Workspace のパフォーマンスを最適化するにはどうすればよいですか？** | 詳しくは、[パフォーマンスの最適化](/help/analysis-workspace/workspace-faq/optimizing-performance.md)を参照してください。 |

## トラブルシューティング

**指標をドラッグすると、「無効なデータ」と表示される。**

無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を並べて配置します。

**指標をドラッグすると、実際のデータは表示されず、ゼロのみが表示される。**

ワークスペースレポートを正常に作成したのにデータがないという場合は、次の点を確認してください。

* レポートにフィルターを適用している場合、そのフィルター条件がどのデータとも一致していない可能性があります。フィルターを削除してみるか、フィルター定義を調整してみてください。
* 右上隅の日付範囲をチェックし、期待する値に設定されていることを確認します。
* Web サイトに移動し、[デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用してデータが収集されていることを検証します。
