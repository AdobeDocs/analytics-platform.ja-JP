---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 70ca04d647645d6ba69f07110f0deced03bd0a77
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# 最新のCustomer Journey Analytics(CJA) リリースノート（2022 年 4 月）

>[!NOTE]
>
>このページには、変更される可能性のあるリリース前の情報が含まれています。

**最終更新日**:2022 年 4 月 20 日

## 主な特長

| 機能 | 説明 | [ターゲット日](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Dimensionの部分文字列 | ディメンション項目として使用する文字列の目的の部分を抽出する複数のメソッドを提供します。 この機能を使用すると、文字列に区切り文字付きの値が含まれる場合に、文字列ディメンションを配列として扱うこともできます。 [詳細情報](../data-views/component-settings/substring.md) | 2022 年 4 月 21 日 |
| Analytics ソースコネクタ用のデータ準備 | この [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) が [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) Adobe Experience Platformが提供する機能 Adobe Real-time Customer Data Platform(RTCDP)、CJA、Adobe Journey Optimizer(AJO) のお客様は、追加のフィールドグループを使用して Analytics フィールドグループを拡張できるようになりました。 また、100 以上の Data Prep 演算子を利用して、Adobe Experience Platform(AEP) への取り込み中に Analytics データを強化することもできます。 RTCDP のお客様は、プロファイルに対して複数のデータ準備対応レポートスイートを有効にできるようになりました。<p>Analytics ソースコネクタを使用して複数のレポートスイートを取り込む CJA のお客様は、レポートスイート間の列の違いを競合解除する手段を持つようになりました。 例えば、「検索語句」が `eVar1` 1 つのレポートスイートと `eVar2` 別のレポートスイートでは、Data Prep を使用して、2 つの eVar の値を結合する新しい列で Analytics フィールドグループを拡張できます。 | 2022 年 4 月 28 日 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
