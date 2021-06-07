---
title: 日付範囲の作成
description: レポートで使用する日付範囲を作成します。
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 8%

---

# 日付範囲の作成

>[!NOTE]
>
>Customer Journey Analytics 内の Analysis Workspace に関するドキュメントを表示しています。この機能セットは、[従来の Adobe Analytics の Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) とは少し異なります。[詳細情報...](/help/getting-started/cja-aa.md)

次の2つの方法のいずれかを使用して、カスタム日付範囲を作成できます。

* 左側の日付範囲コンポーネントのリストの横にある「`+`」ボタンをクリックして、Workspaceプロジェクトに直接移動します
* 日付範囲マネージャー内

日付範囲マネージャーで日付範囲を作成するには：

1. Adobe IDの資格情報を使用して[analytics.adobe.com](https://analytics.adobe.com)にログインします。
1. [!UICONTROL コンポーネント] > [!UICONTROL 日付範囲]に移動します。
1. 「[!UICONTROL 追加]」ボタンをクリックして、日付範囲を作成するモーダルウィンドウを開きます。

## 日付範囲モーダルウィンドウの作成

モーダルウィンドウには、次の4つのフィールドを編集できます。

* **日付範囲**:このコンポーネントに必要な日付範囲。
* **タイトル**:このコンポーネントに必要な名前。タイトルは、Workspaceプロジェクトで使用されます。
* **説明**:このコンポーネントに必要な説明。説明は、「![i](../assets/i.png)」アイコンをクリックすると表示されます。
* **タグ**:タグを使用して日付範囲を整理します。1つの日付範囲は複数のタグに属することができます。

## 日付範囲の選択

モーダルウィンドウで日付範囲をクリックする場合、次のいくつかのオプションがあります。

* **カレンダー**:開始日と終了日を選択します。
* **相対日付を使用する**:時間の経過に応じて日付範囲を変更する場合は、このチェックボックスをオンにします。日付範囲を静的なままにする場合は、このチェックボックスをオンにしないでください。
* **プリセットを選択**:デフォルトでAdobeが提供する範囲に基づいてカスタムの日付範囲を作成する場合は、このドロップダウンを使用します。プリセットを選択すると、必要に応じて日付範囲をさらにカスタマイズできます。 Adobeが提供するプリセットには影響しません。

## 周期的日付範囲

周期的な日付範囲が必要な場合は、周期的な日付範囲をカスタマイズできます。 開始日と終了日を互いに独立して並べるタイミングを制御できます。

* **日付が開始するタイミング**:日付が期間の初めから開始するか、期間の終わりまでに開始するか、または固定日を使用するかを選択します。
* **使用する期間**:日付範囲のロール頻度を選択します。毎日、毎週、毎月、毎四半期、毎年ロールさせることができます。
* **オフセット**:日付範囲のオフセットを選択します。日、週、月、四半期または年を追加または減算できます。

## 相対日付の例

一部の日付範囲は、特定のレポートで役立つ場合があります。

年累計：

```text
Start: Start of current year
End: End of current day
```

先週の木曜日から今週の木曜日まで：

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

会計年度（会計年度が12月に開始する場合など）

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
