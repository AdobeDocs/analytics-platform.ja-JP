---
title: 監査ログ
description: CJA 監査ログの表示方法と管理方法について説明します。
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
source-git-commit: 7fcbac6adb6946efd5c54b9f8edb4587dc34d445
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 79%

---

# 監査ログ

Customer Journey Analytics（CJA）では、システムで実行されるアクティビティの透明性と可視性を高めるために、様々なサービスや機能に関するユーザーアクティビティを「監査ログ」の形式で監査できます。これらのログは、問題のトラブルシューティングに役立つ監査証跡を形成し、HIPAA（Health Insurance Portability and Accountability Act）などの企業のデータ管理ポリシーや規制要件への準拠を効果的に行うのに役立ちます。

基本的に、監査ログでは、**誰が** **どの**&#x200B;アクションを、**いつ**&#x200B;実行したかがわかります。ログに記録される各アクションには、アクションのタイプ、日時、アクションを実行したユーザーの電子メール ID、アクションのタイプに関連する追加の属性を示すメタデータが含まれます。

このトピックでは、UI での表示方法や管理方法など、CJA の監査ログについて説明します。

## 監査ログへのアクセス

組織に対してこの機能が有効になっている場合、アクティビティの発生に応じて監査ログが自動的に収集されます。ログ収集を手動で有効にする必要はありません。

監査ログを表示および書き出すには、Adobe コンソールで&#x200B;**[!UICONTROL 監査ログのアクセス]**&#x200B;アクセス制御権限を付与されている必要があります。CJA 機能の個々の権限を管理する方法については、[アクセス制御ドキュメント](../admin/cja-access-control.md)を参照してください。

## UI での監査ログの表示

CJA で、**[!UICONTROL ツール]**／**[!UICONTROL 監査ログ]**&#x200B;に移動します。

デフォルトでは、今日と昨日の監査ログが表示されます。

![監査ログ](assets/audit_ui.png)

右上の列セレクターに移動して、表示する列を選択できます。

## 個別のログエントリに関する情報の表示

説明の横にある情報（i）ボタンをダブルクリックします。

![監査ログ](assets/info-button-audit.png)

次の項目が表示されます。

* **[!UICONTROL アクション名]**:実行されたアクション。 指定できる値には以下のものがあります。
   * API_REQUEST
   * 承認
   * 作成
   * DELETE
   * 編集
   * 書き出し
   * ORG_CHANGE
   * 更新
   * 共有
   * 転送
   * 承認取消
   * 共有しない
* **[!UICONTROL 作成日]**:アクションが実行された日時。
* **[!UICONTROL 説明]**:アクションの概要。
* **[!UICONTROL ユーザー名]**:アクションを実行したユーザー。
* **[!UICONTROL 電子メール]**:アクションを実行したユーザーの電子メールアドレス。
* **[!UICONTROL コンポーネント名]**:ユーザーがアクションを実行したコンポーネント。
* **[!UICONTROL コンポーネントタイプ]**:コンポーネントのタイプ。 指定できる値には以下のものがあります。
   * 注釈
   * 対象者
   * 計算指標
   * 接続
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * フィルター
   * IMS_ORG
   * モバイル
   * プロジェクト
   * レポート
   * SCHEDULED_PROJECT
   * ユーザー
   * USER_GROUP
* **[!UICONTROL コンポーネント ID]**:ユーザーがアクションを実行したコンポーネントの ID。
* **[!UICONTROL IMS Org ID]**:組織の IMS ID（の形式） `ABC123@AdobeOrg`.
* **[!UICONTROL ログ ID]**:このログエントリを識別する一意の ID。
* **[!UICONTROL ユーザー ID]**:アクションを実行したユーザーを識別する一意の ID。
* **[!UICONTROL ユーザータイプ]**:使用する認証タイプ。 有効な設定値は以下のとおりです。
   * IMS
   * OKTA

### 監査ログのフィルタリング

ファネルアイコン（![フィルター](assets/filter-icon.png)）を選択して、結果を絞り込むのに役立つフィルターコントロールのリストを表示します。選択した各種フィルターに関係なく、最新 1,000 件のレコードのみが表示されます。

![フィルター](assets/filters.png)

UI の監査イベントには、次のフィルターを使用できます。

| フィルター | 説明 |
| --- | --- |
| [!UICONTROL 日付範囲] | 別の日付を選択するか、複数の日付のカーソルをドラッグして日付範囲を選択して、異なる日付範囲をフィルターします。デフォルトでは、今日と昨日の日付が選択されています。 |
| [!UICONTROL アクション] | 上記のアクション名でフィルターします。 |
| [!UICONTROL ユーザー ID] | 特定のユーザーをユーザー ID でフィルタリングします。ユーザー ID は、ユーザー名の横にある情報（i）ボタンを選択すると見つかります。 |
| [!UICONTROL 電子メール] | 特定のユーザーのメールアドレスに基づいてフィルタリングします。電子メールは、ユーザー名の横にある情報（i）ボタンを選択すると見つかります。 |
| [!UICONTROL コンポーネント ID] | 特定のコンポーネント ID に対してフィルタリングします。コンポーネント ID は、目的のコンポーネントの横にある情報（i）ボタンを選択すると見つかります。 |
| [!UICONTROL コンポーネントの種類] | 上記の任意のコンポーネントタイプに対してフィルターします。 |

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

UI で実行できるすべてのアクションは、API 呼び出しを使用して実行することもできます。詳しくは、[CJA API 参照ドキュメント](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs)を参照してください。
