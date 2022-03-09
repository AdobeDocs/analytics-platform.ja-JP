---
description: Customer Journey Analytics の継続的な機能リリース戦略を説明します
title: Customer Journey Analytics 機能リリース
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: f2c82f54ec534603539327597d5f4c4ec875d44c
workflow-type: ht
source-wordcount: '379'
ht-degree: 100%

---

# Customer Journey Analytics 機能リリース

Customer Journey Analytics リリースは、機能のデプロイメントに対するスケーラブルかつ段階的なアプローチを可能にする継続的な配信モデルに基づいて動作します。

## リリース方法

[!UICONTROL Analysis Workspace] では、機能フラグ（「トグル」とも呼ばれます）を使用して新機能の表示/非表示を制御し、完全リリース前の制御スケールテストをおこなうことができます。このリリース戦略には、次のフェーズが含まれます。

* **実稼働環境（RTP）にリリース**: コードが実稼動環境にリリースされ、Analysis Workspace での機能の表示がオフになっています。この機能は、CJA API で利用できる場合があります。

* **制限付きテスト**：段階的なリリースは、アドビの内部ユーザーによるテストで始まります。このリリースでは、数か月の間に 0% から 100% の可用性に拡張されます。Experience Cloud 組織レベルで展開が段階的に行われるので、組織内の権利を持つすべてのユーザーは同じエクスペリエンスを受け取ります。

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
| 機能への早期アクセスをリクエストできますか？ | いいえ。早期アクセスは許可されません。<br>Analytics の初期の概念をテストする場合は、[Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=ja) で業界をリードする革新的なアイデアに対するフィードバックを提供してみることをお勧めします 。 |
| このリリース戦略は、機能へのアクセスに影響を与えますか。 | いいえ。機能が GA に達すると、その機能が Analytics パッケージに含まれている場合はアクセスできます。 |
