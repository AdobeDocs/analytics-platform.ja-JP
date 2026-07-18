---
title: 同意レポートとフィルタリングの設定
description: プロビジョニングウィザードを使用して、Customer Journey Analyticsで接続の同意レポートとオプションの取り込み時間フィルタリングを有効にする方法を説明します。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 2%

---

# 同意に関するレポートとフィルタリングの設定

システム管理者は、1つ以上の接続に対して、同意レポートおよびオプションで同意フィルタリングを有効にできます。 概要情報については、[同意レポートとフィルタリングの概要](/help/connections/consent-reporting-filtering/consent-overview.md)を参照してください。

>[!IMPORTANT]
>
>同意フィルタリングは、取り込み時に同意しない訪問者データを除外します。 フィルタリングによって除外されたデータはCustomer Journey Analyticsに保存されないため、過去の日付に対して復元できません。 フィルタリングを有効にする前に、マーケティングアクションの選択を注意深く確認してください。

## 設定の作成

同意レポートとフィルタリング用の設定を作成する場合、同意ポリシーメンバーシップデータを含むサンドボックスとプロファイルデータセットを選択し、設定する接続または接続を選択し、各マーケティングアクションのデータをフィルタリングするかどうかを選択します。 次に、Customer Journey Analyticsは同意ポリシー検索データセットと同意ポリシーコンポーネントを自動的に作成します。

同意レポートとフィルタリング設定を作成するには：

1. Customer Journey Analyticsで、**[!UICONTROL Data Management]** > **[!UICONTROL 同意レポートとフィルタリング]**&#x200B;を選択します。

1. 「**[!UICONTROL 設定を作成]**」を選択します。

1. 「**[!UICONTROL 詳細]**」セクションで、次の情報を指定します。

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL 名前]** | 設定の名前を指定します。 |
   | **[!UICONTROL サンドボックス]** | プロファイルデータセットと同意ポリシーメンバーシップデータを含むExperience Platform サンドボックスを選択します。 <p>サンドボックスごとに最大1つの同意ポリシー検索データセットが存在します。 同じサンドボックス内の複数の設定が、同じルックアップデータセットを共有します。</p> |

1. 「**[!UICONTROL プロファイルデータセット]**」セクションで、報告する同意ポリシーメンバーシップデータ（`consentPoliciesIDMap` フィールド）を含むプロファイルデータセットを選択します。 同意レポートを有効にすると、このプロファイルデータセットが、まだ一部ではない場合に選択した接続に追加されます。

1. **[!UICONTROL 接続]** セクションで、**[!UICONTROL 接続を選択]**&#x200B;し、設定する1つ以上の接続の横にあるチェックボックスを選択してから、**[!UICONTROL 接続を使用]**&#x200B;を選択します。

   同意レポートとフィルタリングは接続レベルで適用されます。 設定された接続のすべてのデータビューは、同じ動作を継承します。

1. **[!UICONTROL データビュー]** セクションで、**[!UICONTROL データビューを選択]**&#x200B;をクリックします。

1. データビューダイアログで、同意レポートに使用する1つ以上のデータビューの横にあるチェックボックスを選択します。 これらのデータビューは、レポート用にExperience Platformの同意データで自動的に設定されます。

1. 「**[!UICONTROL データビューを使用]**」を選択します。

1. （オプション）「**[!UICONTROL フィルタリング]**」セクションでは、次のマーケティングアクションのフィルタリングを有効にできます。

   >[!NOTE]
   >
   >マーケティングアクションのフィルタリングが有効になっている場合、Customer Journey Analyticsは、訪問者がそのマーケティングアクションに適用される&#x200B;**all**&#x200B;同意ポリシーに一致する場合にのみ、訪問者のデータを取り込みます。 詳しくは、[同意レポートとフィルタリングの概要](/help/connections/consent-reporting-filtering/consent-overview.md)の[同意フィルタリング &#x200B;](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering)を参照してください。

   | マーケティングアクション | 説明 |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Analysis Workspaceの標準Customer Journey Analytics レポートに使用されるフィルターデータ。 |
   | **[!UICONTROL データサイエンス]** | 高度な分析、マシンラーニング、データサイエンスのユースケースに使用されるデータをフィルタリングします。 |

1. **[!UICONTROL 作成]**&#x200B;を選択して、設定を作成します。

   レポートを有効にすると、Customer Journey Analyticsは自動的に次の操作を行います。

   * 選択したプロファイルデータセットを接続に追加します。
   * サンドボックスの同意ポリシー参照データセットを作成し（サンドボックスが存在しない場合）、Experience Platformからポリシー名と説明を同期します。
   * 設定された接続内のデータビューに、同意ポリシーコンポーネント（ディメンション、指標、派生フィールド）を追加します。

1. 設定が完了したら、[同意ポリシーコンポーネントをデータビュー](#view-consent-policy-components-in-the-data-view)で表示して、使用可能であることを確認します。

## データビューでの同意ポリシーコンポーネントの表示

[設定を作成した後](#create-a-configuration)、設定された接続の下のデータビューに同意ポリシーコンポーネントが追加されたことを確認できます。

データビューで同意ポリシーコンポーネントを表示するには、データビューが割り当てられている製品プロファイルの製品プロファイル管理者である必要があります。 詳しくは、[&#x200B; アクセス制御](/help/technotes/access-control.md)を参照してください。

データビューで同意ポリシーコンポーネントを表示するには：

1. Customer Journey Analytics で、**[!UICONTROL データ管理]**／**[!UICONTROL データビュー]**&#x200B;を選択します。

1. 設定された接続に関連付けられているデータビューを開きます。

1. 「**[!UICONTROL ディメンション]**」セクションで、次のディメンションを使用できるようになりました。

   * **[!UICONTROL 同意ポリシーID]**

   * **[!UICONTROL ポリシー名]**

   * **[!UICONTROL ポリシーの説明]**

1. **[!UICONTROL 指標]** セクションで、次の指標を使用できるようになりました。

   * **[!UICONTROL 同意を得た訪問者]**

   * **[!UICONTROL 同意を得たイベント]**

   * **[!UICONTROL 一意の同意ポリシー]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Analysis Workspaceの同意ポリシーコンポーネントを使用します。

   Analysis Workspaceのデータビューにアクセスできるユーザーは、新しいコンポーネントを表示し、分析で使用できるようになりました。 Analysis Workspaceで同意ポリシーコンポーネントを使用する方法について詳しくは、[同意ポリシーデータの分析](/help/connections/consent-reporting-filtering/consent-analyze.md)を参照してください。
