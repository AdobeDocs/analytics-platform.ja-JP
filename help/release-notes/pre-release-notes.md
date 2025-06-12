---
title: Customer Journey Analyticsのプレリリースノート
description: 最新のCustomer Journey Analytics プレリリースノートを表示
feature: Release Notes
hide: true
hidefromtoc: true
source-git-commit: 71776f8c2ffa3154d85bd837921011e14ec0ea3f
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 25%

---


# Adobe Customer Journey Analyticsのプレリリースノート

>[!IMPORTANT]
>
>このドキュメントは、今月のリリースノートの **プレビュー** として提供することを目的としています。 リリース項目は変更される場合があり、最終リリースで追加または削除される場合があります。

このリリースノートは、2025年6月2日～2025年7月15日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する [ 継続的な配信モデル ](releases.md) に基づいて動作します。

Adobe Experience Platformとその他のアプリケーションのリリースノートについては、次のドキュメントを参照してください。

* [Adobe Experience Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [連合オーディエンス構成](https://experienceleague.adobe.com/ja/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/ja/docs/real-time-cdp-collaboration/using/latest?lang=en)

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace の左パネルが開かなくなり、マウスポインターを置くと閉じる** | Analysis Workspace の左パネルを使用すると、コンポーネント、パネル、ビジュアライゼーションなどをプロジェクトに追加できます。左端のいずれかのアイコンにマウスポインターを置いて、一時的に左パネルを開くオプションは使用できなくなりました。代わりに、これらのアイコンのいずれかをクリックしてパネルを開いたままにし、同じアイコンをクリックして閉じます。 |  | 2025年6月2日（PT） <p>（当初は 2025 年 5 月 29 日にリリースする予定です）</p> |
| **Customer Journey AnalyticsB2B edition** | Customer Journey Analytics B2B editionは、売上高の増加を促す実用的なアカウントインサイトを提供することで、B2B 企業がマーケティング、セールス、製品の各チームを連携させるのに役立ちます。 アカウントがデータモデルの中心に配置されるので、すべての分析はアカウントジャーニーに焦点を当てます。 人物および時間ベースのイベントの上に新しいエンティティのレイヤー（アカウント、機会、購入グループ）を追加すると、B2B マーケティングと収益のライフサイクルの全体像が作成されます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025年6月18日（PT） |
| **Report Builderでの安全な宛先のサポート** | 新しい書き出し先がReport Builder アドインに追加されました。 次のクラウドストレージの宛先がサポートされています。 <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 18,2025年6月 |
| **新しいプレビューエクスペリエンス** | セグメントや計算指標などをプレビューするためのプレビューパネルでは、ドーナツビジュアライゼーションではなく、横棒ビジュアライゼーションを使用するようになりました。 |  | 2025年6月18日（PT） |
| **変更されたアトリビューションモデルダイアログ** | アトリビューションモデルダイアログで、コンテナと期間を別々に定義できるようになりました。 |  | 18,2025年6月 |
| **接続マップ** | 新しい [ 接続マップインターフェイス ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection#connection-map) を使用して、接続設定を視覚的に表示できます。 |  | 2025年6月18日（PT） |
| **Analysis Workspace プロジェクトでのコメントの追加と表示** | Analysis Workspaceの新しい [ コメント機能 ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) を使用すると、Analysis Workspace プロジェクトのコンテキスト内でインサイトを共有し、質問することができます。 これにより、データに関する話し合いが合理化され、話し合うデータのコンテキスト内で会話を維持できます。 次のことが可能です。 <ul><li>アクセス権のあるAnalysis Workspace プロジェクトにコメントします</li><li>ビジュアライゼーション内の特定のポイントにコメントする、またはプロジェクトに関して一般的なコメントを作成する</li><li>他のユーザーにタグを付けて、コメントについて通知します</li><li>既存のコメントを管理（編集、ピン留め、解決など）</li></ul>Customer Journey Analytics管理者は [ 組織レベルでコメントを無効にする ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences) ことができます。 プロジェクト所有者は [ プロジェクトレベルでコメントを無効にする ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects) ことができます。 |  | 2025年6月25日（PT） <p>（当初は 2025 年 5 月 29 日にリリースする予定です）</p> |

