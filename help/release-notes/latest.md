---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 45e4a60b6bbf38e33f307dbbbf68ab3124dd6a33
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 45%

---

# Customer Journey Analytics(CJA) リリースノート（2022 年 10 月）

**最終更新日**:2022 年 10 月 14 日

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 関連リソース

* [2022年の以前の CJA リリースノート](/help/release-notes/2022.md)

* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)

* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)

* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)

## 主な機能と更新

| 機能 | 説明 | [ターゲット日](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **実験パネル** | この新しい Workspace パネルを使用すると、CJA ユーザーは、オンライン、オフライン、アドビのソリューション、Adobe Journey Optimizer およびBYO データに至るまで、あらゆるソースから A／B 実験の上昇率と信頼性を評価できます。[詳細情報](/help/analysis-workspace/c-panels/experimentation.md) | 2022 年 10 月 6 日 |
| **[!UICONTROL 主要指標の概要] 視覚化** | この [!UICONTROL 主要指標の概要] ビジュアライゼーションを使用すると、1 つの期間内で重要な指標がどのようにトレンドを示しているかを確認できます。 また、2 つの期間にわたる指標のパフォーマンスを比較することもできます。詳細情報 | 2022 年 10 月 6 日からの段階的な展開 |
| **CJA での日付フィールドのサポート** | CJA が日付および日時フィールドに関するレポートを作成できるようにします。[詳細情報](/help/data-views/data-views-usecases.md#date) | 2022 年 10 月 6 日 |
| **モバイルアプリ：カスタム詳細ビュー** | カスタムの詳細ビューを使用すると、最も重要な情報に焦点を当てることで、オーディエンスと共有する情報に関してさらにターゲットを絞ることができます。 各スコアカードタイルに関連付けられた詳細ビューのレイアウトを変更し、テキストを追加して、エンドユーザーがデータに表示する内容をより深く説明することができます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ja) | 2022 年 10 月 6 日 |
| **複数値の変数で大文字と小文字を区別しない** | 複数値の変数で大文字と小文字を区別しない場合、mvvar1 ～ mvvar3 に格納された値が自動的に小文字に変換されなくなります。 代わりに、Analytics Source Connector を通じてAdobe Experience Platformおよび CJA に渡されたデータは、ページから渡された元のケースを反映します。 | 2022 年 10 月 24 日 |

{style=&quot;table-layout:auto&quot;}

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **デフォルトのランディングページ** | 2023 年 9 月 30 日 | この [新規ランディングページ](/help/getting-started/landing.md) 今年初めに導入されたは、 **2023 年 1 月**. 現在のページは非推奨となり、新しいエクスペリエンスを使用するには全員が必要になります。 |
| **IP からジオロケーションへのマッピングの改善** | 2022年9月29日（PT） | Adobeの IP 検索ベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードします。 Adobe Analyticsは、この新しいデータセットの次への導入を延期しました： **2023 年 1 月**. 新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p> CJA データは、 [!UICONTROL Analytics ソースコネクタ] また、は新しいマッピングを自動的に利用します。 |
| **[!UICONTROL 異常値検出] 自動実行条件** | 2022年9月29日（PT） | 今日、 [!UICONTROL 異常値検出] 時系列フリーフォームテーブルのすべての列で自動実行されます。 データを分析やプロジェクトの読み込みを迅速に行えるように、Adobeは、 [!UICONTROL 異常値検出] 自動実行 開始中 **2022 年 10 月 27 日**&#x200B;の場合、異常値検出は、テーブルの最初の指標列でのみ自動実行されます。 実行する列設定を構成できます [!UICONTROL 異常値検出] 必要に応じて、他の列に配置します。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
