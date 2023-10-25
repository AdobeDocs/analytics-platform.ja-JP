---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8cbd71bf886ea73b7d04875e960c6a1d7a3be484
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 77%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2023 年 10 月/11 月）


**最終更新日**：2023年10月25日（PT）

これらのリリースノートでは、2023 年 10 月 16 日のリリース期間を 2023 年 11 月末にカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **の新機能 [!UICONTROL 使用状況] Adobe Product Analyticsで表示** | に次の機能が追加されました。 [使用状況ビュー](/help/guided-analysis/types/usage.md):<ul><li>**トレンドライン**：トレンドラインがサポートされるようになりました。 クリック [!UICONTROL オーバーレイ] をグラフの上に追加して有効にします。</li><li>**クエリの分類**：このビュータイプに分類を適用できるようになりました。 これらは、クエリレールのオプションとして使用できます。</li></ul> | 該当なし | 2023年10月25日（PT） |
| **CJA データビュー API のドキュメント** | 詳しくは、 [データビュー API](https://developer.adobe.com/cja-apis/docs/endpoints/dataviews/) を参照して、データビューをプログラムで作成、変更、削除する方法を学びます。 | 該当なし | 2023年10月16日（PT） |
| **ルックアップおよびプロファイルデータセットの行数指標** | これらの指標は、以前はイベントデータセットでのみ使用できました。 | 該当なし | 2023年10月16日（PT） |
| **完全なテーブルをクラウドに書き出し** | Customer Journey Analytics の完全なテーブルの書き出しを使用すると、数百万の Workspace 行をクラウドの宛先に書き出すことができます。 <p>完全なテーブルを書き出すと、Workspace 内で設計されたデータテーブルを 1 回限りまたは予定どおりに配信でき、連結されたテーブルで、最大 5 つの分類、5 つの指標、フィルター、計算指標をすべてサポートします。これは、Adobe Analytics のデータウェアハウスレポートの進化版で、現在のデータウェアハウスでは利用できない、リクエストの多い新機能が多数追加されています。</p><p> クラウドの書き出しオプションには以下が含まれます。</p><ul><li>Adobe Experience Platform データランディングゾーン</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>詳しくは、[Customer Journey Analytics レポートをクラウドに書き出し](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=ja)を参照してください。 | 2023年10月4日（PT） | 2023年10月19日（PT） |
| **レポートアクティビティマネージャー** | レポートアクティビティマネージャーでは、組織内の各接続のレポート処理能力を確認できます。レポートの使用状況を詳細に把握し、ピーク時のレポート作成時の処理能力に関する問題を簡単に診断および修正できます。レポートアクティビティマネージャーの主な機能は次のとおりです。<ul><li>現在のレポートリクエストをキャンセルします（ガイド付き分析からのリクエストやテーブル全体の書き出しを含む）。</li><li>定義した期間に対する後続のリクエストの制限</li></ul>管理者は、現在のリクエストのキャンセルに加えて、定義した期間だけリクエストを制限できるようになりました。管理者は、リクエスト、プロジェクトまたはユーザーごとにリクエストを制限できます。[詳細情報](/help/reporting-activity-manager/reporting-activity-overview.md) | 2023年10月17日（PT） | 2023年10月24日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-327661; AN-329282; AN-329383; AN-329808; AN-331030; AN-331087; AN-331105

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | 該当なし | 該当なし |

{style="table-layout:auto"}

## 関連リソース

* [2023年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
