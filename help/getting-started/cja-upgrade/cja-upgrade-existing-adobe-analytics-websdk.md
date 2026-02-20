---
title: プラットフォームにデータを送信するように既存の Adobe Analytics Web SDK の実装を設定します
description: 既存のAdobe Analytics Web SDK実装の設定について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 66%

---

# プラットフォームにデータを送信するように既存の Adobe Analytics Web SDK の実装を設定します {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="データストリームからのサービスとしての Adobe Analytics の削除"
>abstract="Web SDK データが完全に機能したら、Platform 管理者と協力して、データストリームからサービスとして Adobe Analytics を削除します。これを実行する前に、ユーザーが Adobe Analytics から Customer Journey Analytics に移行していることを確認します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics実装で既にAdobe Experience Platform Web SDKを使用している場合は、データストリームを設定して Platform へのデータの送信を開始できます。 または、既に Platform にデータを送信している場合は、Platform データセットと Customer Journey Analytics の間の接続を作成するだけで済みます。


## メリットとデメリット

既存のAdobe Analytics Web SDKを設定して Platform にデータを送信する場合の、次のメリットとデメリットを検討してください。

| メリット | デメリット |
|----------|---------|
| Adobe Analytics の実装で既に Web SDK を使用している場合、これが推奨されるアップグレードパスです。<ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**XDM スキーマを使用するオプションを提供**：既存の Adobe Analytics スキーマを使用するか、XDM スキーマを作成してデータオブジェクトのフィールドを XDM スキーマにマッピングするかを選択できます。[XDM スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home#xdm-schemas)は、必要なフィールドを定義し、関連するフィールドのみを定義できる柔軟なスキーマです。 <p>独自の XDM スキーマを使用するメリットについて詳しくは、以下の「独自の XDM スキーマを使用」を参照してください。</p></li><li>**ルールとデータ要素を保持**：新しいルールアクションが必要ですが、最小限の変更で既存のデータ要素とルール条件を再利用できます。</li><li>**将来性を確保**：独自の XDM スキーマを使用することを選択した場合、将来の実装の更新が簡単になります。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。このアクションでは、データオブジェクトのすべてのフィールドを、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリにする必要があります。このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li><li>**時間の経過と共に、さらなる複雑さが発生します**：将来追加するフィールドは、データストリームの XDM にマッピングする必要があります。<p>実装に新しいフィールドが追加されるたびに、次のいずれかを実行できます。</p><ul><li>**オプション 1:** データオブジェクトに新しい任意の evar または新しい prop を入力し、目的の XDM フィールドにマッピングします。<p>このプロセスは、クライアントサイド実装の一貫性を高めますが、マッピングが必要です。</p></li><li>**オプション 2:** データオブジェクトをレガシー実装のままにして、すべての新しいフィールドに XDM オブジェクトのみを入力し始めます。<p>このプロセスではマッピングは必要ありませんが、つまり、一部の変数はデータオブジェクト内にのみ配置され、その他の変数は XDM オブジェクト内にのみ配置されます。 実装のトラブルシューティングが必要な場合は、いつでも 2 か所に移動する必要があります。 内部ワークフローでこのような状況に対応できることを確認します。</p></li></ul> |

{style="table-layout:auto"}

## 実装手順

1. Edge Networkから Platform へのデータ送信を開始します。 このデータオブジェクトを介して、すべての変数をAppMeasurement形式で送信します。

   詳しくは、[Adobe Analyticsへのデータオブジェクト変数のマッピング ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) を参照してください。

1. スキーマを選択します。

   既存の Platform スキーマを使用するかどうかを選択するか、他のAdobe Analytics サービスを使用し始める際に組織のニーズに合わせて XDM スキーマを作成できます。

   Adobeでは、XDM スキーマを作成することをお勧めします。 詳しくは、[Customer Journey Analytics web SDKの実装で使用するカスタムスキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) を参照してください。

   +++Adobe Analytics スキーマの使用

   | メリット | デメリット |
   |----------|---------|
   | <p>Adobe Analytics スキーマを使用すると、次のようなメリットがあります。</p><ul><li>アップグレードのしやすさ<p>既にAdobe Experience Platform Web SDK を使用して Adobe Analytics にデータを送信している場合は、データストリームに追加サービスを追加して、Adobe Experience Platform にデータを送信できます（これは Customer Journey Analytics 設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用すると、次のようなデメリットがあります。</p><ul><li>Adobe Analytics スキーマを使用しても、他の Platform アプリケーションでの使用方法が制限されることはありませんが、スキーマは他の方法よりも複雑になります。これは、Adobe Analytics スキーマには、組織で使用される可能性が低い Adobe Analytics に固有のオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要があります。</p></li></ul> |

   +++

   +++XDM スキーマの作成

   | メリット | デメリット |
   |----------|---------|
   | <ul><p>独自の XDM スキーマに更新すると、次のようなメリットがあります。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマ。</li><p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。</p></ul> | <p>独自の XDM スキーマに更新すると、次のようなデメリットがあります。</p><ul><li>スキーマの更新は、Platform へのデータの送信を開始する前に必要な時間のかかるプロセスです。</li></ul> |

   +++

1. データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。

   詳しくは、Experience Platform ドキュメントの [ データ収集のためのデータ準備 ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) の [ マッピング ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) を参照してください。

{{upgrade-final-step}}
