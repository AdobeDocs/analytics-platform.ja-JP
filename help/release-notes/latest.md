---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 11171eb6e079adbf41e0abc798a54a5749492eac
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 45%

---

# 最新のCustomer Journey Analytics(CJA) リリースノート（2022 年 7 月）

**最終更新日**:2022 年 7 月 20 日

>[!NOTE]
>
>このページに記載される内容は、リリース前の情報であり、変更される可能性があります。

## 主な特長

| 機能 | 説明 | [ターゲット日](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| ルックアップキーおよびルックアップ値としての数値フィールドの使用のサポート | 製品 SKU の COGS やマージンなどの数値フィールドで文字列値を分類したい場合に便利です。ルックアップからの指標を許可することで、これらのデータポイントをレポートに取り込むことができます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#numeric) | 2022年7月20日（PT） |
| 最初と繰り返しセッションのレポート作成の比較 | 特定のセッションがユーザーの初めてのセッションかどうかを検出できるようになりました。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 2022 年 8 月 18 日 |

## 修正点

AN-288455、AN-288828、AN-289323

## CJA 管理者向けの重要な注意事項

| 通知 | 追加済みまたは更新済み | 説明 |
| --- | --- | --- |
| IP とジオロケーションのマッピングの改善 | 2022 年 7 月 12 日 | Adobeの IP 検索 (Digital Element) ベンダーは、IP とジオロケーションのマッピング用に新しく改善されたデータセット (NetAcuity Pulse) にアップグレードします。 Adobe Analyticsでは、2022 年 10 月に、この新しいデータセットを採用する予定です。 新しいデータベースは、以前のバージョンよりも正確になります。 新しいデータベースを採用する際に、一部の IP と地域とのマッピングは変更/改善されます。<p> Analytics ソースコネクタを通じて提供される CJA データも、新しいマッピングを自動的に利用します。 |

>[!MORELIKETHIS]
>[Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
