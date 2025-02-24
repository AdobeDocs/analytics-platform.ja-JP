---
title: Customer Journey Analyticsへのアップグレード時の代替方法
description: Customer Journey Analyticsへのアップグレード時の代替方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 19%

---

# アップグレードの選択肢：AppMeasurement データ収集をExperience Platform Web SDKおよびCustomer Journey Analyticsで使用する {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Web SDKでのAppMeasurement ロジックの使用"
>abstract="XDM オブジェクトを通じてデータを送信する代わりに、データオブジェクトを通じてAppMeasurement形式のすべての変数を送信します。<br><br> このオプションを使用すると、XDM オブジェクトをゼロから入力するのではなく、AppMeasurement ロジックを XDM にマッピングできるので、実装時間を節約できます。 ただし、将来に追加するフィールドはデータストリームの XDM にマッピングする必要があるので、時間の経過と共に複雑さが増します。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analyticsのアップグレードチェックリスト ](https://gigazelle.github.io/cja-ttv/) に関する質問に答える際は、このページの情報を使用してください。

Customer Journey Analyticsにアップグレードする場合、Adobeは [Experience Platform web SDKの新規実装を推奨 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) します。 ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。

XDM オブジェクトでデータを収集する代わりに、web SDKでAppMeasurementまたは Analytics Extension のデータ収集ロジックを使用して、Platform およびCustomer Journey Analyticsにデータを送信できます。 ただし、この代替オプションを使用すると、時間の経過と共に複雑さが増します。

## メリットとデメリット

どちらの方法も同じタスクを実行するので、この方法は [ データレイヤー全体をCustomer Journey Analyticsに送信する ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md) 方法と相互排他的です。 （この方法は、データレイヤー全体をAdobeに送るよりも望ましいです。 prop と evar はすべてデータを通過するので、より洗練されています。__adobe.analytics._変数名_.）

このアップグレードの代替手段を使用する際には、次のメリットとデメリットを考慮してください。

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analyticsの命名法（prop、eVar、event など）に限定されない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。これにより、XDM オブジェクトをゼロから入力するのではなく、AppMeasurement ロジックを XDM にマッピングできます。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。このアクションでは、データオブジェクトのすべてのフィールドを、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリにする必要があります。このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li><li>**時間の経過と共に、さらなる複雑さが発生します**：将来追加するフィールドは、データストリームの XDM にマッピングする必要があります。<p>実装に新しいフィールドが追加されるたびに、次のいずれかを実行できます。</p><ul><li>**オプション 1:** データオブジェクトに新しい任意の evar または新しい prop を入力し、目的の XDM フィールドにマッピングします。<p>このプロセスは、クライアントサイド実装の一貫性を高めますが、マッピングが必要です。</p></li><li>**オプション 2:** データオブジェクトをレガシー実装のままにして、すべての新しいフィールドに XDM オブジェクトのみを入力し始めます。<p>このプロセスではマッピングは必要ありませんが、つまり、一部の変数はデータオブジェクト内にのみ配置され、その他の変数は XDM オブジェクト内にのみ配置されます。 実装のトラブルシューティングが必要な場合は、いつでも 2 か所に移動する必要があります。 内部ワークフローでこのような状況に対応できることを確認します。</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## 基本手順

Web SDKを使用してCustomer Journey Analyticsにデータを送信するためにAdobe Analytics実装（AppMeasurementまたは Analytics 拡張機能）を移行する基本的な手順は、次のとおりです。

1. （オプション）Adobe Analyticsの実装を移行してAdobe Experience Platform Web SDKを使用し、Edge Networkへのデータの送信を開始します。

   これは、既存のAdobe Analytics実装を移行して Web SDKを使用し、Adobe Analyticsですべてが機能していることを検証できるオプションの手順です。 設定が完了し、Adobe Analyticsのデータに満足したら、Edge NetworkからCustomer Journey Analyticsにデータを送信できます。

   この柔軟性により、Customer Journey Analyticsに対するより体系的で思慮深いアップグレードが可能になります。

   この方法について詳しくは、Adobe Analytics ドキュメントの次の記事を参照してください。

   * [ タグを使用した web SDKへの移行 ](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [JavaScriptを使用した Web SDKへの移行 ](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Edge NetworkからCustomer Journey Analyticsにデータを送信します。

   1. このデータオブジェクトを介して、すべての変数をAppMeasurement形式で送信します。

      詳しくは、[Adobe Analyticsへのデータオブジェクト変数のマッピング ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) を参照してください。

   1. 組織の XDM スキーマをまだ作成していない場合は作成します。

      詳しくは、[Customer Journey Analytics web SDKの実装で使用するカスタムスキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) を参照してください。

   1. データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。

      詳しくは、Experience Platform ドキュメントの [ データ収集のためのデータ準備 [ の ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) マッピング ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) を参照してください。

