---
title: アトリビューションの概要
description: 成功イベントのクレジットを複数のディメンション項目に関連付ける概念について説明します。
feature: Attribution
role: User, Admin
exl-id: 47a3523b-d9eb-4272-84b8-090b921cba13
TQID: https://experienceleague.adobe.com/ncY8TuwUb3duwfK3n8u69eyXWUDzI5OMF-AACOoDmIY
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 453
ht-degree: 96%

---

# アトリビューションの概要

アトリビューションを使用すると、分析者は、成功イベントのクレジットをディメンション項目がどのように取得するかをカスタマイズできます。 例：

1. サイトの訪問者が、いずれかの製品ページへの有料検索リンクをクリックします。 商品を買い物かごに追加しますが、購入はしません。
2. 次の日に、訪問者は友達の 1 人からのソーシャルメディアの投稿を見てリンクをクリックし、購入を完了します。

一部のレポートでは、注文を有料検索に関連付けることが望まれるかもしれません。 他のレポートでは、注文を「ソーシャル」に関連付けることが望まれるかもしれません。 アトリビューションを使用すると、このレポートの側面を制御できます。 Adobe Analytics Ultimate、Prime、Select、Foundation ですべての組織で利用できます。 アドビとの契約のタイプが不明な場合は、組織のアドビのアカウントチームにお問い合わせください。

## アトリビューションの価値

特定のカスタマージャーニーは、線形ではなく、予測不可能な場合も多くあります。 各顧客は、それぞれのペースで進みます。多くの場合、ダブルバック、停止、再起動、または他の非線形動作に関与します。 このような生物的なアクションにより、カスタマージャーニー全体を通したマーケティング活動の影響を把握することが難しくなっています。 また、複数のチャネルのデータを結び付ける作業の妨げにもなります。

<!--
![Attribution problem](assets/attribution_iq_problem.png)
-->

Adobe Analytics を使用すると、以下が可能になるので、アトリビューションを強化できます。

* 有料メディアに勝るアトリビューションの定義：マーケティングキャンペーンだけでなくあらゆるディメンション、指標、チャネル、イベントをモデルに適用できます（例：内部検索）。
* 無制限のアトリビューションモデル比較の利用：必要な数のモデルを動的に比較できます。
* 実装の変更の回避：レポート時間処理とコンテキスト対応セッションで、カスタマージャーニーのコンテキストを実行時間に組み込んで適用できます。
* アトリビューションシナリオに最適なセッションの作成。
* アトリビューションのセグメント別分類：すべての重要なセグメントにわたってマーケティングチャネルのパフォーマンスを容易に比較できます（例：新規顧客とリピート顧客、製品 X と製品 Y、ロイヤルティまたは CLV）。
* チャネルのクロスオーバー分析およびマルチタッチ分析の調査：ベン図やヒストグラムを使用でき、アトリビューション結果のトレンドを追跡できます。
* 主要なマーケティングシーケンスの視覚的分析：コンバージョンにつながったパスをマルチノードのフローおよびフォールアウトビジュアライゼーションで視覚的に調査できます。
* 計算指標の構築：任意の数のアトリビューション割り当て方法を使用できます。

## 機能

アトリビューションは、次の機能で構成されます。

* [アトリビューションパネル](/help/analysis-workspace/c-panels/attribution.md)：任意のディメンションと指標を使用して、様々なアトリビューションモデルとすばやく比較できます。
* [指標へのアトリビューションの適用](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)：プロジェクト内の任意の指標にデフォルト以外のアトリビューションを使用します。
* [分類へのアトリビューションの適用](/help/components/dimensions/t-breakdown-fa.md#apply-attribution-models-to-breakdowns)：分類にデフォルト以外のアトリビューションを使用します。
* [アトリビューションモデルの比較](/help/components/apply-create-metrics.md#compare-metrics-with-different-attribution-models)：指標ごとに異なるアトリビューションモデルがどのように比較されるかをすばやく確認できます。

## ビデオ


<!--  
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in Freeform tables](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

<!-- 
Attribution IQ 
>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in calculated metrics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/attribution-iq-in-calculated-metrics){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [アトリビューションパネルの使用](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/panels/build-the-attribution-panel){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


<!-- 
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding side-by-side comparisons of Attribution models](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/adding-side-by-side-comparisons-of-attribution-iq-models){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

