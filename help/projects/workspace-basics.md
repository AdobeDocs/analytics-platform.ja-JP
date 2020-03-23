---
title: ワークスペースの基本
description: Workspaceで基本レポートを作成する方法を説明します。
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# ワークスペースの基本

Workspaceツールについて詳しくない場合は、次のヒントを参照してください。

Workspaceは、組織にとって実用的なデータベースの決定を行うためのアドビの主要ツールです。 最も一般的なビジュアライゼーションであるフリーフォームテーブルを使用すれば、ディメンション、指標、セグメントおよび日付範囲を使用し、カスタマイズしたレポートを簡単に作成できます。

## Workspace での基本ランクレポートの取り込み

ランクレポートには、各ディメンション値の集計された合計ビューが表示され、最も大きい値が最初に表示されます。これらのタイプのレポートは、最もトラフィックが多いページや最も売れている製品など、サイトのどのコンポーネントが最も効果的かを知るのに役立ちます。

1. analytics.adobe.comにログインしてい [ることを確認します](https://analytics.adobe.com)。
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. クリック **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. 左側に、ディメンション、指標、セグメントおよび日付範囲のリストが表示されます。ページディメンション（色付きのオレンジ色）を見つけ、「ここにディメンションをドロップ」と表示されたキャンバスにドラッグします。
1. 今月の上位ページを示すレポートが表示されます。Analysis Workspace は、[回数](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html)指標を使用してレポートに自動的に入力します。
1. 訪問回数指標（緑色）を見つけ、回数指標ヘッダーの&#x200B;**上**&#x200B;または&#x200B;**隣**&#x200B;にドラッグします（指標の上に配置しないでください）。訪問回数指標を「回数」の上にドラッグすると、レポート内のその指標が置き換えられます。「回数」の横に訪問回数指標をドラッグすると、両方の指標が並べて表示されます。
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Workspace での基本トレンドレポートの取り込み

トレンドレポートは、選択した日付範囲を使用して、指標の時系列表示を示します。これらのタイプのレポートは、経時的なトレンドの特定に役立ち、ビジネス上の意思決定の成功または失敗を測定するために使用できます。例えば、経時的にトレンド表示されたページビュー数レポートを見て、サイトを作り直したことがトラフィックの増減に役立ったかどうかを確認できます。

1. analytics.adobe.comにログインしてい [ることを確認します](https://analytics.adobe.com)。
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. クリック **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. 左側に、ディメンション、指標、セグメントおよび日付範囲のリストが表示されます。Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. ディメンション用に予約されたスペースにドロップしないでください（少なくともこの演習では）。
1. レポートスイートにデータが含まれている場合は、今月の基本ページビュー数レポートが表示されます。Analysis Workspace は自動的に「日」の日付範囲を取り込むので、現在の月のページビューのトレンドを確認できます。
1. 左側の日付範囲コンポーネントのリストで、週の日付範囲（紫色）を探します。日付範囲のタイトルをクリックして、すべての日付範囲コンポーネントを展開して表示するか、検索バーを使用します。
1. キャンバス上の日付範囲ヘッダーの上にある週の日付範囲をドラッグして置き換えます。
1. トレンドレポートは、日ではなく週別に集計されるようになりました。
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## ツールを使って実験する

 Workspace はレポート作成ツールなので、データ収集には影響しません。何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。様々なディメンションと指標の組み合わせをワークスペースプロジェクトにドラッグして、利用可能な項目を確認してください。

無効なコンポーネントを誤ってワークスペースプロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。You can also start with a clean slate by clicking **[!UICONTROL Project]>[!UICONTROL New]**in the upper left menu.

## トラブルシューティング

### 指標をドラッグすると、「無効なデータ」と表示される。

無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を横に並べて配置します。

### 指標をドラッグすると、実際のデータは表示されず、ゼロのみが表示される。

ワークスペースレポートを正常に作成したのにデータがないという場合は、次の点を確認してください。

* レポートスイートを再度チェックし、データが入力されていることを確認します。
* レポートでセグメントを使用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。セグメントを削除するか、セグメント定義を調整してみてください。
* 右上の日付範囲をチェックし、期待する値に設定されていることを確認します。
* Web サイトに移動し、デバッガーを使用してデータが収集されていることを検証します。

## その他のリソース

次のリソースは、Customer Jareny Analyticsではなく、従来のAdobe Analytics製品でWorkspaceを使用することを指す場合があります。

* ブログ投稿：
   * [よりスマートな分析による組織の強化](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Analysis Workspace:シークレットソースが味わえる](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [Analysis Workspace を使用する理由](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)
   * [Analysis Workspace で生産性を最大化するための 5 つのヒント](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/)

## 次の手順

 Workspace の理解を深めるためには、様々なアプローチがあります。アドビが推奨する基本事項を以下に示します。

###  Workspace の使用方法に関する知識を広げたいエンドユーザー向け

* [Workspace UI の詳細](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html)：基本レポートを作成したら、残りのインターフェイスに慣れてください。
* [Workspace のビジュアライゼーション](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)：フリーフォームテーブルは、Analysis Workspace のビジュアライゼーションのタイプの 1 つにすぎません。折れ線グラフ、棒グラフ、地域マップなど、他のビジュアライゼーションの使用方法を説明します。
* [Workspace のディメンション](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)：ディメンションの概要と、単なるランクレポート以外でのディメンションの使用方法について詳しく説明します。
* [Workspace の指標](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html)：指標の概要と、フリーフォームテーブルの他の部分での指標の使用方法について説明します。
* [セグメントの概要](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)：セグメントとは何かを説明し、セグメントを使用して基本レポートを作成します。
* [Workspace の日付範囲](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)：相対日付と日周期について説明し、Workspace プロジェクトで使用します。
* [Workspace でのプロジェクトの共有：自分が作成した Workspace プロジェクトを同僚に表示します。](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### 組織におけるワークスペースの質の向上を検討しているアナリストおよび管理者向け

* [Analysis Workspace 権限](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)：Adobe Admin Console を使用して、Workspace にユーザー権限を割り当てます。
* [Workspace のテンプレート](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html)：テンプレートを作成し、同僚のニーズに合わせて調整されたプロジェクトスペースでの作業を同僚が開始できるようにします。
* [Workspace のキュレーション](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)：使用可能なコンポーネントを制限するプロジェクトを作成し、ツールに慣れていないユーザーがワークスペースにアクセスしやすいようにします。
