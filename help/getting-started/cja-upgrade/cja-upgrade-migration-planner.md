---
title: AppMeasurementまたはタグからXDMへの移行
description: AppMeasurementまたはタグからXDMへの移行について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '2338'
ht-degree: 5%
---
# タグからXDMへの移行 {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="移行の概要"
>abstract="Customer Journey Analyticsにアップグレードする際に、タグ実装をAdobe Experience Platform Web SDKに移行します。<br/>既存の移行を続行するか、新しい移行を開始します。"

<!-- markdownlint-enable MD034 -->

移行プランナーには、タグからXDMへの移行（スキーマの作成を含む）を自動化する移行ウィザードが用意されています。 これらは、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関連する、最も複雑で時間のかかる作業の一部です。

## サポートされているAdobe Analyticsの実装

Migration Plannerは、Analytics拡張機能（タグ）を使用するAdobe Analytics実装をサポートしています。

移行プランナーは、AppMeasurementまたはExperience Platform Web SDKを使用するAdobe Analytics実装では使用できません。

## 移行プランナーに含まれるタスクのアップグレード

移行プランナーには、次の複雑で時間のかかるアップグレードタスクを自動化する移行ウィザードが用意されています。

* **XDM スキーマの作成**: Adobe Analytics レポートスイート変数に基づいて、新しいXDM スキーマを自動的に作成します。 Migration Plannerは、Adobe Analytics レポートスイート変数をインテリジェントにスキャンし、その情報を使用してXDMに必要なフィールドを作成します。 結果のXDM スキーマには、Customer Journey Analytics スキーマで必要なフィールドのみが含まれます。

  または、既存のXDM スキーマを指すか、XDM スキーマをゼロから作成できます。

  +++ XDM スキーマをゼロから作成することを選択した場合は、この節を展開して役立つリソースの情報を得ることができます。

  * [XDM スキーマアーキテクチャを計画します](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}。

  * [Adobe Experience Platform で目的のカスタムスキーマを作成します](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}。

    スキーマを作成する際は、次のオプションを考慮してください。

    * Customer Journey Analytics を RTCDP と統合する場合は、[Customer Journey Analytics で使用する XDM スキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}の説明に従って、スキーマで「**[!UICONTROL プロファイル]**」オプションを有効にする必要があります。 このオプションを有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータがリアルタイム顧客プロファイルと結合されます。

    * ストリーミングメディアデータを含める場合は、[ストリーミングデータを取り込んで使用するスキーマを設定](/help/data-ingestion/streaming.md){target="_blank"}する必要があります。

    +++

  * **Adobe Analytics実装のWeb SDKへの移行**: Adobe Analytics実装でタグを使用するかJavaScriptを使用するかにかかわらず、Migration Plannerは、Experience Platform Web SDKへの移行を順を追って説明します。

    * **AppMeasurementからWeb SDKへのタグプロパティの移行**:

    * **JavaScriptの実装をAppMeasurementからWeb SDK JavaScript ライブラリに移行**

  * **Customer Journey Analyticsでのデータビューの作成**：作成されたXDM スキーマフィールドに基づいて、データビューが自動的に作成され、コンポーネントが入力されます。


## 始める前に

移行を作成する前に、次の項目を確認してください。

* サポートされているAdobe Analyticsの実装（タグのAnalytics拡張機能）。 [&#x200B; サポートされているAdobe Analyticsの実装](#supported-adobe-analytics-implementations)を参照してください。

* 移行するAdobe Tags プロパティに、ログインしているExperience Cloud組織内でアクセスします。

* XDMにマッピングする変数を持つAdobe Analytics レポートスイートにアクセスします。

* Adobe Experience Platformでスキーマを作成する権限。

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Analytics実装のWeb SDKへの移行

移行は、[!UICONTROL **監査**]、[!UICONTROL **マッピング**]、[!UICONTROL **実装**]&#x200B;の3つのステージを進みます。 次の手順を使用して移行を作成し、[移行の検証とデプロイ &#x200B;](#validate-and-deploy-a-migration)を続行して各段階を完了します。

1. Customer Journey Analyticsで、[!UICONTROL **Migration Planner**]&#x200B;を開きます。

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. 移行プランナーの「[!UICONTROL **移行**]」タブで、「[!UICONTROL **新規**]」を選択します。

   <!-- Confirm the exact image: ![The migration overview page with the Audit, Mapping, and Implementation stage cards.](assets/migration-planner-overview.png) -->


1. 次の情報を指定します。

   | フィールド名 | 関数 |
   | --------- | ---------- |
   | [!UICONTROL **名前**] | この移行の名前を指定します。 |
   | [!UICONTROL **説明**] | この移行のオプションの説明を指定します。 |
   | [!UICONTROL **タグのプロパティ**] | 移行するAdobe Tags プロパティを選択します。 詳しくは、Experience Platform ドキュメントの[&#x200B; プロパティ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"}を参照してください。 |
   | [!UICONTROL **タグライブラリ**] | 移行の基となるタグライブラリスナップショットを選択します。 スナップショットによって、使用するタグライブラリのバージョンが決まります。 詳しくは、Experience Platform ドキュメントの[公開の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview){target="_blank"}を参照してください。 |

1. 「[!UICONTROL **移行名**]」フィールドで、この移行の名前を指定し、「[!UICONTROL **次**]」を選択します。

1. 移行するタグプロパティを選択し、[!UICONTROL **次へ**]&#x200B;を選択します。

   サインインしたExperience Cloud組織で使用可能なタグプロパティのみが表示されます。

1. 移行するタグライブラリスナップショットを選択し、[!UICONTROL **次へ**]&#x200B;を選択します。

   スナップショットは、移行が基づくタグライブラリのバージョンを決定します。 各スナップショットには、その環境（[!UICONTROL **開発**]、[!UICONTROL **ステージング**]、[!UICONTROL **実稼動**]&#x200B;など）が表示されます。

1. マッピングセットを選択して、Analytics変数をXDM スキーマフィールドにマッピングする方法を決定します。

   次のいずれかの操作を行います。

   * [!UICONTROL **新しいマッピングセットを作成**]&#x200B;を選択します。

   * 既存のマッピングセットを選択します。

     前回の移行時に作成されたマッピングセットまたはスタンドアロンのマッピングセットとして作成されたマッピングセットを選択できます。

     複数の移行でマッピングセットを再利用すると、各移行に同じマッピングが適用されます。

1. 「[!UICONTROL **移行を作成**]」を選択します。

1. 次の節「[移行の検証とデプロイ &#x200B;](#validate-and-deploy-a-migration)」に進みます。

## 移行の検証とデプロイ

移行を作成した後、移行を開いて3つのステージ（[!UICONTROL **監査**]、[!UICONTROL **マッピング**]、[!UICONTROL **実装**]）を完了します。

1. 移行プランナーで、「[!UICONTROL **移行**]」タブを選択します。

1. 検証する移行の横にある「[!UICONTROL **開く**]」を選択します。

   移行の概要ページには、完了する3つのステージと、移行とそのアーティファクトの概要が表示されます。

   <!-- Confirm the exact image: ![The migration overview page with the Audit, Mapping, and Implementation stage cards.](assets/migration-planner-overview.png) -->

1. [!UICONTROL **監査**] ステージを完了します。

   1. 監査カード（[!UICONTROL **タグ拡張機能audit**]&#x200B;または&#x200B;[!UICONTROL **JavaScript audit**] （移行タイプに応じて）で、[!UICONTROL **監査を開始**]&#x200B;を選択して、移行に含まれるルールとデータ要素を確認します。

      <!-- Confirm the exact image: ![The audit page, where you select rules and data elements and resolve any findings.](assets/migration-planner-audit.png) -->

   1. [!UICONTROL **ルール**]&#x200B;および&#x200B;[!UICONTROL **データ要素**] タブで、移行に含める項目を選択します。

      ライブラリ **の**&#x200B;とマークされたルールが公開されます。 [!UICONTROL **プロパティのみ**]&#x200B;とマークされたルールは、プロパティ内に存在しますが、選択したライブラリの一部ではありません。

   1. 選択したルールに関する調査結果を確認します。 各検索について、[!UICONTROL **Review**]&#x200B;を選択して解決するか、[!UICONTROL **Ignore**]&#x200B;を選択して未解決のままにします。

      例えば、2つのルールに同じイベントと条件がある場合、[!UICONTROL **ルールイベントの重複**]&#x200B;の検索条件を使用すると、一方のルールを保持してもう一方のルールを削除したり、[!UICONTROL **何もしない**]&#x200B;を選択して、変更を加えずに検索結果を確認したりできます。

      調査結果の解決は、続行する前にオプションです。 検索タイプの完全なリストと、それぞれの解決方法については、[監査結果の確認と解決](#review-and-resolve-audit-findings)を参照してください。

   1. 「[!UICONTROL **保存して続行**]」を選択します。

1. [!UICONTROL **マッピング**] ステージを完了します。

   1. [!UICONTROL **Analytics → XDM マッピング**] カードで、[!UICONTROL **新しいマッピングの作成**]&#x200B;を選択します。

   1. Analytics変数に基づいて新しいスキーマを作成するか、既存のExperience Platform スキーマに対してマッピングするかを選択し、プロンプトに従ってレポートスイートを選択し、フィールドをマッピングし、スキーマをレビューします。

      詳細な手順については、[Analytics変数をXDM フィールドにマッピング &#x200B;](#map-analytics-variables-to-xdm-fields)を参照してください。 移行で一連のマッピングを再利用するには、[&#x200B; マッピングセットの作成と管理](#create-and-manage-mapping-sets)を参照してください。

1. [!UICONTROL **実装**] ステージを完了します。

   1. [!UICONTROL **Web SDK実装を生成**] カードで、監査およびマッピング結果を使用してWeb SDK実装パッケージを生成し、サイトにデプロイします。

      詳細な手順については、[Web SDK実装の生成とデプロイ &#x200B;](#generate-and-deploy-the-web-sdk-implementation)を参照してください。


## 監査結果の確認と解決

[!UICONTROL **監査**]&#x200B;段階で、移行プランナーは、選択したルールに関する調査結果をフラグ付けします。 調査結果の解決は続行する前にオプションですが、それらを解決すると、クリーンな移行を確実に行うことができます。

各検索について、[!UICONTROL **レビュー**]&#x200B;を選択して検索を開き、解決方法を選択するか、[!UICONTROL **無視**]&#x200B;を選択して未解決のままにします。

移行プランナーでは、次の種類の調査結果にフラグを付けることができます。

* [!UICONTROL **ルール イベントの重複**]:2つ以上のルールに同じイベントと条件があります。 検索結果を確認する場合は、プライマリルールと重複ルールを比較し、一方のルールを保持してもう一方のルールを削除するか、[!UICONTROL **何もしない**]&#x200B;を選択して、変更を加えずに検索結果を確認します。

* [!UICONTROL **ルール ロジックの重複**]：ルールが同じロジックを共有しています。<!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **ルール アクションの順序が正しくない**]：ルールのアクションが移行中に問題が発生する可能性のある順序で実行されます。<!-- Confirm the exact remediation options for this finding type. -->

検索結果にガイド付きの修正がない場合、移行プランナーに&#x200B;[!UICONTROL **利用可能な修正の詳細がありません**]&#x200B;と表示されます。 検索を手動で確認し、解決したら却下します。

[!UICONTROL **結果**] パネルには、対応済みの調査結果の数と、まだ開いている調査結果の数が表示されます。 完了したら、[!UICONTROL **保存して続行**]&#x200B;を選択します。

## Analytics変数をXDM フィールドにマッピングする

[!UICONTROL **マッピング**]&#x200B;段階では、Analytics変数をXDM フィールドにマッピングし、ターゲットスキーマを生成または選択します。 [!UICONTROL **Analytics → XDM マッピング**] カードで、[!UICONTROL **新しいマッピングの作成**]&#x200B;を選択し、次の手順を実行します。

1. **スキーマの選択**:Analytics変数に基づいて新しいスキーマを作成するか、既存のExperience Platform スキーマにマッピングするかを選択します。

1. **レポートスイート**：変数をマッピングするAnalytics レポートスイートを選択します。

1. **Experience Platform スキーマ**: ターゲット XDM スキーマを作成するか、マッピングする既存のスキーマを選択します。

1. **手動マッピング**：自動マッピングを確認し、個々のAnalytics変数をXDM フィールドにマッピングする方法を調整します。

1. **スキーマを確認**：結果のマッピングとスキーマを確認してから、確認します。

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

移行で一連のマッピングを再利用するには、[&#x200B; マッピングセットの作成と管理](#create-and-manage-mapping-sets)を参照してください。

## 移行出力の比較

移行の概要ページで&#x200B;[!UICONTROL **出力を比較**]&#x200B;して、移行をデプロイする前に移行を検証します。

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## Web SDKの実装を生成してデプロイする

[!UICONTROL **実装**]&#x200B;段階では、Migration Plannerは監査とマッピングの結果を使用してWeb SDK実装パッケージを構築します。

1. 移行の概要ページの&#x200B;[!UICONTROL **Web SDK実装を生成**] カードで、実装パッケージを生成します。

1. [!UICONTROL **タグライブラリを作成**]&#x200B;を選択して、移行用のタグライブラリを作成します。

1. デュアルデプロイメントを設定してから、Web SDKの実装をサイトにデプロイします。

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

このステージで生成されたアーティファクトについては、[移行アーティファクトの書き出し](#export-migration-artifacts)を参照してください。

## 移行アーティファクトの書き出し

移行の概要ページには、移行プランナーが生成するアーティファクトが表示されます。 個々のアーティファクトを&#x200B;[!UICONTROL **プロジェクト アーティファクト**] パネルからダウンロードするか、[!UICONTROL **すべてを書き出し**]&#x200B;を選択して、すべてを一度に書き出すことができます。

次のアーティファクトを使用できます。

* [!UICONTROL **JSONのマッピング**]:Analytics変数とXDM フィールド間のマッピング。

* [!UICONTROL **XDM スキーマ （JSON）**]：移行用に作成されたターゲット XDM スキーマ。

* [!UICONTROL **タグ開発ライブラリ**]: Web SDK実装用に構築されたタグライブラリです。

各アーティファクトには、[!UICONTROL **準備完了**]&#x200B;または&#x200B;[!UICONTROL **ビルドなし**]&#x200B;などのステータスが表示されます。 アーティファクトは、対応するステージで生成された後、ダウンロードできます。

## マッピングセットの作成と管理 {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="マッピングセット"
>abstract="マッピングセットは、Analytics変数をXDM フィールドにマッピングする方法を決定します。<br/>新しいマッピングセットを作成するか、既存のマッピングセットを選択して、複数の移行に同じマッピングを適用します。 他の移行タスクでマッピングセットを参照することもできます。"

<!-- markdownlint-enable MD034 -->

マッピングセットは、Analytics変数をXDM スキーマフィールドにマッピングする方法を決定します。

移行プロセス [&#128279;](#migrate-an-analytics-implementation-to-the-web-sdk)中に、新しいマッピングセット を作成できます。 または、将来の移行または他の移行タスクで使用するスタンドアロンのマッピングセットを作成することもできます。

### スタンドアロンのマッピングセットの作成 {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="スキーマの選択"
>abstract="マッピングセットは、Analytics変数をXDM フィールドにマッピングする方法を決定します。<br/>新しいマッピングセットを作成するか、既存のマッピングセットを選択して、複数の移行に同じマッピングを適用します。 他の移行タスクでマッピングセットを参照することもできます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="フィールドグループ設定"
>abstract="可能な場合は、公開済みのAdobe フィールドグループを使用するように、標準フィールドグループを選択します。 これにより、最大限の一貫性が確保され、標準フィールドが使用できない場合は、カスタムテナントフィールドにフォールバックされます。<br/>可能な場合は、テナント名前空間のカスタムフィールドを使用するカスタムフィールドグループを選択します。 これにより、最大限の柔軟性を実現できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="ルックバック期間"
>abstract="どの変数がアクティブにデータを受信しているかを判断する際にどの程度前を見ているかを制御します。 ルックバック期間内のデータを含む変数は、スキーマに含まれます。"

<!-- markdownlint-enable MD034 -->

1. 移行プランナーで、「[!UICONTROL **マッピングセット**]」タブを選択します。

1. [!UICONTROL **新しいマッピングセット**]&#x200B;を選択します。

1. 「[!UICONTROL **名前**]」フィールドに、わかりやすい名前を入力して、後でこのマッピングセットを特定し、「[!UICONTROL **次へ**]」を選択します。

1. [!UICONTROL **レポートスイート**] メニューから、変数をXDM フィールドにマッピングするレポートスイートを選択し、[!UICONTROL **次へ**]&#x200B;を選択します。

1. [!UICONTROL **XDM マッピングセクションのスキーマを選択**]&#x200B;で、Analytics変数に基づいて新しいスキーマを作成するか、既存のExperience Platform スキーマに対してマッピングするかを選択します。

   新しいスキーマを作成する方法を選択すると、Analytics変数をXDM フィールドにマッピングするプロセスを順を追って説明できます。 既存のスキーマを使用するように選択すると、Experience Platform スキーマレジストリの事前登録済みスキーマに変数を手動でマッピングできます。

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **新しいスキーマを作成**]：基本スキャンと高度スキャンを実行して、Analytics変数のXDM フィールドマッピングを自動的に提案し、結果のスキーマを確認します。

   * [!UICONTROL **既存のスキーマを使用**]:Experience Platform スキーマレジストリに既に登録されているスキーマを検索して選択し、Analytics変数を手動でXDM フィールドにドラッグします。

1. [!UICONTROL **フィールドグループの環境設定**] ドロップダウンメニューで、カスタム変数をフィールドグループに整理する方法を選択します。

   * [!UICONTROL **Standard first**]：可能な場合は、公開されたAdobe フィールドグループを使用します。 これにより、最大限の一貫性が確保され、標準フィールドが使用できない場合は、カスタムテナントフィールドにフォールバックされます。

   * [!UICONTROL **カスタム first**]：可能な場合は、テナント名前空間のカスタムフィールドを使用します。 これにより、最大限の柔軟性を実現できます。

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. 「[!UICONTROL **ルックバック期間**]」フィールドで、どの変数がアクティブにデータを受信しているかを判断する際に、検索する距離を選択します。 ルックバック期間内のデータを含む変数は、スキーマに含まれます。

1. 「[!UICONTROL **マッピングセットを作成**]」を選択します。

新しいマッピングセットは、[!UICONTROL **マッピングセット**] タブに表示されます。このタブを開くと、詳細を確認できます。

### マッピングセットの書き出し

マッピングセットを書き出して、他の移行タスクや他のツールで使用できます。

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### パブリッシュとバージョンのマッピングセット

各マッピングセットにはステータスとバージョンがあります。 「[!UICONTROL **マッピングセット**]」タブでは、マッピングセットは次のように表示されます。

* [!UICONTROL **ドラフト**]&#x200B;: マッピングセットはまだ編集中です。

* [!UICONTROL **公開済み**]&#x200B;: マッピングセットが完成しました。

* [!UICONTROL **移行**]&#x200B;: マッピングセットは1つ以上の移行にバインドされています。

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### マッピングセット <!-- can you? -->を編集

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### マッピングセット <!-- can you? -->を削除

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## 既存の移行の管理

### 移行の検索と追跡

「[!UICONTROL **移行**]」タブには、移行とその進行状況が一覧表示されます。 続行する移行を見つけたり、進行中の移行のステータスを確認したりするために使用します。

* **検索**：検索フィールドを使用して、名前またはプロパティで移行を検索します。

* **フィルター**：移行タイプまたはステータスでリストをフィルタリングします。

* **進行状況を追跡**：各移行は、3つのステージ（1/3など）と全体的なステータスを通じて進行状況を示します。

  * [!UICONTROL **未開始**]：移行は作成されましたが、ステージは完了していません。

  * [!UICONTROL **進行中**]：少なくとも1つのステージが完了しています。

  * [!UICONTROL **完了**]&#x200B;:3つのステージがすべて完了しました。

移行を続行するには、移行の横にある&#x200B;[!UICONTROL **開く**]&#x200B;を選択します。

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

