---
description: 既存の書き出しのログの管理
keywords: Analysis Workspace
title: 失敗した書き出しのトラブルシューティング
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---

# 失敗した書き出しのトラブルシューティング

[Analysis Workspaceからクラウドの宛先に完全なテーブルを書き出す ](/help/analysis-workspace/export/export-cloud.md) 場合、[ 「書き出し」タブ ](/help/components/exports/manage-exports.md) と [ 「ログ」タブ ](/help/components/exports/manage-export-logs.md) の両方で書き出しのステータスを確認できます。 失敗した書き出しは、[!UICONTROL **失敗**] のステータスを示します。

## 一般的なエラーとアクション

書き出しは、様々な理由で失敗する場合があります。 次の表に、最も一般的な理由と、エラーに対処するために実行できるアクションを示します。

| 失敗の理由 | 推奨されるアクション | 詳細情報 |
|---------|----------|---------|
| 無効な場所またはアカウント情報 | 書き出し先のクラウドアカウントと場所に対して、資格情報とその他の情報が正しいことを確認します。 | [ クラウドの書き出しアカウントを設定 ](/help/components/exports/cloud-export-accounts.md) および [ クラウドの書き出し場所を設定 ](/help/components/exports/cloud-export-locations.md) します。 |
| レポート内のディメンションまたは指標がデータビューから削除されました | データ表示から削除されたコンポーネントを確認するには、システム管理者に問い合わせてください。 書き出しで別のデータビューを使用する必要がある場合や、使用できなくなったコンポーネントをテーブルから削除する必要がある場合があります。 | [Customer Journey Analytics レポートのクラウドへの書き出し ](/help/analysis-workspace/export/export-cloud.md) |
| 行の制限を超えています | ライセンスの種類に応じて、最大で 300 万行、3,000 万行、1 億 5,000 万行、または 3 億行を書き出すことができます。 書き出すテーブルを更新して、合計行数を減らします。 | [Customer Journey Analytics レポートのクラウドへの書き出し ](/help/analysis-workspace/export/export-cloud.md) |
| スケジュールされた書き出しの有効期限 | 設定したスケジュールされた書き出しの有効期限が切れています。 書き出しの有効期限を更新します。 | [ 書き出しの管理 ](/help/components/exports/manage-exports.md) |
| Dimensionがサポートされていません | <p>次のすべての条件を満たすディメンションは、フルテーブルの書き出しではサポートされません。</p> <ul><li>オブジェクトの配列の一部であるフィールドから作成されました</li><li>永続性が有効になっています<li>バインディングディメンションを使用していない</li> | <ul><li>[オブジェクトの配列の使用](/help/use-cases/object-arrays.md)</li><li>[ 永続性コンポーネントの設定 ](/help/data-views/component-settings/persistence.md)<li>[Customer Journey Analyticsでのバインディングディメンションと指標の使用 ](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| 組織によって適用されるデータガバナンスポリシーは、テーブル内のコンポーネントが書き出されるのを制限します | 書き出しが制限されているコンポーネントを確認するには、システム管理者に問い合わせてください。 書き出す前に、制限されたコンポーネントを削除します。 | *ラベルとポリシー* のデータビューのデータガバナンスポリシーに対するフィルタリング [ セクション ](/help/data-views/data-governance.md) |

## アドビカスタマーケアに連絡

引き続き問題が発生する場合は、Adobe カスタマーケアにお問い合わせください。 失敗した書き出しに関してカスタマーケアに問い合わせる場合は、次の情報を確認します。

* 書き出し名

* 書き出し ID

* インスタンス ID

* データビュー名

* 場所

* アカウント

* 接続

* 会社名
