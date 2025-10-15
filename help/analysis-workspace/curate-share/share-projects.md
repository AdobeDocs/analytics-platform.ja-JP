---
description: Analysis Workspace でプロジェクトを共有する方法について説明します。
keywords: Analysis Workspace の共有
title: プロジェクトの共有
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '2089'
ht-degree: 100%

---

# プロジェクトの共有 {#share-projects}

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="プロジェクトの共有"
>abstract="これらのプロジェクトの役割を組織内の他のユーザーと共有できます。"



次のタイプのユーザーと Analysis Workspace プロジェクトを共有できます。

* Customer Journey Analytics にアクセスできる、組織内のユーザーとグループ

  編集、複製、表示の各アクセス権を共有できます

* Adobe Customer Journey Analytics にアクセスできない、組織内のユーザーとグループ

  受信者は読み取り専用でアクセスできます

* 組織外のユーザー

  受信者は読み取り専用でアクセスできます

共有より前に適用した[キュレーション](curate.md)は、受信者がプロジェクトを開くと反映されます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace でのプロジェクト共有](https://video.tv.adobe.com/v/40032/?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


## 組織内のユーザーおよびグループとの共有 {#Add}

組織内の既存の Adobe Workspace ユーザーまたはグループと、プロジェクトを共有できます。この節で説明するようにプロジェクトを共有する場合、共有相手となるユーザーは、既に Adobe Customer Journey Analytics アカウントを持っている必要があります。

特定の役割をユーザーやグループと共有したり、リンクを共有したりできます。

* [特定のプロジェクトの役割の共有](#share-a-specific-project-role)

* [プロジェクトへのリンクの共有](#share-a-link-to-a-project)

## 特定のプロジェクトの役割の共有

特定のプロジェクトの役割を組織内のユーザーやグループと共有する場合は、以下の点を考慮してください。

* プロジェクトの役割（**[!UICONTROL オリジナルを編集]**、**[!UICONTROL コピーを編集]**&#x200B;および&#x200B;**[!UICONTROL 読み取り専用]**）は、ユーザーと特定のプロジェクト ID に結び付けられます。プロジェクトの役割は、[Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/ja/docs/core-services/interface/administration/admin-getting-started) で管理されるユーザー権限とは独立しています。

* Customer Journey Analytics では、[Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/ja/docs/core-services/interface/administration/admin-getting-started) の製品プロファイルによってグループが定義されます。管理者は、*すべて*&#x200B;を含む任意のグループと共有できます。管理者以外のユーザーは、*すべて*&#x200B;を除き、自分が属するグループと共有できます。

* 複数の役割に配置されたユーザーは、常に最高のエクスペリエンスを得ることができます。このシナリオは、ユーザーが個人として、またはグループの一部として追加された場合に発生する可能性があります。例えば、個人として&#x200B;**[!UICONTROL オリジナルを編集]**&#x200B;の役割、グループのメンバーとして&#x200B;**[!UICONTROL 読み取り専用]**&#x200B;の役割を付与されたユーザーは、**[!UICONTROL オリジナルを編集]**&#x200B;プロジェクトエクスペリエンスを受け取ります。

* **[!UICONTROL コピーを編集]**&#x200B;または&#x200B;**[!UICONTROL 読み取り専用]**&#x200B;の役割を付与された管理者は、プロジェクトを開いたときに、それらの限定的なエクスペリエンスを受け取ります。管理者は、プロジェクトを自分自身と共有し「編集」の役割を付与することで、自分の役割を&#x200B;**[!UICONTROL オリジナルを編集]**&#x200B;に変更できます（以下の手順を参照）。

* 複数のプロジェクトを共有するように選択した場合、受信者は各プロジェクトの既存の受信者リストに追加されます。

  例えば、プロジェクト A が既に受信者 1、2、3 と共有されていて、プロジェクト B が既に受信者 4、5、6 と共有されているとします。

  次に、プロジェクト A と B が受信者 4 および 7 と共有されます。新しい共有リストはプロジェクト A では 1、2、3、4、7 になり、プロジェクト B では 4、5、6、7 になりました。

特定のプロジェクトの役割を組織内のユーザーまたはグループと共有するには、次の手順に従います。

1. Adobe Customer Journey Analytics で、「[!UICONTROL **Workspace**]」タブを選択し、左側のパネルで「[!UICONTROL **プロジェクト**]」を選択します。

1. 共有する 1 つ以上のプロジェクトの横にあるチェックボックスを選択し、「[!UICONTROL **共有**]」を選択します。

   または

   個々のプロジェクトのみを共有するには、共有するプロジェクトを開き、**[!UICONTROL 共有]**／**[!UICONTROL Workspace ユーザーと共有]**を選択します。
保存されていない変更がある場合は、まずプロジェクトを保存するように求められます。

   共有プロジェクトダイアログボックスが表示されます。ダイアログボックスの「[!UICONTROL **リンクで共有**]」と「[!UICONTROL **設定**]」セクションは、単一のプロジェクトを共有する場合にのみ表示されます。

   ![プロジェクトを共有ウィンドウ ](assets/share-proj-modal.png)

1. 提供された役割フィールドの 1 つに、受信者または受信者のグループを追加します。

   **オリジナルを編集：**&#x200B;受信者は、変更内容をプロジェクトに&#x200B;**[!UICONTROL 保存]**&#x200B;し、共同所有者になることができます。この役割は、プロジェクトを他の同僚と共同管理する場合に役立ちます。この役割には、共有プロジェクトの受信者リストの編集、削除、変更が含まれます。<br>メモ：Analysis Workspace は現在、ライブコラボレーションをサポートしていないので、一度に 1 人のユーザーだけがプロジェクトを編集することをお勧めします。プロジェクトを同時に保存すると、最後のバージョンが保持されます。

   **コピーを編集：**&#x200B;受信者は、**[!UICONTROL 別名で保存]**&#x200B;し、左側のパネルにアクセスできます。この役割には、プロジェクトの操作は制限されません。この役割は、組織のデータと Analysis Workspace の使用方法を理解しているユーザーとプロジェクトを共有する場合に役立ちます。ただし、これらのユーザーにプロジェクトを変更させたくはありません。

   **読み取り専用：**&#x200B;受信者は、**[!UICONTROL 保存]**&#x200B;または&#x200B;**[!UICONTROL 別名で保存]**&#x200B;することができず、左側のパネルにもアクセスできません。プロジェクトの操作も制限されます。この役割は、組織のデータ構造、Analysis Workspace または Customer Journey Analytics の一般的な知識の低いユーザーにプロジェクトを共有する場合に役立ちます。ただし、これらのユーザーに引き続き、安全な環境でデータやインサイトを利用してもらいたい場合です。読み取り専用プロジェクトエクスペリエンスについて詳しくは、[こちら](/help/analysis-workspace/curate-share/view-only-projects.md)を参照してください。

1. （条件付き）単一のプロジェクトを共有する場合、プロジェクトの共有にあたって、次のオプションを有効にするかどうかを選択します。

   * **埋め込みプロジェクトコンポーネント：**&#x200B;セグメント、計算指標、日付範囲をすべての受信者と共有します。共有すると、これらのコンポーネントは受信者の Workspace のコンポーネントドロップダウンメニューに表示されます。この設定は持続しません。共有時の 1 回限りのアクションです。

   * **受信者のランディングページとして設定：**&#x200B;このページを受信者のランディングページとして設定します。この設定は持続しません。共有時の 1 回限りのアクションです。

1. 「**[!UICONTROL 共有]**」を選択します。（プロジェクトが既に共有されている場合は、「[!UICONTROL **更新**]」を選択します。）

   または

   「**[!UICONTROL キュレーションと共有]**」を選択して、プロジェクトのキュレーションを自動的に適用します。（プロジェクトが既に共有されている場合は、「**[!UICONTROL キュレーションと更新]**」を選択します）。詳しくは、[プロジェクトのキュレーション](curate.md)を参照してください。


## プロジェクトへのリンクの共有

この節で説明するようにリンクを共有する場合は、次の点に注意してください。

* リンクを使用する受信者は、プロジェクトにアクセスする前に Customer Journey Analytics にログインする必要があります。

* 役割が割り当てられていない受信者がプロジェクトへの[共有可能なリンク](/help/analysis-workspace/curate-share/shareable-links.md)を受け取った場合（**[!UICONTROL 共有]／[!UICONTROL プロジェクトリンクを取得]**）、その受信者にはデフォルトで役割が割り当てられます。管理者は&#x200B;**[!UICONTROL オリジナルを編集]**&#x200B;の役割を受け取り、管理者以外は&#x200B;**[!UICONTROL コピーを編集]**&#x200B;の役割を受け取ります。

プロジェクトリンクを組織内のユーザーと共有するには、次の手順を実行します。

1. プロジェクトを保存します。保存されていない変更がある場合は、リンクを共有する前にプロジェクトを保存するように求められます。

1. **[!UICONTROL 共有]**／**[!UICONTROL Workspace ユーザーと共有]**&#x200B;を選択したあと、「**[!UICONTROL リンクで共有]**」フィールドの横の「**[!UICONTROL コピー]**」を選択します。

   ![「リンクで共有」フィールドをハイライト表示する共有プロジェクト。](assets/share-proj-modal.png)

1. リンクを組織内のユーザーと共有します。例えば、メールや内部 web サイトなどにペーストすることができます。

## 任意のユーザーとのプロジェクトの共有（ログイン不要） {#share-public-link}

>[!CONTEXTUALHELP]
>id="workspace_share_with_anyone_require_aec_authentication"
>title="Experience Cloud 認証を要求"
>abstract="組織でこのリンクを使用するには、ユーザーが Experience Cloud にログインする必要があります。"


Customer Journey Analytics にアクセスできないユーザーに Analysis Workspace プロジェクトへの[読み取り専用アクセス権](/help/analysis-workspace/curate-share/view-only-projects.md)を付与できます。この付与するアクセス権は、次のユーザーを含めることができます。

* 組織外のユーザー

* Customer Journey Analytics にアクセスできない、組織内のユーザー

>[!NOTE]
>
>Adobe Analytics にアクセスできないユーザーと Customer Journey Analytics プロジェクトを共有する場合は、次の点を考慮してください。
>
>* この方法でプロジェクトを共有する機能は、Customer Journey Analytics 管理者が無効にすることができます（[環境設定](/help/analysis-workspace/user-preferences.md)を参照）。この節での説明どおりにプロジェクトを共有できない場合は、Customer Journey Analytics 管理者の設定によって、この機能が無効になっています。
>
>* 50 を超えるビジュアライゼーションが展開されたプロジェクトは、Customer Journey Analytics にアクセスできるユーザーとのみ共有できます。
>
>* 共有相手となるユーザーは、[キュレーション](curate.md)中にプロジェクトに適用されたすべてのセグメントを表示できます。
> 
>* 共有相手となるユーザーは、プロジェクトの日付範囲を変更できます。プロジェクトに設定した日付範囲がデフォルトで表示されます。
>
>* 多数のユーザーが特定のリンクに同時にアクセスしようとすると、プロジェクトにアクセスできなくなる可能性があります。デフォルトでは、5 分ごとに 190 人を超えるユーザーが  1 つのリンクにアクセスできます。組織がこの上限に達した場合は、5 分待ってから、もう一度リンクにアクセスしてみてください。
>
>* [!DNL Healthcare Shield] ライセンスと [!DNL Privacy & Security Shield] ライセンスの両方で、[!UICONTROL 任意のユーザーと共有]機能を使用するには、Experience Cloud 認証が必要です。[!DNL Healthcare Shield] のお客様の場合、「HIPAA 準拠」の警告が表示されますが、Experience Cloud への認証後はこの機能を引き続き使用できます。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [任意のユーザーと共有](https://video.tv.adobe.com/v/3452450/?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


Analysis Workspace プロジェクトを任意のユーザーと共有するには：

1. 共有する Analysis Workspace プロジェクトを開きます。

1. **[!UICONTROL 共有]**／**[!UICONTROL 任意のユーザーと共有]**&#x200B;を選択します。

   保存されていない変更がある場合は、プロジェクトを保存するように求められます。

   <!-- Add screen shot of new modal -->

1. 「**[!UICONTROL リンクがアクティブです]**」オプションを有効にします（まだ有効になっていない場合）。

   このオプションを選択すると、任意のユーザーと共有できるプロジェクトへのリンクが作成されます。このオプションを無効にすることで、プロジェクトへのアクセスをいつでも無効にできます。

   また、プロジェクトの所有者もこのリンクの所有者です。Analytics 管理ガイドの[ユーザーアセットの転送](/help/tools/asset-transfer/transfer-assets.md)で説明されているように、リンクの所有権を別のユーザーに譲渡できるのは、プロジェクトの所有権を譲渡した場合のみです。

1. 次のセキュリティオプションを有効にするかどうかを選択します（このオプションは Customer Journey Analytics 管理者が制御できます）。

   * **[!UICONTROL Experience Cloud 認証を要求]：**

     このオプションを有効にした場合、プロジェクトにアクセスできるユーザーは、共有しているプロジェクトを作成した Adobe Experience Cloud 組織にログインできるユーザーのみになります。ただし、共有相手のユーザーは、Customer Journey Analytics へのアクセス権が不要です。

     Customer Journey Analytics 管理者は、[環境設定](/help/analysis-workspace/user-preferences.md)で説明されているように、会社用にこの環境設定を設定できます。管理者がどのようにこのオプションを設定したかによっては、次のシナリオが発生する可能性があります。

      * このオプションが表示されない場合、Customer Journey Analytics 管理者はこの機能を有効にしていません。

      * このオプションが有効になっていて無効にできない場合、ロックされたオプションは、Customer Journey Analytics 管理者が Analysis Workspace プロジェクトにアクセスする任意のユーザーに対して Experience Cloud 認証を要求することを意味します。これは、Healthcare Shield のライセンスを取得した組織には常に当てはまります。

1. 「**[!UICONTROL 任意のユーザーと共有（ログイン不要）]**」フィールドの横にある リンク を選択して、![リンク](/help/assets/icons/Link.svg) をシステムクリップボードにコピーします。

1. プロジェクトへのアクセス権を付与するユーザーとリンクを共有します。例えば、リンクをメールにペーストできます。

   リンクの共有相手であるユーザーであれば誰でも、Analysis Workspace プロジェクトを表示できます。

1. （オプション）![新しいリンクを生成アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) を選択すると、以前にプロジェクトへのリンクを受信したユーザーからのアクセスを削除できます。新しいリンクが生成され、プロジェクトへのアクセスを付与するユーザーにそのリンクを共有できます。

1. 「**[!UICONTROL 閉じる]**」を選択して、共有ダイアログボックスを閉じます。変更内容は自動的に保存されます。

## 共有されているプロジェクトの表示

ユーザーが[特定のプロジェクトの役割を共有](#share-a-specific-project-role)してプロジェクトを共有すると、[Analytics ランディングページの「プロジェクト」タブ](/help/getting-started/landing.md#navigate-the-projects-tab)から共有プロジェクトにアクセスできます。

ユーザーが（[「プロジェクトを共有」タブ](#share-a-link-to-a-project)から、または[任意のユーザーと共有のリンク](#share-a-project-with-anyone-no-login-required)を使用して）リンクを共有してプロジェクトを共有した場合、プロジェクトにアクセスするには、共有されたリンクを使用する必要があります。例えば、メールや内部 web サイトなどでリンクが共有されている場合があります。

## 埋め込みコンポーネントを共有

プロジェクトの一部である埋め込みコンポーネントを共有できます。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace での埋め込みコンポーネントの共有](https://video.tv.adobe.com/v/327498/?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


## よくある質問（FAQ） {#FAQs}

| 質問 | 回答 |
|---|---|
| 2 人の編集者が同時にプロジェクトを保存するとどうなりますか？ | 変更は結合されず、最後に保存したプロジェクトのバージョンが保持されます。Analysis Workspace は現在、ライブコラボレーションをサポートしていません。 |
| 管理者として、どのプロジェクトエクスペリエンスが表示されますか？ | **[!UICONTROL コピーを編集]**&#x200B;または&#x200B;**[!UICONTROL 読み取り専用]**&#x200B;の役割を付与された管理者は、プロジェクトを開いたときに、それらの限定的なエクスペリエンスを受け取ります。管理者は、必要に応じて、**[!UICONTROL コンポーネント]／[!UICONTROL プロジェクト]**&#x200B;を使用して、いつでも自分の役割を&#x200B;**[!UICONTROL オリジナルを編集]**&#x200B;に増やすことができます 。 |
| 受信者が 1 つの役割に個人として配置され、別の役割にグループのメンバーとして配置された場合はどうなりますか？ | 受信者が複数の役割に配置されている場合、常により高いエクスペリエンスを受け取ります。例えば、受信者に個人として&#x200B;**[!UICONTROL オリジナルを編集]**&#x200B;の役割、グループのメンバーとして&#x200B;**[!UICONTROL 表示可能]**&#x200B;の役割が付与されている場合、ユーザーは&#x200B;**[!UICONTROL オリジナルを編集]**&#x200B;プロジェクトエクスペリエンスを受信します。 |
| プロジェクトのリンクを開いた場合、ユーザーはどのようなエクスペリエンスを得られますか？ | 受信者は、共有モーダルに配置した役割を受け取ります。受信者に役割が割り当てられておらず、プロジェクトへのリンクを受信した場合（**[!UICONTROL 共有]**／**[!UICONTROL Workspace ユーザーと共有]**&#x200B;で、「**[!UICONTROL リンクごとに共有]**」フィールドの横にある「**[!UICONTROL コピー]**」を選択）、受信者はデフォルトの役割に配置されます。管理者は「**[!UICONTROL オリジナルを編集]**」の役割を受信し、管理者以外は「**[!UICONTROL コピーを編集]**」の役割を受信します。 |
