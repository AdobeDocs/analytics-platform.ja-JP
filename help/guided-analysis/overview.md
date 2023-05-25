---
title: ガイド付き分析：概要
description: 製品チームがレポートやインサイトを簡単に生成できるCustomer Journey Analyticsでのデータ分析方法を提供する。
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# ガイド付き分析：概要

{{release-limited-testing}}

ガイド付き分析は、製品チームがデータのニーズにすばやく応え、より多くのデータ主導型の製品決定を下すことができるレポート形式です。 部門をまたぐチームは、リアルタイムに接続して、これらのレポートを使用し、理解できます。

Analysis Workspaceやモバイルのスコアカードと同様、ガイド付き分析レポートでは [データビュー](../data-views/data-views.md)：を通じてAdobe Experience Platform内のデータを参照します。 [接続](../connections/overview.md). ガイド付き分析で作成したすべてのレポートは、Analysis Workspaceにシームレスに転送して、さらに調査をおこなうことができます。

ガイド付き分析レポートには、現在、次の 3 つの分析タイプがあります。 [ファネル](analysis-types/funnel.md), [トレンド](analysis-types/trends.md)、および [ユーザーの増加](analysis-types/user-growth.md). これらの各分析タイプには複数のビュータイプがあり、各レポートに関する追加のインサイトを提供します。

## プロビジョニング

ガイド付き分析は、Customer Journey Analyticsへの有料アドオンです。 この機能の使用を開始したい場合は、担当のAdobeアカウントチームにお問い合わせください。

## インターフェイス

分析タイプに関係なく、ガイド付き分析のインターフェイスは、次の主な UI 要素で構成されます。

1. **クエリレール**:左側のこのレールを使用して、分析を構築します。
1. **グラフ**:目的のイベント、ユーザーまたはステップを選択すると、右側にデータを視覚化するグラフが表示されます。
1. **テーブル**:ビジュアライゼーションで使用される数を示すグラフの下の表。
1. **設定とインサイト**:グラフの上に表示されるいくつかの UI 要素で、返されるデータをカスタマイズできます。

[UI のスクリーンショット]

ガイド付き分析には、次のインターフェイス部分が含まれます。

| インターフェイスのプレビュー | UI 要素 | 説明 |
| --- | --- | --- |
| [クエリレールのスクリーンショット] | クエリレール | レポートを構成する目的のコンポーネントを設定します。 分析タイプが異なれば、複数のクエリオプションを共有します。2 つの分析タイプがクエリオプションを共有する場合、分析タイプを切り替える際に継承されます。 詳しくは、 [分析タイプ](analysis-types/overview.md) を参照してください。 |
| [グラフのスクリーンショット] | グラフ | クエリレールと設定からの入力に基づいて返されるデータのビジュアライゼーション。 どのビジュアライゼーションが表示されるかは、グラフの上の表示タイプによって異なります。 使用可能なビューのタイプは、 [分析タイプ](analysis-types/overview.md) をクリックします。 |
| [テーブルのスクリーンショット] | テーブル | クエリレールからの入力と設定に基づいて返されるデータのテーブル表現です。 テーブルの列は、グラフの上の表示タイプによって異なります。 使用可能なビューのタイプは、 [分析タイプ](analysis-types/overview.md) をクリックします。 |
| [設定のスクリーンショット] | 設定 | グラフの上にあるいくつかのオプション。グラフと表のデータの返し方をカスタマイズできます。<ul><li>**表示タイプ**:特定の [分析タイプ](analysis-types/overview.md) 別の方法で 各解析タイプには、少なくとも 2 つのビュータイプがあります。</li><li>**グラフ設定**:グラフの外観と使用するイベントを微調整する。 使用できるオプションは、選択した表示タイプによって異なります。</li><li>**日付範囲**:レポートの日付範囲を決定するためのカレンダーピッカー。 また、日別、週別、月別などの間隔を指定できる分析もあります。</li><li>**インサイト**:表示しているレポートに応じて、コンテキストインサイトを提供します。 右上の電球アイコンを使用して、これらのインサイトの表示と非表示を切り替えることができます。</li></ul> |
| [分析メニューのスクリーンショット] | 分析メニュー | ガイド付き分析の右上にある、包括的なアクションを提供するコマンド。<ul><li>**データビューセレクター**:この分析で使用するデータビューを変更します。 データビューを変更すると、クエリレールの使用可能なコンポーネントも変更されます。</li><li>**保存**:解析を保存します。 新しい分析を保存する場合、名前と説明をリクエストするモーダルウィンドウが表示されます。</li><li>**名前を付けて保存**:解析を現在の解析とは別に保存し、コピーを作成します。 新しい名前と説明をリクエストするモーダルウィンドウが表示されます。</li><li>**ワークスペースで開く**:Analysis Workspaceで現在のガイド付き分析を再作成します。 Workspace プロジェクトは新しいタブで作成され、ガイド付き分析内で作業中に中断するのを防ぎます。 ガイド付き分析では、求める柔軟性や具体的なインサイトが得られない場合に、このコマンドを使用します。 例えば、 [トレンド](analysis-types/trends.md) あるセグメントにセッションを使用し、別のセグメントに人を使用するレポート。</li><li>**PNG をダウンロード**:グラフのグラフィックを `.png`. クエリレールとテーブルは、グラフィックに含まれていません。</li><li>**ダウンロードSVG**:グラフのグラフィックを `.svg`. クエリレールとテーブルは、グラフィックに含まれていません。</li></ul> |

{style="table-layout:auto"}

## 権限

Adobeは、今後、ガイド付き分析に固有の権限を提供する予定です。

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
