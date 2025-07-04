---
title: ステッチの概要
description: ステッチの概要
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 1a697ce0372d1cb544940778850714a198a000ec
workflow-type: ht
source-wordcount: '741'
ht-degree: 100%

---

# ステッチの概要

>[!NOTE]
>
>この節で説明している機能を使用するには、**Select** パッケージ以上（[フィールドベースのステッチ](fbs.md)の場合）または **Prime** パッケージ以上（[グラフベースのステッチ](gbs.md)の場合）が必要です。どの Customer Journey Analytics パッケージを使用しているかが不明な場合は、管理者にお問い合わせください。

ID ステッチ（または単に「ステッチ」）は、クロスチャネル分析に対するイベントデータセットの適合性を高める強力な機能です。クロスチャネル分析は、Customer Journey Analytics で処理できる主なユースケースで、共通の ID（ユーザー ID）に基づいて、異なるチャネルの複数のデータセットに関するレポートをシームレスに組み合わせて実行できます。

データセットを同様のユーザー ID と組み合わせると、アトリビューションはデバイスやチャネルにも伝わります。例えば、ユーザーがデスクトップコンピューターの広告を通じて最初にサイトを訪問したとします。また、注文で問題が発生し、その解決方法を求めてカスタマーサービスチームに電話をしたとします。クロスチャネル分析を使用すると、コールセンターイベントを、訪問者が最初にクリックした広告に関連付けることができます。

残念ながら、Customer Journey Analytics の接続に含まれるすべてのイベントベースデータセットに、このアトリビューションを標準でサポートするデータが十分に入力されているわけではありません。特に、web ベースまたはモバイルベースのエクスペリエンスデータセットには、多くの場合、すべてのイベントで使用できる実際のユーザー ID 情報がありません。

ステッチを使用すると、1 つのデータセットの行内の ID を再入力できるので、各イベントでユーザー ID （ステッチ ID）が使用可能であることを確認します。ステッチでは、認証済みセッションと未認証セッションの両方からのユーザーデータを調べて、ステッチ ID として使用できる共通の一時的な ID （ユーザー ID）値を決定します。この再入力により、複数の異なるレコードを単一のステッチ ID に解決し、デバイスレベルや cookie レベルではなく、ユーザーレベルで分析を行うことができます。

Customer Journey Analyticsでは 2 種類のステッチ（[フィールドベースのステッチ](fbs.md)と[グラフベースのステッチ](gbs.md)）をサポートしています。

## 前提条件

>[!IMPORTANT]
>
>すべての前提条件を満たしていないと、クロスチャネル分析を適切に実施できなくなる可能性があります。

ステッチを使用する前に、組織で以下が準備されていることを確認してください。

- ステッチには、認証済みユーザーデータと未認証ユーザーデータの結合が含まれます。イベントデータセットでステッチをアクティブ化する前に、必要なエンドユーザー権限を取得するなど、適用される法令に確実に準拠してください。詳しくは、[UI で ID フィールドを定義](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity)を参照してください。

- 目的のデータを Adobe Experience Platform に読み込みます。

   - Adobe Analytics のデータについては、[Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)を参照してください。
   - 他のタイプのデータについては、Adobe Experience Platform ドキュメントの[スキーマの作成](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/create-schema-ui)と[データの取り込み](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/home)を参照してください。

Customer Journey Analytics 接続の定義の一環として、1 つ以上のステッチされたデータセットを、コールセンターデータなどの他のデータセットと組み合わせると、クロスチャネル分析のメリットが得られます。この接続設定では、ステッチ ID と同様に、他のデータセットのすべての行にユーザー ID が既に含まれていることを前提としています。


## 制限事項

>[!IMPORTANT]
>
>
>- ソースイベントデータセットスキーマに加えた変更を、ステッチされた新しいデータセットスキーマにも適用します。適用しないと、ステッチされたデータセットが破損します。
>
>- ソースデータセットを削除すると、ステッチされたデータセットは処理を停止し、システムによって削除されます。
>
>- データ使用状況ラベルは、ステッチされたデータセットスキーマに自動的には反映されません。ソースデータセットスキーマにデータ使用状況ラベルが適用されている場合は、ステッチされたデータセットスキーマにこれらのデータ使用状況ラベルを手動で適用する必要があります。詳しくは、[Experience Platform でのデータ使用状況ラベルの管理](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/labels/overview)を参照してください。

ステッチは画期的で堅牢な機能ですが、使用方法に制限があります。

- イベントデータセットのみがサポートされます。参照データセットなどの他のデータセットはサポートされていません。
- ステッチでは、ステッチに使用されるフィールドは変換されません。ステッチでは、指定したフィールドの値が使用されます。これは、その値がデータレイク内の未ステッチデータセットに存在するからです。
- ステッチ処理では、大文字と小文字が区別されます。例えば、フィールドに「Bob」という単語が表示されることもあれば、「BOB」という単語が表示されることもある場合、これらの ID は 2 人の別々の人物として扱われます。

ステッチを以下と混同しないでください。

- 2 つ以上のデータセットの結合。ステッチは、1 つのデータセットにのみ適用されます。データセットの結合は、Customer Journey Analytics 接続を設定し、接続内の選択した複数のデータセットで同じユーザー ID を選択した場合に、結果として起こります。

- 2 つのデータセットの結合。Customer Journey Analytics では、結合は、Analysis Workspace での検索や分類によく使用されます。ステッチには結合機能が使用されますが、プロセス自体には複数の結合が含まれます。

>[!MORELIKETHIS]
>
>[フィールドベースのステッチ](fbs.md)
>>[グラフベースのステッチ](gbs.md)
>>[ステッチの使用](use-stitching.md)
>>[ステッチの検証](validate.md)
>>[ステッチに関する FAQ](faq.md)

