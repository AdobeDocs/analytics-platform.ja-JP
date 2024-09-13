---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7b368f81c4036a3992fdfc34b983f344a61dc2fb
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 52%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年9月）

**最終更新日**：2024年9月11日（PT）

これらのリリースノートは、2024 年 9 月 11 日（PT）から 10 月上旬のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **計算指標マネージャーとフィルターマネージャーの「使用されている場所」列の追加情報** | 計算指標マネージャーとフィルターマネージャーの「使用場所」列には、次の新しいレポート領域が含まれています。<ul><li>**Report Builder**:Report Builderで使用されている計算指標またはフィルターの数が表示されます。</li><li>**アドホックコンポーネント**：プロジェクトで使用されているアドホック計算指標またはアドホックフィルターの数を表示します。 これらのアドホック計算指標およびアドホックフィルター（別名「クイック計算指標」および「クイックフィルター」）は、作成元のプロジェクト内のみで使用できるので、「使用場所」列の「プロジェクト」レポート領域とは別に報告されます。</li></ul>詳しくは、[ 計算指標マネージャー ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) および [ フィルターマネージャー ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters) を参照してください。 |  | 2024 年 9 月 11 日（Pt） |
| **インテリジェントアラート** | Customer Journey Analytics のインテリジェントアラートを使用すると、データに異常なイベントが発生した際にすぐに通知を受信できます。<p>異常しきい値、変更された割合、または特定のデータポイントに基づいてアラートをトリガーするように設定できます。アラートは、異常値検出と統合された詳細なコントロールを提供し、最も必要なときにトリガーされます。</p><p>Customer Journey Analytics でインテリジェントアラートを使用するプロセスは、Adobe Analytics でインテリジェントアラートを使用するプロセスとほとんど同じです。1 つの主な違いは、Customer Journey Analytics では 1 時間ごとのアラートが使用できないことです。この違いは、取り込み可能な様々な種類のイベントデータのデータ取り込みが、遅延（通常、データイベント時間から 3～9 時間後）の後にのみ完了するためです。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/c-intelligent-alerts/intellligent-alerts) |  | 2024 年 9 月中旬 |
| **Adobe Analytics ソースコネクタの更新** | Analytics Source コネクタはAdobeによって完全に管理されるので、データセットアクティビティページにバッチに関する情報が表示されません。 取り込んだレコードの周囲の指標を確認することで、データのフローを監視できます。 詳しくは、[Analytics データのソース接続の作成 ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) に関するガイドを参照してください。 |  | 今すぐ利用可能 |
| **使用状況分析** | 組織でのCustomer Journey Analyticsの使用方法を確認する。 この機能を有効にすると、組織内の誰かがAdobe Experience Platformを使用する際にデータを収集するAnalysis Workspaceのデータセットが作成されます。 接続とデータビューも自動的に作成され、上位のプロジェクトタイプ、最もアクティブなユーザー、プロジェクトで使用される最も人気のあるコンポーネントなどのディメンションにアクセスできます。 （ドキュメントへのリンクを添付） |  | 2024 年 9 月 18 日（PT） |
| **ガイド付き分析：Workspaceへの埋め込み** | Analysis Workspaceでは、複数のガイド付き分析を 1 つのビューに組み合わせます。 （ドキュメントへのリンクを添付） | 2024年9月22日（PT） | 2024年10月2日（PT） |


## Customer Journey Analytics の修正点

AN-352461; AN-355446: AN-355665

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
