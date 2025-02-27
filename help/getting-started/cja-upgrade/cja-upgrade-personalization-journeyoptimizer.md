---
title: Adobe Journey Optimizerで使用するパーソナライゼーションオブジェクトの使用
description: Adobe Journey Optimizerで使用するパーソナライゼーションオブジェクトの使用方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Adobe Journey Optimizerで使用するパーソナライゼーションオブジェクトの使用 {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="Adobe Journey Optimizerのパーソナライゼーションオブジェクトの使用"
>abstract="Adobe Journey Optimizerで使用するには、実装でパーソナライゼーションオブジェクトを使用します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

パーソナライゼーションオブジェクトの結果がデータセットに返されます。 実験の結果。 お客様が Target で AA を使用した場合、最終的には、CJA に移行する際やAdobe Targetで CJA を使用する際とは全く異なる領域で使用することになります。

Target は、A/B テストや実験を設定する古い方法でした。 その後、Target でそれらのテストの結果を確認すると、レポート用に AA に変換されていました。 これで、Target を使用する場合に、Target でデータを必要とするのではなく、Adobe Target アクティビティのレポートソースとして CJA を選択できます。 したがって、顧客が AA でこれをおこない、CJA に移行したい場合、

AJOを持ち、AJOでオファーを使用している顧客は、オファーを設定できるので、Platform でもデータセットを作成できます。ただし、これはアップグレードとは正確には関係ありません。



回答が必要な質問：

1. パーソナライゼーション条件を決定する方法（ユーザー A は赤、ユーザー B は青）

1. 赤/青のオブジェクトを決定するために、サイトには何を実装しますか？


2 つの方法で実現できます。

手動によるコンテンツのレンダリングまたは自動コンテンツのレンダリング


## Web SDKの手動実装


## Mobile SDKの実装





## タグ

