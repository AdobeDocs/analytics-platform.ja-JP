---
title: リファレンス — 高度な関数
description: これらの関数にアクセスするには、関数ドロップダウンリストの「詳細を表示」を選択します。
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# リファレンス — 高度な関数

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## 表関数と行関数

テーブル関数とは、テーブルの各行の出力が同じになる関数です。 行関数とは、テーブルの行ごとに出力が異なる関数です。

## ゼロを含むパラメーターの意味

計算にゼロを含めるかどうかを示します。 ゼロは「何もない」ことを意味しますが、時には重要な意味を持ちます。

例えば、売上高指標がある場合に、ページ表示数指標をレポートに追加すると、突然、売上高の行が増え、すべてゼロになります。 平均、最小、四分位数などに影響を与えたくない場合があります。 売上高列の計算。 この場合、ゼロを含むパラメーターを確認します。

一方、2つの指標に関心がある場合は、一部の行がゼロなので、平均または最小値が高いとは言えないので、ゼロを含めるようにパラメータをチェックしないでください。

## AND

引数の値を返します。 NOTを使用して、値が1つの特定の値と等しくないことを確認します。

> [!NOTE]0（ゼロ）は False を表し、それ以外の値は True を表します。

```
AND(logical_test1,[logical_test2],...)
```

| 引数 | 説明 |
|---|---|
| *logical_test1* | 必須の値です。TRUE または FALSE で示される値または式です。 |
| *logical_test2* | (オプション)TRUEまたはFALSEとして評価する追加の条件 |

## 個別概算カウント（ディメンション） 

選択されたディメンションのディメンション項目の概算の個別カウントを返します。この関数は、HyperLogLog(HLL)メソッドを使用して、個別のカウントを近似します。  値が実際の値の95%以内であることを保証するように設定されます。

```
Approximate Count Distinct (dimension)
```

| 引数 |  |
|---|---|
| *ディメンション* | 明確な項目数の近似値を求めるディメンション。 |

## 使用例

個別概算カウント（顧客 ID eVar）は、この関数の一般的な使用例です。

新しい計算指標「概算顧客数」の定義は次のようになります。

![](assets/approx-count-distinct.png)

次に、「おおよその顧客」指標をレポートで使用する方法を示します。

![](assets/approx-customers.png)

## 超過した固有数

Count()やRowCount()と同様に、近似値Count Distinct()は「ユニークが超過しました」 [という制限を受けます](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html)。 ディメンションの特定の月内に「ユニークが超過しました」という制限に達した場合、その値は1つのディメンション項目としてカウントされます。

## カウント関数の比較

近似値の個別カウント()は、作成された指標を任意のディメンションレポートで使用して、個別のディメンションの項目の近似値をレンダリングできるので、Count()関数とRowCount()関数の改良点です。 例えば、モバイルデバイスタイプレポートで使用される顧客IDの数などです。

この関数はHLLメソッドを使用するのに対し、Count()とRowCount()は正確な数値なので、Count()とRowCount()よりもわずかに正確ではありません。

## アークコサイン（行） 

指標のアークコサイン (逆コサイン) を返します。アークコサインは、そのコサインが数値である角度です。0 (ゼロ) ～ pi の範囲のラジアンで角度が返されます。結果をラジアンから度に変換する場合は、その結果に 180/PI( ) を掛けます。

```
ACOS(metric)
```

| 引数 |  |
|---|---|
| *metric*  | -1 から 1 で求める角度のコサインです。 |

## アークサイン（行） 

数のアークサイン (逆サイン) を返します。アークサインは、そのサインが数値である角度です。-pi/2 ～ pi/2 の範囲のラジアンで角度が返されます。アークサインを度で表すには、結果に 180/PI( ) を掛けます。

```
ASIN(metric) 
```

| 引数 |  |
|---|---|
| *metric*  | -1 から 1 で求める角度のコサインです。 |

## アークタンジェント（行） 

数のアークタンジェント (逆タンジェント) を返します。アークタンジェントは、そのタンジェントが数値である角度です。-pi/2 ～ pi/2 の範囲のラジアンで角度が返されます。アークタンジェントを度で表すには、結果に 180/PI( ) を掛けます。

```
ATAN(metric)
```

| 引数 |  |
|---|---|
| *metric*  | -1 から 1 で求める角度のコサインです。 |

## 指数回帰：予測 Y（行） 

「最小二乗」法を使用して最良の当てはめ線を計算し、指定されている既知の x 値（metric_X）に対する予測 y 値（metric_Y）を算出します。

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## Cdf-T

自由度 n のスチューデントの t 分布の値（z スコアが x 未満）の割合を返します。

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

正規分布の値（z スコアが x 未満）の割合を返します。

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## 上限（行） 

指定された値以上の最小の整数を返します。例えば、製品価格が $569.34 であり、通貨の小数点以下を売上高としてレポートしない場合は、CEILING(*Revenue*) という数式を使用して、売上高を直近のドル値（$570）に切り上げます。

```
CEILING(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | 丸める指標です。 |

## コサイン（行） 

指定された角度のコサインを返します。角度が度で表されている場合は、角度に PI( )/180 を掛けます。

```
COS(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | コサインを求めるラジアンによる角度です。 |

## 立方根

数の正の立方根を返します。数の立方根は、3 乗してその数になる値です。

```
CBRT(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | 立方根を求める指標です。 |

## 累積

最後のN行のxの合計を返します（ディメンションの順序に従い、文字列ベースのフィールドにハッシュ値を使用します）。

N &lt;= 0の場合、前の行がすべて使用されます。 ディメンション別に並べられているので、日付やパスの長さなど、自然な順序を持つディメンションでのみ便利です。

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## 累加平均

最後のN行の平均を返します。

N &lt;= 0の場合、前の行がすべて使用されます。 ディメンション別に並べられているので、日付やパスの長さなど、自然な順序を持つディメンションでのみ便利です。

> [!NOTE]この関数は、割合の指標（例：売上高/訪問者数）を使用する場合は機能しません。このような指標では、最終 N にわたる売上高を合計し、最終 N にわたる訪問者数を合計して、それらを除算するのではなく、代わりに割合を平均化します。代わりに、次の数式を使用してください。

```
cumul(revenue)/cumul(visitor)
```

## 次と等しい

数字または文字列の値に完全に一致する項目を返します。

## 指数回帰：相関係数（表） 

回帰式に対して、2 つの指標列（*metric_A* と *metric_B*）の間の相関係数 *r* を返します。

```
CORREL.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 指数回帰：切片（表） 

以下に対して、2 つの指標列（*metric_X* と *metric_Y*）の間の切片 *b* を返します。

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 指数回帰：傾き（表） 

以下に対して、2 つの指標列（*metric_X* と *metric_Y*）の間の傾き *a* を返します。

```
SLOPE.EXP(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 下限（行） 

指定された値以下の最大の整数を返します。例えば、製品価格が $569.34 であり、通貨の小数点以下を売上高としてレポートしない場合は、FLOOR(*Revenue*) という数式を使用して、売上高を直近のドル値（$569）に切り捨てます。

```
FLOOR(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | 丸める指標です。 |

## 以下の値を超える

入力された値よりも大きい数字を持つ項目を返します。

## 次よりも大きいか等しい

入力された値よりも大きいか等しい数字を持つ項目を返します。

## ハイパボリックコサイン（行） 

数のハイパボリックコサインを返します。

```
COSH(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | ハイパボリックコサインを求めるラジアンによる角度です。 |

## ハイパボリックサイン（行） 

数のハイパボリックサインを返します。

```
SINH(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | ハイパボリックサインを求めるラジアンによる角度です。 |

## ハイパボリックタンジェント（行） 

数のハイパボリックタンジェントを返します。

```
TANH(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | ハイパボリックタンジェントを求めるラジアンによる角度です。 |

## IF（行） 

IF関数は、指定した条件がTRUEの場合に1つの値を返し、その条件がFALSEの場合にもう1つの値を返します。

```
IF(logical_test, [value_if_true], [value_if_false])
```

| 引数 | 説明 |
|---|---|
| *logical_test* | 必須の値です。TRUE または FALSE で示される値または式です。 |
| *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.) |
| *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.) |

## 未満

入力された値よりも小さい数字を持つ項目を返します。

## 次よりも小さいか等しい

入力された値よりも小さいか等しい数字を持つ項目を返します。

## 線形回帰：相関係数

Y = a X + b。相関係数を返します。

## 線形回帰：切片

Y = a X + b。b を返します。

## 線形回帰：予測 Y

Y = a X + b。Y を返します。

## 線形回帰：傾き

Y = a X + b。a を返します。

## 10 を底とする対数（行） 

数の 10 を底とする対数を返します。

```
LOG10(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | 基数-10 の対数を求める正の実数です。 |

## 対数回帰：相関係数（表） 

回帰式 *に対して、2 つの指標列（* metric_X *と* metric_Y *）の間の相関係数* r[!DNL Y = a ln(X) + b] を返します。計算には CORREL 式を使用します。

```
CORREL.LOG(metric_X,metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 対数回帰：切片（表） 

回帰式 *に対して、2 つの指標列（* metric_X *と* metric_Y *）の間の最小二乗回帰として、切片* b[!DNL Y = a ln(X) + b] を返します。計算には INTERCEPT 式を使用します。

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 対数回帰：予測 Y（行） 

最小二乗法で [!DNL Y = a ln(X) + b]**** に基づいて最良の当てはめ線を計算し、指定されている既知の [!DNL x] 値（metric_X）に対する予測 [!DNL y] 値（metric_Y）を算出します。計算には ESTIMATE 式を使用します。

回帰分析では、この関数は、回帰方程式 [!DNL Y = a ln(X) + b] = a ln() + b の最良の当てはめ線を計算する対数を使用して既知の [!DNL x]x 値（*metric_X*）に対する予測 [!DNL y] 値（*metric_Y*）を算出します。[!DNL a] 値は各 x 値に対応し、[!DNL b] は定数値です。

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 対数回帰：傾き（表） 

回帰式 *に対して、2 つの指標列（* metric_X *と* metric_Y *）の間の傾き* a[!DNL Y = a ln(X) + b] を返します。計算には SLOPE 式を使用します。

```
SLOPE.LOG(metric_A, metric_B)
```

| 引数 | 説明 |
|---|---|
| *metric_A* | 依存データとして指定する指標です。 |
| *metric_B* | 非依存データとして指定する指標です。 |

## 自然対数

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | 自然対数を求める正の実数です。 |

## NOT

数が0の場合は1を返し、別の数の場合は0を返します。

```
NOT(logical)
```

| 引数 | 説明 |
|---|---|
| *論理* | 必須の値です。TRUE または FALSE で示される値または式です。 |

NOT を使用する場合は、式（&lt;、>、=、&lt;> など）が0または1の値を返します。

## 等しくない

入力された値の完全一致を含まない項目をすべて返します。

## OR（行） 

いずれかの引数が TRUE の場合は TRUE を返します。すべての引数が FALSE の場合は FALSE を返します。

> [!NOTE]0（ゼロ）は False を表し、それ以外の値は True を表します。

```
OR(logical_test1,[logical_test2],...)
```

| 引数 | 説明 |
|---|---|
| *logical_test1* | 必須の値です。TRUE または FALSE で示される値または式です。 |
| *logical_test2* | (オプション)TRUEまたはFALSEとして評価する追加の条件 |

## 円周率

15 桁の精度の定数 PI（3.14159265358979）を返します。

```
PI()
```

[!DNL PI] 関数には引数がありません。

## 累乗回帰：相関係数（表） 

[!DNL Y = b*X] に対して、2 つの指標列（*metric_X* と *metric_Y*）の間の相関係数 *r* を返します。

```
CORREL.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 累乗回帰：切片（表） 

*に対して、2 つの指標列（* metric_X *と* metric_Y *）の間の切片* b[!DNL Y = b*X] を返します。

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 累乗回帰：予測 Y（行） 

「最小二乗」法を使用して、[!DNL Y = b*X] に対する最良の当てはめ線を計算し、指定されている既知の [!DNL x] 値（[!DNL metric_X]）に対する予測 [!DNL y] 値（[!DNL metric_Y]）を算出します。

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 累乗回帰：傾き（表） 

[!DNL Y = b*X] に対して、2 つの指標（*metric_X* と *metric_Y*）の間の傾き *a* を返します。

```
SLOPE.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 二次回帰：相関係数（表） 

[!DNL Y=(a*X+b)]**** に対して、2 つの指標列（*metric_X* と *metric_Y*）の間の相関係数 *r* を返します。

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 二次回帰：切片（表） 

[!DNL Y=(a*X+b)] に対して、2 つの指標列（*metric_X* と *metric_Y*）の間の切片 *b* を返します。

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 二次回帰：予測 Y（行） 

最小二乗法で [!DNL Y=(a*X+b)]**** を使用して最良の当てはめ線を計算し、指定されている既知の [!DNL x] 値（metric_X）に対する予測 [!DNL y] 値（metric_Y）を算出します。

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| 引数 | 説明 |
|---|---|
| *metric_A* | 依存データとして指定する指標です。 |
| *metric_B* | 依存データとして指定する指標です。 |

## 二次回帰：傾き（表） 

[!DNL Y=(a*X+b)] に対して、2 つの指標列（*metric_X* と metric_Y）の間の傾き *a* を返します。

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 逆数回帰：相関係数（表） 

[!DNL Y = a/X+b] に対して、2 つの指標列（*metric_X* と *metric_Y*）の間の相関係数 *r* を返します。

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 逆数回帰：切片（表） 

*に対して、2 つの指標列（* metric_X *と* metric_Y *）の間の切片* b[!DNL Y = a/X+b] を返します。

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 逆数回帰：予測 Y（行） 

最小二乗法で [!DNL Y = a/X+b] を使用して最良の当てはめ線を計算し、指定されている既知の [!DNL x] 値（metric_X）に対する予測 [!DNL y] 値（metric_Y）を算出します。

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## 逆数回帰：傾き（表） 

[!DNL Y = a/X+b] に対して、2 つの指標（*metric_X* と *metric_Y*）の間の傾き *a* を返します。

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| 引数 | 説明 |
|---|---|
| *metric_X* | 依存データとして指定する指標です。 |
| *metric_Y* | 非依存データとして指定する指標です。 |

## サイン（行） 

指定された角度のサインを返します。角度が度で表されている場合は、角度に PI( )/180 を掛けます。

```
SIN(metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | サインを求めるラジアンによる角度です。 |

## t スコア

z スコアのエイリアス。つまり、平均値を標準偏差で割って求める偏差値です。

## t 検定

t スコア col および自由度 n の t 検定（m-tailed）を実行します。

署名は `t_test( x, n, m )` です。その下では、単に `m*cdf_t(-abs(x),n)` を呼び出します。（これは z 検定関数と似ており、z 検定関数は `m*cdf_z(-abs(x))` を実行します）。

ここで、`m` はテール数、`n` は自由度です。これらは数値でなければなりません（全体レポートの場合は、行ごとに変わらない定数でなければなりません）。

`X` は t 検定統計量です。一般的には指標に基づく数式（zscore など）で、すべての行で評価されます。

戻り値は、指定された自由度とテール数のテスト統計xが表示される確率です。

**例：**

1. 次の式を使用して外れ値を見つけます。

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. この式に `if` を組み合わせて、極度に高いまたは低いバウンス率を無視し、その他すべてへの訪問回数をカウントします。

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## タンジェント

指定された角度のタンジェントを返します。角度が度で表されている場合は、角度に PI( )/180 を掛けます。

```
TAN (metric)
```

| 引数 | 説明 |
|---|---|
| *metric*  | タンジェントを求めるラジアンによる角度です。 |

## z スコア（行） 

正規分布に基づいてZスコア（通常のスコア）を返します。 zスコアは、観測値が平均から偏差した標準偏差の数です。 zスコア0（ゼロ）は、スコアが平均と同じであることを意味します。 Zスコアは正または負の値で、平均値を上回るか下回るか、標準偏差の数で示されます。

zスコアの式は次のとおりです。

![](assets/z_score.png)

ここで、[!DNL x] は生のスコア、[!DNL μ] は母集団の平均値、[!DNL σ] は母集団の標準偏差です。

> [!NOTE] [!DNL μ] （ミュー）および [!DNL σ]（シグマ）は、指標から自動的に計算されます。

Z スコア（指標）

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i> metric</i>  </td> 
   <td colname="col2"> <p> 最初のゼロでない引数の値を返します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z 検定

ZスコアAのn-tailed Z検定を実行します。

現在の行が列内で偶然見つかる確率を返します。

> [!NOTE]値が正規分布されると仮定します。

