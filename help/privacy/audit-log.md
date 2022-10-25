---
title: 監査ログ
description: CJA 監査ログの表示方法と管理方法について説明します。
hide: true
hidefromtoc: true
source-git-commit: eba2eb71ca434e0306c018b80209caf52266ee15
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 18%

---


# 監査ログ

Customer Journey Analytics(CJA) では、システムで実行されるアクティビティの透明性と可視性を高めるために、様々なサービスや機能に関するユーザーアクティビティを「監査ログ」の形式で監査できます。 これらのログは、問題のトラブルシューティングに役立つ監査証跡を形成し、HIPAA(Health Insurance Portability and Accountability Act) などの企業のデータ管理ポリシーや規制要件に効果的に準拠するのに役立ちます。

基本的な意味では、監査ログは、 **who** 実行済み **what** アクションおよび **when**. ログに記録される各アクションには、アクションのタイプ、日時、アクションを実行したユーザーの E メール ID、アクションのタイプに関連する追加の属性を示すメタデータが含まれます。

このトピックでは、UI での表示方法や管理方法など、CJA の監査ログについて説明します。

## 監査ログへのアクセス

組織でこの機能を有効にすると、アクティビティの発生に応じて監査ログが自動的に収集されます。 ログ収集を手動で有効にする必要はありません。

監査ログを表示および書き出すには、 **[!UICONTROL 監査ログのアクセス]** Adobe・コンソールでのアクセス制御権限 CJA 機能の個々の権限を管理する方法については、 [アクセス制御ドキュメント](/help/getting-started/cja-access-control.md).

## UI での監査ログの表示

CJA で、に移動します。 **[!UICONTROL ツール]** > **[!UICONTROL 監査ログ]**.

今日と昨日の監査ログは、デフォルトで表示されます。

![監査ログ](assets/audit_ui.png)

右上の列セレクターに移動して、表示する列を選択できます。

## 個々のログエントリに関する情報の表示

説明の横にある情報 (i) ボタンをダブルクリックします。

![監査ログ](assets/info-button-audit.png)

次の項目が表示されます。

| 項目 | 説明 |
| --- | --- |
| アクション名 | 次に、実行可能なアクションのリストを示します。 <ul><li>API_Request</li><li>承認</li><li>選択からの    </li><li>テンプレートを</li><li>エクスポート</li><li>Login_failed</li><li>Login_successful</li><li>ログアウト</li><li>Org_change</li><li>更新</li><li>共有</li><li>転送</li><li>承認取消</li><li>共有しない</li></ul> |
| 説明 | アクション、コンポーネントタイプ（ID を含む）およびその他の値の概要。 |
| ユーザー名 | アクションを実行するユーザー。 |
| コンポーネントの種類 | 使用可能なコンポーネントタイプは次のとおりです。 <ul><li>注釈</li><li>オーディエンス</li><li>計算指標</li><li>接続</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>フィルター</li><li>IMS_Org</li><li>モバイル</li><li>プロジェクト</li><li>レポート</li><li>Scheduled_Project</li><li>ユーザー</li><li>User_Group</li></ul> |
| IMS 組織 ID | 初めてAdobe Experience Cloudにログインしたときにインスタンスに割り当てられる一意の ID です。 次の形式である必要があります。xxx@AdobeOrg. |
| ユーザー ID | このアクションを実行したユーザーを識別する一意の ID。 |
| 作成日 | このアクションが実行されたとき。 |
| 電子メール | アクションを実行するユーザーの電子メール。 |
| コンポーネント ID | アクションを実行するコンポーネントを識別する一意の ID。 |
| ログ ID | このログエントリを識別する一意の ID。 |
| ユーザータイプ | 使用できるタイプは次のとおりです。IMS、OKTA |

### 監査ログのフィルタリング

ファネルアイコン (![フィルター](assets/filter-icon.png)) をクリックして、結果を絞り込むのに役立つフィルターコントロールのリストを表示します。 選択した各種フィルターに関係なく、直近の 1,000 件のレコードのみが表示されます。

![フィルター](assets/filters.png)

UI の監査イベントには、次のフィルターを使用できます。

| フィルター | 説明 |
| --- | --- |
| [!UICONTROL 日付範囲] | 別の日付を選択するか、複数の日付のカーソルをドラッグして日付範囲を選択し、異なる日付範囲をフィルターします。 デフォルトでは、今日と昨日の日付が選択されています。 |
| [!UICONTROL アクション] | 次の 1 つ以上のアクションに対してフィルターを設定します。 <ul><li>API_Request</li><li>承認</li><li>選択からの    </li><li>テンプレートを</li><li>エクスポート</li><li>Login_failed</li><li>Login_successful</li><li>ログアウト</li><li>Org_change</li><li>更新</li><li>共有</li><li>転送</li><li>承認取消</li><li>共有しない</li></ul> |
| [!UICONTROL ユーザー ID] | ユーザー ID で特定のユーザーをフィルタリングします。 ユーザ ID は、ユーザ名の横にある情報 (i) ボタンを選択すると見つかります。 |
| [!UICONTROL 電子メール] | 特定のユーザーの電子メールアドレスに基づいてフィルタリングします。 電子メールは、ユーザー名の横にある情報 (i) ボタンを選択すると見つかります。 |
| [!UICONTROL コンポーネント ID] | 特定のコンポーネント ID に対してフィルタリングします。 ユーザ ID は、目的のコンポーネントの情報 (i) ボタンを選択すると見つかります。 |
| [!UICONTROL コンポーネントの種類] | 1 つ以上のコンポーネントタイプに対するフィルター： <ul><li>注釈</li><li>オーディエンス</li><li>計算指標</li><li>接続</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>フィルター</li><li>IMS_Org</li><li>モバイル</li><li>プロジェクト</li><li>レポート</li><li>Scheduled_Project</li><li>ユーザー</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 監査ログで記録されるイベントタイプ

次の表に、監査ログによって記録されるコンポーネントタイプに対するアクションの概要を示します。

| コンポーネントの種類 | アクション |
| --- | --- |
| [!UICONTROL 注釈] | <ul><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL オーディエンス] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li><li>エクスポート</li><li>更新</li></ul> |
| [!UICONTROL 計算指標] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL 接続] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL データビュー] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL 日付範囲] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL フィルター] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL IMS 組織] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL プロジェクト] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL レポート] | <ul><li>API_Request</li></ul> |
| [!UICONTROL スケジュール済みプロジェクト] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL ユーザー] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |
| [!UICONTROL ユーザーグループ] | <ul><li>API_Request</li><li>選択からの    </li><li>削除</li><li>テンプレートを</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 監査ログをダウンロード

監査ログは CSV 形式または JSON 形式でダウンロードできます。 適用されたフィルターまたは選択された列は、ダウンロードされたファイルに反映されます。

1. クリック **[!UICONTROL ダウンロード]** をクリックします。
1. 形式を指定します。
1. クリック **[!UICONTROL ダウンロード]** 再び

## API での監査ログの管理

UI で実行できるすべてのアクションは、API 呼び出しを使用して実行することもできます。 詳しくは、 [CJA API リファレンスドキュメント](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) を参照してください。