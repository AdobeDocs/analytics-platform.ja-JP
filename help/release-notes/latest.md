---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 21bcc23b37372fc96347228b8b40fa970bb09bb5
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 74%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2023 年 8 月）

**最終更新日**：2023年8月9日（PT）

これらのリリースノートでは、8 月 9 日から 2023 年 9 月 13 日のリリース期間を扱っています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Report Builder の機能強化** | <ul><li>「ワークブック」タブからスケジュール済みタスクをダウンロードし、そのタスクにタイトルを付けて保存し、共有することができます。 [詳細情報](/help/report-builder/schedule-reportbuilder.md)</li><li>開始日をディメンションとして使用すると、データブロックの開始日をディメンションとしてデータブロック出力に表示できます。 [詳細情報](/help/report-builder/create-a-data-block.md) </li></ul> | 該当なし | 2023年8月17日（PT） |
| **通貨換算** | 顧客ジャーニーは、複数の通貨をサポートする機能を追加しています。 データビューの設定で、通貨を別の通貨に変換できます。 [詳細情報](/help/data-views/component-settings/format.md) | 該当なし | 2023年8月31日（PT） |
| **Analytics Source Connector での A4T 分類のサポート** | Adobe Targetのアクティビティとエクスペリエンスイベントの分類データを簡単に結合できるように、相関 ID を追加しています。 | 該当なし | 2023年8月31日（PT） |
| **レポートアクティビティマネージャー** | 管理者は、各接続のレポート消費状況を詳細に把握できるので、管理者は、ピーク時のレポート作成時に容量の問題を簡単に診断し、修正できます。 | 該当なし | 2023 年 9 月 7 日 |
| **Power BI および Tableau から Customer Journey Analytics データビューへのアクセス** | Adobe Customer Journey Analytics SQL コネクタを使用すると、Customer Journey Analytics で定義したデータビューへの SQL アクセスが可能になります。Power BI、Tableau またはその他のビジネスインテリジェンスおよびビジュアライゼーションツールに精通したデータエンジニアやアナリストは、Customer Journey Analytics ユーザーが Analysis Workspace プロジェクトに使用しているものと同じデータビューに基づいて、レポートやダッシュボードを作成できるようになりました。[詳細情報](/help/data-views/sql-connector.md) | 該当なし | 2023 年 9 月 14 日 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **Customer Journey Analytics によるデータの処理方法の変更** | 2023年6月22日（PT） | 最近、Customer Journey Analytics でのデータの処理方法が変更されました。<ul><li>発生後の経過時間が 24 時間未満のイベントデータは、すべてストリーミングで取り込まれます。</li><li>経過時間が 24 時間以上のイベントデータは、（より新しいデータと同じバッチにある場合でも）バックフィルと見なされ、低い優先度で取り込まれます。</li></ul> |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API、Customer Journey Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。2024年5月1日（PT）以降、Adobe I/O では新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 関連リソース

* [2023年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
