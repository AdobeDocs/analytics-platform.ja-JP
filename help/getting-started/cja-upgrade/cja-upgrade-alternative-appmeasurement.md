---
title: Customer Journey Analyticsにアップグレードする際の代替方法
description: Customer Journey Analyticsにアップグレードする際の代替方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
TQID: https://experienceleague.adobe.com/ZqnH8IZau2fC-ucGAjMFQyolfhCe2pYbLiWJ7BKKhII
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 1381
ht-degree: 58%

---

# アップグレードの代替案：Experience Platform Web SDK と Customer Journey Analytics での AppMeasurement データ収集の使用 {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Web SDK での AppMeasurement ロジックの使用"
>abstract="XDM オブジェクトを通じてデータを送信する代わりに、データオブジェクトを通じてすべての変数を AppMeasurement 形式で送信します。<br><br>このオプションを使用すると、XDM オブジェクトをゼロから入力するのではなく、AppMeasurement ロジックを XDM にマッピングできるので、実装時間が節約されます。 ただし、今後追加するフィールドはデータストリームの XDM にマッピングする必要があるので、時間の経過と共に複雑さが増します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="Web SDK を参照する AppMeasurement ロジックの変更"
>abstract="この手順は、実装のショートカットを選択したので表示されます。 AppMeasurement ロジックをコピーまたは変更して、s オブジェクトの代わりにデータオブジェクトを入力します。 例えば、s.eVar1 の割り当てを data.__adobe.analytics.eVar1 に変更し、これをすべての Analytics 変数に対して繰り返します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Customer Journey Analytics にアップグレードする場合は、[Experience Platform Web SDK の新しい実装をお勧め](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)します。 ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。

AppMeasurementまたはAnalytics拡張機能のデータ収集ロジックをWeb SDKで使用して、XDM オブジェクトでデータを収集する代わりに、PlatformおよびCustomer Journey Analyticsにデータを送信できます。 しかし、この代替案は、時間の経過とともにさらなる複雑さを引き起こします。

## メリットとデメリット

このメソッドは、両方のメソッドが同じタスクを実行するため、[&#x200B; データレイヤー全体をCustomer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)に送信する場合は相互に排他的です。 （この方法は、データレイヤー全体をAdobeに送信するのに適しています。 propとeVarはすべてdata.__ adobe.analytics._variable-name_）を経由するため、より洗練されています。

このアップグレードの代替手段を使用する場合は、次の利点と欠点を考慮してください。

| メリット | デメリット |
|----------|---------|
| Adobe Analytics の実装で既に Web SDK を使用している場合、これが推奨されるアップグレードパスです。<ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>Adobe CX Enterpriseのデータ収集の実装を、他のCX Enterprise製品（AJO、RTCDPなど）と統合します</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。 実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**XDM スキーマを使用するオプションを提供**：既存の Adobe Analytics スキーマを使用するか、XDM スキーマを作成してデータオブジェクトのフィールドを XDM スキーマにマッピングするかを選択できます。 [XDM スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home#xdm-schemas)は、必要なフィールドを定義し、関連するフィールドのみを定義できる柔軟なスキーマです。 <p>独自の XDM スキーマを使用するメリットについて詳しくは、以下の「独自の XDM スキーマを使用」を参照してください。</p></li><li>**ルールとデータ要素を保持**：新しいルールアクションが必要ですが、最小限の変更で既存のデータ要素とルール条件を再利用できます。</li><li>**将来性を確保**：独自の XDM スキーマを使用することを選択した場合、将来の実装の更新が簡単になります。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。 このアクションでは、データオブジェクトのすべてのフィールドを、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリにする必要があります。 このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。 ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li><li>**時間の経過に伴う追加の複雑さをもたらします**：今後追加するフィールドは、データストリームのXDMにマッピングする必要があります。<p>実装に新しいフィールドを追加するたびに、次のいずれかを実行できます。</p><ul><li>**オプション 1:** データオブジェクトに新しい任意のEvarまたは新しいpropを入力し、それを目的のXDM フィールドにマッピングします。<p>このプロセスにより、クライアントサイドの実装の一貫性が向上しますが、マッピングが必要です。</p></li><li>**オプション 2:** データオブジェクトを従来の実装のままにし、すべての新しいフィールドに対してXDM オブジェクトのみを入力し始めます。<p>このプロセスではマッピングは必要ありませんが、一部の変数はデータオブジェクトにのみ配置され、他の変数はXDM オブジェクトにのみ配置されることを意味します。 実装のトラブルシューティングを行う必要がある場合は、2つの場所に移動する必要があります。 社内ワークフローがこれに対応していることを確認しましょう。</p></li></ul> |

{style="table-layout:auto"}

## 基本手順

Web SDKを使用してCustomer Journey Analyticsにデータを送信するために、Adobe Analytics実装（AppMeasurementまたはAnalytics拡張機能）を移行する基本的な手順は次のとおりです。

1. Adobe Analyticsの導入を移行して、Adobe Experience Platform Web SDKを使用し、Edge Networkへのデータ送信を開始します。

   この手順では、既存のAdobe Analytics実装を移行して、Web SDKを使用できるようにします。 必要に応じて、データをAdobe Analyticsに送信し、データをCustomer Journey Analyticsに送信する前に、すべてがAdobe Analyticsで動作していることを検証できます。 この設定を行い、Adobe Analyticsのデータに問題がなければ、Edge NetworkからCustomer Journey Analyticsにデータを送信できます。

   この柔軟性により、Customer Journey Analytics に対する、より系統的かつ慎重なアップグレードが可能になります。

   この方法について詳しくは、Adobe Analytics ドキュメントの次の記事を参照してください。

   * [タグを使用した Web SDK への移行](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [JavaScript を使用した Web SDK への移行](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Edge NetworkからPlatformへのデータ送信を開始します。

   1. データオブジェクトを介して、すべての変数をAppMeasurement形式で送信します。

      詳しくは、[Adobe Analyticsへのデータオブジェクト変数のマッピング &#x200B;](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping)を参照してください。

   1. スキーマの選択。

      既存のAdobe Analytics スキーマを使用するか、XDM スキーマを作成して、他のPlatform サービスの使用を開始する際に組織のニーズにより適切に対応させるかを選択できます。

      Adobeでは、XDM スキーマを作成することをお勧めします。 詳しくは、[Customer Journey Analytics Web SDKの実装で使用するカスタムスキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)を参照してください。

      +++Adobe Analytics スキーマの使用

      | メリット | デメリット |
      |----------|---------|
      | <p>Adobe Analytics スキーマを使用すると、次のようなメリットがあります。</p><ul><li>アップグレードのしやすさ<p>既にAdobe Experience Platform Web SDK を使用して Adobe Analytics にデータを送信している場合は、データストリームに追加サービスを追加して、Adobe Experience Platform にデータを送信できます（これは Customer Journey Analytics 設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用すると、次のようなデメリットがあります。</p><ul><li>Adobe Analytics スキーマを使用しても、他の Platform アプリケーションでの使用方法が制限されることはありませんが、スキーマは他の方法よりも複雑になります。 これは、Adobe Analytics スキーマには、組織で使用される可能性が低い Adobe Analytics に固有のオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要があります。</p></li></ul> |

      +++

      +++XDM スキーマの作成

      | メリット | デメリット |
      |----------|---------|
      | <ul><p>独自の XDM スキーマに更新すると、次のようなメリットがあります。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマ。</li><p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。</p></ul> | <p>独自の XDM スキーマに更新すると、次のようなデメリットがあります。</p><ul><li>スキーマの更新は、Platform へのデータの送信を開始する前に必要な時間のかかるプロセスです。</li></ul> |

      +++

   1. データストリームマッピングを使用すると、データオブジェクトのすべてのフィールドをXDM スキーマにマッピングできます。

      詳しくは、Experience Platform ドキュメントの[Data Prep for Data Collection](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)の[&#x200B; マッピング &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)を参照してください。

{{upgrade-final-step}} を参照してください。




