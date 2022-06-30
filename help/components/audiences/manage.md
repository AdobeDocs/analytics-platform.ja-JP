---
title: Customer Journey Analytics で作成したオーディエンスの管理
description: Customer Journey Analytics でのオーディエンスの管理方法を学ぶ
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
source-git-commit: 86998458bd79f1fc17c17e58932b2b8434abf041
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 92%

---

# Customer Journey Analytics で作成したオーディエンスの管理

>[!NOTE]
>
>この機能は、現在、[限定的にテスト中](/help/release-notes/releases.md)です。

以前に作成したオーディエンスを管理することで、

* オーディエンスの自動更新／アップデートを&#x200B;**スケジュール設定またはスケジュール解除**&#x200B;できます。スケジュールの最大有効期限は 1 年です。
* 有効期限が近づいたら&#x200B;**オーディエンスの更新スケジュールを更新**&#x200B;します。有効期限が近づいたオーディエンスは、予定レポートの有効期限が近づいた場合と同様に扱われます。管理者は、スケジュールの期限が切れる 1 か月前にメールを受け取ります。
* 次を表示： **更新間隔** そして **オーディエンスが最後に更新された時刻**
* Customer Journey Analytics（CJA）からの&#x200B;**オーディエンスの作成に要した時間**、およびオーディエンスがアクティベーション目的でリアルタイム顧客プロファイルに表示されるまでに要した時間に関するインサイトを得ます。
* CJA のオーディエンスが **リアルタイム顧客プロファイル** または（理想的に）CJA で作成されたオーディエンスを使用する Experience Platform アプリケーションでアクティブに使用されているかを確認します。

## 管理 UI

![](assets/manage.png)

| UI 設定 | 定義 |
| --- | --- |
| フィルターを表示／非表示 | 左側のパネルで以下のフィルターの表示／非表示を切り替えることができます。 <ul><li>[!UICONTROL データビュー]</li><li>[!UICONTROL 所有者]</li><li>[!UICONTROL 更新頻度]</li><li>[!UICONTROL タグ]</li></ul> |
| [!UICONTROL タイトルと説明] | オーディエンスの作成時に付与されるタイトルと説明。 |
| [!UICONTROL データビュー] | このオーディエンスが作成されたデータビュー。 |
| [!UICONTROL オーディエンスサイズ] | このオーディエンスのユーザーの合計数。 |
| [!UICONTROL 所有者] | オーディエンスの所有者 - オーディエンスを作成したユーザー。 |
| [!UICONTROL 更新頻度] | オーディエンスの作成時に設定された更新間隔。 |
| [!UICONTROL タグ] | このオーディエンスに適用されるタグ。 |
| [!UICONTROL 公開ステータス] | 表示可能 [!UICONTROL 準備完了], [!UICONTROL 処理中]または [!UICONTROL エラー]. |
| [!UICONTROL  前回の更新] | オーディエンスが最後に更新された日時。 |
| [!UICONTROL 最終変更日] | オーディエンスが最後に編集または変更された日時。 |

{style=&quot;table-layout:auto&quot;}
