---
description: 詳細
title: 指標タイプとアトリビューション
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 36%

---

# 指標タイプとアトリビューション

指標の横にある歯車アイコンをクリックすると、指標タイプとアトリビューションモデルを指定できます。

## 指標タイプ

計算指標を作成する際に指標タイプを指定するには：

1. タイプを選択する指標の横にある歯車アイコンを選択します。

   ![指標タイプが標準と等しいポップアップを示す歯車アイコン。](assets/cm_type_alloc.png)

1. 次のオプションから選択します。

   | 指標タイプ | 定義 |
   |---|---|
   | 標準 | これらの指標は、標準の [!DNL Analytics] レポートで使用される指標と同じです。1 つの標準指標で構成される数式は、その標準指標に対応する計算指標以外の指標と同じデータを表示します。標準指標は、個々の行項目に固有の計算指標を作成する場合に役立ちます。例： [購入回数] / [セッション] は、特定の行項目の注文を受け取り、その特定の行項目のセッション数で割ります。 |
   | 総計 | 各行項目のレポート期間に、総計を使用します。 1 つの総計指標で構成される数式の場合、各行項目に同じ総計数が表示されます。 総計指標は、合計データと比較する計算指標を作成する場合に役立ちます。 例： [購入回数] / [合計セッション数] は、特定の行項目に対するセッションだけでなく、チャネル上のすべてのセッションに対する注文の割合を示します。 |

## アトリビューション

Customer Journey Analyticsのアトリビューションについて詳しくは、 [アトリビューションコンポーネントの設定](/help/data-views/component-settings/attribution.md).
