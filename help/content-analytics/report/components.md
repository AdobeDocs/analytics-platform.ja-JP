---
title: Content Analytics コンポーネント
description: ディメンション、（計算）指標および派生フィールドなど、特定の Content Analytics コンポーネントの詳細
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 100%

---

# Content Analytics コンポーネント

Content Analytics では、Customer Journey Analytics で既に使用可能なコンポーネントに、次のコンポーネントのカテゴリ（ディメンション、（計算）指標、派生フィールド）を追加します。

* [エクスペリエンスメタデータ](#experience-metadata)
* [エクスペリエンス属性](#experience-attributes)
* [エクスペリエンスイベント](#experience-events)
* [アセットメタデータ](#asset-metadata)
* [アセット属性](#asset-attributes)
* [アセットイベント](#asset-events)
* [計算指標](#calculated-metrics)

以下の表では、![AI 生成](/help/assets/icons/AI.svg)は、AI/ML で生成された属性／値のペアを示しています。

## エクスペリエンスメタデータ

| タイトル | 説明 | タイプ |
|---|---|---|
| エクスペリエンスチャネル | エクスペリエンスのチャネル。 | ディメンション |
| エクスペリエンス ID | エクスペリエンスの一意の ID。 | ディメンション |
| エクスペリエンスサムネール URL | エクスペリエンスのサムネイルの URL。 | ディメンション |
| エクスペリエンスの水平方向の割合の深度 | エクスペリエンスの水平方向の割合の深度を定量化できる値。 | ディメンション<br/>派生フィールド |
| エクスペリエンスの垂直方向の割合の深度 | エクスペリエンスの垂直方向の割合の深度を定量化できる値。 | ディメンション<br/>派生フィールド |

{style="table-layout:fixed"}



## エクスペリエンス属性

| タイトル | 説明 | タイプ |
|---|---|---|
| エクスペリエンス属性 | ![AI による生成](/help/assets/icons/AI.svg) すべてのエクスペリエンス属性名と値の完全なリスト | ディメンション<br>派生フィールド |
| エクスペリエンスの読みやすさスコア | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスの読みやすさスコア | ディメンション |
| エクスペリエンスキーワード | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスのキーワード。 | ディメンション<br>派生フィールド |
| エクスペリエンス説得戦略 | ![AI による生成](/help/assets/icons/AI.svg) 特定のエクスペリエンスに存在する説得戦略。可能な値として、社会的同一性、社会的証明、権威、具体性、段階的要請、リアクタンスの克服、相互主義、固着と比較、社会的影響、希少性および擬人化があります。 | ディメンション<br/>派生フィールド |
| エクスペリエンスのナラティブ数 | ![AI による生成](/help/assets/icons/AI.svg) マーケターの視点からの関連性に基づいてエクスペリエンスが構築されるナラティブ。 | ディメンション<br/>派生フィールド |
| エクスペリエンスのトーン | ![AI による生成](/help/assets/icons/AI.svg) マーケターの視点からの関連性に基づいてエクスペリエンスが構築しているトーン。 | ディメンション<br/>派生フィールド |
| エクスペリエンスのマーケティング感情 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスの一部として使用されるテキストを読むときに、読者に喚起される感情：緊急性、排他性、励まし、挑戦、好奇心、達成、信頼、単純さ、魅力。 | ディメンション<br/>派生フィールド |
| エクスペリエンス絵文字数 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスの絵文字の数。 | 指標 |
| エクスペリエンスハッシュタグ数 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスのハッシュタグの数。 | 指標 |
| エクスペリエンス文の数 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスの文の数。 | 指標 |
| エクスペリエンスストップワード割合 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスのストップワードの数。 | 指標 |
| エクスペリエンステキスト引用数 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスのテキスト引用の数。 | 指標 |
| エクスペリエンス語数 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスの単語の数。 | 指標 |
| エクスペリエンス 1 文あたりの語数 | ![AI による生成](/help/assets/icons/AI.svg) エクスペリエンスの文あたりの単語の数。 | 指標 |

{style="table-layout:fixed"}


## エクスペリエンスイベント

| タイトル | 説明 | タイプ |
|---|---|---|
| エクスペリエンスビュー数 | エクスペリエンスのビューの数の定量化可能な測定。 | 指標 |
| エクスペリエンスのクリック数 | エクスペリエンスのクリック数の定量化可能な測定。 | 指標 |

{style="table-layout:fixed"}


## アセットメタデータ

| タイトル | 説明 | タイプ |
|---|---|---|
| アセット ID | アセットの一意の ID。アセットバイナリは一意性を決定します。アセットバイナリが変更されると、ID も変更されます。一意の ID は URL にすることができますが、ハッシュを作成することもできます。 | ディメンション |
| アセット HTML パス | アセットの連結された HTML パス。 | ディメンション |
| アセットリンク URL | アセットに最も近いページアンカー。 | ディメンション |
| アセット表示の幅 | コンテンツアセット表示の幅。 | ディメンション |
| アセット表示の高さ | コンテンツアセット表示の高さ。 | ディメンション |
| アセットの絶対左 | コンテンツアセットの絶対左。 | ディメンション |
| アセットの絶対上 | コンテンツアセットの絶対上。 | ディメンション |

{style="table-layout:fixed"}


## アセット属性

| タイトル | 説明 | タイプ |
|---|---|---|
| アセット属性 | ![AI による生成](/help/assets/icons/AI.svg) すべてのアセット属性の名前と値の完全なリスト | ディメンション<br>派生フィールド |
| アセットの向き | ![AI による生成](/help/assets/icons/AI.svg) アセットの向き。 | ディメンション<br/>派生フィールド |
| アセットの全体的なトーン | ![AI による生成](/help/assets/icons/AI.svg) アセットの全体的なトーン。 | ディメンション<br/>派生フィールド |
| アセット前景色 | ![AI による生成](/help/assets/icons/AI.svg) アセットの前景色。 | ディメンション<br/>派生フィールド |
| アセット背景色 | ![AI による生成](/help/assets/icons/AI.svg) アセットの背景色。 | ディメンション<br/>派生フィールド |
| アセットタグ | ![AI による生成](/help/assets/icons/AI.svg) アセットのタグ。 | ディメンション<br/>派生フィールド |
| アセットシーン | ![AI による生成](/help/assets/icons/AI.svg) アセットのシーン。 | ディメンション<br/>派生フィールド |
| アセットオブジェクト | ![AI による生成](/help/assets/icons/AI.svg) アセットのオブジェクト。 | ディメンション<br/>派生フィールド |
| アセットフォトスタイル | ![AI による生成](/help/assets/icons/AI.svg) アセットのフォトスタイル。 | ディメンション<br/>派生フィールド |
| アセット画像タイプ | ![AI による生成](/help/assets/icons/AI.svg) アセットの画像タイプ。使用可能な値は、photograph、sketch、painting、digital_cartoon、infographics、graphic_design、collage、software_screenshot です。 | ディメンション<br/>派生フィールド |
| アセットカメラ位置 | ![AI による生成](/help/assets/icons/AI.svg) アセットのカメラ位置。 | ディメンション<br/>派生フィールド |
| アセットカメラ近接性 | ![AI による生成](/help/assets/icons/AI.svg) アセットのカメラの近接性。 | ディメンション<br/>派生フィールド |
| アセット人物カテゴリ | ![AI による生成](/help/assets/icons/AI.svg) アセットの人物カテゴリ。使用可能な値は、person、man、woman、social group、crowd、people、boy、girl、kid です。 | ディメンション<br/>派生フィールド |
| アセットビジュアルコンテンツ密度 | ![AI による生成](/help/assets/icons/AI.svg) アセットの視覚的なコンテンツ密度。使用可能な値は、low、medium または high です。コンテンツ密度が低い場合は、画像の単位面積当たりに存在する情報の量が少ないことを意味します。 | ディメンション |
| アセット視覚的注意の拡散 | ![AI による生成](/help/assets/icons/AI.svg) アセットの視覚的な注目の広がり。使用可能な値は、low、medium または high です。注意の拡散は、視聴者の注意が画像の様々な部分に分割される度合いを指します。 | ディメンション<br/>派生フィールド |
| アセット照明条件 | ![AI による生成](/help/assets/icons/AI.svg) アセットの照明条件。使用可能な値は、golden hour、blue hour、midday、overcast、night、high-key、low-key、daylighting、incandescent、fluorescent、colorful、studio です。 | ディメンション<br/>派生フィールド |
| アセットカメラ設定 | ![AI による生成](/help/assets/icons/AI.svg) アセットのカメラ設定。使用可能な値は、fast shutter speed、long exposure、bokeh blur、motion blur、tilt-shift blur、flash、wide-angle、black and white、surreal、double-exposure、macro、normal mode です。 | ディメンション<br/>派生フィールド |

{style="table-layout:fixed"}


## アセットイベント

| タイトル | 説明 | タイプ |
|---|---|---|
| アセットビュー数 | アセットのビュー数の定量化可能な測定。 | 指標 |
| アセットのクリック数 | アセットのクリック数の定量化可能な測定。 | 指標 |

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
| アセットのクリックスルー率 | アセットクリック数／アセットビュー数 | 計算指標 |
| エクスペリエンスのクリックスルー率 | エクスペリエンスクリック数／エクスペリエンスビュー数 | 計算指標 |

{style="table-layout:fixed"}

