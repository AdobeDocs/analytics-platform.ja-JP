---
title: Content Analytics JavaScript Library
description: Experience Platform Data Collection Tagsを使用せずにContent Analyticsを設定し、代わりにContent Analytics JavaScript ライブラリを使用する方法を説明します。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: 35abfb5b77384b16beaddab2554a7d48d10be012
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 4%

---


# Content Analytics JavaScript library

Adobe Content Analytics JavaScript ライブラリを使用すると、Experience Platform Edge Networkを介してAdobe Experience Platformにコンテンツデータを送信することで、web サイト上のコンテンツ関連イベントを追跡できます。 このライブラリは、Adobe Experience Platform タグを使用せずにContent Analyticsを実装する場合に使用します。

>[!NOTE]
>
>この記事は、web チャネル用のContent Analyticsに適用されます。


>[!PREREQUISITES]
>
>* `initializeContentLibrary`を呼び出す前に、Adobe Experience Platform Web SDK （Alloy）をページ上で初期化する必要があります。
>* Content Analytics ガイド付きコンフィギュレーションウィザードを実行して、Content Analyticsのコンフィギュレーションの前提条件を設定するために必要なすべての手順をガイドします。
>* ガイド付き設定が完了すると、JavaScriptの設定を使用できるようになります。


## インストール

ライブラリは、次の2つの方法でインストールできます。

### npm パッケージ

`npm`を使用してライブラリをインストールします。

1. コマンドラインで、次を使用します。

   ```bash
   npm install @adobe/content-analytics
   ```

1. ライブラリを読み込みます。

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### スクリプトタグ（CDN）

CDNから直接ライブラリを読み込みます。

1. [Web SDK JavaScript ライブラリ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/install/library)を初期化し、Content Analytics バンドルを読み込みます。

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   場所
   * `alloy/2.x.x`は、[Web SDK JavaScript ライブラリ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/install/library)を使用するバージョンを指します。
   * `content-analytics/1.x.x`は、Content Analytics SDK ライブラリを使用するバージョンを指します。

2. スタンドアロン ビルドでは、`window.contentAnalytics`が初期化関数として公開されます。


## データストリーム設定

`datastreamId` オプションは必須であり、有効なContent Analytics エクスペリエンスイベント データセットで設定されたExperience Platform サービスを持つデータストリームを参照する必要があります。 データストリームに関連付けられたサンドボックスが、別のContent Analytics設定にまだ関連付けられていないことを確認します。

環境ごとに個別のデータストリーム IDを指定できます。

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## エクスペリエンスのキャプチャと定義

エクスペリエンスの追跡を有効にし、web サイトでのエクスペリエンスの識別方法を制御します。 エクスペリエンスは、**ドメインの正規表現**&#x200B;と、一致するページ内で1つのエクスペリエンスを別のエクスペリエンスと区別するオプションの&#x200B;**クエリパラメーター**&#x200B;を組み合わせることで定義されます。

| オプション | タイプ | デフォルト | 説明 |
|--------|------|---------|-------------|
| `includeExperiences` | ブール型 | `false` | ページ/エクスペリエンスビューの追跡を有効にする |
| `experienceConfigurations` | 配列 | - | ドメイン正規表現とクエリパラメーターによるエクスペリエンスの定義 |

`experienceConfigurations`の各エントリは次を受け入れます。

| プロパティ | タイプ | 説明 |
|----------|------|-------------|
| `regEx` | string | ページ URLに一致するドメインの正規表現（例：`^(?!.*\b(store\|help\|admin)\b)`） |
| `queryParameters` | 配列 | 一致するページで値がエクスペリエンスを区別するクエリパラメーター名（例：`["outdoors", "patio", "kitchen"]`） |

### 例

ドメイン正規表現とクエリパラメーターを使用してエクスペリエンスのトラッキングを有効にする方法の例については、以下を参照してください。

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## イベントフィルタリング

正規表現を使用して、データ収集に含めるページ URLとアセット URLを制御します。 以下のパターン例を出発点として使用し、デプロイメント前に正規表現テスターでパターンを検証します。

| オプション | タイプ | デフォルト | 説明 |
|--------|------|---------|-------------|
| `pageUrlQualifier` | 文字列（正規表現） | - | このパターンに一致するURLを持つページのみをトラック |
| `assetUrlQualifier` | 文字列（正規表現） | - | このパターンに一致するURLを持つアセットのみを追跡 |
| `excludeURLsFromTracking` | 配列 | `[]` | トラッキングから除外するURL文字列のリスト |

### 例

Content Analyticsからドキュメントページを除外し、Content Analyticsの商品画像のみを考慮する方法の例については、以下を参照してください。

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
