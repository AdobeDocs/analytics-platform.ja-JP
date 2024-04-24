---
title: Customer Journey Analyticsへの移行時にAdobe Experience Platformにデータを送信
description: Customer Journey Analyticsへの移行時にAdobe Experience Platformにデータを送信
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 2d35e49ca9afe37ed53d7c5da5aafd31dd2da632
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 1%

---

# 手順 3：移行時にAdobe Experience Platformにデータを送信する

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている、移行の手順 3 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行パスを選択](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| <span class="preview">**手順 3:Adobe Experience Platformへのデータの送信**</span> | <span class="preview">Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択した移行パスによって異なります。</span> |
| **手順 4: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | Customer Journey Analyticsプロセスのこの時点では、移行に使用する準備が整う前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからの移行と、新しいCustomer Journey Analytics実装に当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


お先に [移行パスを選択](#step-2-choose-your-customer-journey-analytics-migration-method) 組織に最適な方法は、Adobe Experience Platformへのデータの送信を開始して、Customer Journey Analyticsで利用できるようにすることです。

次に、各移行パスのデータをExperience Platformに送信するプロセスを示します。 次の表に示すリンクを参照して、詳細な設定情報を確認します。

| 移行パス | Platform へのデータ送信プロセス | 追加情報 |
|---------|----------|----------|
| Experience PlatformWeb SDK の新しい実装 | <ol><li>組織の XDM スキーマを作成します。<p>データチームと協力して、Customer Journey Analyticsに向けた組織の理想的なスキーマデザインを特定します。</p></li><li>Experience PlatformWeb SDK を実装します。</li><li>Platform にデータを送信します。</li></ol><p>これらの各手順について詳しくは、を参照してください [Adobe Experience Platform Web SDK を使用したデータの取り込み](/help/data-ingestion/aepwebsdk.md). | これはExperience Platform Web SDK の新しい実装なので、実装時の最初の手順の 1 つとしてスキーマを作成する必要があるので、スキーママッピングは必要ありません。 |
| Web SDK を使用するようにAdobe Analytics実装を移行する | <ol><li>既存のAdobe Analytics実装をExperience PlatformWeb SDK に移行し、Adobe Analyticsですべてが機能していることを検証します。<p>この方法について詳しくは、現在の実装が Analytics タグ拡張機能かAppMeasurementかに応じて、次のリソースを使用してください。</p><ul><li>Analytics タグ拡張機能を使用している場合は、を参照してください。 [Adobe Analyticsのタグ拡張機能から Web SDK のタグ拡張機能への移行](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>AppMeasurementを使用する場合は、を参照してください [AppMeasurementから Web SDK への移行](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[組織の XDM スキーマの作成](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>データチームと協力して、Customer Journey Analyticsに向けた組織の理想的なスキーマデザインを特定します。</p></li><li>[データ準備を使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>次の方法で Platform へのデータ送信を開始 [データストリームの設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| 既存のAdobe Analytics Web SDK 実装を設定し、データをCustomer Journey Analyticsに送信します | <ol><li>次の方法で Platform へのデータ送信を開始 [データストリームの設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>Adobe Analyticsの実装は既にExperience Platform Web SDK を使用しているので、の他の節を無視できます [Adobe Experience Platform Web SDK を使用したデータの取り込み](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>（オプション） [組織の XDM スキーマの作成](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>データチームと協力して、Customer Journey Analyticsに向けた組織の理想的なスキーマデザインを特定します。</p><p>メモ：XDM スキーマを作成する利点については、を参照してください。 [Web SDK を使用したAdobe Analytics実装の場合：](/help/getting-started/cja-migration/cja-migration-path.md#for-adobe-analytics-implementations-using-web-sdk).</li><li>（任意） XDM スキーマを作成した場合、 [データ準備を使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |
| Analytics ソースコネクタの使用 | [従来の Adobe Analytics からのデータの取り込みと使用](/help/data-ingestion/analytics.md) | Adobe Analytics データは、Analytics ソースコネクタを使用すると、XDM スキーマに自動的にマッピングされます。 追加のマッピングは必要ありません。 |

## 次に、履歴データを保持します

次に、あなたがする方法を決定 [Adobe Analyticsの履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md).
