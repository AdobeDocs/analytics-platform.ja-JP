---
title: 基本関数
description: 計算指標ビルダーを使用すると、統計関数と数学関数を適用して、高度な計算指標を作成できます。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 29%

---

# 基本関数


[ 計算指標ビルダー ](cm-workflow/cm-build-metrics.md) では、統計関数および数学関数を適用できます。 この記事では、関数とその定義のアルファベット順のリストについて説明します。

>[!NOTE]
>
>[!DNL metric] が関数の引数として特定されている場合は、指標の他の式も許可されます。例えば、[COLUMN MAXIMUM （metrics） ](#column-maximum) では [COLUMN MAXIMUM （PageViews + Visits） ](#column-maximum) も使用できます。



## テーブル関数と行関数

表関数とは、表のどの行についても出力が同じになる関数です。行関数とは、表の各行で出力が異なる関数です。

該当する場合および関連する場合、関数には、関数のタイプで注釈が付けられます。[!BADGE  表 ]{type="Neutral"}[!BADGE 行]{type="Neutral"}

## include-zeros パラメータは何を意味しますか？

このパラメーターは、計算にゼロを含むかどうかを示します。ゼロは時には *無* を意味することもありますが、時にはそれが重要です。

例えば、売上高指標を持っていて、レポートにページビュー指標を追加すると、突然売上高の行が増え、すべてがゼロになります。 その追加の指標が、売上高列にある **[MEAN](cm-functions.md#mean)**、**[ROW MINIMUM](cm-functions.md#row-min)**、**[QUARTILE](cm-functions.md#quartile)** およびその他の計算に影響を与えることはお勧めしません。 この場合、`include-zeros` パラメーターを確認します。

別のシナリオとして、2 つの目標指標があり、一方の指標の平均または最小値が高くなるのは、一部の行がゼロであるためです。  その場合、パラメーターにゼロを含めるかどうかを確認しないことを選択できます



## 絶対値

![ 効果 ](/help/assets/icons/Effect.svg)**[!UICONTROL 絶対値（指標）]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 絶対値を計算する指標。 |


## 列の最大値

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM （metric, include_zeros）]**

指標列の一連のディメンション要素の中の最大値を返します。MAXV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。

| 引数 | 説明 |
|---|---|
| metric | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定することもできます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 列の最小値

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM （metric, include_zeros）]**

指標列の一連のディメンション要素の中の最小値を返します。MINV は、複数のディメンション要素の 1 つの列（指標）内を垂直方向に評価します。

| 引数 | 説明 |
|---|---|
| metric | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定することもできます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 列の合計値

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 列の合計（指標）]**

（1 つのディメンションのすべての要素について） 1 つの列内の指標の数値をすべて加算します。

| 引数 | 説明 |
|---|---|
| metric | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定することもできます。 |


## カウント

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL カウント（指標）]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | カウントする指標。 |


## 指数

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT （metric）]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 底 e に適用される指数です。 |


## 平均

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN （metric, include_zeros）]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 平均を計算する指標。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 中央値

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN （metric, include_zeros）]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 中央値を計算する指標。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 剰余

![ エフェクト ](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO （metric_X, metric_Y）]**

ユークリッド除算を使用して x を y で除算した後の剰余を返します。

| 引数 | 説明 |
|---|---|
| metric_X | 分割する最初の指標。 |
| metric_Y | 除算する 2 番目の指標。 |

### 例

返される値の符号は入力した値の符号と同じです（またはゼロが返されます）。

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

常に正の数を取得するには、を使用します

```
MODULO(MODULO(x,y)+y,y)
```

## 百分位

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE （metric, k, include_zeros）]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 0 ～ 100（0 と 100 を含む）の範囲のパーセンタイル値です。 |
| k | 相対的な値を定義する指標列です。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |



## 累乗演算子

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL POWER 演算子（metric_X, metrix_Y）]**

x の y 乗を返します。

| 引数 | 説明 |
|---|---|
| metric_X | metric_Y の累乗に上げたい指標です。 |
| metric_Y | metric_X を発生させる指数です。 |


## 四分位数

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE （metric, quartile, include_zeros）]**

[!BADGE テーブル]{type="Neutral"}[COLUMN MINIMUM](#column-minimum)、[MEDIAN](#median)、および [COLUMN MAXIMUM](#column-maximum) は、四分位数がそれぞれ `0` （ゼロ）、`2`、`4` に等しい場合、[QUARTILE](#quartile) と同じ値を返します。

| 引数 | 説明 |
|---|---|
| metric | 四分位値を計算する指標です。 |
| 四分位数 | 返される四分位値を示します。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## ラウンド数

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND （metric, number）]**

*number* パラメーターを指定しない round は、*number* パラメーターが 0 の round と同じです。つまり、最も近い整数に round します。  *number* パラメーターを指定すると、小数点以下の *number* 桁が返されます。  *数値* が負の場合、小数の左側の 0 を返します。

| 引数 | 説明 |
|---|---|
| metric | 丸める指標です。 |
| number | 返す小数点以下の桁数。 負の値を指定すると、小数の左側にゼロが返されます。 |

### 例

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## 行数

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT （）]**

指定された列の行の数（ディメンション内でレポートされた一意の要素の数）を返します。*ユニーク数を超えています* は 1 としてカウントされます。


## 行最大

![ エフェクト ](/help/assets/icons/Effect.svg)**[!UICONTROL ROW MAX（metric, include_zeros）]**

各行の列の最大値。

| 引数 | 説明 |
|---|---|
| metric | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定することもできます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |

## 行の最小

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN （metric, include_zeros）]**

各行の列の最小値。

| 引数 | 説明 |
|---|---|
| metric | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定することもできます。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |



## 行の合計

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM （metric, include_zeros）]**

各行の列の合計。

| 引数 | 説明 |
|---|---|
| metric | 少なくとも 1 つの指標が必要ですが、任意の数の指標をパラメーターとして指定することもできます。 |


## 平方根

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根（メートル，include_zeros）]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 平方根を計算する指標です。 |


## 標準偏差

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 標準偏差（metric, include_zeros）]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| | 標準偏差を計算する指標。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


## 平方偏差

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE （metric, include_zeros）]**

[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 平方偏差を計算する指標。 |
| include_zeros | 計算にゼロ値を含めるかどうか。 |


VARIANCE の式は次のようになります。

![](assets/variance_eq.png){width="100"}

ここで、*x* はサンプル平均、[MEAN （*metric*） ](#mean)、*n* はサンプルサイズです。


分散を計算するには、数値の列全体を調べます。 まず、すべての数字の平均を求めます。平均を求めたら、各エントリを調べて、次の計算を行います。

1. 数字から平均を減算します。

1. 結果を 2 乗します。

1. その結果を合計に加算します。

列全体に対して反復処理が行われると、合計が 1 つになります。 その合計を列内にある数字の個数で除算します。その結果が列の平方偏差です。平方偏差は単一の数字です。ただし、数字の列として表示されます。

次の 3 項目列の例では、

| 列 |
|:---:|
| 1 |
| 2 |
| 3 |

この列の平均は 2 です。列の差異は、（（1 - 2） <sup>2</sup> + （2 - 2） <sup>2</sup> + （3 - 2） <sup>2</sup>/3） = 2/3 です。




<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->