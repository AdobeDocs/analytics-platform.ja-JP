---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e2a372d6e1fcbcfc26a63ddc804a592d6ee1725
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 99%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年5月）

**最終更新日**：2024年6月4日（PT）

このリリースノートは、2024年5月15日（PT）～2024年6月のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **BI 拡張機能** | BI 拡張機能を使用すると、Customer Journey Analytics で定義したデータビューへの SQL アクセスが可能になります。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024年5月15日（PT） |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをよりすばやく見つけることができます。</li></ul> <p>（更新されたドキュメントへのリンクを添付）</p> |  | 2024年5月下旬～6月上旬 |
| **Customer Journey Analytics 向けの AI アシスタント** | Customer Journey Analytics UI で自然言語の質問をし、Customer Journey Analytics ドキュメントに基づいて回答を得ることができます。 <p>（更新されたドキュメントへのリンクを添付）</p> | | 2024年6月6日（PT） |
| **ストリーミングメディア：Web SDK を使用した Adobe Experience Platform Edge Network への web データの送信** | Adobe Experience Platform Web SDK を使用して、ストリーミングメディア web データを Adobe Experience Platform Edge Network に送信できるようになりました。これにより、よりパーソナライズされたキャンペーンを作成し、よりパーソナライズされたコンテンツを提供できるので、レポート対象のトラッキングデータが増加します。<p>この機能強化により、Customer Journey Analytics、RT-CDP、AJO、イベント転送など、すべてのプラットフォームソリューションにわたる web 実装に統一された収集方法が提供されます。以前は、ストリーミングメディア web データを Edge Network に送信する唯一の方法は、Media Edge API を使用することでした。 <p>[詳細情報](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 2024年5月29日（PT） |
| **派生フィールド - 数学関数** | データビュー内で簡単な数学演算子を実行して、ユーザーに関する質問に回答できます。例えば、製品、保証、発送による収益を組み合わせることができます。 <p>（更新されたドキュメントへのリンクを添付）</p> | | 2024年6月5日（PT） |
| **書き出しと読み込みに使用されるアカウントと場所の共有** | ユーザーは、作成したアカウントと場所を組織内のすべてのユーザーに対して使用できるようになりました。アカウントと場所の所有者およびシステム管理者のみが、アカウントと場所を編集および削除できます。<p>以前は、アカウントと場所は、作成したユーザーのみが使用できました。</p><p>これらの設定は、ユーザーがクラウドの書き出しアカウントを設定し、クラウドの書き出し場所を設定する際に使用できます。</p> <p>（更新されたドキュメントへのリンクを添付）</p> | 2024年6月12日（PT） | 2024年6月30日（PT） |
| **Adobe Analytics から Customer Journey Analytics へのアップグレードに関する新しいドキュメント** | Adobe Analytics から Customer Journey Analytics にアップグレードする組織の場合、組織の現在の Adobe Analytics 実装と長期目標に基づいて、複数のアップグレードオプションと多くの考慮事項があることに留意する必要があります。次の内容に対する理解を深めるのに役立つ、新しいドキュメントリソースが利用できるようになりました。<ul><li>存在する様々なアップグレードパス</li><li>組織の現在の Adobe Analytics 実装に基づいて利用可能なアップグレードパス</li><li>各アップグレードパスのメリットとデメリット</li><li>各アップグレードパスの段階的なガイダンス</li><li>履歴データの処理に関する考慮事項</li></ul>[詳しくは、Customer Journey Analytics へのアップグレードを参照してください](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted)。 | | 今すぐ利用可能 |
| **[データの書き出しのユースケース](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-usecases/data-export/overview)に関する新しいドキュメント** | この新しい節では、次のようなデータの書き出しのユースケースについて説明します<ul><li>データのバックアップ</li><li>データの検証</li><li>データレイク、データウェアハウスまたは BI ツール</li><li>AI／ML の対応</li></ul> また、Experience Platform と Customer Journey Analytics 機能を使用して、これらを実装する方法について説明します。 | | 今すぐ利用可能 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-342309、AN-342312、AN-345267、AN-345909、AN-346016、AN-346049、AN-346052、AN-346287、AN-346624、AN-347919

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

{style="table-layout:auto"}

## 関連リソース

* [2024年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2024.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
