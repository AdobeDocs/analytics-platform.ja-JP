---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 785ea95049135adef888c20a6d9fef9f31439a7d
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 71%

---

# Customer Journey Analytics(CJA) リリースノート（2022 年 10 月）

**最終更新日**：2022年10月18日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 関連リソース

* [2022年の以前の CJA リリースノート](/help/release-notes/2022.md)

* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)

* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)

* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)

## 主な機能と更新

| 機能 | 説明 | [ターゲット日](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Workspace プロジェクトのフォルダ** | Workspace プロジェクトのフォルダーを使用すると、ユーザーは、検索やアクセスを改善するために、フォルダーを使用してプロジェクトを整理および分類できます。 共有会社フォルダーを使用すると、管理者は、コンテンツを簡単に作成してすべての Workspace ユーザーと共有できます [詳細情報](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md) | 2022年10月19日（PT） |
| **実験パネル** | この新しい Workspace パネルを使用すると、CJA ユーザーは、オンライン、オフライン、アドビのソリューション、Adobe Journey Optimizer およびBYO データに至るまで、あらゆるソースから A／B 実験の上昇率と信頼性を評価できます。[詳細情報](/help/analysis-workspace/c-panels/experimentation.md) | 2022年10月5日（PT） |
| **[!UICONTROL 主要指標の概要]のビジュアライゼーション** | [!UICONTROL 主要指標の概要]のビジュアライゼーションを使用すると、1 つの期間内で重要な指標のトレンドを確認できます。また、2 つの期間で指標のパフォーマンスを比較することもできます。詳細情報 | 2022年10月5日（PT）から段階的にロールアウトを開始 |
| **CJA での日付フィールドのサポート** | CJA が日付および日時フィールドに関するレポートを作成できるようにします。[詳細情報](/help/data-views/data-views-usecases.md#date) | 2022年10月5日（PT） |
| **モバイルアプリ：カスタム詳細ビュー** | カスタム詳細ビューを使用すると、最も重要な情報に注目させることで、オーディエンスと共有する情報に関してさらにターゲットを絞ることができます。 各スコアカードタイルに関連付けられている詳細ビューのレイアウトを変更したり、エンドユーザーに表示されるデータ内容をより適切に説明するテキストを追加したりできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ja) | 2022年10月5日（PT） |
| **複数値の変数で大文字と小文字を区別しない** | 大文字と小文字を区別しない複数値の変数の場合、 `mvvar1` - `mvvar3` が自動的に小文字に変換されなくなりました。 代わりに、Analytics Source Connector を通じてAdobe Experience Platformおよび CJA に渡されたデータは、ページから渡された元のケースを反映します。 | 2022年10月24日（PT） |

{style=&quot;table-layout:auto&quot;}

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **デフォルトのランディングページ** | 2023年9月29日（PT） | 今年初めに導入された[新しいランディング ページ](/help/getting-started/landing.md)は、**2023年1月**&#x200B;にすべてのユーザーにとってデフォルトエクスペリエンスになります。現在のページは非推奨（廃止予定）になり、すべてのユーザーが新しいエクスペリエンスを使用する必要があります。 |
| **IP からジオロケーションへのマッピングの改善** | 2022年9月29日（PT） | Adobeの IP 検索ベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードします。 Adobe Analyticsは、この新しいデータセットの次への導入を延期しました： **2023 年 1 月**. 新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p> CJA データは、 [!UICONTROL Analytics ソースコネクタ] また、は新しいマッピングを自動的に利用します。 |
| **[!UICONTROL 異常値検出]の自動実行条件** | 2022年9月29日（PT） | 現在、[!UICONTROL 異常値検出]は、時系列フリーフォームテーブルのすべての列に対して自動実行されます。 データを分析やプロジェクトの読み込みを迅速に行えるように、Adobeは、 [!UICONTROL 異常値検出] 自動実行 **2022年10月26（PT）**&#x200B;以降異常値検出は、テーブルの最初の指標列でのみ自動実行されます。 実行する列設定を構成できます [!UICONTROL 異常値検出] 必要に応じて、他の列に配置します。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
