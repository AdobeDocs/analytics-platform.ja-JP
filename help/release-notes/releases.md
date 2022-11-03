---
description: Customer Journey Analytics の継続的な機能リリース戦略を説明します
title: Customer Journey Analytics 機能リリース
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: 44a140fdd5069cbe806f694377802215bcf50b31
workflow-type: ht
source-wordcount: '359'
ht-degree: 100%

---

# Customer Journey Analytics 機能リリース

Customer Journey Analytics リリースは、機能のデプロイメントに対するスケーラブルかつ段階的なアプローチを可能にする継続的な配信モデルに基づいて動作します。

## リリース方法

[!UICONTROL Analysis Workspace] では、機能フラグ（「トグル」とも呼ばれます）を使用して新機能の表示/非表示を制御し、完全リリース前の制御スケールテストを行うことができます。このリリース戦略には、次のフェーズが含まれます。

* **ロールアウトの開始**：段階的なリリースのロールアウトは、アドビの内部ユーザーによる限定的テストから始まります。リリースはその後、数か月かけて顧客への可用性を 0％から 100％に拡張していきます。Experience Cloud 組織レベルで展開が段階的に行われるので、組織内の権利を持つすべてのユーザーは同じエクスペリエンスを受け取ります。

* **GA (General Availability)**：この機能は、権利を付与されている Experience Cloud の組織の 100% が利用でき、機能のリリースが完了しました。

各機能リリースにより、RTP から GA までのタイムラインが変わる場合があります。目標は、リリース開始（RTP）から 2 か月以内に機能が GA になるように、リリースを短く保つことです。

## 機能フラグ

機能フラグは、リリース時の新機能の表示を制御するために使用します。リリース時に最適なエクスペリエンスを得るために、`app.launchdarkly.com` をファイアウォールの[許可リスト](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=ja)に追加することを推奨します。GA に達した直後に、フラグが削除されます。

アクティブな機能フラグは、**ヘルプ／Workspace について／アクティブな機能フラグ**&#x200B;からいつでも表示できます。

## メリット

各段階的なリリースにより、アドビはソフトウェアのデプロイメントプロセスをより適切に拡張でき、一般公開の前に機能を完全に強化できます。また、毎月の固定リリースウィンドウを守らずに、機能が使用可能になったらすぐにリリースできます。

## よくある質問（FAQ）

| 質問 | 回答 |
| --- | --- |
| 機能への早期アクセスをリクエストできますか？ | いいえ。早期アクセスは許可されません。<br>Analytics の初期の概念をテストする場合は、[Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=ja) で業界をリードする革新的なアイデアに対するフィードバックを提供してみることをお勧めします。 |
| このリリース戦略は、機能へのアクセスに影響を与えますか。 | いいえ。機能が GA に達すると、その機能が Analytics パッケージに含まれている場合はアクセスできます。 |
