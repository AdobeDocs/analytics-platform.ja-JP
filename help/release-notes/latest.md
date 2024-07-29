---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fa6f549c83f8b91907f1bb174f061cbe32aeb13c
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 100%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年7月）

**最終更新日**：2024年7月24日（PT）

このリリースノートは、2024年7月17日（PT）～2024年8月のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **インテリジェントアラート** | インテリジェントアラートを Customer Journey Analytics で使用できるようになり、データに異常なイベントが発生した際にすぐに通知を受信できます。<p>異常しきい値、変更された割合、または特定のデータポイントに基づいてアラートをトリガーするように設定できます。アラートは、異常値検出と統合された詳細なコントロールを提供し、最も必要なときにトリガーされます。</p><p>Customer Journey Analytics でインテリジェントアラートを使用するプロセスは、Adobe Analytics でインテリジェントアラートを使用するプロセスとほとんど同じです。1 つの主な違いは、Customer Journey Analytics では 1 時間ごとのアラートが使用できないことです。この違いは、取り込み可能な様々な種類のイベントデータのデータ取り込みが、通常はデータイベント時間から 3～9 時間遅れて完了するためです。</p><p>（更新されたドキュメントへのリンクを添付）</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 未定 |
| **レポートをクラウドに書き出す際に使用されるアカウントと場所を制御する管理者設定** | [場所マネージャーの新しい「管理設定」タブ](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only)により、管理者はユーザーがアカウントと場所を作成および編集できるかどうかを制御できます。<p>これらの設定は、ユーザーが[クラウドの書き出しアカウントを設定](/help/components/exports/cloud-export-accounts.md)し、[クラウドの書き出し場所を設定](/help/components/exports/cloud-export-locations.md)する際に適用されます。</p><p>また、管理者は、ユーザーが作成および使用できるアカウントのタイプを制限することもできます。アカウントタイプには、Google Cloud Platform、Azure RBAC、Amazon S3、AEP データランディングゾーン、Snowflake などがあります。</p><p>以前は、すべてのユーザーが、あらゆるタイプのアカウントと場所を作成、編集、使用できました。</p> | 2024年7月11日（PT） | 2024年7月19日（PT） |
| **概要レベルデータソース** | ユーザー ID を持たない時系列データを取り込むことができます。この時系列データは、次のような様々なユースケースをサポートするために使用できます。<ul><li>イベントレベルのデータの一部として、またはイベントレベルのデータの横に、大まかなパフォーマンスのインジケーターを表示する。これには、日付や単一の指標値などの単純なものや、広告インプレッション数、メール開封数、広告費、売上原価などの複数のディメンションと指標が含まれる場合があります。</li><li>毎日、毎週、毎月、または四半期ごとにターゲットまたは目標をアップロードし、これらのターゲットまたは目標をイベントレベルの指標に対して配置して、組織のターゲットまたは目標に対する指標のトレンドを視覚化する。</li></ul><p>（更新されたドキュメントへのリンクを添付）</p> |  | 2024年7月31日（PT） |
| **派生フィールド - 重複排除関数** | 派生フィールドの[重複排除関数](/help/data-views/derived-fields/derived-fields.md#deduplicate)を使用すると、値が複数回カウントされるのを防ぐことができます。 |  | 2024年7月17日（PT） |
| **CJA のお客様向けのガイド付き分析プロビジョニング** | ガイド付き分析を使用すると、Customer Journey Analytics のクロスチャネルデータに基づいて構築されたガイド付きワークフローを通じて、カスタマージャーニーに関する高品質のデータとインサイトをセルフサービスで提供できます。 <p>マーケティングから製品まで部門を横断するチームがリアルタイムでつながって、これらのレポートを使用し理解することができます。</p><p>CJA パッケージ内で最大 11 個のガイド付き分析ビューを使用できるようになりました。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024年7月17日（PT） |
| **書き出しと読み込みに使用されるアカウントと場所の共有** | ユーザーは、作成したアカウントと場所を組織内のすべてのユーザーに対して使用できるようになりました。アカウントと場所の所有者およびシステム管理者のみが、アカウントと場所を編集および削除できます。以前は、アカウントと場所を使用できるのは、それらを作成したユーザーのみでした。これらの設定は、ユーザーが[クラウドの書き出しアカウントを設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)し、[クラウドの書き出し場所を設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)する際に使用できます。 | 2024年6月12日（PT） | 2024年7月中旬 |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをより迅速に見つけることができます。</li></ul> <p>（ドキュメントへのリンクを添付）</p> |  | 未定 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-306000、AN-288748、AN-351547、AN-351110

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
