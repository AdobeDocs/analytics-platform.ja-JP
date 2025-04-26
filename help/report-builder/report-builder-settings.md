---
title: Customer Journey AnalyticsでReport Builderを設定する方法
description: オフラインモード、言語、基準日、トラブルシューティングの設定方法について説明します。
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 29%

---

# Report Builder設定

「**設定**」ペインを使用して、UI で表示される言語やオフラインモードで動作するかどうかなど、アプリケーションレベルの設定を行います。設定は直ちに適用され、変更されるまで、今後のすべてのセッションに対して設定されます。

Report Builder 設定を変更するには

1. **設定** アイコンを選択します。

1. [ オフラインモードの無効化の有効化 ](#off-line-mode)、[ 言語の選択 ](#language)、または [ トラブルシューティングの有効化 ](#troubleshooting) を変更します。

1. 「**[!UICONTROL 適用]**」を選択します。

   ![ 「キャンセルして適用」ボタンを表示するReport Builderの日付範囲ペイン。](./assets/report-builder-settings.png){zoomable="yes"}

## オフラインモード

オフラインモードでデータブロックを作成および編集する場合、データは取得されません。 代わりに、リクエストの実行を待たずにすばやく作業できるように、シミュレーションデータを使用します。 オンラインに戻ったら、「![ 更新 ](/help/assets/icons/Refresh.svg) **[!UICONTROL データブロックを更新]**」または「![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL すべてのデータブロックを更新]**」を選択して、データブロックを実際のデータで更新します。

オフラインモードを有効にするには

1. ![ 設定 ](/help/assets/icons/Setting.svg) を選択します。

1. **[!UICONTROL オフラインモードを有効にする]** をオンにします。

1. 「**[!UICONTROL 指標データを表示]** フィールドに正の整数を入力します。

1. 「**[!UICONTROL 適用]**」を選択します。


## 言語

Report Builder インターフェイスの言語を選択できます。 サポートされているCustomer Journey Analytics言語はすべて利用できます。

Report Builder インターフェイスで使用する言語を選択するには：

1. **[!UICONTROL 言語]** ドロップダウンメニューから言語を選択します。

1. 「**適用**」を選択します。

## トラブルシューティング

**[!UICONTROL トラブルシューティングログ]** 設定は、すべてのクライアント/サーバーデータをローカルファイルに記録します。 このオプションを使用して、サポートチケットの解決に役立てます。

トラブルシューティングログを有効にするには、「**[!UICONTROL Report Builder リクエストをローカルファイルに記録]**」をオンにします。
