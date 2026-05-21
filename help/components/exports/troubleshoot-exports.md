---
description: 既存の書き出しのログの管理
keywords: Analysis Workspace
title: 書き出しに失敗した場合のトラブルシューティング
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
TQID: https://experienceleague.adobe.com/pKXaX-DMxsFn9Y39AjqL1VGaSM--WFda9fuD7zJLgoI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 6%

---

# 書き出しに失敗した場合のトラブルシューティング

Analysis Workspaceからクラウド宛先](/help/analysis-workspace/export/export-cloud.md)に完全なテーブルを[書き出すと、[書き出しタブ ](/help/components/exports/manage-exports.md)と[ ログ タブ ](/help/components/exports/manage-export-logs.md)の両方から、それらの書き出しのステータスを表示できます。 書き出しに失敗しました。ステータスは&#x200B;[!UICONTROL **失敗**]&#x200B;です。

## 一般的なエラーとアクション

書き出しは、さまざまな理由で失敗する可能性があります。 次の表に、最も一般的な理由の一部を示し、エラーに対処するために実行できるアクションを示します。

| 失敗の理由 | 推奨アクション | 詳細情報 |
|---------|----------|---------|
| 無効な場所またはアカウント情報 | クラウドアカウントと書き出し先の場所の資格情報およびその他の情報が正しいことを確認します。 | [ クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)および[ クラウド書き出し場所の設定](/help/components/exports/cloud-export-locations.md)。 |
| レポート内のディメンションまたは指標がデータビューから削除されました | システム管理者に連絡して、どのコンポーネントがデータビューから削除されたかを確認します。 書き出しに別のデータビューを使用する必要がある場合や、使用できなくなったコンポーネントをテーブルから削除する必要がある場合があります。 | [Customer Journey Analytics レポートをクラウドにエクスポート ](/help/analysis-workspace/export/export-cloud.md) |
| 行数の上限を超えました | ライセンスの種類に応じて、最大300万行、3000万行、1億5000万行、または3億行を書き出すことができます。 書き出すテーブルを更新して、合計行数を減らします。 | [Customer Journey Analytics レポートをクラウドにエクスポート ](/help/analysis-workspace/export/export-cloud.md) |
| スケジュールされた書き出しの有効期限 | 設定したスケジュール済み書き出しの有効期限が切れています。 書き出しの有効期限を更新します。 | [書き出しを管理](/help/components/exports/manage-exports.md) |
| Dimensionはサポートされていません | <p>次のすべての条件を満たすディメンションは、テーブルの書き出しではサポートされていません。</p> <ul><li>は、オブジェクトの配列の一部であるフィールドから作成されました</li><li>永続性が有効になっています<li>バインディングディメンションを使用していない</li> | <ul><li>[オブジェクトの配列の使用](/help/use-cases/object-arrays.md)</li><li>[永続性コンポーネント設定](/help/data-views/component-settings/persistence.md)<li>[Customer Journey Analyticsでバインディングディメンションと指標を使用](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| 組織によって適用されるデータガバナンスポリシーは、テーブル内のコンポーネントの書き出しを制限します | どのコンポーネントの書き出しが制限されているかを確認するには、システム管理者にお問い合わせください。 書き出す前に、制限されたコンポーネントを削除します。 | *ラベルとポリシー](/help/data-views/data-governance.md)のデータビュー* セクションのデータガバナンスポリシーに関するフィルター[ |

## Adobe カスタマーケアへのお問い合わせ

引き続き問題が発生する場合は、Adobe カスタマーケアにお問い合わせください。 失敗した書き出しについてカスタマーサポートに問い合わせる場合は、次の情報が利用可能であることを確認してください。

* 書き出し名

* 書き出し ID

* インスタンス ID

* データビュー名

* 場所

* アカウント

* 接続

* 会社名
