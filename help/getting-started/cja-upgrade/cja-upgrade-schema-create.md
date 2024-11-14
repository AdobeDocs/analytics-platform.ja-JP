---
title: Customer Journey Analytics用スキーマの作成
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: ce19cf00d70220b6d7dcdfaeb1d4c9ec5c14e5dd
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 48%

---

# Customer Journey AnalyticsWeb SDK 実装で使用する XDM スキーマを作成します

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

>[!IMPORTANT]
>
>XDM スキーマの作成を開始する前に、データチームや組織全体のその他の関係者と協力して、Customer Journey Analyticsおよび使用するその他のAdobe Experience Platform アプリケーションに対する組織の理想的なスキーマデザインを特定します。 詳しくは、[Customer Journey Analyticsで使用するスキーマの構築 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md) を参照してください。

Adobeでは、Customer Journey Analyticsへのアップグレード時にエクスペリエンスデータモデル（XDM）スキーマを作成することをお勧めします。 XDM スキーマを使用すると、組織のニーズや使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマを提供できます。 スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。

## スキーマの作成

定義する XDM スキーマは、Adobe Experience Platformに収集するデータのモデルを表します。

スキーマを作成するには：

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. Adobe Experience Platformの左パネルの「**[!UICONTROL DATA MANAGEMENT]**」で「[!UICONTROL  スキーマ ]」を選択します。

1. **[!UICONTROL スキーマを作成]** を選択します。

1. スキーマ作成ウィザードの **[!UICONTROL クラスを選択]** 手順で、次の操作を行います。

   1. **[!UICONTROL エクスペリエンスイベント]** を選択します。

      ![ エクスペリエンスイベントをハイライト表示したスキーマの作成 ](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    エクスペリエンスイベントスキーマは、プロファイルの _動作_ をモデル化するために使用します（シーン名、買い物かごに追加するプッシュボタンなど）。 個々のプロファイルスキーマは、プロファイル&#x200B;_属性_（名前、メール、性別など）のモデル化に使用されます。

   1. 「**[!UICONTROL 次へ]**」を選択します。


1. [!UICONTROL  スキーマを作成 ] ウィザードの [!UICONTROL  名前とレビューの手順 ] で、次の操作を行います。

   1. スキーマの **[!UICONTROL スキーマ表示名]** と（オプション） **[!UICONTROL 説明]** を入力します。

      ![ スキーマフィールドに名前を付けるを表示するスキーマを作成ウィンドウ ](assets/create-ee-schema-wizard-step-2.png)

   1. 「**[!UICONTROL 完了]**」を選択します。

1. スキーマに含めるフィールドを含むすべてのフィールドグループを追加します。

   フィールドグループは、スキーマを簡単に拡張できる、再利用可能なオブジェクトと属性のコレクションです。

   1. 「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL +追加]**」を選択します。

      ![フィールドグループを追加](assets/add-field-group-button.png)

   1. [!UICONTROL フィールドグループを追加]ダイアログで、リストから「**[!UICONTROL AEP Web SDK ExperienceEvent]**」フィールドグループを選択します。

      ![AEP Web SDK ExperienceEvent フィールドグループ](assets/select-aepwebsdk-experienceevent.png)

      「プレビュー」ボタンを選択すると、このフィールドグループに属するフィールド（`web > webPageDetails > name` など）のプレビューを表示できます。

      ![AEP Web SDK ExperienceEvent フィールドグループのプレビュー](assets/aepwebsdk-experiencevent-preview.png)

      「**[!UICONTROL 戻る]**」を選択してプレビューを閉じます。

   1. （オプション）含める追加のフィールドグループを選択します。

   1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. （オプション）スキーマに含めるカスタムフィールドがある場合は、カスタムフィールドグループを作成し、そのフィールドグループにカスタムフィールドを追加します。

   1. 「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL +追加]**」を選択します。

      ![フィールドグループを追加](assets/add-field-group-button.png)

   1. [!UICONTROL  フィールドグループを追加 ] ダイアログで、「**[!UICONTROL 新しいフィールドグループを作成]**」を選択します。

   1. 表示名と説明（オプション）を指定し、「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. [!UICONTROL 構造]パネルで、スキーマ名の隣にある「**[!UICONTROL +]**」をクリックします。

   ![スキーマ追加フィールドボタンの例](assets/example-schema-plus.png)

1. 「[!UICONTROL フィールドプロパティ]」パネルで、名前に `Identification`、[!UICONTROL 表示名]に&#x200B;**[!UICONTROL ID]** と入力し、[!UICONTROL タイプ]で&#x200B;**[!UICONTROL オブジェクト]**、[!UICONTROL フィールドグループ]で **[!UICONTROL ExperienceEvent Core v2.1]** を選択します。

   >[!NOTE]
   >
   >そのフィールドグループが使用できない場合は、ID フィールドを含む別のフィールドグループを探します。 または [ 新しいフィールドグループを作成 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) して [ 新しい ID フィールドを追加 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) （`ecid`、`crmId` など、必要なその他）をフィールドグループに追加し、その新しいフィールドグループを選択します。

   ![ID オブジェクト](assets/identification-field.png)

   ID オブジェクトは、スキーマに ID 機能を追加します。 この場合、Experience Cloud ID とメールアドレスを使用して、サイトを訪問しているプロファイルを識別します。 人物の ID を追跡するために使用できる属性は他にも多数あります（顧客 ID、ロイヤルティ ID など）。

   「**[!UICONTROL 適用]**」を選択して、このオブジェクトをスキーマに追加します。

1. 先ほど追加した ID オブジェクトで「**[!UICONTROL ecid]**」フィールドをクリックし、右パネルの [!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]**、**[!UICONTROL プライマリ ID]** および **[!UICONTROL ECID]** を選択します。

   ![ECID を ID として指定](./assets/specify-identity.png)

   Experience Cloud ID を、Adobe Experience Platform Identity Service が同じ ECID を持つプロファイルの動作を組み合わせる（ステッチする）ために使用するプライマリ ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。ecid 属性にフィンガープリントアイコンが表示されます。

1. 先ほど追加した ID オブジェクトで「**[!UICONTROL メール]**」フィールドをクリックし、[!UICONTROL フィールドプロパティ]パネルの[!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]** と&#x200B;**[!UICONTROL メール]**&#x200B;を選択します。

   ![メールを ID として指定](./assets/specify-email-identity.png)

   メールアドレスを、Adobe Experience Platform Identity Service がプロファイルの動作を組み合わせる（ステッチする）ために使用するもう一つの ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。メール属性にフィンガープリントアイコンが表示されます。

   「**[!UICONTROL 保存]**」を選択します。

1. （オプション）Customer Journey Analyticsを RTCDP と統合する場合は、スキーマの名前を表示しているスキーマのルート要素を選択してから、「**[!UICONTROL プロファイル]**」スイッチを選択します。

   プロファイルのスキーマを有効にするよう求められます。有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータをリアルタイム顧客プロファイルと結合します。

   詳しくは、[リアルタイム顧客プロファイルで使用するスキーマを有効にする](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile)を参照してください。

   >[!IMPORTANT]
   >
   >プロファイルでスキーマを有効にした後は、プロファイルで無効にすることはできません。

   ![プロファイルでスキーマを有効にする](./assets/enable-for-profile.png)

1. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

   Web サイトから取得できるデータをモデル化する、最小限のスキーマを作成しました。このスキーマを使用することで、Experience Cloud ID とメールアドレスを使用してプロファイルを識別できます。プロファイルのスキーマを有効にすることで、web サイトから取り込んだデータをリアルタイム顧客プロファイルへと確実に追加できます。

   行動データの横にある、サイトからプロファイル属性データ（ニュースレターを購読したプロファイルの詳細など）を取り込むこともできます。

   このプロファイルデータを取得するには、次を実行します。

   * XDM Individual Profile クラスに基づいてスキーマを作成します。

   * Profile Core v2 フィールドグループをスキーマに追加します。

   * Profile Core v2 フィールドグループに基づいて ID オブジェクトを追加します。

   * Experience Cloud ID をプライマリ識別子、メールを識別子として定義します。

   * プロファイルでスキーマを有効にする

   フィールドグループと個々のフィールドをスキーマに追加、またはスキーマから削除する方法について詳しくは、[UI でのスキーマの作成と編集](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=ja)を参照してください。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
