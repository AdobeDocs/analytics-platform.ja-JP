---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b7e8c535d178ef406e1563408cee83c638d6858b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 100%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年9月）

**最終更新日**：2024年9月11日（PT）

このリリースノートは、2024年9月11日（PT）～10月上旬のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **計算指標マネージャーとフィルターマネージャーの「使用場所」列に含まれる追加情報** | 計算指標マネージャーとフィルターマネージャーの「使用場所」列には、次の新しいレポート領域が含まれています。<ul><li>**Report Builder**：Report Builder で使用中の計算指標またはフィルターの数を示します。</li><li>**アドホックコンポーネント**：プロジェクトで使用中のアドホック計算指標またはアドホックフィルターの数を表示します。これらのアドホック計算指標およびアドホックフィルター（別名「クイック計算指標」および「クイックフィルター」）は、作成元のプロジェクト内でしか使用できないので、「使用場所」列の「プロジェクト」レポート領域とは別に報告されます。</li></ul>詳しくは、[計算指標マネージャー](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager)および[セグメントマネージャー](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/cja-filters/manage-filters)を参照してください。 |  | 2024年9月11日（PT） |
| **アラート** | Customer Journey Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。<p>また、Customer Journey Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。これらのアラート（「インテリジェントアラート」とも呼ばれる）は、異常値検出と統合された詳細なコントロールを提供し、最も必要なときにトリガーされます。</p><p>Customer Journey Analytics でアラートを使用するプロセスは、Adobe Analytics でアラートを使用するプロセスとほとんど同じです。1 つの主な違いは、Customer Journey Analytics では 1 時間ごとのアラートが使用できないことです。この違いは、取り込み可能な様々な種類のイベントデータのデータ取り込みが、通常はデータイベント時間から 3～9 時間遅れて完了するためです。</p><p>Adobe Analytics の Customer Journey Analytics でアラートを使用する場合の違いについて詳しくは、[アラート機能の比較](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)を参照してください。</p><p>アラートについて詳しくは、[アラートの概要](/help/components/c-intelligent-alerts/intelligent-alerts.md)を参照してください。 |  | 2024年9月13日（PT） |
| **Adobe Analytics ソースコネクタの更新** | Analytics ソースコネクタは、アドビが完全に管理しているので、データセットアクティビティページには、バッチに関する情報が表示されません。取り込まれたレコードに関する指標を確認することで、データのフローを監視できます。詳しくは、[Analytics データのソース接続の作成](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)に関するガイドを参照してください。 |  | 公開中 |
| **ガイド付き分析：Workspace への埋め込み** | 複数のガイド付き分析を Analysis Workspace の 1 つのビューに組み合わせます。（ドキュメントへのリンクを添付） | 2024年10月2日（PT） | 2024年10月31日（PT） |

## Customer Journey Analytics の修正点

AN-352461、AN-355446、AN-355665

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
