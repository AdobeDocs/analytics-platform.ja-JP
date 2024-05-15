---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cc74a8fdb3e44c5fa46e82a5111619970f090870
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 40%

---

# 最新のAdobe Customer Journey Analytics リリースノート（2024 年 5 月）

**最終更新日**：2024年5月15日（PT）

これらのリリースノートは、2024 年 5 月 15 日（PT）から 2024 年 6 月までのリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **BI 拡張機能** | BI 拡張機能を使用すると、Customer Journey Analyticsで定義したデータ・ビューへの SQL アクセスが可能になります。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024年5月15日（PT） |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをよりすばやく見つけることができます。</li></ul> [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/audiences/publish) |  | 2024年5月15日（PT） |
| **Customer Journey Analytics用 AI アシスタント** | Customer Journey AnalyticsUI で自然言語の質問をし、Customer Journey Analyticsドキュメントに基づいて回答を得ることができます。 （ドキュメントへのリンクを添付） | | 2024年5月30日（PT） |
| **ストリーミングメディア：Web SDK を使用したAdobe Experience Platform Edge Networkへの web データの送信** | Adobe Experience Platform Web SDK を使用して、Streaming Media web データをAdobe Experience Platform Edge Networkに送信できるようになりました。これにより、よりパーソナライズされたキャンペーンを作成し、よりパーソナライズされたコンテンツを提供して、レポートするトラッキングデータを増やすことができます。<p>この機能強化により、Customer Journey Analytics、RT-CDP、AJO、イベント転送など、すべての Platform ソリューションにわたって Web 実装の統合的な収集手段が提供されます。 以前は、Streaming Media web データをEdge Networkに送信する唯一の方法は、Media Edge API を使用することでした。 [詳細情報](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | | 2024年5月31日（PT） |
| **派生フィールド – 数学関数** | では、データビュー内で単純な数学演算子を使用して、ユーザーに関する質問に回答できます。 例えば、製品、保証、配送料を組み合わせることができます。 （ドキュメントへのリンクを添付） | | 2024年6月5日 |
| **Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関する新しいドキュメント** | Adobe AnalyticsからCustomer Journey Analyticsにアップグレードする場合、組織の現在のAdobe Analyticsの実装と長期目標に基づいて、複数のアップグレードオプションや多くの考慮事項に留意する必要があります。 次の内容をより深く理解するのに役立つ新しいドキュメントリソースが利用できるようになりました。<ul><li>存在するさまざまなアップグレードパス</li><li>組織の現在のAdobe Analytics実装に基づいて使用可能なアップグレードパス</li><li>各アップグレードパスのメリットとデメリット</li><li>各アップグレードパスのステップバイステップのガイダンス</li><li>履歴データの処理に関する考慮事項</li></ul>[Customer Journey Analyticsへのアップグレードの概要](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 今すぐ利用可能 |
| **に関する新しいドキュメント [データ書き出しの使用例](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | この新しい節では、次のようなデータ書き出しの使用例について説明します<ul><li>データバックアップ</li><li>データの検証</li><li>Data Lake、Data Warehouseまたは BI ツール</li><li>AI/ML に対する対応</li></ul> Experience PlatformとCustomer Journey Analyticsの機能を使用して実装する方法について説明します。 | | 今すぐ利用可能 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-346287; AN-346624; AN-347919

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

{style="table-layout:auto"}

## 関連リソース

* [2024年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2024.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
