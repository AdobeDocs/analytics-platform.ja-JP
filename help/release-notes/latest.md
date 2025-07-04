---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cbe5f3894a01f662a6ebe9c380583d0a039863fd
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 72%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年6月）

**最終更新日**：2025年6月18日（PT）


このリリースノートは、2025年6月2日～2025年7月15日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace の左パネルが開かなくなり、マウスポインターを置くと閉じる** | Analysis Workspace の左パネルを使用すると、コンポーネント、パネル、ビジュアライゼーションなどをプロジェクトに追加できます。左端のいずれかのアイコンにマウスポインターを置いて、一時的に左パネルを開くオプションは使用できなくなりました。代わりに、これらのアイコンのいずれかをクリックしてパネルを開いたままにし、同じアイコンをクリックして閉じます。 |  | 2025年6月2日（PT） <p>（当初は 2025 年 5 月 29 日にリリースする予定です）</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition は、売上高の増加を促進する実用的なアカウントインサイトを提供することで、B2B 企業がマーケティング、セールス、製品の各チームを連携させるのに役立ちます。データモデルの中心となるのはアカウントなので、すべての分析はアカウントジャーニーに焦点を当てます。ユーザーおよび時間ベースのイベントの上にエンティティ（アカウント、商談、購買グループ）の新しいレイヤーを追加すると、B2B マーケティングおよび収益のライフサイクルの全体像が作成されます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025年6月18日（PT） |
| **Report Builderでのセキュアなクラウド宛先のサポート** | Report Builderから次のクラウドストレージの宛先にレポートを書き出せるようになりました。<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>以前は、ワークブックをメールで他のユーザーと共有できましたが、Report Builderからクラウドの宛先にレポートを書き出すことはできませんでした。</p><p>詳しくは、[ クラウド宛先への書き出しによるワークブックのスケジュール設定 ](/help/report-builder/report-builder-export.md) を参照してください。</p> |  | 2025 年 6 月 19 日（Pt）（当初は 2025 年 6 月 18 日（Pt）） |
| **新しいプレビューエクスペリエンス** | セグメントの作成時やデータビューの設定を行う際に使用するプレビューパネルでは、ドーナツビジュアライゼーションではなく、横棒ビジュアライゼーションを使用するようになりました。 |  | 2025年6月18日（PT） |
| **変更されたアトリビューションモデルダイアログ** | アトリビューションモデルダイアログでコンテナと期間を個別に定義できるようになりました。 |  | 2025年6月18日（PT） |
| **接続マップ** | 新しい [ 接続マップインターフェイス ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection#connection-map) を使用して、接続設定を視覚的に表示できます。 |  | 2025年6月18日（PT） |
| **Analysis Workspace プロジェクトでのコメントの追加と表示** | Analysis Workspace の新しい[コメント機能](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)を使用すると、Analysis Workspace プロジェクトのコンテキスト内でインサイトを共有し質問をすることができます。これにより、データに関する議論を効率化して、議論の対象となっているデータのコンテキスト内に会話を維持できます。次のことが可能です。 <ul><li>自身がアクセス権を持っている Analysis Workspace プロジェクトにコメントする</li><li>ビジュアライゼーション内の特定のポイントにコメントする、またはプロジェクトに関する一般的なコメントをする</li><li>他のユーザーにタグを付けて、コメントについて通知する</li><li>既存のコメントを管理する（編集、ピン留め、解決など）</li></ul>Customer Journey Analytics 管理者は[組織レベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)ことができます。プロジェクト所有者は[プロジェクトレベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)ことができます。 | 2025年6月25日（PT） | 2025年7月11日（PT） <p>（当初は 2025 年 5 月 29 日にリリースする予定です）</p> |
| **Chrome 事前レンダリングのサポート** | Chrome がページを事前レンダリングする際のデータ収集ライブラリの動作を制御します。（ドキュメントへのリンクを添付） |  | 2025年6月30日（PT） |

## Customer Journey Analytics の修正点

**アラート**:AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B**: AN-376028
**Tableau 用の BI 拡張機能**: AN-377488
**コンポーネント**:AN-376174
**データビュー**: AN-379011
**書き出し場所**:AN-382191
**完全テーブルのエクスポート**: AN-375646; AN-376986; AN-380355; AN-381310
**ジャーニー キャンバス**: AN-375865; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**レポート**: AN-372615; AN-378578;


## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
