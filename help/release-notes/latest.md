---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7737a285c701946dcf92c2610c1918022e05de36
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 66%

---

# 最新の Customer Journey Analytics（CJA）リリースノート（2023年4月）

**最終更新日**：2023年4月12日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 主な機能と更新

| 機能 | 説明 | [ロールアウトの開始](/help/release-notes/releases.md) | [一般公開](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Analytics ソースコネクタストリーミングの行／列フィルタリング** | Adobe Experience Platform の Analytics ソースコネクタを使用すると、[リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)におけるプロファイルへの入力に使用される Analytics データをフィルタリングできるようになりました。行レベルのフィルタリングは、プロファイルに関連付けられたイベントの数を減らすのに役立ちます。列レベルのフィルタリングは、イベント自体の豊富さを軽減するのに役立つので、プロファイル使用権限の行使を最適化できます。このフィルタリングは、リアルタイム顧客プロファイルと [ID サービス](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja)に送信されるデータにのみ適用されます。**フィルタリングは、Customer Journey Analytics などのアプリケーションで使用するためにデータレイクに送信されるデータには影響しません**。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja#filtering-for-profile) | 該当なし | 2023年3月29日（PT） |
| **Analysis Workspace でのデータ要素** | データ要素は、ユーザーと管理者の両方が CJA 環境のコンポーネント（ディメンションや指標）を追跡し、よりよく理解するのに役立ちます。[詳細情報](/help/components/data-dictionary/data-dictionary-overview.md) | 2023年3月8日（PT） | 2023年3月29日（PT） |
| **プロジェクトのリンク共有（ログインは不要）** | <p>Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。 これには、組織外のユーザーや、組織内で CJA 用にプロビジョニングされていないユーザーとの共有が含まれます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>この機能はデフォルトで有効になっており、システム管理者が無効にできます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023 年 5 月 4 日 | 2023年6月 |
| **Adobe製品分析 — プライベートベータ版アクセスのみ** | 2023 年 3 月 22 日に、Adobeは、Customer Journey Analyticsでクロスチャネルのデータとインサイトを操作する新しい方法であるAdobeProduct Analytics を発表しました。 これらの新機能を使用すると、製品チームは、ガイド付き分析ワークフローを通じて、製品エクスペリエンスに関するデータやインサイトをセルフサービスでき&#x200B;ます。 チームが実行できる操作：<ul><li>ユーザーエンゲージメントのパターンの経時的な&#x200B;把握</li><li>ユーザーベースの増加を&#x200B;分析</li><li>一連の手順を通じて摩擦の領域を特定する&#x200B;</li><li>機能リリースの影響を測定&#x200B;</li><li>製品に関する生涯のジャーニーを通じてエンゲージメントと育成に役立つ有意義なセグメントを見つけ&#x200B;る</li><li>Analysis Workspaceで詳細な分析やアナリストとのコラボレーションを可能にする、その他の機能を利用できま&#x200B;す。</li></ul>CJA のお客様で、プライベートベータ版への参加を希望される場合は、担当のAdobeアカウントチームにお問い合わせください。 [詳細情報](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | 該当なし | 2023 年 7 月 18 日 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-313118;AN-313390;AN-314135;AN-316381;AN-316811

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | 該当なし | 該当なし |

{style="table-layout:auto"}

## 関連リソース

* [2023年の以前の CJA リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
