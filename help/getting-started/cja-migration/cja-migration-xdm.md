---
title: Customer Journey Analyticsへの移行時にデータを XDM スキーマにマッピングする
description: Customer Journey Analyticsに移行する際に、データを XDM スキーマにマッピングする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 4%

---

# 手順 4:Customer Journey Analyticsへの移行時の XDM スキーマへのデータのマッピング

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている手順 4 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行方法の選択](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 1 で選択した移行方法によって異なります。 |
| <span class="preview">**手順 4: [XDM スキーマへのデータのマッピング](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、Adobe Experience Platformで使用され、一貫した再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。<p>ほとんどの移行方法では、新しい XDM スキーマを作成するか、データストリームマッピングを使用して既存のAdobe Analytics スキーマを XDM にマッピングする必要があります。</p></span> |
| **手順 5: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 6: [ユーザーのオンボーディングの計画](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。 |
| **手順 7: [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| **手順 8: [データフィードとData Warehouseの置き換え](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analyticsで使用していたデータフィードとData Warehouse機能を置き換えるために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。 |
| **手順 9: [プロジェクトとコンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。 |

{style="table-layout:auto"}

+++

すべての移行方法で、Adobe Analytics データを XDM スキーマにマッピングする必要があるわけではありません。 次の表に、XDM スキーママッピングが必要な実装方法を示します。


| 移行方法 | XDM マッピングが必要ですか？ | 詳細情報 |
|---------|----------|---------|
| **Web SDK の新しい実装**<p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマの作成</li><li>Web SDK の実装</li><li>Platform にデータを送信</li></ol> | × | 既にマッピングしているので、マッピングは必要ありません [新しい XDM スキーマの設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 新しい実装の一環として。 |
| **Web SDK を使用するようにAdobe Analytics実装を移行する**<p>基本的な手順は次のとおりです。</p><ol><li>既存のAdobe Analytics実装を Web SDK に移行し、すべてがそこで機能していることを検証します。</li><li>時間の経過に応じて、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li><li>Platform にデータを送信</li></ol> | ○ | データチームと協力して、Customer Journey Analyticsに対する組織の理想的なスキーマデザインを特定し、eVar と Prop を XDM にマッピングする方法を決定します。</br>[データ準備を使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **既存のAdobe Analytics Web SDK 実装を設定し、データをCustomer Journey Analyticsに送信します**<p>基本的な手順は次のとおりです。</p><ol><li>Customer Journey Analyticsへのデータ送信を開始します。<!-- What's involved here? Just point it at CJA? --></li><li>（オプション）時間に応じて、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li></ol> | ○ | データチームと協力して、Customer Journey Analyticsに対する組織の理想的なスキーマデザインを特定し、eVar と Prop を XDM にマッピングする方法を決定します。</br>[データ準備を使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Analytics ソースコネクタ**</br> Adobe Analyticsの実装がAppMeasurementまたは Analytics 拡張機能の場合、Customer Journey Analyticsでデータビューへのデータ送信を開始できます。<p>これは、データをCustomer Journey Analyticsに取得する最も簡単な方法ですが、長期的には最も実行可能でない方法です。</p> | × | Analytics ソースコネクタは XDM スキーマではなく既存のAdobe Analytics スキーマを使用するので、マッピングは必要ありません。 |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## 次に、履歴データを保持します

次に、使用する方法を選択します [Adobe Analyticsの履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md).
