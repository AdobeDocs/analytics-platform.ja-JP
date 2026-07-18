---
title: 同意レポートとフィルタリングの概要
description: Customer Journey Analyticsで取り込み時に、訪問者の同意ポリシーのメンバーシップをレポートし、同意しない訪問者をフィルタリングする方法について説明します。
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 1058
ht-degree: 2%

---

# 同意レポートとフィルタリングの概要

同意のレポートとフィルタリングは、Adobe Experience Platform プロファイルデータセットに保存されている同意ポリシーメンバーシップデータを使用して、訪問者の同意に関するレポートを作成し、同意しない訪問者をCustomer Journey Analyticsに取り込む前に除外することができます。

## 前提条件

同意レポートとフィルタリングを設定する前に、次のことを確認します。

* Adobe Healthcare ShieldまたはPrivacy &amp; Security Shieldのライセンスを取得しています。
* Customer Journey Analyticsにはシステム管理者の権限があります。
* 使用するサンドボックスには、`consentPoliciesIDMap` フィールドに同意ポリシーメンバーシップデータを含むプロファイルデータセットが含まれています。
* 設定する接続は既に存在します。 詳細については、[接続の作成または編集](/help/connections/create-connection.md)を参照してください。

次の図と関連する表は、同意レポートとフィルタリングによってAnalysis Workspaceで同意ポリシーデータを使用できるようにし、取り込み時に訪問者データをフィルタリングする方法の概要を示しています。

![同意レポートとフィルタリングの概要](assets/consent-overview.png)

| 数値 | 機能 | 関数 |
|---------|----------|---------|
| 1 | 同意レポートとフィルタリングの設定 | Customer Journey Analyticsの設定インターフェイスは、同意レポートと、オプションで同意フィルタリングを有効にするために使用されます。 |
| 2 | サンドボックス | 報告する同意ポリシーメンバーシップデータを含むプロファイルデータセットを含める必要があります。 |
| 3 | Profile データセット | 各訪問者の同意ポリシーメンバーシップデータを含めます。 同意ポリシーメンバーシップは、プロファイルデータセットの`consentPoliciesIDMap` フィールドに保存されます。 このプロファイルデータセットは、選択した接続に追加されます。 <p>各訪問者のプロファイルには、訪問者が一致する同意ポリシーが一覧表示されます。 Customer Journey Analyticsでは、このフィールドを読み取り、レポートで同意ポリシーを使用できるようにし、取り込み中に含める訪問者を評価します。</p> |
| 4 | 同意ポリシー検索データセット | レポート用のわかりやすいポリシー名と説明を提供します。 ルックアップデータセットは自動的に作成され、Experience Platformと同期されます。 サンドボックスごとに最大1つの同意ポリシー検索データセットが存在します。 |
| 5 | 接続 | 同意レポートとフィルタリングが適用される接続。 接続の下にあるすべてのデータビューは、設定を継承します。 |
| 6 | 同意ポリシーコンポーネント | 同意ポリシーメンバーシップを表す新しいディメンション、指標、派生フィールド。 これらのコンポーネントは自動的に作成され、Analysis Workspaceでレポートに使用できます。 |
| 7 | 取り込み時間フィルタリング | フィルタリングが有効になっている場合、同意しない訪問者は、設定したマーケティングアクションに基づいて、取り込み中に除外されます。 |

## 同意に関するレポートとフィルタリング

同意に関するレポートとフィルタリングは、それぞれ別の機能です。 同意レポートを単独で有効にすることも、レポートとフィルタリングの両方を同時に有効にすることもできます。

### 同意レポート

同意レポートを有効にすると、Customer Journey Analyticsは、設定された接続の下のデータビューに一連の同意ポリシーコンポーネントを追加します。 これらのコンポーネントを使用すると、Analysis Workspaceを使用して、Experience Platform プロファイルデータセットの同意ポリシーメンバーシップデータを使用して、どの訪問者が様々な同意ポリシーに一致するかをレポートできます。

レポートを読みやすくするために、Customer Journey Analyticsは、Experience Platformのポリシー名と説明を同意ポリシー参照データセットに同期します。 Experience Platformでポリシーを作成、更新、名前変更または削除すると、ルックアップデータセットが自動的に更新されます。

同意レポートが作成するコンポーネントについて詳しくは、[同意ポリシーデータの分析](/help/connections/consent-reporting-filtering/consent-analyze.md)を参照してください。

### 同意フィルタリング

>[!IMPORTANT]
>
>フィルタリングされた（除外された）同意データはCustomer Journey Analyticsには保存されないため、設定を更新して過去の日付を復元することはできません。

同意フィルタリングを有効にすると、Customer Journey Analyticsは、取り込み時に同意しない訪問者を除外します。 フィルタリングは取り込み時に行われるため、除外された訪問者のデータはCustomer Journey Analyticsに入ることはなく、レポートには使用できません。

同意フィルタリングを使用する場合は、次の点を考慮してください。

* Customer Journey Analyticsは、設定したマーケティングアクションに適用される同意ポリシーを決定します。

  マーケティングアクションは、データ使用のカテゴリです。 Customer Journey Analyticsは、各マーケティングアクションに適用される同意ポリシーを決定し、[設定の作成時に、各マーケティングアクションに対するフィルタリングを個別に有効にします](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration)。

  | マーケティングアクション | 説明 |
  |---------|----------|
  | **[!UICONTROL Analytics]** | Analysis Workspaceの標準Customer Journey Analyticsレポート： |
  | **[!UICONTROL データサイエンス]** | 高度な分析、マシンラーニング、データサイエンスのユースケース。 |

* 訪問者のデータは、訪問者が該当する同意ポリシー&#x200B;**all**&#x200B;に一致する場合にのみ取り込まれます。 訪問者に該当するポリシーがない場合、その訪問者のデータは除外されます。

## 同意に関するレポートとフィルタリングの設定

同意レポートとフィルタリングを設定する場合、同意ポリシーメンバーシップデータを含むサンドボックスとプロファイルデータセットを選択し、設定する接続または接続を選択し、各マーケティングアクションのデータをフィルタリングするかどうかを選択します。 次に、Customer Journey Analyticsは同意ポリシー検索データセットと同意ポリシーコンポーネントを自動的に作成します。

詳しくは、[同意レポートとフィルタリングの設定](/help/connections/consent-reporting-filtering/consent-configure.md)を参照してください。

## 同意レポートとフィルタリング設定の管理

同意レポートとフィルタリング設定は、作成後に管理できます。 設定を表示、編集、削除できます。

既存の設定の管理について詳しくは、[同意レポートとフィルター設定の管理](/help/connections/consent-reporting-filtering/consent-manage.md)を参照してください。

## 同意ポリシーデータの分析

Customer Journey Analyticsで利用可能な同意ポリシーデータを使用すると、どの訪問者がどの同意ポリシーに一致しているかをレポートでき、そのinsightを使用して、レポート全体で同意オーディエンスを把握できます。

詳しくは、[同意ポリシーデータの分析](/help/connections/consent-reporting-filtering/consent-analyze.md)を参照してください。

## 同意に関するレポートおよびフィルタリングの役割と権限要件

同意のレポートとフィルタリングには、次のCustomer Journey Analyticsの役割とExperience Platformの権限が必要です。

| 機能 | Customer Journey Analyticsの役割または権限の要件 | Experience Platformの権限の要件 |
|---------|----------|----------|
| [同意レポートとフィルター設定の作成](/help/connections/consent-reporting-filtering/consent-configure.md) | システム管理者 | <ul><li>データセット：読み取り、書き込み</li><li>スキーマ：読み取り、書き込み</li></ul> <p>同意ポリシーメンバーシップデータを含むプロファイルデータセットには、読み取りアクセスが必要です。 同意ポリシーのルックアップデータセットが作成され、同期されているため、書き込みアクセスが必要です。</p> |
| データビューでの同意ポリシーコンポーネントの表示 | データビューが割り当てられている製品プロファイルの製品プロファイル管理者 <p>詳しくは、[&#x200B; アクセス制御](/help/technotes/access-control.md)を参照してください。</p> | 該当なし |
| Analysis Workspaceの同意ポリシーコンポーネントの使用 | 同意ポリシーコンポーネントが追加されたデータビューへのアクセス | 該当なし |

## 同意レポートとフィルタリングのユースケース

同意レポートとフィルタリングが提供する値を強調表示するユースケースの例については、[同意レポートとフィルタリングのユースケース &#x200B;](/help/connections/consent-reporting-filtering/consent-use-cases.md)を参照してください。

## 同意に関するレポートとフィルタリングの制限

同意レポートとフィルタリングを[設定する場合は、次の制限を考慮してください](/help/connections/consent-reporting-filtering/consent-configure.md)。

* 単一のサンドボックスには、同意ポリシーのルックアップデータセットを1つだけ設定できます。 同じサンドボックス内の複数の設定が、ルックアップデータセットを共有します。

* 1つの接続は、1つの同意レポートとフィルタリング設定にのみ関連付けることができます。
