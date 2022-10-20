---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a3d47318d74df161cf9054b849c9eb8ef09e60c4
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 90%

---

# Customer Journey Analytics（CJA）リリースノート（2022年10月）

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
| **実験パネル** | この新しい Workspace パネルを使用すると、CJA ユーザーは、オンライン、オフライン、アドビのソリューション、Adobe Journey Optimizer および BYO データに至るまで、あらゆるソースから A/B 実験の上昇率と信頼性を評価できます。[詳細情報](/help/analysis-workspace/c-panels/experimentation.md) | 2022年10月5日（PT） |
| **[!UICONTROL 主要指標の概要]ビジュアライゼーション** | [!UICONTROL 主要指標の概要]ビジュアライゼーションを使用すると、1 つの期間内で重要な指標のトレンドを確認できます。また、2 つの期間にわたる指標のパフォーマンスを比較することもできます。詳細情報 | 2022年10月5日（PT）から段階的にロールアウトを開始 |
| **CJA での日付フィールドのサポート** | CJA が日付および日時フィールドに関するレポートを作成できるようにします。[詳細情報](/help/data-views/data-views-usecases.md#date) | 2022年10月5日（PT） |
| **モバイルアプリ：カスタムの詳細ビュー** | カスタムの詳細ビューを使用すると、最も重要な情報に焦点を当てることで、オーディエンスと共有する情報に関してさらにターゲットを絞ることができます。各スコアカードタイルに関連付けられた詳細ビューのレイアウトを変更し、テキストを追加することで、エンドユーザーに対して表示されるデータの内容をより明確に説明できます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ja) | 2022年10月5日（PT） |
| **複数値の変数で大文字と小文字を区別しない** | 大文字と小文字を区別しない複数値の変数の場合、 `mvvar1` - `mvvar3` が自動的に小文字に変換されなくなりました。 代わりに、Analytics Source Connector を通じてAdobe Experience Platformおよび CJA に渡されたデータは、ページから渡された元のケースを反映します。 | 2022年10月24日（PT） |

{style=&quot;table-layout:auto&quot;}

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **デフォルトのランディングページ** | 2023年9月29日（PT） | 今年初めに導入された[新規ランディングページ](/help/getting-started/landing.md)は、**2023年1月**&#x200B;にすべてのユーザーのデフォルトのエクスペリエンスとなる予定です。現在のページは廃止される予定で、すべてのユーザーは新しいエクスペリエンスを利用する必要があります。 |
| **IP からジオロケーションへのマッピングの改善** | 2022年9月29日（PT） | アドビの IP 検索ベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードします。 Adobe Analytics では、この新しいデータセットの導入を **2023年1月**&#x200B;まで延期しました。新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p> [!UICONTROL Analytics ソースコネクタ]を通じて提供される CJA データも、新しいマッピングを自動的に活用します。 |
| **[!UICONTROL 異常値検出]の自動実行条件** | 2022年9月29日（PT） | 現在、[!UICONTROL 異常値検出]は、時系列フリーフォームテーブルのすべての列で自動実行されます。分析のデータ確保やプロジェクトの読み込みの高速化を目的に、アドビでは[!UICONTROL 異常値検出]の自動実行方法を変更します。**2022年10月26日（PT）**&#x200B;より、異常値検出は、テーブルの最初の指標列でのみ自動実行されます。必要に応じて、他の列で[!UICONTROL 異常値検出]を実行するように列設定を設定できます。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
