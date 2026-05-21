---
title: Content Analytics Data Collection
description: Content Analyticsがどのようにデータを収集するかをご確認ください。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
TQID: https://experienceleague.adobe.com/B2j6BrXAHMu-3LKI61LbK01i-UdpMlELsqYSfAWYDCo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 1093
ht-degree: 52%

---


# Content Analytics データ収集

この記事では、Content Analytics でデータを収集する方法について詳しく説明します。

## 定義

この記事のコンテキストでは、次の定義を使用します。

* **エクスペリエンス**:
   * **web** チャネルの場合、エクスペリエンスはweb ページ全体のテキストコンテンツとして定義されます。 データ収集の場合、Content Analyticsはページ URLに基づくエクスペリエンス IDを記録します。 その後、ページ上のテキストが取得サービスを通じて取得されます。
   * **mobile** チャネルでは、Adobe Experience Platform Mobile SDKのContent Analytics拡張機能を使用して、モバイルアプリでエクスペリエンスが定義および追跡されます。
* **エクスペリエンス ID**:
   * Web チャネルの場合、エクスペリエンス IDは、関連するURL （ベース URLとページ上のコンテンツを駆動するパラメーター）と[&#x200B; エクスペリエンス バージョン &#x200B;](manual.md#versioning)の一意の組み合わせです。
      * [設定](configuration.md)の一部として、特定の完全な URL に関連するパラメーターを指定します。
      * 使用する[バージョン識別子](manual.md#versioning)を定義して、エクスペリエンスに対する変更を適切に収集します。
   * **mobile** チャネルの場合、エクスペリエンス IDは、`registerExperience` API呼び出しを使用したの戻り値です。
* **アセット**：画像。 Content Analytics では、アセット URL を記録します。
* **アセット ID**：アセットの URL。
* **関連 URL**：ベース URL と、ページ上のコンテンツを駆動するパラメーター。


## 機能

Content Analyticsでは、コンテンツイベントデータを収集するには、Experience Platform Edge Network Web SDK（web チャネル用）とExperience Platform Edge Network モバイルSDK（モバイルチャネル用）が必要です。 このイベントデータは、Experience Platform Edge Network（Web SDK、モバイルSDK、またはServer API）またはAdobe AppMeasurementなどのAnalytics ソースコネクタを使用して、既存の行動データと組み合わされます。

Content Analytics ライブラリでは、次の場合にデータを収集します。

* Content Analyticsは、ページに読み込まれるか、モバイルアプリ内で使用されるタグライブラリに含まれています。
* ページ URLとアセット URLは、含まれるタグライブラリの一部である[Content Analytics web拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}で設定されます。
* アセット URL、アセットの場所またはエクスペリエンスの場所は、[Content Analytics モバイル拡張機能](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)では除外されません。


## Content Analytics イベント

この節では、web Content Analytics イベントの詳細について説明します。 モバイル Content Analytics イベントの詳細については、[&#x200B; エクスペリエンスのトラッキング &#x200B;](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/)を参照してください。
Content Analytics イベントは、以下で構成されます。

* 標準フィールド
   * タイムスタンプ
   * ID
* エクスペリエンスビュー数（存在する場合と設定されている場合）
* エクスペリエンスクリック数（存在する場合と設定されている場合）
* アセットビュー数（存在する場合と設定されている場合）
* アセットクリック数（存在する場合と設定されている場合）

Content Analytics イベントは、次のシーケンスとして収集されます。

1. [録画ビューまたはクリック &#x200B;](#recorded-view-or-click)。
1. Content Analytics イベントを送信するための[トリガー](#trigger-to-send-a-content-analytics-event)。

コンテンツ分析では、ビューまたはクリックを個別に収集し、そのビューまたはクリックの直後のイベントを収集する代わりに、シーケンスを反映するのにこの方法でデータを収集します。 また、コンテンツ分析データを収集するこの方法では、収集されるデータの量も削減されます。

### 記録されたビューまたはクリック

アセットビューは、次の場合に記録されます。

* Content Analytics 拡張機能の設定ごとにアセットが除外されていない。
* アセットの 75％が表示される。
* そのアセットがこのページにまだ記録されていない。

アセットクリックは、次の場合に記録されます。

* アセットが表示される。
* Content Analytics 拡張機能の設定ごとにアセットが除外されていない。
* リンクであるアセットを直接クリックすると、別のページに移動します。

エクスペリエンスビューは、次の場合に記録されます。

* エクスペリエンスが、Content Analytics 設定で有効になっている。

エクスペリエンスクリックは、次の場合に記録されます。

* 有効なリンクをクリックすると、エクスペリエンスがトリガーされます。


### コンテンツ分析イベントを送信するトリガー

ページから送信されるネットワークリクエストの数を減らすために、Content Analyticsは情報を収集しますが、その情報をすぐに送信しません。 コンテンツインタラクション情報が収集され、その情報を含むイベントは、次のいずれかのトリガーが発生した場合にのみ送信されます。

* Web SDKまたはAdobe AppMeasurementがイベントを送信します。
* 表示が非表示に変更される。例：
   * ページのアンロード
   * タブを切り替え
   * ブラウザーを最小化
   * ブラウザーを閉じる
   * 画面をロック
* URL が変更され、関連する URL が変更される。
* 記録され、送信可能なアセットビューは32を超えています。

>[!NOTE]
>
>追加のコンテンツ分析イベントは、セッションまたはページ内のイベント数に基づくバウンス率定義に影響を与える可能性が高くなります。
>

## ID

この節では、Content AnalyticsでのIDの処理方法について説明します。

### Web

Content Analyticsは、次の方法でweb チャネルのIDを処理します。

* ECID は、コンテンツ分析スキーマの `identityMap` 部分に自動的に入力されます。
* `identityMap` に他の ID 値が必要な場合は、Web SDK 拡張機能内の `onBeforeEventSend` コールバックでこれらの値を設定する必要があります。
* スキーマはシステム所有なので、フィールドベースのステッチはサポートされていません。 したがって、フィールドベースのステッチをサポートするために、スキーマに別のフィールドを追加することはできません。


Content Analytics ID データとWeb SDK データ ID データがフィールドレベルで正しく結合されていることを確認するには、イベント send[&#128279;](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"} コールバックの前にWeb SDK を変更します。

1. Adobe Experience Platform Web SDK 拡張機能と Adobe コンテンツ分析拡張機能を含む&#x200B;**[!UICONTROL タグ]**&#x200B;プロパティに移動します。
1. ![プラグ](/help/assets/icons/Plug.svg) **[!UICONTROL 拡張機能]**&#x200B;を選択します。
1. **[!UICONTROL Adobe Experience Platform Web SDK]** 拡張機能を選択します。
1. 「**[!UICONTROL 設定]**」を選択します。
1. 「**[!UICONTROL SDK インスタンス]**」セクションで、「**[!UICONTROL データ収集]** - **[!UICONTROL 「イベント送信の前にオン」コールバック]**」までスクロールします。

   ![「イベント送信の前にオン」コールバック](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. 「**[!UICONTROL &lt;/> 「イベント送信の前にオン」コールバックコードを指定]**」を選択します。
1. 次のコードを追加します。

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![「イベント送信の前にオン」コールバック](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. 「**[!UICONTROL 保存]**」を選択してコードを保存します。
1. 「**[!UICONTROL 保存]**」を選択して拡張機能を保存します。
1. タグプロパティの更新を[公開](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)します。


### モバイル

モバイルアプリでIDを操作する方法について詳しくは、[Experience Cloud ID サービス拡張機能](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/)および[Edge Network モバイル拡張機能](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)のIDを参照してください。

モバイルアプリでIDが変更されるとすぐに、Content Analytics データの現在の[&#x200B; バッチ &#x200B;](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings)がリセットされ、新しいIDのContent Analytics データの新しいコレクションが開始されます。

## スキーマ

Experience Platformは、特定のContent Analytics スキーマに基づいて、データセット内のContent Analytics データを収集します。 参照スキーマは、次の記事で公開されています。

* [デジタルアセットスキーマ](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [デジタルエクスペリエンスのスキーマ](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [エクスペリエンスイベントコンテンツスキーマ](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
