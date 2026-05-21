---
title: Customer Journey Analytics プレリリースノート
description: 最新のCustomer Journey Analytics プレリリースノートを見る
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 80%

---

# Adobe Customer Journey Analytics プレリリースノート

>[!IMPORTANT]
>
>このドキュメントは、今月のリリースノートの&#x200B;**プレビュー**&#x200B;として作成されます。 リリース項目は変更される可能性があり、最終リリースで追加または削除される場合があります。

このリリースノートは、2025年6月2日～2025年7月15日（PT）のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。

Adobe Experience Platformおよびその他のアプリケーションのリリースノートについては、次のドキュメントを参照してください。

* [Adobe Experience Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [連合オーディエンス構成](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace の左パネルが開かなくなり、マウスポインターを置くと閉じる** | Analysis Workspace の左パネルを使用すると、コンポーネント、パネル、ビジュアライゼーションなどをプロジェクトに追加できます。 左端のいずれかのアイコンにマウスポインターを置いて、一時的に左パネルを開くオプションは使用できなくなりました。 代わりに、これらのアイコンのいずれかをクリックしてパネルを開いたままにし、同じアイコンをクリックして閉じます。 |  | 2025年6月2日（PT） <p>（当初は 2025年5月29日（PT）にリリースされる予定でした）</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition は、売上高の増加を促進する実用的なアカウントインサイトを提供することで、B2B 企業がマーケティング、セールス、製品の各チームを連携させるのに役立ちます。 データモデルの中心となるのはアカウントなので、すべての分析はアカウントジャーニーに焦点を当てます。 ユーザーおよび時間ベースのイベントの上にエンティティ（アカウント、商談、購買グループ）の新しいレイヤーを追加すると、B2B マーケティングおよび収益のライフサイクルの全体像が作成されます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025年6月18日（PT） |
| **Report Builderのセキュアな宛先のサポート** | Report Builder のアドインに書き出しの新しい宛先が追加されました。 次のクラウドストレージの宛先がサポートされています。 <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 2025年6月18日（PT） |
| **新しいプレビューエクスペリエンス** | セグメントや計算指標などをプレビューするために使用されるプレビューパネルでは、ドーナツビジュアライゼーションではなく、横棒グラフビジュアライゼーションが使用されるようになりました。 |  | 2025年6月18日（PT） |
| **変更されたアトリビューションモデルダイアログ** | アトリビューションモデルダイアログでコンテナと期間を個別に定義できるようになりました。 |  | 2025年6月18日（PT） |
| **接続マップ** | 接続設定を視覚的に表示する、新しい[接続マップインターフェイス](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection#connection-map)を使用できます。 |  | 2025年6月18日（PT） |
| **Analysis Workspace プロジェクトでのコメントの追加と表示** | Analysis Workspace の新しい[コメント機能](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)を使用すると、Analysis Workspace プロジェクトのコンテキスト内でインサイトを共有し質問をすることができます。 これにより、データに関する議論を効率化して、議論の対象となっているデータのコンテキスト内に会話を維持できます。 次のことが可能です。 <ul><li>自身がアクセス権を持っている Analysis Workspace プロジェクトにコメントする</li><li>ビジュアライゼーション内の特定のポイントにコメントする、またはプロジェクトに関する一般的なコメントをする</li><li>他のユーザーにタグを付けて、コメントについて通知する</li><li>既存のコメントを管理する（編集、ピン留め、解決など）</li></ul>Customer Journey Analytics 管理者は[組織レベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)ことができます。 プロジェクト所有者は[プロジェクトレベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)ことができます。 |  | 2025年6月25日（PT） <p>（当初は 2025年5月29日（PT）にリリースされる予定でした）</p> |
