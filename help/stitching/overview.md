---
title: ステッチの概要
description: ステッチの概要。
solution: Customer Journey Analytics
feature: Stitching
source-git-commit: ec316d36c1e2ec6eb6e75e980ad3fed4ededfb94
workflow-type: tm+mt
source-wordcount: '1220'
ht-degree: 29%

---

# ステッチの概要

ID ステッチ（または単にステッチ）は、イベントデータセットのクロスチャネル分析に対する適合性を高める強力な機能です。 クロスチャネル分析は、Customer Journey Analyticsが処理できる主な使用例で、共通の識別子（ユーザー ID）に基づいて、様々なチャネルの複数のデータセットに関するレポートをシームレスに組み合わせ、実行できます。

データセットを同様のユーザー ID と組み合わせると、アトリビューションはデバイスやチャネルにも伝わります。例えば、ユーザーがデスクトップコンピューターの広告を通じて最初にサイトを訪問したとします。また、注文で問題が発生し、その解決方法を求めてカスタマーサービスチームに電話をしたとします。クロスチャネル分析を使用すると、コールセンターイベントを、訪問者が最初にクリックした広告に関連付けることができます。

残念ながら、Customer Journey Analyticsの接続に含まれるすべてのイベントベースのデータセットには、初期設定でこのアトリビューションをサポートするために、十分なデータが入力されているわけではありません。 特に、Web ベースまたはモバイルベースのエクスペリエンスデータセットには、多くの場合、すべてのイベントで実際のユーザー ID 情報を使用できません。

ステッチを使用すると、データセットの行内で ID を再入力して、目的のユーザー ID（ステッチ済み ID）が各イベントで使用できるようにします。 ステッチでは、認証済みセッションと未認証セッションの両方からユーザーデータを調べて、ステッチされた ID を生成します。 ステッチを使用すると、デバイスや cookie レベルではなく、個人レベルでの分析用に、個々のレコードを単一のステッチ ID に解決できます。

Customer Journey Analytics接続の定義の一環として、1 つ以上の関連付けられたデータセットをコールセンターデータなどの他のデータセットと組み合わせる場合、クロスチャネル分析のメリットが得られます。 これは、他のデータセットに、ステッチされた ID と同様に、すべての行に既に人物 ID が含まれていることを前提としています。


## 前提条件

>[!IMPORTANT]
>
>すべての前提条件を満たしていない場合、クロスチャネル分析を適切に実行できない可能性があります。

ステッチを使用する前に、組織で以下が準備されていることを確認します。

* 目的のデータをAdobe Experience Platformにインポートします。

   * Adobe Analyticsのデータについては、 [Customer Journey AnalyticsでのAdobe Analyticsレポートスイートデータの利用](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * 他のタイプのデータについては、Adobe Experience Platform ドキュメントの[スキーマの作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja)と[データの取り込み](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja)を参照してください。

* ステッチを適用するAdobe Experience Platformのデータセットには、訪問者を識別するのに役立つ次の 2 つの列が必要です。

   * **永続 ID** - 各行に存在する識別情報です。例えば、Adobe AnalyticsAppMeasurementライブラリによって生成された訪問者 ID や、Adobe Experience Cloud ID サービスによって生成された ECID などです。
   * **一時的な ID** - 一部の行にのみ存在する識別情報です。例えば、訪問者の認証後にハッシュ化されたユーザー名やメールアドレスなどがあります。ほぼすべての識別子を使用できます。ただし、特定の永続 ID と同じイベントに 1 回以上存在する場合に限ります。

* ステッチには、認証済みと未認証のユーザーデータの結合が含まれます。 データセットを結合する前に、適用される法規制（必要なエンドユーザー権限の取得を含む）に従っていることを確認します。


## ステッチを使用

組織がすべての前提条件を満たし、 [制限](#limitations)では、次の手順に従って、Customer Journey Analyticsでのステッチの使用を開始できます。

### サポートをリクエスト

1. 次の情報をアドビカスタマーサポートに連絡してください。

   * ステッチを有効にするリクエスト。
   * キーを変更するデータセットのデータセット ID.
   * 目的のデータセットの永続 ID の列名（各行に表示される識別子）。
   * 目的のデータセットの一時的な ID の列名（データセット間のユーザー ID リンク）。
   * [再生](explained.md)の頻度とルックバックの期間。オプションとしては、週に 1 回の再生（7 日間のルックバックウィンドウ）や、毎日の再生（1 日間のルックバックウィンドウ）があります。
   * サンドボックス名


2. Adobeカスタマーサポートは、Adobeエンジニアリングと連携し、リクエストを受け取ったときにステッチを有効にします。 有効にすると、新規のユーザー ID 列を含んだ新しいキー再設定済みデータセットが Adobe Experience Platform に表示されます。アドビカスタマーサポートは、新しいデータセット ID とユーザー ID の列名を提供できます。

3. 初めてオンにしたとき、前月の初め（最大 60 日前）まで遡ってステッチデータのバックフィルが行われます。このバックフィルをおこなうには、一時的な ID が、それまでの時間に関連付けられていないデータに存在する必要があります。

4. [接続の作成](/help/connections/create-connection.md) Customer Journey Analyticsで、新しく生成されたデータセットと、含める他のデータセットを使用します。 各データセットに適切なユーザー ID を選択します。

5. 接続に基づいて、[データ表示を作成](/help/data-views/create-dataview.md)します。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

データビューが設定されると、Customer Journey Analyticsのクロスチャネル分析は、Customer Journey Analyticsの他の分析と同様に機能します。ただし、データはチャネルとデバイスをまたいで機能します。

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## 制限事項

>[!IMPORTANT]
>
>グローバルイベントデータセットスキーマに加えた変更を新しいステッチ済みデータセットスキーマにも適用します。そうしないと、ステッチ済みデータセットが壊れます。
>
>また、ソースデータセットを削除すると、ステッチされたデータセットは、処理を停止し、システムによって削除されます。

ステッチは画期的で堅牢な機能ですが、使用方法に制限があります。

* 現在のキー変更機能は、1 つの手順（永続 ID から一時的な ID への変更）に制限されます。複数手順でのキーの変更（例えば、永続 ID を一時的な ID に、その後別の一時的な IDに変更）はサポートされません。
* イベントデータセットのみがサポートされます。参照データセットなどの他のデータセットはサポートされていません。
* 組織で使用されているカスタム ID マップはサポートされていません。
* ステッチでは、ステッチに使用されるフィールドは変換されません。 ステッチでは、データレイク内の未ステッチデータセットに存在する、指定されたフィールドの値を使用します。 ステッチ処理では、大文字と小文字が区別されます。例えば、「Bob」という単語がフィールドに表示され、「BOB」という単語が表示される場合、これらの ID は 2 人の別々の人として扱われます。
* ステッチでは、大文字と小文字が区別されます。 Analytics Source Connector を使用して生成されたデータセットの場合、Adobeでは、一時的な ID フィールドに適用される VISTA ルールまたは処理ルールを確認することをお勧めします。 このレビューでは、これらのルールで同じ ID の新しい形式が導入されていないことを確認します。 例えば、VISTA ルールまたは処理ルールにより、イベントの一部のみで一時的な ID フィールドが小文字になっていないか確認する必要があります。
* ステッチでは、フィールドの組み合わせや連結は行われません。
* 一時的な ID フィールドには、単一のタイプの ID（単一の名前空間の ID）を含める必要があります。 例えば、一時的な ID フィールドにログイン ID と電子メール ID の組み合わせを含めることはできません。
* 同じ永続 ID に対して同じタイムスタンプで複数のイベントが発生し、一時的な ID フィールドの値が異なる場合、アルファベット順に基づいて ID がステッチによって選択されます。 したがって、永続 ID A に同じタイムスタンプを持つ 2 つのイベントがあり、いずれかのイベントが Bob を指定し、もう一方が Ann を指定した場合、ステッチは Ann を選択します。
* デバイスが複数のユーザーによって共有され、ユーザー間のトランジションの合計数が 50,000 を超える場合、Customer Journey Analyticsはそのデバイスのデータのステッチを停止します。

ステッチを次のものと混同しないでください。

* 2 つ以上のデータセットの結合。 ステッチは、1 つのデータセットにのみ適用されます。 データセットの結合は、Customer Journey Analytics接続を設定し、接続内の選択したデータセット全体で同じユーザー ID を選択した結果として発生します。

* 2 つのデータセットの結合。 Customer Journey Analyticsでは、Analysis Workspaceでの検索や分類に結合がよく使用されます。 ステッチでは結合機能が使用されますが、プロセス自体には結合以上のものが含まれます。

