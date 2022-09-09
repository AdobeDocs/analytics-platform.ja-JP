---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 41cca39d73773af09981bde10c93c767ebdb77d4
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 79%

---

# 最新のCustomer Journey Analytics(CJA) リリースノート（2022 年 9 月）

**最終更新日**:2022 年 9 月 10 日

>[!NOTE]
>
>このページに記載される内容は、リリース前の情報であり、変更される可能性があります。

## 関連リソース

* [以前の CJA リリースノート（2022 年）](/help/release-notes/2022.md)

* [年 Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)

* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)

* [Adobe Experience Cloud のリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)

## 主な特長

| 機能 | 説明 | [ターゲット日](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **メディア同時ビューアパネル** | ピーク同時実行が発生した場所、または下降が発生した場所を把握します。コンテンツの質と閲覧者のエンゲージメントに関する貴重なインサイトを取得でき、ボリュームやスケールのトラブルシューティングや計画に役立ちます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=ja) | 2022年8月9日（PT） |
| **メディア再生滞在時間パネル** | メディア再生滞在時間は、ビューアエンゲージメントに関する貴重なインサイトを提供し、メディア企業は日分割機能を備えた高度な滞在時間分析を通じて、分単位のユーザーエンゲージメントに関する、より深く、より詳細なインサイトを得ることができます。<p>特定の時点でのメディアストリームの視聴時間を確認できます。再生時間は、様々な粒度（新たな 5 分、15 分、30 分の時間粒度を含む）で分割できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=ja) | 2022年8月9日（PT） |
| **リアルタイム顧客プロファイルへのオーディエンス公開** | CJA で検出されたオーディエンスを Adobe Experience Platform／リアルタイム顧客プロファイルに公開して、顧客のターゲティングとパーソナライゼーションを行います。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=ja) | 2022年8月17日 |
| **データガバナンスラベルとポリシーに対する CJA のサポート** | CJA と Adobe Experience Platform のプライバシーラベルおよびポリシーの統合を自動化します。Platform で使用されるデータセットで作成されたデータラベルは、CJA データビューで表示され、機密性の高いフィールドから指標やディメンションを作成するユーザーを停止や警告します。また、データが CJA から書き出される場合（Workspace または Report Builder のレポート、書き出し、API などを介して）は、特定の方法で扱われるべき機密情報がレポートに含まれていることをユーザーに通知するために、警告またはラベルが追加されます。[詳細情報](/help/data-views/data-governance.md) | 2022年8月17日 |
| **Analytics ソースコネクタのクロス地域サポート** | 任意の地域（米国、英国またはシンガポール）からレポートスイートを取り込めるようになりました。ただし、これらのレポートスイートは、ソース接続が作成される Experience Platform サンドボックスインスタンスと同じ組織にマッピングする必要があります。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) | 2022年8月24日（PT） |
| **最初のセッションのレポート** | 特定のセッションがユーザーの初めてのセッションであったかどうかを確認します。 [詳細情報](/help/data-views/data-views-usecases.md) | 2022年8月24日（PT） |
| **CJA の実験パネル** | この新しい Workspace パネルを使用すると、CJA ユーザーは、オンライン、オフライン、Adobeソリューション、Adobe Journey Optimizer、BYO(bring-your-own) データなど、あらゆるソースから A/B 実験の上昇率と信頼性を評価できます。 [詳細情報](/help/analysis-workspace/c-panels/experimentation.md) | [限定リリース](/help/release-notes/releases.md) 2022 年 9 月 14 日より |
| **Workspace でのコンボグラフのビジュアライゼーション** | コンボグラフを使用すると、Workspace 内で指標をより簡単かつ直感的に比較できます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts.html?lang=en) | 2022 年 9 月 15 日 |

{style=&quot;table-layout:auto&quot;}

## 修正点

AN-298412

##  CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **IP からジオロケーションへのマッピングの改善** | 2022 年 9 月 10 日 | Adobeの IP 検索ベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードします。 Adobe Analyticsは、 **2022 年 10 月 6 日**. 新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースが採用されると、一部の IP からジオへのマッピングが変更／改善されます。<p> Analytics ソースコネクタを通じて提供される CJA データも、新しいマッピングを自動的に活用します。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
