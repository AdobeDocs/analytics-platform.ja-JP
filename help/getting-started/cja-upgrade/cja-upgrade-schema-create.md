---
title: Customer Journey Analytics のカスタムスキーマの作成
description: Customer Journey Analytics のカスタムスキーマの作成方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 100%

---

# Customer Journey Analytics で使用するカスタムスキーマの作成 {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="Adobe Experience Platform で目的のカスタムスキーマを作成"
>abstract="Adobe Experience Platform UI を使用してスキーマを作成し、アドビがデータを格納するための正しい形式を認識できるようにします。<br><br>この手順には、組織で合意されたスキーマの実際の作成が含まれます。Adobe Experience Platform インターフェイスでスキーマを作成するのにかかる推定時間は、作成する必要があるディメンションと指標の数に応じて約 1 週間です。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="Adobe Analytics ExperienceEvent フィールドグループを使用したスキーマの作成"
>abstract="「Adobe Analytics ExperienceEvent」フィールドグループを使用して、Adobe Analytics で使用されるすべてのフィールドを含むスキーマを Adobe Experience Platform に作成します。<br><br>Adobe Analytics ExperienceEvent フィールドグループに基づくスキーマの作成は簡単で、完了するまでに数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="プロファイルのスキーマを有効にする"
>abstract="Adobe Real-Time CDP で使用するために、スキーマ内のプロファイルを有効にします。この手順は、Adobe Real-Time CDP との統合を選択したので表示されます。<br><br>この手順では 1 つのボックスをクリックするだけなので、この手順には数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

>[!IMPORTANT]
>
>カスタムスキーマの作成を開始する前に、組織全体のデータチームや他の関係者と協力して、Customer Journey Analytics や使用する他の Adobe Experience Platform アプリケーションに対する組織の理想的なスキーマ設計を特定します。詳しくは、[Customer Journey Analytics で使用するスキーマの設計](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)を参照してください。

次の節では、Customer Journey Analytics で使用できるスキーマの作成方法について説明します。 次のスキーマオプションを使用できます。

* **カスタム XDM スキーマ：**（推奨）組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマを可能にします。必要な今後の変更は簡単です。

* **Adobe Analytics ExperienceEvent フィールドグループを使用する Adobe Analytics スキーマ：**&#x200B;数千の不要なフィールドの追加が必要です。必要な今後の変更はより困難になります。

これらのスキーマオプションについて詳しくは、[Customer Journey Analytics のスキーマの選択](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)を参照してください。

## スキーマの作成

Web SDK 実装用に定義するカスタムスキーマは、Adobe Experience Platform に収集するデータのモデルを表します。

カスタムスキーマを作成するには：

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. Adobe Experience Platform の左側のパネルで、[!UICONTROL データ管理]内の「**[!UICONTROL スキーマ]**」を選択します。

1. 「**[!UICONTROL スキーマを作成]**」を選択します。

1. スキーマを作成ウィザードの&#x200B;**[!UICONTROL クラスを選択]**&#x200B;手順で、次の操作を行います。

   1. 「**[!UICONTROL エクスペリエンスイベント]**」を選択します。

      ![エクスペリエンスイベントをハイライト表示するスキーマの作成](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    エクスペリエンスイベントスキーマを使用すると、プロファイルの&#x200B;_動作_（シーン名、買い物かごに追加するプッシュボタンなど）をモデル化できます。個々のプロファイルスキーマは、プロファイル&#x200B;_属性_（名前、メール、性別など）のモデル化に使用されます。

   1. 「**[!UICONTROL 次へ]**」を選択します。


1. [!UICONTROL スキーマを作成]ウィザードの[!UICONTROL 名前とレビューの手順]で、次の操作を行います。

   1. スキーマの&#x200B;**[!UICONTROL スキーマ表示名]**&#x200B;と&#x200B;**[!UICONTROL 説明]**（オプション）を入力します。

      ![ スキーマフィールドに名前を付けるを示すスキーマを作成ウィンドウ](assets/create-ee-schema-wizard-step-2.png)

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

      カスタム XDM スキーマを作成するのではなく、デフォルトの Adobe Analytics スキーマを使用することを選択した場合は、ここで Adobe Analytics ExperienceEvent フィールドグループを追加できます。ただし、アドビでは、このフィールドグループを追加するのではなく、カスタム XDM スキーマを作成することをお勧めします。

      これらのスキーマオプションについて詳しくは、[Customer Journey Analytics のスキーマの選択](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)を参照してください。

   1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. （オプション）スキーマに含めるカスタムフィールドがある場合は、カスタムフィールドグループを作成し、カスタムフィールドをフィールドグループに追加します。

   1. 「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL +追加]**」を選択します。

      ![フィールドグループを追加](assets/add-field-group-button.png)

   1. [!UICONTROL フィールドグループを追加]ダイアログで、「**[!UICONTROL 新しいフィールドグループを作成]**」を選択します。

   1. 表示名とオプションの説明を指定して、「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. [!UICONTROL 構造]パネルで、スキーマ名の隣にある「**[!UICONTROL +]**」をクリックします。

   ![スキーマ追加フィールドボタンの例](assets/example-schema-plus.png)

1. 「[!UICONTROL フィールドプロパティ]」パネルで、名前に `Identification`、[!UICONTROL 表示名]に&#x200B;**[!UICONTROL ID]** と入力し、[!UICONTROL タイプ]で&#x200B;**[!UICONTROL オブジェクト]**、[!UICONTROL フィールドグループ]で **[!UICONTROL ExperienceEvent Core v2.1]** を選択します。

   >[!NOTE]
   >
   >このフィールドグループが使用できない場合は、ID フィールドを含む別のフィールドグループを検索します。または、フィールドグループに[新しいフィールドグループを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=ja)し、（`ecid`、`crmId` など）[新しい ID フィールドを追加](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=ja#define-a-identity-field)して、この新しいフィールドグループを選択します。

   ![ID オブジェクト](assets/identification-field.png)

   ID オブジェクトは、スキーマに ID 機能を追加します。この場合、Experience Cloud ID とメールアドレスを使用して、サイトを訪問しているプロファイルを識別する必要があります。ユーザーの ID を追跡するために使用できる属性は他にも多数あります（例：顧客 ID、ロイヤルティ ID）。

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

1. （オプション）Customer Journey Analytics を RTCDP と統合する場合は、スキーマの名前が表示されているスキーマのルート要素を選択し、**[!UICONTROL プロファイル]**&#x200B;スイッチを選択します。

   プロファイルのスキーマを有効にするよう求められます。有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータをリアルタイム顧客プロファイルと結合します。

   詳しくは、[リアルタイム顧客プロファイルで使用するスキーマを有効にする](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#profile)を参照してください。

   >[!IMPORTANT]
   >
   >プロファイルのスキーマを有効にした後は、プロファイルに対して無効にすることはできません。

   ![プロファイルでスキーマを有効にする](./assets/enable-for-profile.png)

1. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

   Web サイトから取得できるデータをモデル化する、最小限のスキーマを作成しました。このスキーマを使用することで、Experience Cloud ID とメールアドレスを使用してプロファイルを識別できます。プロファイルのスキーマを有効にすることで、web サイトから取り込んだデータをリアルタイム顧客プロファイルへと確実に追加できます。

   行動データの横にある、サイトからプロファイル属性データ（ニュースレターを購読したプロファイルの詳細など）を取り込むこともできます。

   このプロファイルデータを取得するには、次を実行します。

   * XDM Individual Profile クラスに基づいてスキーマを作成します。

   * Profile Core v2 フィールドグループをスキーマに追加します。

   * Profile Core v2 フィールドグループに基づいて ID オブジェクトを追加します。

   * Experience Cloud ID をプライマリ識別子として定義し、メールを識別子として定義します。

   * プロファイルでスキーマを有効にする

   フィールドグループと個々のフィールドをスキーマに追加、またはスキーマから削除する方法について詳しくは、[UI でのスキーマの作成と編集](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=ja)を参照してください。

{{upgrade-final-step}}
