---
description: Workspace に関する FAQ
title: よくある質問と Workspace のトラブルシューティング
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 87%

---


# よくある質問

>[!NOTE]
>
>Customer Journey Analytics 内の Analysis Workspace に関するドキュメントを表示しています。この機能セットは、[従来の Adobe Analytics の Analysis Workspace](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) とは少し異なります。[詳細情報...](/help/getting-started/cja-aa.md)

| 質問 | 回答 |
|--- |--- |
| Analysis Workspace を使用するための前提条件を教えてください。 | Analysis Workspaceを使用するには、Customer Journey Analyticsの実装が必要です。 ツールを使用する前に、組織がAdobe Experience Platformにデータを送信していることを確認してください。 |
| Analysis Workspace の管理およびアクセスの要件を教えてください。 | See[管理要件](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。 |
| Analysis Workspace を使用するとデータ収集に影響が出ますか。 | Analysis Workspace はレポート作成ツールなので、データ収集には影響しません。何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。様々なディメンションと指標の組み合わせをワークスペースプロジェクトにドラッグして、利用可能な項目を確認してください。無効なコンポーネントを誤ってワークスペースプロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。左上のメニューで&#x200B;*[!UICONTROL プロジェクト]／[!UICONTROL 新規]*&#x200B;をクリックして、新しいスレートから始めることもできます。 |
| Analysis Workspace はどのようにして実装しますか。 | 特別な実装は必要ありません。Analysis Workspaceはすべての会社Customer Journey Analyticsが利用できます。 ただし、コンテンツ（プロジェクトコンポーネントなど）に対する標準の権限は、プロジェクトのキュレーションや共有に適用されます。 詳しくは、[管理およびアクセス要件](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。 |
| Analysis Workspace のパフォーマンスを最適化するにはどうすればよいですか。 | 詳しくは、[パフォーマンスの最適化](/help/analysis-workspace/workspace-faq/optimizing-performance.md)を参照してください。 |

## トラブルシューティング

**指標をドラッグすると、「無効なデータ」と表示される。**

無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を並べて配置します。

**指標をドラッグすると、実際のデータは表示されず、ゼロのみが表示される。**

ワークスペースレポートを正常に作成したのにデータがないという場合は、次の点を確認してください。

* レポートスイートを再度チェックし、データが入力されていることを確認します。
* レポートにセグメントを適用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。セグメントを削除するか、セグメント定義を調整してみてください。
* 右上隅の日付範囲をチェックし、期待する値に設定されていることを確認します。
* Web サイトに移動し、[デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja-JP)を使用してデータが収集されていることを検証します。