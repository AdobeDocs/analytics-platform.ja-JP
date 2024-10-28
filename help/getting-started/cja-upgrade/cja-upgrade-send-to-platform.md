---
title: Customer Journey Analytics への移行時にデータを Adobe Experience Platform に送信
description: Customer Journey Analytics への移行時にデータを Adobe Experience Platform に送信
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: cffc62f16120bd95e581e16e7cf692472a715e41
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 66%

---

# 手順 3：アップグレード時にAdobe Experience Platformにデータを送信する

+++このセクションを展開すると、このページの情報が大きなアップグレードプロセスのどこに適合するかを確認できます。 以前のアップグレード手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のアップグレードタスクがすべて完了していることを確認してください。

このページの情報では、次の表で強調表示されている、アップグレードプロセスの手順 3 について説明します。

| アップグレードタスク | 詳細 |
|---------|----------|
| **手順 1:[ アップグレードの概要](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analyticsへのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。 |
| **手順 2:[ アップグレードパスを選択する](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analyticsへのアップグレードには様々な方法があります。 組織の現在の Adobe Analytics 環境と長期的な目標に応じて、組織に最適な方法を選択してください。 |
| <span class="preview">**手順 3：データを Adobe Experience Platform に送信**</span> | <span class="preview">Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。</span> |
| **手順 4：[履歴データの保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | ほとんどの組織では、Adobe Analytics の履歴データを一定期間保持する必要があります。これを実現するために様々なオプションが利用できます。 |
| **手順 5：[追加の実装タスクを実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからのアップグレードや、新しいCustomer Journey Analyticsの実装にも当てはまります。</p><p>これらのタスクには次のものが含まれます。</p><ul><li>他のデータを Experience Platform に取り込む</li><li>手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとデータウェアハウスの考慮</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーオンボーディングの計画</li></ul> <p>詳しくは、[Customer Journey Analytics の概要](/help/getting-started/cja-getting-started.md)を参照してください。 |

{style="table-layout:auto"}

+++


組織に最適な [ アップグレードパスを選択 ](/help/getting-started/cja-upgrade/cja-upgrade-path.md) した後、Adobe Experience Platformへのデータの送信を開始して、Customer Journey Analyticsで利用できるようにします。

各アップグレードパスのデータをExperience Platformに送信するプロセスを以下に示します。 詳細な設定情報については、表内のリンクに従ってください。

| アップグレードパス | Platform にデータを送信するプロセス | 追加情報 |
|---------|----------|----------|
| Experience Platform Web SDK の新しい実装 | <ol><li>組織の XDM スキーマを作成します。<p>データチームと連携して、Customer Journey Analytics に対する組織の理想的なスキーマ設計を特定します。</p></li><li>Experience Platform Web SDK を実装します。</li><li>Platform にデータを送信します。</li></ol><p>これらの各手順について詳しくは、[Adobe Experience Platform Web SDK を使用したデータの取り込み](/help/data-ingestion/aepwebsdk.md)を参照してください。 | これは Experience Platform Web SDK の新しい実装であることにより、実装時の最初の手順の 1 つとしてスキーマを作成する必要があるので、スキーママッピングは必要ありません。 |
| Web SDK を使用するための Adobe Analytics の実装の移行 | <ol><li>既存の Adobe Analytics の実装を Experience Platform Web SDK に移行し、Adobe Analytics ですべてが機能していることを検証します。<p>これを行う方法については、現在の実装が Analytics タグ拡張機能であるか AppMeasurement であるかに応じて、次のリソースを使用してください。</p><ul><li>Analytics タグ拡張機能を使用している場合は、[Adobe Analytics タグ拡張機能から Web SDK タグ拡張機能への移行](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)を参照してください</li><li>AppMeasurement を使用している場合は、[AppMeasurement から Web SDK への移行](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)を参照してください</li></ul><li>[組織の XDM スキーマを作成します](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>データチームと連携して、Customer Journey Analytics に対する組織の理想的なスキーマ設計を特定します。</p></li><li>[データ準備を使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします](https://experienceleague.adobe.com/ja/docs/experience-platform/data-prep/home)。</li><li>[データストリームを設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream)して、Platform へのデータの送信を開始します。</li></ol> |  |
| Platform にデータを送信するように既存のAdobe Analytics Web SDK を設定する | <ol><li>[データストリームを設定](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)して、Platform へのデータの送信を開始します。<p>Adobe Analytics の実装では既に Experience Platform Web SDK が使用されているので、[Adobe Experience Platform Web SDK を使用したデータの取り込み](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)の他の節は無視してかまいません。</p><p>Adobe Analyticsの実装で既に Platform にデータを送信している場合、この手順は必要ありません。 このプロセスで後ほど説明するように、Platform データセットとCustomer Journey Analyticsの間で接続を作成するだけで済みます。</p></li><li>（オプション）[組織の XDM スキーマを作成します](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>データチームと連携して、Customer Journey Analytics に対する組織の理想的なスキーマ設計を特定します。</p><p>メモ：XDM スキーマを作成するメリットについては、[スキーマの選択](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema)を参照してください。</li><li>（条件付き）XDM スキーマを作成した場合、[データ準備を使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします](https://experienceleague.adobe.com/ja/docs/experience-platform/data-prep/home)。</li></ol> |  |
| Analytics ソースコネクタの使用 | [従来の Adobe Analytics からのデータの取り込みと使用](/help/data-ingestion/analytics.md) | Analytics ソースコネクタを使用すると、Adobe Analytics データが XDM スキーマに自動的にマッピングされます。追加のマッピングは必要ありません。 |

## 次に、履歴データを保持します

次に、[Adobe Analytics の履歴データを保持する方法](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)を決定します。
