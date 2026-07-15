---
title: 同意レポートとフィルタリング設定の管理
description: Customer Journey Analyticsで同意レポートとフィルター設定を表示、編集、削除する方法と、同意ポリシーのルックアップデータセットが同期したままになる方法について説明します。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# 同意レポートとフィルタリング設定の管理

同意レポートとフィルター設定を[作成した後](/help/connections/consent-reporting-filtering/consent-configure.md)、表示、編集、または削除できます。

同意レポートとフィルタリングの設定を管理できるのはシステム管理者のみです。

概要情報については、[同意レポートとフィルタリングの概要](/help/connections/consent-reporting-filtering/consent-overview.md)を参照してください。

## 既存の設定の表示

既存の設定を表示するには：

1. Customer Journey Analyticsで、**[!UICONTROL Data Management]** > **[!UICONTROL 同意レポートとフィルタリング]**&#x200B;を選択します。

   各設定について、次の情報の列を使用できます。

   * **[!UICONTROL 作成者]**：設定を作成したユーザー。

   * **[!UICONTROL Sandbox]**: プロファイルデータセットを含むExperience Platform サンドボックス。

   * **[!UICONTROL 接続]**：設定が適用される接続。

   * **[!UICONTROL フィルタリング]**：フィルタリングが有効になっているマーケティングアクション（存在する場合）。

   * **[!UICONTROL 作成日]**：設定が作成された日付。

   * **[!UICONTROL 最終変更日]**：設定が最後に変更された日付。

   * **[!UICONTROL ステータス]**：設定のステータス。

   列アイコン ![列アイコン &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)を選択し、非表示にする列の選択を解除してから&#x200B;**[!UICONTROL 適用]**&#x200B;を選択すると、列を非表示にできます。

1. （オプション）設定のリストをフィルタリングするには、**フィルター** ![&#x200B; フィルターアイコン &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)を選択し、次のいずれかの条件でフィルタリングします。

   * **[!UICONTROL 接続]**

   * **[!UICONTROL 作成者]**

   * **[!UICONTROL サンドボックス]**

   * **[!UICONTROL ステータス]**

## 設定の編集

>[!IMPORTANT]
>
>フィルタリングの変更は、設定に変更を保存した後に取り込まれたデータにのみ影響します。 フィルタリングを有効にしても、変更前に取り込まれた同意のない訪問者データは削除されず、フィルタリングを無効にしても、フィルタリングが有効になっている間に除外されたデータは回復されません。

既存の設定を編集するには：

1. Customer Journey Analyticsで、**[!UICONTROL Data Management]** > **[!UICONTROL 同意レポートとフィルタリング]**&#x200B;を選択します。

1. 編集する設定の名前を選択します。

   または

   編集する設定の横にあるチェックボックスを選択し、**[!UICONTROL 編集]**&#x200B;を選択します。

1. 変更を加え、**[!UICONTROL 保存]**&#x200B;を選択します。

## 設定の削除

既存の設定を削除するには：

1. Customer Journey Analyticsで、**[!UICONTROL Data Management]** > **[!UICONTROL 同意レポートとフィルタリング]**&#x200B;を選択します。

1. 削除する設定の横にあるチェックボックスを選択し、**[!UICONTROL 削除]**&#x200B;を選択します。

## 同意ポリシーのルックアップデータセットの同期の維持

Customer Journey Analyticsでは、同意ポリシーのルックアップデータセットがExperience Platformと自動的に同期されます。 Experience Platformで同意ポリシーを作成、更新、名前変更または削除すると、ルックアップデータセット内の対応するポリシー名と説明が更新されます。

次の点に留意してください。

* サンドボックスごとに最大1つの同意ポリシー検索データセットが存在します。 同じサンドボックス内の複数の設定が、ルックアップデータセットを共有します。
* ポリシー名と説明はExperience Platformから取得されるため、ルックアップデータセットを直接編集するのではなく、Experience Platformでポリシーメタデータを更新します。
