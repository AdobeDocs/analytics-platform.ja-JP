---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 524aed20a62b8d8648230be81c63f9c58c84ae87
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 32%

---

# 最新のCustomer Journey Analytics(CJA) リリースノート（2023 年 2 月）

**最終更新日**：2023年2月6日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 主な機能と更新

| 機能 | 説明 | [ロールアウトの開始](/help/release-notes/releases.md) | [一般公開](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **CJA オーディエンスの更新** | オーディエンスを作成した後、Adobeは新しい CJA オーディエンスごとにExperience Platformストリーミングセグメントを作成します。 ストリーミングセグメントは、組織がストリーミングセグメント化用に設定されている場合にのみ作成されます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created) | 該当なし | 2023 年 2 月 4 日 |
| **モバイルスコアカードで比較日付範囲を非表示にする** | モバイルスコアカードで、比較日付範囲を非表示にできるようになりました。 | 該当なし | 2023 年 2 月 9 日 |
| **Workspace でのカレンダーの更新** | <ul><li>パネルの日付を固定：日付範囲コンポーネントは、パネルカレンダーに対して相対的に設定できます。 [詳細情報](/help/components/date-ranges/calendar.md)</li><li>カレンダーのスタイル設定の更新：UI 全体のカレンダースタイルがアップグレードされ、より一貫性が高く使いやすいワークフローが提供されました。</li><li>カレンダー式の更新：相対日付を使用する場合、すべてのカレンダー式はパネルの日付範囲の開始を反映します。 [詳細情報](/help/components/date-ranges/calendar.md)</li></ul> | 該当なし | 2023 年 2 月 9 日 |
| **パネルの日付範囲の更新** | Workspace で、次の機能強化が追加されました。<ul><li>2 月のリリース以降、コンポーネントとデータのプレビューは、過去 90 日間ではなく、パネルの日付範囲に基づいておこなわれます。 </li><li>左側のパネルに表示されるすべてのコンポーネントは、パネルの日付範囲に基づいて使用できます。</li><li>セグメントおよび計算指標ビルダーのすべての日付プレビューは、パネルの日付範囲に基づきます（関連するパネルがないコンポーネントマネージャーからアクセスしない限り、過去 90 日間の日付が基になります）。</li><li>データプレビューでは、パネルの日付範囲に基づいて、データやコンポーネントが表示されます。</li></ul> | 該当なし | 2023 年 2 月 9 日 |
| **Adobe Analytics Source Connector ストリーミング用の行/列フィルタリング** | Adobe Experience Platformの Analytics Source コネクタで、 [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja).<p>行レベルのフィルタリングを使用すると、プロファイルに関連するイベントの数を減らすことができます。 列レベルのフィルタリングを使用すると、イベント自体の充実性を低減でき、プロファイルの使用を最適化できます。 このフィルターは、リアルタイム顧客プロファイルに送信されたデータと [ID サービス](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja).<p>**フィルタリングは、Customer Journey Analyticsなどのアプリケーションで使用するためにデータレイクに送信されるデータには影響しません**. [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | 該当なし | 2023 年 2 月 23 日 |

{style=&quot;table-layout:auto&quot;}

## Customer Journey Analytics の修正点

AN-309106

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 現在の通知はありません | 該当なし | 該当なし |

{style=&quot;table-layout:auto&quot;}

## 関連リソース

* [2023年の以前の CJA リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
