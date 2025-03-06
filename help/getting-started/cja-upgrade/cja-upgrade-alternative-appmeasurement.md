---
title: Customer Journey Analyticsへのアップグレード時の代替方法
description: Customer Journey Analyticsへのアップグレード時の代替方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 967d8a957e722a080cd712ea7cf77f26660289da
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 40%

---

# アップグレードの選択肢：AppMeasurement データ収集をExperience Platform Web SDKおよびCustomer Journey Analyticsで使用する {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Web SDKでのAppMeasurement ロジックの使用"
>abstract="XDM オブジェクトを通じてデータを送信する代わりに、データオブジェクトを通じてAppMeasurement形式のすべての変数を送信します。<br><br> このオプションを使用すると、XDM オブジェクトをゼロから入力するのではなく、AppMeasurement ロジックを XDM にマッピングできるので、実装時間を節約できます。 ただし、将来に追加するフィールドはデータストリームの XDM にマッピングする必要があるので、時間の経過と共に複雑さが増します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="Web SDK を指すように AppMeasurement ロジックを変更"
>abstract="この手順が表示されるのは、実装のショートカットを選択したためです。 AppMeasurement ロジックをコピーまたは変更し、s オブジェクトではなく、データオブジェクトを入力します。 例えば、s.eVar1 の割り当てを data に変更します。__adobe.analytics.eVar1 を繰り返し、すべての Analytics 変数に対して繰り返します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Customer Journey Analyticsにアップグレードする場合、Adobeは [Experience Platform web SDKの新規実装を推奨 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) します。 ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。

XDM オブジェクトでデータを収集する代わりに、web SDKでAppMeasurementまたは Analytics Extension のデータ収集ロジックを使用して、Platform およびCustomer Journey Analyticsにデータを送信できます。 ただし、この代替オプションを使用すると、時間の経過と共に複雑さが増します。

## メリットとデメリット

どちらの方法も同じタスクを実行するので、この方法は [ データレイヤー全体をCustomer Journey Analyticsに送信する ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md) 方法と相互排他的です。 （この方法は、データレイヤー全体をAdobeに送るよりも望ましいです。 prop と evar はすべてデータを通過するので、より洗練されています。__adobe.analytics._変数名_.）

このアップグレードの代替手段を使用する際には、次のメリットとデメリットを考慮してください。

| メリット | デメリット |
|----------|---------|
| Adobe Analytics実装で既に web SDKを使用している場合は、このアップグレードパスを選択することをお勧めします。<ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**XDM スキーマを使用するオプションを提供**：既存の Adobe Analytics スキーマを使用するか、XDM スキーマを作成してデータオブジェクトのフィールドを XDM スキーマにマッピングするかを選択できます。[XDM スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home#xdm-schemas)は、必要なフィールドを定義し、関連するフィールドのみを定義できる柔軟なスキーマです。 <p>独自の XDM スキーマを使用するメリットについて詳しくは、以下の「独自の XDM スキーマを使用」を参照してください。</p></li><li>**ルールとデータ要素を保持**：新しいルールアクションが必要ですが、最小限の変更で既存のデータ要素とルール条件を再利用できます。</li><li>**将来性を確保**：独自の XDM スキーマを使用することを選択した場合、将来の実装の更新が簡単になります。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。このアクションでは、データオブジェクトのすべてのフィールドを、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリにする必要があります。このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li><li>**時間の経過と共に、さらなる複雑さが発生します**：将来追加するフィールドは、データストリームの XDM にマッピングする必要があります。<p>実装に新しいフィールドが追加されるたびに、次のいずれかを実行できます。</p><ul><li>**オプション 1:** データオブジェクトに新しい任意の evar または新しい prop を入力し、目的の XDM フィールドにマッピングします。<p>このプロセスは、クライアントサイド実装の一貫性を高めますが、マッピングが必要です。</p></li><li>**オプション 2:** データオブジェクトをレガシー実装のままにして、すべての新しいフィールドに XDM オブジェクトのみを入力し始めます。<p>このプロセスではマッピングは必要ありませんが、つまり、一部の変数はデータオブジェクト内にのみ配置され、その他の変数は XDM オブジェクト内にのみ配置されます。 実装のトラブルシューティングが必要な場合は、いつでも 2 か所に移動する必要があります。 内部ワークフローでこのような状況に対応できることを確認します。</p></li></ul> |

{style="table-layout:auto"}

## 基本手順

Web SDKを使用してCustomer Journey Analyticsにデータを送信するためにAdobe Analytics実装（AppMeasurementまたは Analytics 拡張機能）を移行する基本的な手順は、次のとおりです。

1. Adobe Analyticsの実装を移行してAdobe Experience Platform Web SDKを使用し、Edge Networkへのデータ送信を開始します。

   この手順では、既存のAdobe Analytics実装を移行して、web SDKを使用することができます。 オプションで、Customer Journey Analyticsにデータを送信し、Adobe Analyticsにデータを送信する前に、Adobe Analyticsですべてが機能していることを検証することもできます。 設定が完了し、Adobe Analyticsのデータに満足したら、Edge NetworkからCustomer Journey Analyticsにデータを送信できます。

   この柔軟性により、Customer Journey Analyticsに対するより体系的で思慮深いアップグレードが可能になります。

   この方法について詳しくは、Adobe Analytics ドキュメントの次の記事を参照してください。

   * [ タグを使用した web SDKへの移行 ](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [JavaScriptを使用した Web SDKへの移行 ](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Edge Networkから Platform へのデータ送信を開始します。

   1. このデータオブジェクトを介して、すべての変数をAppMeasurement形式で送信します。

      詳しくは、[Adobe Analyticsへのデータオブジェクト変数のマッピング ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) を参照してください。

   1. スキーマを選択します。

      既存の Platform スキーマを使用するかどうかを選択するか、他のAdobe Analytics サービスを使用し始める際に組織のニーズに合わせて XDM スキーマを作成できます。

      Adobeでは、XDM スキーマを作成することをお勧めします。 詳しくは、[Customer Journey Analytics web SDKの実装で使用するカスタムスキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) を参照してください。

      +++Adobe Analytics スキーマの使用

      | メリット | デメリット |
      |----------|---------|
      | <p>Adobe Analytics スキーマを使用すると、次のようなメリットがあります。</p><ul><li>アップグレードが容易<p>既にAdobe Experience Platform Web SDK を使用して Adobe Analytics にデータを送信している場合は、データストリームに追加サービスを追加して、Adobe Experience Platform にデータを送信できます（これは Customer Journey Analytics 設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用すると、次のようなデメリットがあります。</p><ul><li>Adobe Analytics スキーマを使用しても、他の Platform アプリケーションでの使用方法が制限されることはありませんが、スキーマは他の方法よりも複雑になります。これは、Adobe Analytics スキーマには、組織で使用される可能性が低い Adobe Analytics に固有のオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要があります。</p></li></ul> |

+++

      +++XDM スキーマの作成

      | メリット | デメリット |
      |----------|---------|
      | <ul><p>独自の XDM スキーマに更新すると、次のようなメリットがあります。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマ。</li><p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。</p></ul> | <p>独自の XDM スキーマに更新すると、次のようなデメリットがあります。</p><ul><li>スキーマの更新は、Platform へのデータ送信を開始する前に必要な、時間がかかるプロセスです。</li></ul> |

+++

   1. データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。

      詳しくは、Experience Platform ドキュメントの [ データ収集のためのデータ準備 [ の ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) マッピング ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) を参照してください。

   1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。




