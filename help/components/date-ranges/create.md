---
title: 日付範囲の作成
description: レポートで使用する日付範囲を作成します。
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 10%

---


# 日付範囲の作成

>[!NOTE]
>
>Customer Journey Analytics 内の Analysis Workspace に関するドキュメントを表示しています。この機能セットは、[従来の Adobe Analytics の Analysis Workspace](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) とは少し異なります。[詳細情報...](/help/getting-started/cja-aa.md)

次の2つの方法のいずれかを使用して、カスタムの日付範囲を作成できます。

* ワークスペースプロジェクト内で直接`+`&#39;左側の日付範囲コンポーネントのリストの横のボタン
* 日付範囲マネージャ内

日付範囲マネージャーで日付範囲を作成するには：

1. ログイン先 [analytics.adobe.com](https://analytics.adobe.com) Adobe ID資格情報を使用している。
1. 移動先 [!UICONTROL コンポーネント] > [!UICONTROL 日付範囲].
1. 「 [!UICONTROL 追加] ボタンをクリックして、日付範囲を作成するモーダルウィンドウを開きます。

## 日付範囲モーダルウィンドウを作成する

モーダルウィンドウには、次の4つのフィールドを編集できます。

* **日付範囲**:このコンポーネントに指定する日付範囲。
* **タイトル**:このコンポーネントに付ける名前。 タイトルは、ワークスペースプロジェクトで使用されます。
* **説明**:このコンポーネントに必要な説明。 説明は、 ![i](../assets/i.png) アイコン。
* **タグ**:タグを使用して日付範囲を整理します。 日付範囲は複数のタグに属することができます。

## 日付範囲の選択

モーダルウィンドウで日付範囲をクリックすると、次のいくつかのオプションが表示されます。

* **カレンダー**:開始と終了日を選択します。
* **相対日付を使用**:日付範囲を経時的に変更する場合は、このチェックボックスをオンにします。 日付範囲を静的なままにする場合は、このチェックボックスをオンにしないでください。
* **プリセットを選択**:このドロップダウンは、Adobeオファーがデフォルトで指定する範囲に基づいてカスタムの日付範囲を設定する場合に使用します。 プリセットを選択すると、必要に応じて日付範囲をさらにカスタマイズできます。 Adobeオファーのプリセットには影響しません。

## 周期的な日付範囲

日付範囲を周期的にする場合は、ロールするタイミングをカスタマイズできます。 開始日と終了日を互いに独立してロールするタイミングを制御できます。

* **日付開始**:期間の初め、開始の終わり、または固定日を使用するかを選択します。
* **使用する期間**:日付範囲のロール頻度を選択します。 毎日、毎週、毎月、毎四半期、毎年ロールさせることができます。
* **オフセット**:日付範囲のオフセットを選択します。 日、週、月、四半期、年を追加または削除できます。

## 相対的な日付の例

一部のレポートでは、日付範囲が役立つ場合があります。

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

会計年度(例えば、12月の会計年度開始の場合)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
