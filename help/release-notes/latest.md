---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5877ff515147964c2d4fbd6eaa43a8a99f0fe0
workflow-type: ht
source-wordcount: '540'
ht-degree: 100%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年8月）

**最終更新日**：2024年8月14日（PT）

このリリースノートは、2024年8月14日（PT）～2024年9月のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **概要レベルデータソース** | ユーザー ID を持たない時系列データを取り込むことができます。この時系列データは、次のような様々なユースケースをサポートするために使用できます。<ul><li>イベントレベルのデータの一部として、またはイベントレベルのデータの横に、大まかなパフォーマンスのインジケーターを表示する。これには、日付や単一の指標値などの単純なものや、広告インプレッション数、メール開封数、広告費、売上原価などの複数のディメンションと指標が含まれる場合があります。</li><li>時間単位または日単位でターゲットまたは目標をアップロードし、イベントレベルの指標に対してこれらのターゲットまたは目標を配置します。これは、組織のターゲットまたは目標に対する指標のトレンドを視覚化するのに役立ちます。</li></ul><p>詳しくは、[概要データ](/help/data-views/summary-data.md)を参照してください。</p> | 2024年8月13日（PT） | 2024年8月21日（PT） |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをより迅速に見つけることができます。</li></ul> <p>詳しくは、[オーディエンスの作成と公開](/help/components/audiences/publish.md)の記事の [Experience Platform での Customer Journey Analytics オーディエンスの使用](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform)を参照してください。</p> | 2024年9月 | 2024年9月 |
| **インテリジェントアラート** | Customer Journey Analytics のインテリジェントアラートを使用すると、データに異常なイベントが発生した際にすぐに通知を受信できます。<p>異常しきい値、変更された割合、または特定のデータポイントに基づいてアラートをトリガーするように設定できます。アラートは、異常値検出と統合された詳細なコントロールを提供し、最も必要なときにトリガーされます。</p><p>Customer Journey Analytics でインテリジェントアラートを使用するプロセスは、Adobe Analytics でインテリジェントアラートを使用するプロセスとほとんど同じです。1 つの主な違いは、Customer Journey Analytics では 1 時間ごとのアラートが使用できないことです。この違いは、取り込み可能な様々な種類のイベントデータのデータ取り込みが、通常はデータイベント時間から 3～9 時間遅れて完了するためです。</p><p>（更新されたドキュメントへのリンクを添付）</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 未定 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-354359、AN-351646、AN-346873、AN-352504、AN-353755、AN-354199、AN-354268、AN-354791、AN-354598、AN-354462、AN-354547、

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

{style="table-layout:auto"}

## 関連リソース

* [2024年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2024.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションアドオンのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
