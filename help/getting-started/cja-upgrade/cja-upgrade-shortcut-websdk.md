---
title: アップグレードショートカット Web SDK を使用するようにAppMeasurementまたは Analytics 拡張機能の実装を移行する
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8ef60cc3918b79919674e3c0478a2c1b1bd21d27
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 46%

---

# アップグレードショートカット：Web SDK を使用するようにAppMeasurementまたは Analytics 拡張機能の実装を移行します {#shortcut-migrate-websdk}

>[!NOTE]
>
>このドキュメントは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードアンケート ](https://gigazelle.github.io/cja-ttv/) の一部として使用してください。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Web SDK を使用するように Analytics 実装を移行する"
>abstract="XDM オブジェクトを通じてデータを送信する代わりに、データオブジェクトを通じてAppMeasurement形式ですべての変数を送信できます。 このショートカットを使用すると、AppMeasurementロジックを引き続き使用して Platform にデータを送信できます。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analyticsにアップグレードする場合、Adobeでは [Experience Platform Web SDK の新規実装をお勧めします ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。 ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。

お使いのAdobe Analytics実装がAppMeasurementまたは Analytics 拡張機能の場合は、アップグレードショートカットを使用してAdobe Analytics実装を移行し、Adobe Experience Platform Web SDK を使用してEdge NetworkおよびAdobe Analyticsへのデータ送信を開始してから、Customer Journey Analyticsに送信することができます。

## メリットとデメリット

アップグレードショートカットの次のメリットとデメリットを考慮して、AppMeasurementまたは Analytics 拡張機能の実装を Web SDK を使用するように移行します。

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**後で組織の XDM スキーマを作成できる柔軟性を提供**：既存の Adobe Analytics 実装を Web SDK を使用するように移行し、Adobe Analytics ですべてが機能していることを検証してから、XDM スキーマを作成できます。この柔軟性により、Customer Journey Analyticsに対するより体系的で思慮深いアップグレードが可能になります。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。このアクションでは、データオブジェクトのすべてのフィールドを、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリにする必要があります。このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li><li>**技術的負債**：このアプローチでは、既存の実装の修正された形式が使用されるので、実装ロジックを追跡し、今後必要に応じて変更を実行することが難しくなる可能性があります。 </li></ul> |

{style="table-layout:auto"}

## 基本手順

アップグレード ショートカットを使用して、AppMeasurementまたは Analytics 拡張機能の実装から Web SDK を使用するように移行する場合は、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で、動的に生成される手順に新しい手順が追加されます。

Web SDK を使用するように Analytics またはAppMeasurement拡張機能の実装を移行する基本的な手順は、次のとおりです。

1. Platform へのデータ送信を開始します。

   Adobe Analyticsの実装で既に Platform にデータを送信している場合、この手順は必要ありません。 このプロセスで後ほど説明するように、Platform データセットとCustomer Journey Analyticsの間で接続を作成するだけで済みます。

1. （オプション）時間があれば、組織の XDM スキーマを作成します。

1. （条件付き）XDM スキーマを作成した場合は、データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。

