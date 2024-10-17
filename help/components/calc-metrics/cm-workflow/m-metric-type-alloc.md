---
description: 指標タイプとアトリビューションについて説明します
title: 指標タイプとアトリビューション
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 40%

---

# 指標タイプとアトリビューション

計算指標定義の指標に対して、指標タイプと [ アトリビューションモデル ](#attribution-models) を設定できます。

1. 指標コンポーネントで ![ 設定 ](/help/assets/icons/Setting.svg) を選択します。
1. ポップアップダイアログで、次の手順を実行します。

   ![ 指標タイプとアトリビューション ](assets/cm-type-alloc.png)

   * **[!UICONTROL 指標タイプ]** を指定します。

     | 指標タイプ | 定義 |
     |---|---|
     | **[!UICONTROL 標準]** | 数式が 1 つの標準指標で構成されている場合、計算指標以外の対応する指標と同一のデータが表示されます。 標準指標は、個々の行項目に固有の計算指標を作成する場合に役立ちます。 <p>例えば、![ イベント ](/help/assets/icons/Event.svg) **[!UICONTROL 注文]** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **[!UICONTROL セッション]** は、その特定の行項目の注文を受け、その特定の行項目のセッション数で除算します。 |
     | **[!UICONTROL 総計]** | 各行項目のレポート期間には **[!UICONTROL 総計]** を使用します。 数式が 1 つの総合計メトリックで構成されている場合、計算されたメトリックは、各行項目に同じ総合計を表示します。 総合計指標は、合計データと比較する計算指標を作成する場合に役立ちます。 <p>例えば、![ イベント ](/help/assets/icons/Event.svg)**[!UICONTROL 注文]**![ 除算 ](/help/assets/icons/Divide.svg)![ イベント ](/help/assets/icons/Event.svg)**[!UICONTROL 合計セッション]** は、特定の行項目に対するセッションだけでなく、すべてのセッションに対する注文の割合を示します。 この例では、計算指標の **[!UICONTROL イベント]****[!UICONTROL セッション数 ![ 指標に対して ](/help/assets/icons/Event.svg) 総計]** を指定すると、自動的に ![ イベント ](/help/assets/icons/Event.svg)**[!UICONTROL セッション数の合計]** に変わります。 |

   * **[!UICONTROL 属性]** を指定します。

      1. 以下のいずれかを実行できます。

         * デフォルトの列アトリビューションモデル（ラストタッチ）を 30 日間のルックバックウィンドウで使用するには、**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]** を無効にします。
         * **[!UICONTROL デフォルト以外のアトリビューションモデルを使用]** を有効にします。 **[!UICONTROL 列アトリビューションモデル]** ダイアログで、

            * アトリビューションモデルから **[!UICONTROL モデル]** を選択します。
            * **[!UICONTROL ルックバックウィンドウ]** を選択します。 **[!UICONTROL カスタム時間]** を選択した場合は、期間を **[!UICONTROL 分]** 最大 **[!UICONTROL 四半期]** で定義できます。 詳しくは、[ ルックバックウィンドウ ](#lookback-window) を参照してください

      1. デフォルト以外のアトリビューションモデルを適用するには、「**[!UICONTROL 適用]**」を選択します。 「キャンセル」を選択してキャンセルします。

     デフォルト以外のアトリビューションモデルを既に定義している場合は、「**[!UICONTROL 編集]** を選択して、選択項目を変更します。

アトリビューションモデルとルックバックウィンドウの使用例については、[ 例 ](#example) を参照してください。


## アトリビューション {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_nondefaultattributionmodel"
>title="デフォルト以外のアトリビューションモデルを使用"
>abstract="選択した指標に対してデフォルト以外のアトリビューションモデルを有効にします。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attributionmodel"
>title="モデル"
>abstract="指標のアトリビューションモデルを選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lasttouch"
>title="ラストタッチ"
>abstract="訪問者が閲覧した最後のディメンション値に、クレジットの 100％を割り当てます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_firsttouch"
>title="ファーストタッチ"
>abstract="訪問者が閲覧した最初のディメンション値に、クレジットの 100％を割り当てます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_linear"
>title="線形"
>abstract="クレジットはすべてのディメンション値に均等に配分されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_participation"
>title="パーティシペーション"
>abstract="訪問者が閲覧したすべてのディメンション値に 100%クレジットされます。<br/>列の合計は誇張されています。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_sametouch"
>title="同じタッチ"
>abstract="コンバージョンと同じイベントで発生するディメンション値にのみ、クレジットを割り当てます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_ushaped"
>title="U 字型"
>abstract="最初のディメンション値に 40%、最後のディメンション値に 40%、中央の値に 20%のクレジットが配分されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_jcurve"
>title="J カーブ"
>abstract="最後のディメンション値に 60%、最初のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_inversej"
>title="逆 J 形"
>abstract="最初のディメンション値に 60%、最後のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_timedecay"
>title="タイムディケイ"
>abstract="コンバージョンに最も近いディメンション値に、最も多くのクレジットを付与します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_custom"
>title="カスタム"
>abstract="独自の位置ベースのアトリビューションの重み付けを定義します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_algorithmic"
>title="アルゴリズム"
>abstract="クレジットは、統計的アルゴリズムに基づいて動的に決定されます。"

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### ルックバックウィンドウ {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lookbackwindow"
>title="ルックバックウィンドウ"
>abstract="この設定により、各コンバージョンに適用されるデータアトリビューションの期間が決まります。"

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### アトリビューションの例 {#attribution-example}

次の例をご覧ください。

1. 9 月 15 日（PT）に、ある人物が有料検索広告を通じてサイトに到達した後、退出します。
1. 9 月 18 日（PT）、その人物は友人から取得したソーシャルメディアリンクを通じてサイトに再び到達します。 訪問者は買い物かごに複数の品目を追加しますが、何も購入しません。
1. 9 月 24 日に、マーケティングチームはこれらのユーザーに対し、買い物かご内の一部の品目に対するクーポンが記載されたメールを送信します。ユーザーはクーポンを適用しますが、他の複数のサイトを訪問して、利用可能なクーポンがあるかどうかを確認します。ディスプレイ広告で別の広告を見つけ、最終的に 50 ドルで購入します。

ルックバックウィンドウとアトリビューションモデルに応じて、チャネルは異なるクレジットを受け取ります。以下に例を示します。

* **ファーストタッチ** と **セッションルックバックウィンドウ** を使用して、アトリビューションでは 3 回目の訪問のみが表示されます。 電子メールとディスプレイ広告では、電子メールが先だったので、50 ドルの購入に対して 100％のクレジットが電子メールに与えられます。

* **ファーストタッチ** と **人物ルックバックウィンドウ** を使用して、アトリビューションは 3 回の訪問すべてを調べます。 有料検索が最初なので、50 ドルの購入に対して 100％のクレジットが与えられます。

* **線形** と **セッションルックバックウィンドウ** を使用して、クレジットをメールとディスプレイで分割します。 これらのチャンネルは両方とも 25 ドルずつクレジットを受け取っている。
**線形** と **人物ルックバックウィンドウ** を使用して、クレジットを、有料検索、ソーシャル、メール、ディスプレイに分割します。 各チャネルは、この購入に対して 12.50 ドルのクレジットを受け取ります。

* **J字型** と **人物ルックバックウィンドウ** を使用して、クレジットを、有料検索、ソーシャル、メール、ディスプレイに分割します。

   * 60％のクレジット（30 ドル）がディスプレイ広告に与えられます。
   * 20％のクレジット（10 ドル）が有料検索に与えられます。
   * 残りの 20％はソーシャルと電子メールの間で分割され、それぞれに 5 ドルが与えられます。

* **タイムディケイ** と **人物ルックバックウィンドウ** を使用して、クレジットを、有料検索、ソーシャル、メール、ディスプレイに分割します。 デフォルトである 7 日間の半減期を使用する場合：

   * 表示タッチポイントとコンバージョンの間のゼロ日のギャップ。`2^(-0/7) = 1`
   * 電子メールタッチポイントとコンバージョンの間のゼロ日のギャップ。`2^(-0/7) = 1`
   * ソーシャルタッチポイントとコンバージョンの間の 6 日間のギャップ。`2^(-6/7) = 0.552`
   * 有料検索タッチポイントとコンバージョンの間の 9 日間のギャップ。`2^(-9/7) = 0.41`
   * これらの値を正規化すると、次の結果になります。

      * ディスプレイ広告：33.8％、16.88 ドル
      * 電子メール：33.8％、16.88 ドル
      * ソーシャル：18.6％、9.32 ドル
      * 有料検索：13.8％、6.92 ドル

通常、整数を持つコンバージョンイベントは、クレジットが複数のチャネルに属する場合は分割されます。 例えば、線形アトリビューションモデルを使用して 1 つの注文に対して 2 つのチャネルが貢献している場合、両方のチャネルがその注文の 0.5 を受け取ります。 これらの部分指標は、すべてのユーザーについて合計され、レポート用に最も近い整数に丸められます。


>[!MORELIKETHIS]
>
>[ アトリビューションコンポーネントの設定 ](/help/data-views/component-settings/attribution.md)
>[パーティシペーション指標 ](participation-metric.md)
>

