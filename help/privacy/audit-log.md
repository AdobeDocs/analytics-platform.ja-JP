---
title: 監査ログ
description: Customer Journey Analytics監査ログの表示方法と管理方法について説明します。
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 9ed7b541ebb1a89b286040c4ea96025b08029499
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 58%

---

# 監査ログ {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_userid"
>title="ユーザー ID"
>abstract="ユーザー ID は、目的のユーザーを含むログエントリの情報ボタンを押すことで確認できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_componentid"
>title="コンポーネント ID"
>abstract="コンポーネント ID は、目的のコンポーネントを含むログエントリの情報ボタンを押すことで確認できます。"

<!-- markdownlint-enable MD034 -->


Adobe Customer Journey Analyticsでは、システムで実行されるアクティビティの透明性と可視性を高めるために、様々なサービスや機能に関するユーザーアクティビティを「監査ログ」の形式で監査できます。 これらのログは、問題のトラブルシューティングに役立つ監査記録を形成し、HIPAA（Health Insurance Portability and Accountability Act）などの企業のデータ管理ポリシーや規制要件への準拠を効果的に行うのに役立ちます。

基本的に、監査ログでは、**誰が** **どの**&#x200B;アクションを、**いつ**&#x200B;実行したかがわかります。ログに記録される各アクションには、アクションのタイプ、日時、アクションを実行したユーザーの電子メール ID、アクションのタイプに関連する追加の属性を示すメタデータが含まれます。

このトピックでは、UI での表示方法や管理方法など、Customer Journey Analyticsの監査ログについて説明します。

## 監査ログへのアクセス

組織に対してこの機能が有効になっている場合、アクティビティの発生に応じて監査ログが自動的に収集されます。ログ収集を手動で有効にする必要はありません。

監査ログを表示および書き出すには、Adobe コンソールで&#x200B;**[!UICONTROL 監査ログのアクセス]**&#x200B;アクセス制御権限を付与されている必要があります。Customer Journey Analytics機能の個々の権限を管理する方法については、[ アクセス制御ドキュメント ](../technotes/access-control.md) を参照してください。

## UI での監査ログの表示

Customer Journey Analyticsで、**[!UICONTROL ツール]**/**[!UICONTROL 監査ログ]** に移動します。

デフォルトでは、今日と昨日の監査ログが表示されます。

![ 今日と昨日の監査ログのハイライト表示。](assets/audit_ui.png)

右上の列セレクターに移動して、表示する列を選択できます。

## 個別のログエントリに関する情報の表示

説明の横にある情報（i）ボタンをダブルクリックします。

![ 「情報」ボタンをハイライト表示した監査ログ。](assets/info-button-audit.png)

次の項目が表示されます。

* **[!UICONTROL アクション名]**：実行されるアクション。 指定できる値には以下のものがあります。
   * API_REQUEST：すべてのアクションが、バックエンドの API リクエストをトリガーします。 API リクエストの内容に関する詳細が表示されます。
   * 承認：「承認」アクションが実行されました。
   * 作成：「作成」アクションが実行されました。
   * DELETE:「削除」アクションが実行されました。
   * 編集：「編集」アクションが実行されました。
   * EMBARGO: [ レポート・アクティビティ・マネージャ ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity-cancel-requests) で要求を制限すると、アクションは EMBARGO の監査ログに記録されます。
   * 書き出し：「書き出し」アクションが実行されました。
   * ORG_CHANGE：組織変更アクションが実行されました。
   * 更新：「更新」アクションが実行されました。
   * 共有：「共有」アクションが実行されました。
   * 転送：転送アクションが実行されました。
   * 承認取消：「承認取消」アクションが実行されました。
   * 共有解除：「共有解除」アクションが実行されました。
* **[!UICONTROL 作成日]**：アクションが実行された日時。
* **[!UICONTROL 説明]**：アクションの概要。
* **[!UICONTROL ユーザー名]**：アクションを実行したユーザー。 場合によっては、ユーザー名が見つからない可能性があります。 [ 製品の使用状況 ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/tools/product-usage/usage-overview) 機能には常にログインユーザー名が含まれるので、この機能の使用を検討してください。
* **[!UICONTROL メール]**：アクションを実行したユーザーのメールアドレス。
* **[!UICONTROL コンポーネント名]**：ユーザーがアクションを実行したコンポーネント。
* **[!UICONTROL コンポーネントタイプ]**: コンポーネントのタイプ。 指定できる値には以下のものがあります。
   * 注釈
   * 対象読者
   * CALCULATED_METRIC
   * 接続
   * DATA_GROUP
   * DATA_ビュー
   * DATASET_STITCHING
   * DATE_レンジ
   * FEATURE_アクセス
   * フィルター
   * IMS_ORG
   * MOBILE
   * プロジェクト （Workspace）
   * レポート
   * SCHEDULED_PROJECT
   * ユーザー
   * USER_GROUP
* **[!UICONTROL コンポーネント ID]**：ユーザーがアクションを実行したコンポーネントの ID。
* **[!UICONTROL IMS 組織 ID]**：組織の IMS ID （`ABC123@AdobeOrg` 形式）。
* **[!UICONTROL ログ ID]**：このログエントリを識別する一意の ID。
* **[!UICONTROL ユーザー ID]**：アクションを実行したユーザーを識別する一意の ID。
* **[!UICONTROL ユーザータイプ]**：使用する認証タイプ。 有効な設定値は以下のとおりです。
   * IMS
   * OKTA

### 監査ログのフィルタリング

ファネルアイコン（![フィルター](assets/filter-icon.png)）を選択して、結果を絞り込むのに役立つフィルターコントロールのリストを表示します。選択した各種フィルターに関係なく、最新 1,000 件のレコードのみが表示されます。

![ 日付範囲に対して表示されたフィルターを示す監査ログ。](assets/filters.png)

UI の監査イベントには、次のフィルターを使用できます。

| フィルター | 説明 |
| --- | --- |
| [!UICONTROL 日付範囲] | 別の日付を選択するか、複数の日付のカーソルをドラッグして日付範囲を選択して、異なる日付範囲をフィルターします。デフォルトでは、今日と昨日の日付が選択されています。 |
| [!UICONTROL アクション] | 上記のアクション名でフィルタリングします。 |
| [!UICONTROL ユーザー ID] | 特定のユーザーをユーザー ID でフィルタリングします。ユーザー ID は、ユーザー名の横にある情報（i）ボタンを選択すると見つかります。 |
| [!UICONTROL 電子メール] | 特定のユーザーのメールアドレスに基づいてフィルタリングします。電子メールは、ユーザー名の横にある情報（i）ボタンを選択すると見つかります。 |
| [!UICONTROL コンポーネント ID] | 特定のコンポーネント ID に対してフィルタリングします。コンポーネント ID は、目的のコンポーネントの横にある情報（i）ボタンを選択すると見つかります。 |
| [!UICONTROL コンポーネントの種類] | 上記の任意のコンポーネントタイプでフィルタリングします。 |

{style="table-layout:auto"}

## 監査ログで記録されるイベントタイプ

次の表に、監査ログでコンポーネントの種類が記録されるアクションの概要を示します。

| コンポーネントの種類 | アクション |
| --- | --- |
| [!UICONTROL 注釈] | <ul><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL オーディエンス] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li><li>書き出し</li><li>更新</li></ul> |
| [!UICONTROL 計算指標] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL 接続] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL データビュー] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL 日付範囲] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL フィルター] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL IMS 組織] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL プロジェクト] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL レポート] | <ul><li>API_Request</li></ul> |
| [!UICONTROL スケジュール済みプロジェクト] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL ユーザー] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |
| [!UICONTROL ユーザーグループ] | <ul><li>API_Request</li><li>作成</li><li>削除</li><li>編集</li></ul> |

{style="table-layout:auto"}

## 監査ログのダウンロード

監査ログは CSV 形式または JSON 形式でダウンロードできます。適用されたフィルターまたは選択した列は、ダウンロードされたファイルに反映されます。

1. 画面右上にある「**[!UICONTROL ダウンロード]**」をクリックします。
1. 形式を指定します。
1. もう一度「**[!UICONTROL ダウンロード]**」をクリックします。

## API での監査ログの管理

UI で実行できるすべてのアクションは、API 呼び出しを使用して実行することもできます。詳しくは、[Customer Journey Analytics API リファレンスドキュメント ](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) を参照してください。
