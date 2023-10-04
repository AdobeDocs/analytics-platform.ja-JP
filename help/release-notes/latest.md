---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e1254a5ecff0f638cbef1051564c1ce856f715bd
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 51%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2023 年 10 月）

**最終更新日**：2023年10月4日（PT）

これらのリリースノートでは、2023 年 10 月 4 日から 2023 年 10 月 24 日までのリリース期間を扱っています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **完全なテーブルをクラウドにエクスポート** | Customer Journey Analyticsの完全なテーブルの書き出しを使用すると、数百万行の Workspace 行をクラウドの宛先に書き出すことができます。 フルテーブルの書き出しでは、連結されたテーブルで、最大 5 つの分類、5 つの指標、フィルター、計算指標をサポートし、Workspace 内で設計されたデータテーブルを 1 回限りまたは予定どおりに配信できます。 Adobe AnalyticsでのData Warehouseレポートの発展です。現在のData Warehouseでは、リクエストの多い新機能が多数追加されています。 クラウドの書き出しオプションは次のとおりです。<ul><li>Adobe Experience Platform Data Landing Zone</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>詳しくは、 [Customer Journey Analyticsレポートをクラウドにエクスポート](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). | 2023年10月4日（PT） | 2023年10月19日 |
| **コンポーネントを管理する際に使用できる新しい列** | コンポーネントを管理する際に、[計算指標マネージャー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html)と[フィルターマネージャー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html)で次の新しい列を使用できるようになりました。<ul><li>使用場所</li><li>前回の使用</li></ul>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、削除または変更する必要があるかどうかを判断するのに役立ちます。この情報と共にデータ辞書を使用すると、組織内でのコンポーネントの使用方法を追跡し、より深く理解することができます。 | 2023年9月23日（PT） | 2023年10月4日（PT） |
| **Adobe Analyticsプロジェクトと含まれるコンポーネントをCustomer Journey Analyticsに移行** | これで、Adobe AnalyticsプロジェクトをCustomer Journey Analyticsに移行できます。 このプロセスにより、Adobe AnalyticsからCustomer Journey Analyticsへの移行が簡単になります。 プロジェクトをCustomer Journey Analyticsに移行すると、アセットはAdobe AnalyticsレポートスイートからCustomer Journey Analyticsデータビューにマッピングされます。 **Adobe AnalyticsインターフェイスからCustomer Journey Analyticsにプロジェクトを移行します。** [詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | 該当なし | 2023年10月4日（PT） |
| **Adobe Product Analytics：シリーズを表示/非表示** | グラフの凡例またはテーブルの行をクリックして、ビジュアライゼーションでの系列の表示を制御します。  詳細情報（近日公開） | 該当なし | 2023年10月4日（PT） |
| **Adobe Product Analytics内の注釈** | ガイド付き分析プロジェクトで、注釈の表示機能がサポートされるようになりました。 各ビュータイプについては、 [ガイド付き分析](/help/guided-analysis/overview.md) 注釈との相互作用に関する詳細 | 該当なし | 2023年10月4日（PT） |
| **レポートアクティビティマネージャー** | レポートアクティビティマネージャーでは、組織の各接続のレポート容量を確認できます。 このレポートは、レポートの消費状況を詳細に把握し、ピーク時のレポート作成時に容量の問題を簡単に診断して修正できるように管理者に提供します。 レポートアクティビティマネージャーの主な機能は次のとおりです。<ul><li>現在のレポートリクエストをキャンセルします（ガイド付き分析からのリクエストやテーブル全体のエクスポートを含む）。</li><li>定義した期間に対する後続のリクエストの制限</li></ul>管理者は、現在のリクエストのキャンセルに加えて、定義した期間だけリクエストを制限できるようになりました。 管理者は、リクエスト、プロジェクトまたはユーザーごとにリクエストを制限できます。  詳細情報（近日公開） | 2023年10月17日（PT） | 2023年10月23日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-325940、AN-326468、AN-328301、AN-328640、AN-329370

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | 該当なし | 該当なし |

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
