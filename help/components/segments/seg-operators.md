---
title: 演算子
description: コンポーネントがセグメント内の値とどのように相互作用するかを決定します。
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 54%

---

# 演算子

セグメントビルダーでは、選択した演算子を使用して、コンポーネントの値を比較および制限できます。 演算子には、[[!UICONTROL 標準カウント]](#standard-operators)と[[!UICONTROL 個別カウント]](#distinct-count-operators)の 2 つのカテゴリがあります。

## 標準演算子

| 演算子 | 説明 |
| --- | --- |
| **[!UICONTROL 次に等しい]** | 数字または文字列の値に完全に一致する項目を返します。ワイルドカード文字を使用する場合は、一致演算子を使用します。 |
| **[!UICONTROL 等しくない]** | 入力された値の完全一致を含まない項目をすべて返します。ワイルドカード文字を使用する場合は、does not match 演算子を使用します。 |
| **[!UICONTROL 次のいずれかと等しい]** | 入力された部分文字列値の一致を含む、コンマで区切られた項目を返します。 |
| **[!UICONTROL が次の値を含む]** | 入力された値のサブ文字列と比較される項目を返します。例えば、ページ名ディメンションの値に `Search` が含まれる場合、この演算子は、名前に部分文字列 `Search` が含まれるすべてのページ（`Search Results`、`Search`、`Searching` など）に一致します。 この演算子では大文字と小文字が区別されます。 |
| **[!UICONTROL 次を含まない]** | 入力した値に一致する項目は、結果からすべて除外されます。 例えば、ページ名ディメンションの値に `Search` が含まれていない場合、名前に部分文字列 `Search` が含まれるページ（`Search Results`、`Search`、`Searching` など）は、この演算子によって除外されます。 |
| **[!UICONTROL 次のすべてを含む]** | （スペースで区切られた）すべての部分文字列が任意の順序で含まれる項目を返します。例えば、この演算子の値として `Search Results` を指定すると、`Search Results` と `Results of Search` は一致しますが、`Search` と `Results` はそれぞれ一致しません。 この演算子は、スペースで区切られた最大 100 個の単語をサポートします。 |
| **[!UICONTROL 次のすべてを含まない]** | 入力したすべての値に一致する項目は、結果からすべて除外されます。 例：この演算子の値として `Search Results` を指定すると、`Search Results` および `Results of Search` は除外されますが、`Search` または `Results` は除外されません。 この演算子は、スペースで区切られた最大 100 個の単語をサポートします。 |
| **[!UICONTROL 次のいずれかを含む]** | 指定されたサブ文字列のいずれかを含む項目を返します。例えば、この演算子の値として `Search Results` を指定すると、`Search Results`、`Results of Search`、`Search` および `Results` と一致します。 この演算子は、スペースで区切られた最大 100 個の単語をサポートします。 |
| **[!UICONTROL 次のいずれかを含まない]** | 任意の部分文字列に一致する項目は、すべて結果から除外されます。 例：この演算子の値として `Search Results` を指定すると、`Search Results`、`Results of Search`、`Search` および `Results` は除外されます。 この演算子は、スペースで区切られた最大 100 個の単語をサポートします。 |
| **[!UICONTROL 次の語句で始まる]** | 指定された値の文字または文字列で始まる項目を返します。 |
| **[!UICONTROL 次の語句で始まらない]** | 指定された値の文字または文字列で始まらない項目をすべて返します。 |
| **[!UICONTROL 次の語句で終わる]** | 指定された値の文字または文字列で終わる項目を返します。 |
| **[!UICONTROL 次の語句で終わらない]** | 指定された値の文字または文字列で終わらない項目をすべて返します。 |
| **[!UICONTROL 一致する]** | 指定された数値または文字列値に基づいて項目に完全に一致する項目を返します。 アスタリスク（`*`）を使用したワイルドカードをサポートします。このパラメーターでは大文字と小文字が区別されます。次に例を示します。<ul><li>`a*e` は `ae`、`abcde`、`adobe` および `a whole sentence` と一致します。</li><li>`adob*` は `adobe`、`adobe analytics` および `adobo recipe` と一致します</li><li>`*dobe` は `dobe`、`adobe` および `cute little dobe` と一致します。</li></ul> |
| **[!UICONTROL 一致しない]** | 文字列に一致する項目はすべて除外されます。アスタリスク（`*`）を使用したワイルドカードをサポートします。 |
| **[!UICONTROL 存在する]** | 値が null でない場合に項目を戻します。 |
| **[!UICONTROL 存在しない]** | 値が null の場合に項目を戻します。 |

## 個別カウント演算子

セグメントの条件としてディメンション項目のアイテム数を指定できます。例えば、5 つ以上の異なる製品を表示したユーザーや、5 ページ以上の異なるページを表示した訪問に対するセグメントを作成できます。

| 演算子 | 説明 |
| --- | --- |
| **[!UICONTROL 次に等しい]** | 入力された値と等しいユニーク数を持つディメンション項目を返します。 |
| **[!UICONTROL 等しくない]** | 入力された値と等しくないユニーク数を持つディメンション項目を返します。 |
| **[!UICONTROL 次よりも大きい]** | 入力された値よりも大きいユニーク数を持つディメンション項目を返します。 |
| **[!UICONTROL 次よりも小さい]** | 入力された値よりも小さいユニーク数を持つディメンション項目を返します。 |
| **[!UICONTROL 次よりも大きいか等しい]** | 入力された値以上のユニーク数を持つディメンション項目を返します。 |
| **[!UICONTROL 次よりも小さいか等しい]** | 入力された値以下のユニーク数を持つディメンション項目を返します。 |
