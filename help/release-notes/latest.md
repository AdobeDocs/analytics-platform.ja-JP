---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f961bf0a615199de931a98f14d8b640890df7a2b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
