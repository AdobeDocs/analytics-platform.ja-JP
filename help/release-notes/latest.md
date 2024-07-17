---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c7aad8e75f47b978da109972928d1f314c15a9f9
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 42%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年7月）

**最終更新日**：2024年7月17日（PT）

これらのリリースノートは、2024 年 7 月 17 日（PT）から 2024 年 8 月 17 日（PT）までのリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する [ 継続的な配信モデル ](releases.md) に基づいて動作します。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **インテリジェントアラート** | インテリジェントアラートがCustomer Journey Analyticsで使用できるようになり、データで異常なイベントが発生した場合に、すぐに通知を受け取れるようになりました。<p>異常値のしきい値、変更された割合、または特定のデータポイントに基づいてトリガーされるアラートを設定できます。 アラートは、異常値検出と統合され、最も必要なときにトリガーされる詳細なコントロールを提供します。</p><p>Customer Journey Analyticsでインテリジェントアラートを使用するプロセスは、Adobe Analyticsでインテリジェントアラートを使用するプロセスとほとんど同じです。 1 つの主な違いは、1 時間ごとのアラートはCustomer Journey Analyticsでは使用できないことです。 この違いは、取り込み可能な様々な種類のイベントデータのデータ取り込みが、遅延（通常、データイベント時間から 3～9 時間後）の後にのみ完了するためです。</p><p>（フォローするドキュメントのリンクを更新）</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 2024年7月26日（PT） |
| **レポートをクラウドに書き出す際に使用するアカウントと場所を制御するための管理者設定** | [ ロケーションマネージャー」の新しい「管理者設定」タブでは ](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) ユーザーがアカウントとロケーションを作成および編集できるかどうかを管理者が制御できます。<p>これらの設定は、ユーザー [ クラウド書き出しアカウントを設定 ](/help/components/exports/cloud-export-accounts.md) および [ クラウド書き出し場所を設定 ](/help/components/exports/cloud-export-locations.md) の際に適用されます。</p><p>また、管理者は、ユーザーが作成および使用できるアカウントのタイプを制限することもできます。 アカウントタイプには、Google Cloud Platform、Azure RBAC、Amazon S3、AEP Data Landing Zone、Snowflakeなどがあります。</p><p>以前は、すべてのユーザーが、あらゆるタイプのアカウントと場所を作成、編集、使用できました。</p> | 2024年7月11日（PT） | 2024年7月19日（PT） |
| **概要レベルデータソース** | 人物 ID を持たない時系列データを取り込むことができます。 この時系列データは、次のような様々なユースケースをサポートするために使用できます。<ul><li>イベントレベルのデータの一部または隣にハイレベルのパフォーマンス指標を提示する。 これには、日付などの単純なものから 1 つの指標値を含めるか、広告インプレッション数、メール開封数、広告費用、売上原価など、複数のディメンションと指標を含めることができます。</li><li>毎日、毎週、毎月、または四半期ごとにターゲットまたは目標をアップロードし、イベントレベルの指標に対してこれらのターゲットまたは目標を配置すると、組織のターゲットまたは目標に対する指標のトレンドを視覚化するのに役立ちます。</li></ul><p>（フォローするドキュメントのリンクを更新）</p> |  | 2024年7月31日（PT） |
| **派生フィールド – 重複排除関数** | 派生フィールドの重複排除機能は、値が複数回カウントされるのを防ぐのに役立ちます。<p>[詳細情報](/help/data-views/derived-fields/derived-fields.md#deduplicate)</p> |  | 2024年7月17日（PT） |
| **CJA のお客様向けのガイド付き分析プロビジョニング** | ガイド付きCustomer Journey Analyticsを使用すると、分析のクロスチャネルデータに基づいて構築されたガイド付きワークフローを通じて、カスタマージャーニーに関する高品質のデータとインサイトをセルフサービスで提供できます。 <p>マーケティングから製品まで部門を横断するチームがリアルタイムでつながって、これらのレポートを使用し理解することができます。</p><p>CJA パッケージ内で最大 11 個のガイド付き分析ビューを使用できるようになりました。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024年7月17日（PT） |
| **書き出しと読み込みに使用されるアカウントと場所の共有** | ユーザーは、作成したアカウントと場所を組織内のすべてのユーザーに対して使用できるようになりました。アカウントと場所の所有者およびシステム管理者のみが、アカウントと場所を編集および削除できます。以前は、アカウントと場所を使用できるのは、それらを作成したユーザーのみでした。これらの設定は、ユーザーが[クラウドの書き出しアカウントを設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)し、[クラウドの書き出し場所を設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)する際に使用できます。 | 2024年6月12日（PT） | 2024年7月中旬 |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platformの「フィルター」オプションと「並べ替え」オプションを使用すると、関連するオーディエンスをより迅速に見つけることができます。</li></ul> <p>（ドキュメントへのリンクを添付）</p> |  | 未定 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-306000; AN-288748; AN-351547; AN-351110

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
