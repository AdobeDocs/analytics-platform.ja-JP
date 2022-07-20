---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e1e147b63053f63c90d8e433d90e1bc5a4f1acd4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 50%

---

# 最新のCustomer Journey Analytics(CJA) リリースノート（2022 年 7 月）

**最終更新日**:2022 年 7 月 20 日

## 主な特長

| 機能 | 説明 | [ターゲット日](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| ルックアップキーおよびルックアップ値としての数値フィールドの使用のサポート | 製品 SKU の COGS やマージンなどの数値フィールドで文字列値を分類したい場合に便利です。ルックアップからの指標を許可することで、これらのデータポイントをレポートに取り込むことができます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#numeric) | 2022年7月20日（PT） |
| メディア同時ビューアパネル | ピーク同時実行が発生した場所、または下降が発生した場所を理解します。 コンテンツの質と閲覧者のエンゲージメントに関する貴重なインサイトを取得でき、ボリュームやスケールのトラブルシューティングや計画に役立ちます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022 年 7 月 31 日 |
| メディア再生滞在時間パネル | メディア再生滞在時間は、ビューアエンゲージメントに関する貴重なインサイトを提供し、日分割機能を備えた高度な滞在時間分析を通じて、分単位のユーザーエンゲージメントで、より深くより詳細なインサイトを導き出すことができます。 特定の時点でのメディアストリームの視聴時間を確認できます。再生時間は、様々な粒度（新たな 5 分、15 分、30 分の時間粒度を含む）で分割できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022 年 7 月 31 日 |
| 最初と繰り返しセッションのレポート作成の比較 | 特定のセッションがユーザーの初めてのセッションかどうかを検出できるようになりました。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 2022 年 8 月 18 日 |

{style=&quot;table-layout:auto&quot;}

## 修正点

AN-288455、AN-288828、AN-289323

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **IP とジオロケーションのマッピングの改善** | 2022 年 7 月 12 日 | Adobeの IP 検索 (Digital Element) ベンダーは、IP とジオロケーションのマッピング用に新しく改善されたデータセット (NetAcuity Pulse) にアップグレードします。 Adobe Analyticsは、 **2022 年 10 月**、期間。 新しいデータベースは、以前のバージョンよりも正確になります。 新しいデータベースを採用する際に、一部の IP と地域とのマッピングは変更/改善されます。<p> Analytics ソースコネクタを通じて提供される CJA データも、新しいマッピングを自動的に利用します。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
