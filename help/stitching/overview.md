---
title: ステッチの概要
description: ID合成の概念、利点、前提条件、制限事項について説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
autotag-review: '2026-05-19T09:24:34.962Z'
TQID: 'https://experienceleague.adobe.com/Y7Q0pAx9s4p2YxrcfVKsvJcppHFmtNCKAgA0oCc0CeA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1022
ht-degree: 58%

---

# ステッチの概要

>[!NOTE]
>
>この節で説明する機能を使用するには、Customer Journey Analytics **Select** パッケージ以上（[&#x200B; フィールドベースのステッチ &#x200B;](fbs.md)の場合）またはCustomer Journey Analytics **Prime** パッケージ以上（[&#x200B; グラフベースのステッチ &#x200B;](gbs.md)の場合）が必要です。 どの Customer Journey Analytics パッケージを使用しているかが不明な場合は、管理者にお問い合わせください。

ID ステッチ（または単に「ステッチ」）は、クロスチャネル分析に対するイベントデータセットの適合性を高める強力な機能です。 クロスチャネル分析は、Customer Journey Analytics の主なユースケースです。 この機能では、共通の ID（ユーザー ID）に基づいて、異なるチャネルの複数のデータセットに関するレポートをシームレスに組み合わせて実行できます。

データセットを類似のユーザー ID と組み合わせた場合、アトリビューションはデバイスやチャネルをまたいで引き継がれます。 例えば、あるユーザーがデスクトップコンピューターを使用して、広告経由でサイトを訪問したとします。 利用者は商品を購入しましたが、その後、注文に関する問題に遭遇しました。 次に、ユーザーは問題の解決を支援するカスタマーサービスチームに電話をかけます。 クロスチャネル分析では、コールセンターイベントを、ユーザーが最初にクリックした広告に関連付けることができます。

残念ながら、Customer Journey Analytics の接続に含まれるすべてのイベントベースデータセットに、このアトリビューションを標準でサポートするデータが十分に入力されているわけではありません。 特に、web ベースまたはモバイルベースのエクスペリエンスデータセットには、多くの場合、すべてのイベントで使用できる実際のユーザー ID 情報がありません。

照合すると、1つのデータセットの行内でIDが再入力され、目的の個人ID情報ができるだけ多くのイベントで利用できるようになります。 合成では、認証済みセッションと未認証セッションの両方からユーザーデータを調べ、使用できる共通の人物ID値を決定します。 この再入力により、デバイスやCookieのレベルではなく、個人レベルで分析するために、異なるレコードを単一の個人IDに解決できます。 ただし、共通の人物ID値を決定できない場合は、代わりに永続的なID値が使用されます。

Customer Journey Analyticsでは 2 種類のステッチ（[フィールドベースのステッチ](fbs.md)と[グラフベースのステッチ](gbs.md)）をサポートしています。

## 前提条件

>[!IMPORTANT]
>
>すべての前提条件を満たしていないと、クロスチャネル分析を適切に実施できなくなる可能性があります。

ステッチを使用する前に、組織で以下が準備されていることを確認してください。

- ステッチには、認証済みユーザーデータと未認証ユーザーデータの結合が含まれます。 イベントデータセットでステッチをアクティブ化する前に、必要なエンドユーザー権限を取得するなど、適用される法令に確実に準拠してください。

- 目的のデータを Adobe Experience Platform に読み込みます。

   - Adobe Analytics のデータについては、[Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)を参照してください。
   - 他のタイプのデータについては、Adobe Experience Platform ドキュメントの[スキーマの作成](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/create-schema-ui)と[データの取り込み](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/home)を参照してください。

Customer Journey Analytics 接続の定義の一環として、1 つ以上のステッチされたデータセットを、コールセンターデータなどの他のデータセットと組み合わせると、クロスチャネル分析のメリットが得られます。 この接続設定では、これらの他のデータセットに、同じ名前空間の人物IDが可能な限り多くの行に既に含まれていることを前提としています。

一般的な[前提条件](overview.md#prerequisites)を満たし、一般的な[制限](overview.md#limitations)を理解し、ステッチ方式に固有の（[&#x200B; フィールドベース &#x200B;](fbs.md)および[&#x200B; グラフベース &#x200B;](gbs.md)）前提条件と制限事項を理解したら、次の手順に従って、Customer Journey Analyticsでステッチをリクエストして使用を開始できます。

## 制限事項

ステッチは画期的で堅牢な機能ですが、使用方法に制限があります。

- イベントデータセットのみがサポートされます。 参照データセットなどの他のデータセットはサポートされていません。
- ステッチでは、ステッチに使用されるフィールドは変換されません。 ステッチでは、指定したフィールドの値が使用されます。これは、その値がデータレイク内の未ステッチデータセットに存在するからです。
- ステッチ処理では、大文字と小文字が区別されます。 例えば、ID値`Bob`と`BOB`は2人の別々の人物として扱われます。

ステッチを以下と混同しないでください。

- 2 つ以上のデータセットの結合。 ステッチは、1 つのデータセットにのみ適用されます。 データセットの結合は、Customer Journey Analytics 接続を設定し、接続内の選択した複数のデータセットで同じユーザー ID を選択した場合に、結果として起こります。

- 2 つのデータセットの結合。 Customer Journey Analytics では、結合は、Analysis Workspace での検索や分類によく使用されます。 ステッチには結合機能が使用されますが、プロセス自体には複数の結合が含まれます。


## オプション

使用できるCustomer Journey Analytics パッケージによって、使用可能なステッチ方法、初期バックフィル期間のオプション、ルックバックウィンドウ、再生頻度、ステッチに使用できるデータセットの最大数が決まります。 詳しくは、[Customer Journey Analytics製品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html)を参照してください。 ステッチを有効にする前に、使用可能なオプションを決定します。

| | Customer Journey Analytics<br/>選択 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 使用可能なステッチ方法 | フィールドベースのステッチ | フィールドベースの合成<br/> グラフベースの合成 | フィールドベースの合成<br> グラフベースの合成</li> |
| 1回限りのステッチのバックフィル時間 | 13 か月 | 13 か月 | 25 か月 |
| ルックバックウィンドウと再生頻度 | 1日、毎日<br/>最大7日間、毎週 | 1日、毎日<br/>最大14日間、毎週 | 1日、毎日<br/>最大30日間、毎週 |
| 結合に許可されるデータセットの最大数 | 5 | 15 | 50 |

## ステッチを有効にする

ステッチは次の 2 つの方法で有効にできます。

- [&#x200B; ステッチを有効にするリクエスト &#x200B;](/help/stitching/use-stitching.md) （非推奨）。 承認されると、ステッチをリクエストしたデータセットに対して重複したデータセットが作成されます。 この重複データセットには、ステッチされた識別子を持つ追加の列が含まれています。 Customer Journey Analyticsで結合データを使用するには、結合データセットを含む新しい接続を作成するか、既存の接続を編集する必要があります。
- [接続インターフェイス &#x200B;](/help/stitching/use-stitching-ui.md)でステッチを有効にします。 Connections インターフェイスでデータセットのステッチを設定すると、ステッチは、そのデータセットからCustomer Journey Analyticsにデータを取り込む際に、その場で実行されます。


## Journey Optimizer データセット

ステッチでは、次の自動生成された Journey Optimizer データセットをサポートしています。

- AJO ジャーニーステップイベント
- AJO 受信アクティビティイベントデータセット
- AJO サーフェスデータセット
- AJO メッセージフィードバックイベントデータセット* AJO プッシュトラッキングエクスペリエンスイベントデータセット
- AJO メールトラッキングエクスペリエンスイベントデータセット
- AJO BCC フィードバックイベントデータセット
- AJO ライブアクティビティフィードバックイベントデータセット
- AJO ExD 決定イベントデータセット

>[!MORELIKETHIS]
>
>[&#x200B; フィールドベースの合成](fbs.md)
>[グラフベースのステッチ](gbs.md)
>[ステッチの使用](use-stitching.md)
>[ステッチの検証](validate.md)
>[ステッチに関する FAQ](faq.md)

