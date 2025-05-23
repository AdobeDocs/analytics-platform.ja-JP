---
title: Content Analytics コンポーネント
description: ディメンション、（計算）指標、派生フィールドなど、特定のContent Analytics コンポーネントの詳細
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 22%

---

# Content Analytics コンポーネント

Content Analytics では、次に示すカテゴリのコンポーネント（ディメンション、（計算）指標、派生フィールド）を、Customer Journey Analyticsの既に使用可能なコンポーネントに追加します。

* [エクスペリエンスメタデータ](#experience-metadata)
* [エクスペリエンス属性](#experience-attributes)
* [エクスペリエンスイベント](#experience-events)
* [アセットメタデータ](#asset-metadata)
* [アセット属性](#asset-attributes)
* [Assets イベント](#asset-events)
* [計算指標](#calculated-metrics)

以下の表では、![AI 生成 ](/help/assets/icons/AI.svg) は、AI/ML で生成された属性/値のペアを示しています。

## エクスペリエンスメタデータ

| タイトル | 説明 | タイプ |
|---|---|---|
| エクスペリエンスチャネル | エクスペリエンスのチャネル。 | ディメンション |
| エクスペリエンス ID | エクスペリエンスの一意の ID。 | ディメンション |
| エクスペリエンスサムネール URL | エクスペリエンスのサムネールの URL。 | ディメンション |
| エクスペリエンスの水平方向の割合の深度 | エクスペリエンスの水平方向の深さのパーセンテージを定量化可能な値。 | Dimension<br/> 派生フィールド |
| エクスペリエンスの垂直方向の割合の深度 | エクスペリエンスの垂直方向の深さの定量化可能な値。 | Dimension<br/> 派生フィールド |

{style="table-layout:fixed"}



## エクスペリエンス属性

| タイトル | 説明 | タイプ |
|---|---|---|
| エクスペリエンス属性 | ![AI が生成されました ](/help/assets/icons/AI.svg) すべてのエクスペリエンス属性名と値の完全なリスト | Dimension<br> 派生フィールド |
| エクスペリエンスの読みやすさスコア | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスの読みやすさスコア | ディメンション |
| エクスペリエンスキーワード | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスのキーワード。 | Dimension<br> 派生フィールド |
| エクスペリエンス説得戦略 | ![AI が生成しました ](/help/assets/icons/AI.svg) 特定のエクスペリエンスに存在する説得力の戦略。 可能な値は、社会的同一性、社会的証明、権威、具体性、ドアの中の足、リアクタンスの克服、相互主義、アンカーと比較、社会的影響、希少性、および神人同形主義です。 | Dimension<br/> 派生フィールド |
| エクスペリエンスのナラティブ数 | ![AI が生成 ](/help/assets/icons/AI.svg) マーケターの視点からの関連性に基づいて、エクスペリエンスが構築している物語。 | Dimension<br/> 派生フィールド |
| エクスペリエンスのトーン | ![AI 生成 ](/help/assets/icons/AI.svg) マーケターの視点からの関連性に基づいて、エクスペリエンスが構築しているトーン | Dimension<br/> 派生フィールド |
| エクスペリエンスのマーケティング感情 | ![ 生成された AI](/help/assets/icons/AI.svg) エクスペリエンスの一部として使用されるテキストを読むときに、読者に呼び出される感情：緊急度、排他性、励まし、挑戦、好奇心、達成、信頼、単純さ、魅力的。 | Dimension<br/> 派生フィールド |
| エクスペリエンス絵文字数 | ![ 生成された AI](/help/assets/icons/AI.svg) エクスペリエンスの絵文字の数。 | 指標 |
| エクスペリエンスタグ数 | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスのハッシュタグの数。 | 指標 |
| エクスペリエンス文の数 | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスの文数。 | 指標 |
| エクスペリエンスストップワード割合 | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスのストップワード数。 | 指標 |
| エクスペリエンステキスト引用数 | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスのテキスト引用符の数。 | 指標 |
| エクスペリエンス語数 | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスの単語数。 | 指標 |
| エクスペリエンス 1 文あたりの語数 | ![AI が生成されました ](/help/assets/icons/AI.svg) エクスペリエンスの文あたりの単語数。 | 指標 |

{style="table-layout:fixed"}


## エクスペリエンスイベント

| タイトル | 説明 | タイプ |
|---|---|---|
| エクスペリエンスビュー数 | エクスペリエンスのビュー数の定量化可能な測定。 | 指標 |
| エクスペリエンスのクリック数 | エクスペリエンスのクリック数の定量化可能な測定。 | 指標 |

{style="table-layout:fixed"}


## アセットメタデータ

| タイトル | 説明 | タイプ |
|---|---|---|
| アセット ID | アセットの一意の ID。 アセットバイナリは一意性を決定します。 アセットバイナリが変更されると、id も変更されます。 一意の ID は URL にすることもできますが、ハッシュを作成することもできます。 | ディメンション |
| アセット HTML パス | アセットの連結されたHTML パス。 | ディメンション |
| アセットリンク URL | アセットに最も近いページアンカー。 | ディメンション |
| アセットの表示の幅 | コンテンツアセットの表示の幅。 | ディメンション |
| アセットの表示の高さ | コンテンツアセットの表示の高さ。 | ディメンション |
| アセットの絶対左 | コンテンツアセットの絶対左。 | ディメンション |
| アセットの絶対上 | コンテンツアセットの絶対上。 | ディメンション |

{style="table-layout:fixed"}


## アセット属性

| タイトル | 説明 | タイプ |
|---|---|---|
| アセット属性 | ![AI 生成 ](/help/assets/icons/AI.svg) すべてのアセット属性の名前と値の完全なリスト | Dimension<br> 派生フィールド |
| アセットの向き | ![AI により生成 ](/help/assets/icons/AI.svg) アセットの向き。 | Dimension<br/> 派生フィールド |
| アセットの全体的なトーン | ![ 生成された AI](/help/assets/icons/AI.svg) アセットの全体的なトーン。 | Dimension<br/> 派生フィールド |
| アセット前景色 | ![AI 生成 ](/help/assets/icons/AI.svg) アセットの前景色。 | Dimension<br/> 派生フィールド |
| アセット背景色 | ![AI により生成 ](/help/assets/icons/AI.svg) アセットの背景色 | Dimension<br/> 派生フィールド |
| アセットタグ | ![AI が生成されました ](/help/assets/icons/AI.svg) アセットのタグ。 | Dimension<br/> 派生フィールド |
| アセットシーン | ![AI 生成 ](/help/assets/icons/AI.svg) アセットのシーン。 | Dimension<br/> 派生フィールド |
| アセットオブジェクト | ![AI によって生成 ](/help/assets/icons/AI.svg) アセットのオブジェクト。 | Dimension<br/> 派生フィールド |
| アセットフォトスタイル | ![AI が生成されました ](/help/assets/icons/AI.svg) アセットの写真スタイル。 | Dimension<br/> 派生フィールド |
| アセット画像タイプ | ![AI が生成されました ](/help/assets/icons/AI.svg) アセットの画像タイプ。 使用可能な値は、photograph、sketch、painting、digital_cartoon、infographics、graphic_design、collage、software_screenshot です。 | Dimension<br/> 派生フィールド |
| アセットカメラ位置 | ![AI が生成されました ](/help/assets/icons/AI.svg) アセットのカメラ位置。 | Dimension<br/> 派生フィールド |
| アセットカメラ近接性 | ![AI が生成しました ](/help/assets/icons/AI.svg) アセットのカメラのプロキシ。 | Dimension<br/> 派生フィールド |
| アセット担当者カテゴリ | ![AI が生成されました ](/help/assets/icons/AI.svg) アセットの人物カテゴリ。 取り得る値は、person、man、woman、social group、crowd、people、boy、girl、kid です。 | Dimension<br/> 派生フィールド |
| アセットビジュアルコンテンツ密度 | ![AI が生成しました ](/help/assets/icons/AI.svg) アセットの視覚的なコンテンツ密度。 可能な値は、low、medium または high です。 コンテンツ密度が低い場合は、画像の単位面積当たりに存在する情報の量が少ないことを意味します。 | ディメンション |
| アセット視覚的注意の拡散 | ![AI が生成 ](/help/assets/icons/AI.svg) アセットの視覚的な注目の広がり。 可能な値は、low、medium または high です。 アテンションの広がりは、視聴者の注意が画像の異なる部分に分割される度合いを指します。 | Dimension<br/> 派生フィールド |
| アセット照明条件 | ![AI 生成 ](/help/assets/icons/AI.svg) アセットの照明条件。 取り得る値は、ゴールデンアワー、ブルーアワー、正午、曇り、夜、ハイキー、ローキー、デイライト、白熱灯、蛍光灯、カラフルおよびスタジオです。 | Dimension<br/> 派生フィールド |
| アセットカメラ設定 | ![AI 生成 ](/help/assets/icons/AI.svg) アセットのカメラ設定。 可能な値：速いシャッタースピード、長い露出。 ボケブラー、モーションブラー、チルトシフトブラー、フラッシュ、広角、白黒、シュール、二重露光、マクロ、ノーマルモード。 | Dimension<br/> 派生フィールド |

{style="table-layout:fixed"}


## アセットイベント

| タイトル | 説明 | タイプ |
|---|---|---|
| アセットビュー数 | アセットの表示数の定量化可能な測定。 | 指標 |
| アセットのクリック | アセットのクリック数の定量化可能な測定。 | 指標 |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## 計算指標

| タイトル | 説明 | タイプ |
|---|---|---|
| アセットのクリックスルー率 | アセットのクリック数/アセットビュー数 | 計算指標 |
| エクスペリエンスのクリックスルー率 | エクスペリエンスクリック数/エクスペリエンスビュー数 | 計算指標 |

{style="table-layout:fixed"}

