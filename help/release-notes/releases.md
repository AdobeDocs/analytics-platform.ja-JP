---
description: Customer Journey Analytics の継続的な機能リリース戦略を説明します
title: Customer Journey Analytics の機能リリース戦略
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
TQID: https://experienceleague.adobe.com/KTMrEfZBHkdpRHlEGj8s4hfAtlPPjAqQrh6mtS-yAWM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 90%

---

# Customer Journey Analytics の機能リリース戦略

Customer Journey Analytics リリースは、機能のデプロイメントに対するスケーラブルかつ段階的なアプローチを可能にする継続的な配信モデルに基づいて動作します。

## リリース方法

[!UICONTROL Analysis Workspace] では、機能フラグ（「切替スイッチ」とも呼ばれます）を使用して新機能の表示/非表示を制御し、完全リリース前の制御スケールテストを行うことができます。 このリリース戦略には、次のフェーズが含まれます。

* **制限付きテスト**：段階的なリリースは、アドビの内部ユーザーによるテストで始まります。 その後、少数の顧客アカウントのグループに公開して、機能が顧客のニーズと期待に応えているかどうかを確認します。

* **ロールアウトの開始**：段階的なリリースのロールアウトは限定的テストフェーズから始まります。 リリースはその後、数か月かけて顧客への可用性を 0％から 100％に拡張していきます。 段階的な展開は、CX企業レベルで行われるため、組織内の権限のあるユーザーはすべて同じエクスペリエンスを受け取ることができます。

* **一般提供（GA）**：この機能は、資格のあるCX Enterprise組織の100%が利用でき、機能リリースが完了しました。

各機能リリースにより、RTP から GA までのタイムラインが変わる場合があります。 目標は、リリース開始（RTP）から 2 か月以内に機能が GA になるように、リリースを短く保つことです。

## 機能フラグ

機能フラグは、リリース時の新機能の表示を制御するために使用します。 アドビでは、リリース時に最適なエクスペリエンスを実現するために、組織のファイアウォール経由で `app.launchdarkly.com` を許可することをお勧めします。 これらのフラグは、機能がすべてのユーザーにリリースされた後に削除されます。 詳しくは、[Customer Journey Analytics で使用されるドメイン](../technotes/domains.md)を参照してください。

アクティブな機能フラグは、**ヘルプ／Workspace について／アクティブな機能フラグ**&#x200B;からいつでも表示できます。

## メリット

各段階的なリリースにより、アドビはソフトウェアのデプロイメントプロセスをより適切に拡張でき、一般公開の前に機能を完全に強化できます。 また、毎月の固定リリースウィンドウを守らずに、機能が使用可能になったらすぐにリリースできます。

## よくある質問（FAQ）

| 質問 | 回答 |
| --- | --- |
| 機能への早期アクセスをリクエストできますか？ | いいえ。 早期アクセスは許可されません。<br>Analytics の初期の概念をテストする場合は、[Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=ja) で業界をリードする革新的なアイデアに対するフィードバックを提供してみることをお勧めします。 |
| このリリース戦略は、機能へのアクセスに影響を与えますか。 | いいえ。 機能が GA に達すると、その機能が Analytics パッケージに含まれている場合はアクセスできます。 |
