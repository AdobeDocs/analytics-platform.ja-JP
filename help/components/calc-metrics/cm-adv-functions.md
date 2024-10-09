---
title: 高度な関数
description: これらの関数にアクセスするには、関数ドロップダウンリストの「詳細を表示」を選択します。
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '3126'
ht-degree: 19%

---

# 高度な関数

[ 計算指標ビルダー ](cm-workflow/cm-build-metrics.md) では、統計関数および数学関数を適用できます。 この記事では、高度な関数とその定義をアルファベット順にリストして説明します。

これらの関数にアクセスするには、コンポーネントパネルの ![ エフェクト ](/help/assets/icons/Effect.svg)**[!UICONTROL 関数]** リストの下にある **[!UICONTROL すべて表示]** を選択します。 下にスクロールして、**[!UICONTROL 高度な関数]** のリストを表示します。

## テーブル関数と行関数

表関数とは、表のどの行についても出力が同じになる関数です。行関数とは、表の各行で出力が異なる関数です。

該当する場合および関連する場合、関数には、関数のタイプで注釈が付けられます。[!BADGE  表 ]{type="Neutral"}[!BADGE 行]{type="Neutral"}

## include-zeros パラメータは何を意味しますか？

このパラメーターは、計算にゼロを含むかどうかを示します。ゼロは時には *無* を意味することもありますが、時にはそれが重要です。

例えば、売上高指標を持っていて、レポートにページビュー指標を追加すると、突然売上高の行が増え、すべてがゼロになります。 その追加の指標が、売上高列にある **[MEAN](cm-functions.md#mean)**、**[ROW MINIMUM](cm-functions.md#row-min)**、**[QUARTILE](cm-functions.md#quartile)** およびその他の計算に影響を与えることはお勧めしません。 この場合、`include-zeros` パラメーターを確認します。

別のシナリオとして、2 つの目標指標があり、一方の指標の平均または最小値が高くなるのは、一部の行がゼロであるためです。  その場合、パラメーターにゼロを含めるかどうかを確認しないことを選択できます。


## および

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL AND （logical_test）]**


接続詞。 ゼロに等しくないは true、ゼロに等しいは false と見なされます。 出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| logical_test | 少なくとも 1 つのパラメーターが必要ですが、任意の数のパラメーターを指定できます。 TRUE または FALSE と評価できる値または式 |

## 重複を除外した概算カウント

![ 効果 ](/help/assets/icons/Effect.svg)**[!UICONTROL 個別概算カウント（ディメンション）]**


選択したディメンションのディメンション項目の個別概算カウントを返します。


| 引数 | 説明 |
|---|---|
| ディメンション | 概算の個別品目数を計算するディメンション |

### 例

この関数の一般的なユースケースは、おおよその顧客数を取得したい場合です。




## 逆余弦

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 逆余弦（メートル法）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | -1 から 1 までの角度のコサイン |



## 逆正弦

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 逆正弦（メートル法）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | 角度の正弦を–1 から 1 に指定します |



## 円弧の接線

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT （メートル）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | -1 から 1 までの角度の接線 |



## Cdf-T

![ 効果 ](/help/assets/icons/Effect.svg)**[!UICONTROL CDF-T （指標、数値）]**


自由度 n の student-t 分布を持つ確率変数の z スコアが col より小さい確率を返します。


| 引数 | 説明 |
|---|---|
| metric | スチューデント t 分布の累積分布関数を求める指標です。 |
| number | スチューデント t 分布の累積分布関数の自由度 |

### 例

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z

![ エフェクト ](/help/assets/icons/Effect.svg)**[!UICONTROL CDF-Z （指標、数値）]**


正規分布を持つ確率変数の z スコアが col 未満になる確率を返します。


| 引数 | 説明 |
|---|---|
| metric | 標準正規分布の累積分布関数を求める指標です |

### 例

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## 天井

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING （metric）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | 丸める指標 |


## 信頼性 (下限)

![Effect](/help/assets/icons/Effect.svg)**[!UICONTROL CONFIDENCE （normalizing-container, success-metric, control, significity-treshold）]**

[ 時間一様中央限界理論と漸近的信頼性シーケンス **で説明されているように** WASKR メソッドを使用して任意の時間の有効な信頼性 ](http://arxiv.org/pdf/2103.06476) 低い）を計算します。

信頼性は、特定のバリアントがコントロールバリアントと同じであるという証拠がどの程度あるかを示す確率測度です。 信頼性が高いほど、コントロールバリアントおよびコントロールバリアント以外のパフォーマンスが等しいという仮定に対する証拠が少ないことを示します。

| 引数 | 説明 |
| --- | --- |
| normalizing-container | テストが実行される基準（人、セッションまたはイベント）。 |
| 成功指標 | ユーザーがバリアントと比較する指標。 |
| control | 実験におけるその他すべてのバリアントと比較されるバリアント。コントロールバリアントディメンション項目の名前を入力します。 |
| 有意しきい値 | この関数のしきい値は、デフォルトの 95%に設定されています。 |

## 信頼性 (上限)

![Effect](/help/assets/icons/Effect.svg)**[!UICONTROL CONFIDENCE （normalizing-container, success-metric, control, significity-treshold）]**

[ 時間一様中央限界理論と漸近的信頼性シーケンス **で説明されているように** WASKR メソッドを使用して任意の時間の有効な信頼性 ](http://arxiv.org/pdf/2103.06476) 上限）を計算します。

信頼性は、特定のバリアントがコントロールバリアントと同じであるという証拠がどの程度あるかを示す確率測度です。 信頼性が高いほど、コントロールバリアントおよびコントロールバリアント以外のパフォーマンスが等しいという仮定に対する証拠が少ないことを示します。

| 引数 | 説明 |
| --- | --- |
| normalizing-container | テストが実行される基準（人、セッションまたはイベント）。 |
| 成功指標 | ユーザーがバリアントと比較する指標。 |
| control | 実験におけるその他すべてのバリアントと比較されるバリアント。コントロールバリアントディメンション項目の名前を入力します。 |
| 有意しきい値 | この関数のしきい値は、デフォルトの 95%に設定されています。 |


## 余弦

![ エフェクト ](/help/assets/icons/Effect.svg)**[!UICONTROL COSINE （metric）]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | コサインを求める角度（ラジアン単位） |


## 立方根

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 立方根（メトリック）]**


数の正の立方根を返します。数の立方根は、3 乗してその数になる値です。


| 引数 | 説明 |
|---|---|
| metric | キューブのルートを計算する指標 |



## 累積

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE （number, metric）]**

列 x の最後の n 個の要素の合計を返します。n > 0 の場合、最後の n 個の要素または x を合計します。n &lt; 0 の場合、前の要素を合計します。

| 引数 | 説明 |
| --- | --- |
| number | 合計を返す最後の N 行。 N &lt;= 0 の場合は、前の行をすべて使用します。 |
| metric | 累積合計を求める指標。 |

### 例

| 日付 | 売上高 | 累積（0，収益） | 累積（2，収益） |
|------|------:|--------------:|--------------:|
| 5月 | 500 ドル | 500 ドル | 500 ドル |
| 6月 | 200 ドル | 700 ドル | 700 ドル |
| 7月 | $400 | 1,100 ドル | $600 |


## 累積（平均）

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 累積平均（数値、指標）]**

列 x の最後の n 個の要素の平均を返します。n > 0 の場合、最後の n 個の要素または x を合計します。n &lt; 0 の場合、前の要素を合計します。

| 引数 | 説明 |
| --- | --- |
| number | 平均を返す最後の N 行。 N &lt;= 0 の場合は、前の行をすべて使用します。 |
| metric | 累積平均を求める指標です。 |

>[!NOTE]
>
>この関数は、1 人当たりの売上高などのレート指標では機能しません。 この関数は、過去 N 個の収益を合計し、過去 N 個の人物を合計して除算するのではなく、割合を平均します。 <br/> 代わりに、[**[!UICONTROL CUMULATIVE （revenue） ]**](#cumulative)![Divide](/help/assets/icons/Divide.svg)[**[!UICONTROL CUMULATIVE （person） ]**](#cumulative) を使用します。
>


## 次と等しい

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL （）]**


等しい。 出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 = Metric 2`



## 指数回帰：相関係数

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 指数回帰：相関係数（metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y と関連付ける指標 |
| metric_Y | metric_X と関連付ける指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |

## 指数回帰：予測 Y

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 指数回帰：予測 Y （metric_X, metric_Y, include_zeros）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 非依存データとして指定する指標です。 |
| metric_Y | 依存データとして指定する指標です。 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 指数回帰：切片

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 指数回帰：INTERCEPT （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 指数回帰：勾配

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 指数回帰：SLOPE （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## Floor

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR （metric_X, metric_Y, include_zeros）]**

[!BADGE 行]{type="Neutral"}

| 引数 | 説明 |
|---|---|
| metric | 丸める指標です。 |


## 次よりも大きい

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN （）]**


出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 > Metric 2`

## 次よりも大きいか等しい

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL （）]**


次よりも大きいか等しい。 出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| metric_X |  |
| metric_Y |  |

### 例

`Metric 1 >= Metric 2`



## 双曲線余弦

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 双曲線余弦（メートル法）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | 双曲線余弦を求める角度（ラジアン） |



## 双曲線正弦

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 双曲線正弦（メートル法）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | 双曲線正弦を求める角度（ラジアン） |



## 双曲線正接

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 双曲線正接（メートル）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | 双曲線正接を求める角度（ラジアン） |


##   

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL IF （logical_test, value_if_true, value_if_false）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| logical_test | 必須。TRUE または FALSE と評価できる値または式 |
| value_if_true | logical_test 引数の値が TRUE の場合に返す値。 （含まれない場合、この引数のデフォルト値は 0 です）。 |
| value_if_false | logical_test 引数の値が FALSE の場合に返す値です (含まれない場合、この引数のデフォルト値は 0 です)。 |


## 未満

![Effect](/help/assets/icons/Effect.svg)**[!UICONTROL LESS THAN （）]**


出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |


### 例

`Metric 1 < Metric 2`

## 次よりも小さいか等しい

![Effect](/help/assets/icons/Effect.svg)**[!UICONTROL LESS THAN OR EQUAL （）]**

次よりも小さいか等しい。 出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 <= Metric 2`



## 線形回帰：相関係数

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 線形回帰：相関係数（metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y と関連付ける指標 |
| metric_Y | metric_X と関連付ける指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 線形回帰：切片

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 線形回帰：INTERCEPT （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 線形回帰：予測 Y

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 線形回帰：予測された Y （metric_X, metric_Y, include_zeros）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 線形回帰：勾配

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 線形回帰：SLOPE （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## ログベース 10

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL ログベース 10 （指標）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | 底が 10 の対数を求める正の実数 |


## 回帰を記録：相関係数

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL LOG 回帰：相関係数（metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y と関連付ける指標 |
| metric_Y | metric_X と関連付ける指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## ログ回帰：インターセプト

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL LOG 回帰：INTERCEPT （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 回帰を記録：予測 Y

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL ログ回帰：予測された Y （metric_X, metric_Y, include_zeros）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 回帰を記録：勾配

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL LOG 回帰：SLOPE （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 自然対数

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 自然ログ（指標）]**


数の自然対数を返します。自然対数の底は定数 e（2.71828182845904）です。LN は、EXP 関数の逆関数です。


| 引数 | 説明 |
|---|---|
| metric | 自然対数を求める正の実数 |



##  ではない

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NOT （logical）]**


否定（ブール値として）。 出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| 論理 | 必須。TRUE または FALSE と評価できる値または式 |



## 次と等しくない

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL （）]**


等しくない。 出力は 0 （false）または 1 （true）です。


| 引数 | 説明 |
|---|---|
| metric_X | |
| metric_Y | |

### 例

`Metric 1 != Metric 2`


## または

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL OR （logical_test）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| logical_test | 少なくとも 1 つのパラメーターが必要ですが、任意の数のパラメーターを指定できます。 TRUE または FALSE と評価できる値または式 |


>[!NOTE]
>
>0（ゼロ）は False を表し、それ以外の値は True を表します。


## 円周率

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL PI （）]**

円周率を返します。円周率：3.14159..


## 累乗回帰：相関係数

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL POWER 回帰：相関係数（metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y と関連付ける指標 |
| metric_Y | metric_X と関連付ける指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 累乗回帰：インターセプト

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL POWER 回帰：INTERCEPT （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 累乗回帰：予測 Y

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL POWER 回帰：予測 Y （metric_X, metric_Y, include_zeros）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 累乗回帰：勾配

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL POWER 回帰：SLOPE （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 二次回帰：相関係数

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回帰：相関係数（metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y と関連付ける指標 |
| metric_Y | metric_X と関連付ける指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |

## 二次回帰：切片

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回帰：INTERCEPT （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 二次回帰：予測 Y

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回帰：予測 Y （metric_X, metric_Y, include_zeros）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |

## 二次回帰：勾配

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回帰：SLOPE （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |



## 逆回帰：相関係数

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 逆回帰：相関係数（metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | metric_Y と関連付ける指標 |
| metric_Y | metric_X と関連付ける指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 逆回帰：インターセプト

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 回帰回帰：INTERCEPT （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 逆回帰：予測 Y

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 逆回帰：予測 Y （metric_X, metric_Y, include_zeros）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## 逆回帰：勾配

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 回帰回帰：SLOPE （metric_X, metric_Y, include_zeros）]**


[!BADGE テーブル]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric_X | 依存データとして指定する指標 |
| metric_Y | 独立データとして指定する指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |




## 正弦

![ 効果 ](/help/assets/icons/Effect.svg) **[!UICONTROL 正弦（メートル法）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | 正弦を求める角度（ラジアン単位） |




## t スコア

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE （metric, include_zeros）]**


[MEAN](cm-functions.md#mean) からの偏差を標準偏差で割ったもの。 [Z スコア ](#z-score) のエイリアス。


| 引数 | 説明 |
|---|---|
| metric | T スコアを求める指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |


## t 検定

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST （metric, degrees, tail）]**


t スコアが x および n 自由度の m テール型 t 検定を実行します。


| 引数 | 説明 |
|---|---|
| metric | T 検定を実行する指標 |
| degrees | 自由度 |
| 尾 | T 検定を行うために使用するテールの長さ |

### 詳細

シグネチャは T-TEST （metric, degrees, tail）です。 その下では、単に ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)** を呼び出します。 この関数は、***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)** を実行する **[Z-TEST](#z-test)** 関数に類似しています。

- ***m*** は尾の数です。
- ***n*** は自由度で、レポート全体に対して一定の数値である必要があります。つまり、行単位で変更されません。
- ***x*** は T 検定の統計量で、多くの場合、指標に基づく数式（**[Z-SCORE](#z-score)** など）であり、すべての行で評価されます。

返される値は、指定された自由度とテール数において検定統計量 x が見られる確率です。

**例：**

1. 関数を使用して異常値を検索します。

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. 関数を **[IF](#if)** と組み合わせて、非常に高いバウンス率または低いバウンス率を無視し、その他のすべてに関するセッションをカウントします。

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```




## タンジェント

![ エフェクト ](/help/assets/icons/Effect.svg)**[!UICONTROL TANGENT （metric）]**


指定された角度のタンジェントを返します。角度が度で表されている場合は、角度に PI( )/180 を掛けます。


| 引数 | 説明 |
|---|---|
| metric | 接線を求める角度（ラジアン単位） |



## Z スコア

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE （metric, include_zeros）]**


[!BADGE 行]{type="Neutral"}


| 引数 | 説明 |
|---|---|
| metric | Z スコアを求める指標 |
| include_zeros | 計算にゼロ値を含めるかどうか |

Z スコアが 0 （ゼロ）の場合は、スコアが平均と同じであることを意味します。 z スコアは正と負のどちらにもなり得ます。平均値を上回るか下回るかを標準偏差の数で示します。

z スコアの式は次のようになります。

![](assets/z_score.png)

ここで、***[!DNL x]*** は生のスコア、***[!DNL μ]*** は母集団の平均、***[!DNL σ]*** は母集団の標準偏差です。

>[!NOTE]
>
>***[!DNL μ]*** （mu）と ***[!DNL σ]*** （sigma）は、指標から自動的に計算されます。



## Z 検定

![ エフェクト ](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST （metric_tails）]**


z スコアが x の n 方向の z 検定を実行します。


| 引数 | 説明 |
|---|---|
| metric | Z テストを実行する指標 |
| 尾 | Z 検定を行うために使用するテールの長さ |

>[!NOTE]
>
>値が正規分布されると仮定します。









<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->