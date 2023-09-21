---
description: 既存のエクスポートのログを管理
keywords: Analysis Workspace
title: 失敗した書き出しのトラブルシューティング
feature: Components
hide: true
hidefromtoc: true
source-git-commit: a2b2c6bca0557521ac7b6bcf635f467ca41731b7
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 9%

---

# 失敗した書き出しのトラブルシューティング

次の場合： [完全なテーブルをAnalysis Workspaceからクラウドの宛先に書き出す](/help/analysis-workspace/export/export-cloud.md)を使用すると、 [「書き出し」タブ](/help/components/exports/manage-exports.md) そして [「ログ」タブ](/help/components/exports/manage-export-logs.md). 失敗したエクスポートのステータスは次のとおりです： [!UICONTROL **失敗**].

## 一般的な失敗とアクション

様々な理由で輸出が失敗する可能性がある。 次の表に、最も一般的な理由と、失敗に対処するために実行できるアクションを示します。

| 失敗の理由 | 推奨アクション | 詳細情報 |
|---------|----------|---------|
| 場所またはアカウント情報が無効です | 書き出し先のクラウドアカウントと場所に対して、資格情報とその他の情報が正しいことを確認します。 | [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md) および [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md). |
| レポート内のディメンションまたは指標がデータビューから削除されました | データビューから削除されたコンポーネントを確認するには、システム管理者に問い合わせてください。 エクスポートで別のデータビューを使用する必要が生じる場合や、使用できなくなったコンポーネントをテーブルから削除する必要が生じる場合があります。 | [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md) |
| 組織で強制されるデータガバナンスポリシーは、テーブル内のコンポーネントのエクスポートを制限します | 書き出しが制限されているコンポーネントを確認するには、システム管理者に問い合わせてください。 書き出す前に、制限されたコンポーネントを削除します。 | *データビューのデータガバナンスポリシーに対するフィルタリング* のセクション [ラベルとポリシー](/help/data-views/data-governance.md) |

## アドビカスタマーケアに連絡

引き続き問題が発生する場合は、Adobeカスタマーケアにお問い合わせください。 エクスポートの失敗に関してカスタマーケアに問い合わせる際は、次の情報が提供されていることを確認してください。

* 書き出し名

* 書き出し ID

* インスタンス ID

* データビュー名

* 場所

* アカウント

* 会社名

* 接続

* データビュー