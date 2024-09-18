---
description: アラートを作成、編集または削除します。
title: アラートマネージャー（Analysis Workspace）
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 7%

---

# アラートの管理

アラートマネージャーでは、既存のアラートを管理できます。 タグ付け、名前の変更、削除など、アラートに対して様々な管理タスクを実行できます。

アラートマネージャーは、[ フィルターマネージャー ](/help/components/filters/manage-filters.md) および [ 計算指標マネージャー ](/help/components/calc-metrics/cm-workflow/cm-manager.md) と非常に似た構造になっています。

## アラートの作成

アラート・マネージャからアラートを作成するには、次の手順に従います。

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択して、Customer Journey Analyticsのアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. [!UICONTROL **追加**] （または既存のアラートがない場合は [!UICONTROL **新しいアラートの作成**]）を選択します。

1. アラートの作成について詳しくは、[ アラートの作成 ](/help/components/c-intelligent-alerts/alert-builder.md) を参照してください。

## 既存アラートの管理

アラート・マネージャで既存のアラートを管理するには：

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択して、Customer Journey Analyticsのアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. 管理する 1 つ以上のアラートを選択します。

   ![](assets/alert-manager-tasks.png)

1. アクションバーで、次のいずれかのオプションを選択します。

   | アクション | 関数 |
   |---------|----------|
   | [!UICONTROL **タグ**] | アラートにタグを適用します。 これにより、アラートを整理して使いやすくすることができます。 |
   | [!UICONTROL **削除**] | アラートを削除します。 |
   | [!UICONTROL **名前変更**] | アラートの名前を変更します。 |
   | [!UICONTROL **承認**] | アラートを承認済みとしてマークします。 |
   | [!UICONTROL **コピー**] | アラートのコピー（複製）を作成します。 |
   | [!UICONTROL **無効**] | 現在有効になっているアラートを無効にします。 |
   | [!UICONTROL **有効にする**] | 現在無効になっているアラートを有効にします。 |
   | [!UICONTROL **更新**] | アラートの有効期限を更新します。 これにより、元の有効期限に関係なく、このオプションを選択した日から 1 年間に有効期限が延長されます。 |
   | [!UICONTROL **CSV に書き出し**] | アラートを.CSV ファイルに書き出します。 |

## アラートの編集

既存のアラートを編集するには：

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択して、Adobe Analyticsのアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. [!UICONTROL **タイトルと説明**] 列のアラート名を選択します。

1. 必要に応じてアラートを編集します。

   アラートを編集する際に実行できる操作の一部を次に示します。

   * 他のレポートスイートへのアラートの追加
   * 所有者の変更
   * フィルターを更新
   * 有効期限の更新

1. アラートを編集して、「[!UICONTROL **保存**]」を選択します。

## 列の設定

アラート・マネージャで各アラートに表示される情報を構成するには、表示される列を構成します。

アラート・マネージャで表示可能な列を構成するには、次の手順に従います。

1. Adobe Analyticsで、「**[!UICONTROL コンポーネント]**」タブを選択し、「**[!UICONTROL アラート]**」を選択します。

1. アラートマネージャーで **列のカスタマイズ** アイコン ![ 列のカスタマイズ ](assets/customize-columns-icon.png) を選択し、アラートマネージャーに表示する列を選択します。

   次の列を表示できます。

   | 列タイトル | 説明 |
   |---|---|
   | タイトルと説明 | これらの値は、アラートビルダーで提供されます。 タイトルと説明を編集するには、タイトルリンクを選択してアラートビルダーを開きます。 |
   | お気に入り | 各アラートの横に星アイコンが表示され、アラートをお気に入りとしてマークできます。<!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | タイプ | アラートが Analytics データアラートかサーバーコールの使用状況アラートかを表示します。 |
   | 有効 | アラートが現在有効か無効かを表示します。 |
   | レポートスイート | アラートが最後に保存されたレポートスイートを示します。 |
   | 所有者 | アラートの所有者を示します。 管理者以外のユーザーには、自分が所有しているアラートまたは自分と共有されていたアラートのみが表示されます。 |
   | タグ | 自分または自分とアラートを共有したユーザーによってアラートに適用されたタグを表示します。 |
   | 有効期限 | アラートの有効期限が切れるように設定された日時を表示します。 |
   | 変更日 | アラートが最後に変更された日付を示します。 |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

## アラートのトラブルシューティング

アラートの問題をトラブルシューティングする際には、Adobeサポートに JID （ジョブインスタンス ID）番号を伝えます。 JID 番号は、受信したアラートメール通知の下部にあります。

![ アラートメール ](assets/alerts-email.PNG)