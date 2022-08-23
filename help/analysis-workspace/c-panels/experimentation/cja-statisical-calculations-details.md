---
source-git-commit: c95e01a80f3f3ddcabfee171ee357a5cf9e81e53
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---
# CJA の実験パネルの統計指標：詳細

このページでは、CJA の実験パネルで使用される詳細な統計指標について説明します。 技術ユーザー向けです。


## コンバージョン率

コンバージョン率、または **mean**, *μ<sub>ν</sub>* 各バリアントの *ν* 実験では、指標の合計と、その指標に割り当てられた単位数との比率を定義します。 *N<sub>ν</sub>*:
<p style="text-align:center;"><img width="15%" src="img/mean_definition.png" alt="metric-mean"></p>
ここで、

- *Y<sub>iν</sub>* は、各単位の指標の値です *i*&#x200B;に含まれ、特定のバリアントに割り当てられている *ν*.
- 単位の合計 *i* 指標の標準化の選択に依存します。
   - If *人* は標準化指標で、各単位は一意の人物/プロファイルです。
   - If *セッション* は標準化指標で、各単位は一意のセッションです。
   - If *イベント* は標準化指標で、各単位は一意のイベントです。

一般に、この標準化指標は、独立の単位と同じように選択する必要があります。つまり、あるセッションでのユーザーの行動が別のセッションでの行動とは独立した場合、セッションは適切な標準化指標になります。

必要に応じて、サンプルの標準偏差が式と共に使用されます


<p style="text-align:center;"><img width="30%" src="img/stdev_definition.png" alt="metric-mean"></p>


## 上昇率

バリアント間の上昇率  *ν*、およびコントロールバリアント  *ν<sub>0</sub>* は、コンバージョン率の相対的な「デルタ」で、
<p style="text-align:center;"><img width="15%" src="img/lift_definition.png" alt="metric-mean"></p>
個々のコンバージョン率は、上で定義したとおりです。


## 信頼性シーケンス

CJA 実験パネルには表示されませんが、個々のバリアントの信頼性シーケンスは表示されます *ν* は、Adobeが使用する統計的手法の中心となるもので、ここで定義します（以下から再現）。 [Waudby-Smith 等](https://doi.org/10.48550/arXiv.2103.06476)) をクリックします。

> ターゲットパラメーターの見積もりに関心があるとします。 *ψ* （実験のバリアントのコンバージョン率など）。 その後、「固定時間」信頼区間 (CI) のシーケンスと時間的に均一な信頼シーケンス (CS) の間の二重関係を次のように要約できます。
<p style="text-align:center;"><img width="60%" src="img/ci_vs_cs.png" alt="metric-mean"></p>

つまり、通常の信頼区間の場合、確率論的には、ターゲットパラメーターが値の範囲内にあることが保証されます *ċ<sub>t</sub>* は、 *n* ( *n* はサンプル数です )。 逆に、信頼性シーケンスの場合、サンプルサイズのすべての値/常に保証されます *t*&#x200B;を指定した場合、対象のパラメーターの「true」値は範囲内にあります *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*.

これは、オンラインテストにとって非常に重要な、いくつかの深い意味を持ちます。
- CS は、新しいデータが利用可能になったときに、オプションで更新できます。
- 実験は、連続的に監視、適応的に停止または継続することができる。
- type-I エラーは、データに依存する時間を含め、すべての停止時間で制御されます。

Adobeは、平均推定値を持つ個々のバリアントに対して漸近的信頼順序を使用します *μ* はフォームを持ちます

<p style="text-align:center;"><img width="45%" src="img/confidence_sequence_individual.png" alt="metric-mean"></p>

要素の説明：
- *N* は、そのバリアントの単位数です
- *σ* は、標準偏差のサンプルの推定値です（既に定義済み）。
- *α* は、I 型エラー（または誤りの可能性）の目的のレベルです
- *ρ*<sup> 2</sup> は、CS が最も厳密なサンプルサイズを調整する定数です。 Adobeは、 *ρ*<sup> 2</sup> = 10<sup>-2.8</sup>は、オンライン実験で見られるコンバージョン率のタイプに適しています。


## 信頼性

Adobeが使用する信頼性は、平均治療効果に対して信頼性の順序を反転させて得られる「いつでも有効な」信頼性です。

正確に言うと、2 つの例で示すとおりです。 *t* 2 つのバリアント間の手段の違いをテストする場合、 *p*-value （このテストの値）と、の差の信頼区間（手段の違い）。 アナロジーでは、いつでも有効です *p*-value は、平均処理効果見積もりの（いつでも有効な）信頼性シーケンスを反転することで取得できます。
<p style="text-align:center;"><img width="22%" src="img/ate_definition.png" alt="metric-mean"></p>

使用する見積もりは、逆傾向加重 (IPW) 見積もりです。 検討 *N = N<sub>0</sub>* + *N<sub>1</sub>* 単位、各単位$i$のバリアント割り当てのラベルは次のとおりです。 *A<sub>i</sub>=0,1* 単位が variantν=0,1 に割り当てられている場合。 ユーザーに固定の確率（傾向）が割り当てられている場合 *π<sub>0</sub>, (1-π<sub>0</sub>)*&#x200B;の結果を示し、その結果指標は *Y<sub>i</sub>*&#x200B;を指定した場合、IPW 見積もりが
<p style="text-align:center;"><img width="45%" src="img/ipw_definition.png" alt="metric-mean"></p>

注意 *f* は影響関数、Waudby-Smith などです。 この見積もりの信頼性シーケンスが次のようになっていることを示しています。
<p style="text-align:center;"><img width="55%" src="img/cs_ate_definition1.png" alt="metric-mean"></p>

割り当ての確率を経験的な推定値に置き換える： *π<sub>0</sub> = N<sub>0</sub>/N*&#x200B;の場合、差異の項は個々の標本平均推定値に基づいて表すことができます  *μ<sub>{0,1}</sub>* 標準偏差の推定値  *σ<sub>{0,1}</sub>* 形式：

<p style="text-align:center;"><img width="55%" src="img/cs_ate_var.png" alt="metric-mean"></p>


テスト統計を使用した通常の仮説テストの場合の呼び出し *z = (μ)<sub>1</sub> - μ<sub>0</sub>)/σ<sub>p</sub>*&#x200B;の場合、$p$-values と信頼区間の間に次の対応があります。

<p style="text-align:center;"><img width="55%" src="img/pvalue_ci_correspondence.png" alt="metric-mean"></p>

場所 *Φ* は、標準法線の累積分布です。 いつでも有効です *p* — 値は、上で定義した平均処理効果の信頼性シーケンスを考慮すると、この関係を反転できます。
<p style="text-align:center;"><img width="75%" src="img/anytimevalid-pvalue.png" alt="metric-mean"></p>

最後に、 **いつでも有効 *信頼性*** が
<p style="text-align:center;"><img width="22%" src="img/anytimevalid-confidence.png" alt="metric-mean"></p>


## 実験の最終的な結果を宣言する

2 つの腕を持つ実験の場合、CJA 実験パネルに、実験が **決定的な** いつでも有効な信頼性が 95%を超える場合 ( つまり、いつでも有効な *p*-value は 5%を下回っています )。

2 つ以上の変種が存在する場合、ボンフェロンニ補正が適用されます。 を使用した実験の場合 *K* 治療と単一の基準（制御）治療は、 *K-1* 独立仮説テスト。 ボンフェロンニ補正とは、いつでも有効な場合、制御と与えられた変種が等しい手段を持つというヌル仮説を拒否することを意味します *p*-value は 0.05/(K-1) のしきい値を下回っています。


## 最もパフォーマンスの高い腕

実験の最終的な結果が宣言されると、最もパフォーマンスの高い腕が表示されます。 これは、コントロールを含むセットと、 *p* — ボンフェロンニしきい値を下回る値