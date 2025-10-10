---
title: Customer Journey Analyticsのプレリリースノート
description: 最新のCustomer Journey Analytics プレリリースノートを表示
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
source-git-commit: 9a489831ebbb579a2f0e368426dfed73b1ee5962
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 79%

---

# Adobe Customer Journey Analyticsのプレリリースノート

>[!IMPORTANT]
>
>このドキュメントは、今月のリリースノートの **プレビュー** として提供することを目的としています。 リリース項目は変更される場合があり、最終リリースで追加または削除される場合があります。

このリリースノートは、2025年6月2日～2025年7月15日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する [&#x200B; 継続的な配信モデル &#x200B;](releases.md) に基づいて動作します。

Adobe Experience Platformとその他のアプリケーションのリリースノートについては、次のドキュメントを参照してください。

* [Adobe Experience Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [連合オーディエンス構成](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace の左パネルが開かなくなり、マウスポインターを置くと閉じる** | Analysis Workspace の左パネルを使用すると、コンポーネント、パネル、ビジュアライゼーションなどをプロジェクトに追加できます。左端のいずれかのアイコンにマウスポインターを置いて、一時的に左パネルを開くオプションは使用できなくなりました。代わりに、これらのアイコンのいずれかをクリックしてパネルを開いたままにし、同じアイコンをクリックして閉じます。 |  | 2025年6月2日（PT） <p>（当初は 2025年5月29日（PT）にリリースされる予定でした）</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition は、売上高の増加を促進する実用的なアカウントインサイトを提供することで、B2B 企業がマーケティング、セールス、製品の各チームを連携させるのに役立ちます。データモデルの中心となるのはアカウントなので、すべての分析はアカウントジャーニーに焦点を当てます。ユーザーおよび時間ベースのイベントの上にエンティティ（アカウント、商談、購買グループ）の新しいレイヤーを追加すると、B2B マーケティングおよび収益のライフサイクルの全体像が作成されます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025年6月18日（PT） |
| **Report Builderでの安全な宛先のサポート** | Report Builder のアドインに書き出しの新しい宛先が追加されました。次のクラウドストレージの宛先がサポートされています。 <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 2025年6月18日（PT） |
| **新しいプレビューエクスペリエンス** | セグメントや計算指標などをプレビューするために使用されるプレビューパネルでは、ドーナツビジュアライゼーションではなく、横棒グラフビジュアライゼーションが使用されるようになりました。 |  | 2025年6月18日（PT） |
| **変更されたアトリビューションモデルダイアログ** | アトリビューションモデルダイアログでコンテナと期間を個別に定義できるようになりました。 |  | 2025年6月18日（PT） |
| **接続マップ** | 接続設定を視覚的に表示する、新しい[接続マップインターフェイス](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection#connection-map)を使用できます。 |  | 2025年6月18日（PT） |
| **Analysis Workspace プロジェクトでのコメントの追加と表示** | Analysis Workspace の新しい[コメント機能](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)を使用すると、Analysis Workspace プロジェクトのコンテキスト内でインサイトを共有し質問をすることができます。これにより、データに関する議論を効率化して、議論の対象となっているデータのコンテキスト内に会話を維持できます。次のことが可能です。 <ul><li>自身がアクセス権を持っている Analysis Workspace プロジェクトにコメントする</li><li>ビジュアライゼーション内の特定のポイントにコメントする、またはプロジェクトに関する一般的なコメントをする</li><li>他のユーザーにタグを付けて、コメントについて通知する</li><li>既存のコメントを管理する（編集、ピン留め、解決など）</li></ul>Customer Journey Analytics 管理者は[組織レベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)ことができます。プロジェクト所有者は[プロジェクトレベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)ことができます。 |  | 2025年6月25日（PT） <p>（当初は 2025年5月29日（PT）にリリースされる予定でした）</p> |
