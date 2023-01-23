---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a6ce6409eb7a4d853d5390cd62f4a9506ee6282a
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 40%

---

# 最新のCustomer Journey Analytics(CJA) リリースノート（2023 年 1 月）

**最終更新日**:2023 年 1 月 24 日

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 主な機能と更新

| 機能 | 説明 | [ロールアウトの開始](/help/release-notes/releases.md) | [一般公開](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **CJA オーディエンスの更新** | オーディエンスを作成した後、 [Adobeは、新しい CJA オーディエンスごとにExperience Platformストリーミングセグメントを作成します](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created). | 該当なし | 2023 年 1 月 24 日 |
| **Workspace のフォルダー** | フォルダーを使用すると、プロジェクトを整理および分類して、取得やアクセスを改善できます。 さらに、共有 **[!UICONTROL 会社]** フォルダーを使用すると、管理者は、すべての Workspace ユーザーと簡単にコンテンツを作成および共有できます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html?lang=ja) | 該当なし | 2023年1月11日（PT） |
| **デフォルトのランディングページ** | この [新規ランディングページ](/help/getting-started/landing.md) 2022 年以前に導入されたは、 **2023 年 1 月 12 日**. 従来のランディングページは廃止され、新しいエクスペリエンスを使用するには全員が必要になります。 | 該当なし | 2023年1月11日（PT） |
| **プロジェクトマネージャーページは非推奨** | 新しいランディングページのリリースに伴い、 **[!UICONTROL プロジェクトマネージャー]** 次に示すように **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL コンポーネント]**. 新しいランディングページには、古いプロジェクトマネージャーページのすべての機能が含まれています。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | 該当なし | 2023年1月11日（PT） |
| **ワークブックのスケジュールReport Builder** | Customer Journey Analyticsでは、一定の間隔でワークブックを送信するスケジュールを作成できます。 受信者は、ワークブックの最新の更新を定期的に受け取ることができるようになりました。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | 該当なし | 2023年1月11日（PT） |
| **新しいプロジェクトを自動保存** | Analysis Workspaceは新しく作成したプロジェクトを自動保存するようになりました。 何らかの理由で、手動で保存する前に新しく作成したプロジェクトへのアクセス権が予期せず失われた場合は、プロジェクトの回復バージョンが使用できるようになりました。 以前は、プロジェクトは手動で保存した後にのみ自動保存されていました。 [詳細情報](/help/analysis-workspace/build-workspace-project/save-projects.md) | 該当なし | 2023年1月11日（PT） |
| **ユーザー環境設定の強化** | ユーザーレベルで追加の環境設定を設定できるようになりました ( [!UICONTROL コンポーネント] > [!UICONTROL 環境設定]) をクリックします。 ユーザー環境設定を設定すると、選択はプロジェクト、テーブルおよびビジュアライゼーション全体にわたって行われます。 環境設定ページには、次の新しいタブが含まれ、それぞれに多数の新しい設定オプションが含まれています。<ul><li>フリーフォームテーブル</li><li>ビジュアライゼーション >/li></ul>。さらに、 **[!UICONTROL 一般]** および **[!UICONTROL プロジェクト]** タブ<p>以前は、これらの環境設定の多くは、個々のプロジェクト、テーブルおよびビジュアライゼーションに対してのみ設定できました。 [詳細情報](/help/analysis-workspace/user-preferences.md) | 該当なし | 2023年1月11日（PT） |

{style=&quot;table-layout:auto&quot;}

## 修正点

AN-287349;AN-301684;AN-305491;AN-305769;AN-307912

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **IP からジオロケーションへのマッピングの改善** | 2022年9月29日（PT） | アドビの IP 検索ベンダーである Digital Element は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）へのアップグレードを行います。Adobe Analyticsは、この新しいデータセットの次への導入を延期しました： **2023 年 1 月 12 日**. 新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p> [!UICONTROL Analytics ソースコネクタ]を通じて提供される CJA データも、新しいマッピングを自動的に活用します。 |

{style=&quot;table-layout:auto&quot;}


## 関連リソース

* [2022年の以前の CJA リリースノート](/help/release-notes/2022.md)

* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)

* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)

* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)

* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
