---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b73404d9594b0915cea64f4016c9c7b36c3aaf01
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 80%

---

# 最新の Customer Journey Analytics（CJA）リリースノート（2023年2月）

**最終更新日**：2023年2月23日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 主な機能と更新

| 機能 | 説明 | [ロールアウトの開始](/help/release-notes/releases.md) | [一般公開](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **CJA オーディエンスの更新** | オーディエンスを作成すると、新しい CJA オーディエンスごとに Experience Platform ストリーミングセグメントが作成されます。ストリーミングセグメントは、組織がストリーミングセグメント化用に設定されている場合にのみ作成されます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=ja#after-audience-created) | 該当なし | 2023年2月3日（PT） |
| **モバイルスコアカードでの比較日付範囲の非表示** | モバイルスコアカードで、比較日付範囲を非表示にできるようになりました。 | 該当なし | 2023年2月8日（PT） |
| **ワークスペースでのカレンダーの更新** | <ul><li>パネルの日付の固定：パネルカレンダーを基準とする相対的な日付範囲コンポーネントにすることができます。[詳細情報](/help/components/date-ranges/calendar.md)</li><li>カレンダースタイルの更新：UI 全体を通してカレンダースタイルがアップグレードされて、より一貫性のある使いやすいワークフローが提供されるようになりました。</li><li>カレンダー式の更新：相対的な日付を使用する場合は、すべてのカレンダー式にパネルの日付範囲の開始日が反映されます。[詳細情報](/help/components/date-ranges/calendar.md)</li></ul> | 該当なし | 2023年2月8日（PT） |
| **パネルの日付範囲の更新** | Workspace で、次の機能強化が追加されました。<ul><li>2 月のリリース以降、コンポーネントとデータのプレビューは、過去 90 日間ではなく、パネルの日付範囲に基づいておこなわれます。 </li><li>表示されるすべてのディメンション項目は、パネルの日付範囲に基づいて使用できます。</li><li>セグメントおよび計算指標ビルダーのすべての日付プレビューは、パネルの日付範囲に基づきます（関連するパネルがないコンポーネントマネージャーからアクセスしない限り、過去 90 日間の日付が基になります）。</li><li>データプレビューでは、パネルの日付範囲に基づいて、データやコンポーネントが表示されます。</li></ul> | 該当なし | 2023年2月8日（PT） |
| **Adobe Analytics ソースコネクタストリーミングの行／列フィルタリング** | Adobe Experience Platform の Analytics ソースコネクタを使用すると、[リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)におけるプロファイルへの入力に使用される Analytics データをフィルタリングできるようになりました。<p>行レベルのフィルタリングは、プロファイルに関連付けられたイベントの数を減らすのに役立ちます。列レベルのフィルタリングは、イベント自体の豊富さを軽減するのに役立つので、プロファイル使用権限の行使を最適化できます。このフィルタリングは、リアルタイム顧客プロファイルと [ID サービス](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja)に送信されるデータにのみ適用されます。<p>**フィルタリングは、Customer Journey Analytics などのアプリケーションで使用するためにデータレイクに送信されるデータには影響しません**。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja#filtering-for-profile) | 該当なし | 2023 年 3 月 30 日に再スケジュールされました |

{style=&quot;table-layout:auto&quot;}

## Customer Journey Analytics の修正点

AN-309106

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 最新の注意事項はありません | 該当なし | 該当なし |

{style=&quot;table-layout:auto&quot;}

## 関連リソース

* [2023年の以前の CJA リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
