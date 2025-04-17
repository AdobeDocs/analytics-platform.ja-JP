---
title: Customer Journey Analytics でデータを分類するためのルックアップデータセットを作成する
description: Customer Journey Analytics でルックアップデータセットを作成してデータを分類する方法を学ぶ
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 96%

---

# Customer Journey Analytics でデータを分類するためのルックアップデータセットを作成する {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="分類データを含む各ディメンションのルックアップデータセットを作成"
>abstract="Adobe Analytics のデータの分類と同様に、ルックアップデータセットは、Customer Journey Analytics のデータを分類するための手段です。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Analytics のデータの分類と同様に、ルックアップデータセットは、Customer Journey Analytics のデータを分類するための手段です。

Analytics ソースコネクタを使用する場合、一部の標準検索データセットは、レポート時に自動的に適用されます。詳しくは、[データセットへの標準検索の追加](/help/connections/standard-lookups.md)を参照してください。

Experience Platform Web SDK を使用する場合、Customer Journey Analytics でデータを分類するには、分類するデータを含む各ディメンションのカスタムスキーマとルックアップデータセットを作成する必要があります。

## ルックアップデータセットで使用するカスタムスキーマの作成

Customer Journey Analytics で分類するデータを含むカスタムスキーマをディメンションごとに新規作成します。後の手順でルックアップデータセットを作成する際に、このスキーマが参照されます。

分類するデータを含む各ディメンションに対して、このプロセスを繰り返します。

Customer Journey Analytics でルックアップデータセットと併用するスキーマを作成するには、次の手順を実行します。

1. Adobe Experience Platform で、左パネルの「**[!UICONTROL データ管理]**」セクションの「**[!UICONTROL スキーマ]**」を選択します。

1. 「**[!UICONTROL スキーマを作成]**」を選択します。

   ![スキーマ作成ボタン](assets/schema-create.png)

1. 「**[!UICONTROL 手動]**」を選択します。これにより、フィールドとフィールドグループをスキーマに手動で追加できます。「**[!UICONTROL 選択]**」を選択して、作成ウィザードの次のページに進みます。

1. **[!UICONTROL スキーマの詳細]**&#x200B;ページで、「**[!UICONTROL その他]**」を選択し、「**[!UICONTROL カスタム]**」を選択します。

   ![カスタムを作成](assets/schema-custom.png)

1. 「**[!UICONTROL クラスを作成]**」を選択します。

   <!-- add screenshot -->

1. **[!UICONTROL クラスを作成]**&#x200B;ダイアログボックスで、スキーマの名前と説明を指定し、「**[!UICONTROL レコード]**」を選択してから「**[!UICONTROL 作成]**」を選択します。

1. [ルックアップデータセットの作成](#create-a-lookup-dataset)を参照してください。

## ルックアップデータセットの作成

[カスタムスキーマを作成](#create-a-custom-schema-to-use-with-the-lookup-dataset)してルックアップデータセットに使用するには、ルックアップデータセットを作成してスキーマにマッピングする必要があります。

分類するデータを含む各ディメンションに対して、このプロセスを繰り返します。

Customer Journey Analytics でスキーマと併用するルックアップデータセットを作成するには、次の手順を実行します。

>[!NOTE]
>
>次のプロセスでは、CSV ファイルを使用してデータセットを作成します。また、データストリームの設定など、Experience Platform へのデータの読み込みに使用できるその他の方法も使用できます。

1. Adobe Experience Platform で、左側のパネルの「**[!UICONTROL ワークフロー]**」を選択します。

   ![カスタムを作成](assets/lookup-dataset-workflows.png)

1. 「**[!UICONTROL CSV を XDM スキーマにマッピング]**」を選択し、「**[!UICONTROL 開始]**」を選択します。

1. 「**[!UICONTROL データセットの詳細]**」セクションで、「**[!UICONTROL 新しいデータセット]**」を選択します。

1. データセットの名前と説明を指定します。

1. 「**[!UICONTROL スキーマ]**」フィールドで、[ルックアップデータセットのスキーマの作成](#create-a-schema-for-lookup-datasets)の説明に従って、ルックアップデータセット用に作成したスキーマを選択します。

1. 「**[!UICONTROL 次へ]**」を選択します。

1. **[!UICONTROL CSV を XDM スキーマにマッピング]**&#x200B;ページの「**[!UICONTROL ファイルをアップロード]**」セクションで、「**[!UICONTROL ファイルを選択]**」を選択します。次に、分類データを適用するディメンションの分類情報を含むファイルをファイルシステムで参照します。例えば、フィールド ID と対応するフィールド名を一覧表示するスプレッドシートなどがあります。<!-- correct? How can I better explain what this file is?-->

   ![CSV ファイルのマッピング](assets/lookup-map-csv.png)

1. 「**[!UICONTROL 次へ]**」を選択します。

1. ファイルをアップロードした後、マッピングが正確であることを確認します。CSV ファイルの列は「**[!UICONTROL ソースフィールド]**」の下にリストされ、対応する XDM スキーマフィールドが「**[!UICONTROL ターゲットフィールド]**」の下にリストされます。

   Platform は、選択したターゲットスキーマまたはデータセットに基づいて、自動マッピングされたフィールドに対してインテリジェントなレコメンデーションを自動的に提供します。 マッピングルールは、ユースケースに合わせて手動で調整できます。

   マッピングプロセスについて詳しくは、Experience Platform ドキュメントの[既存の XDM スキーマへの CSV ファイルのマッピング](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)を参照してください。

1. 「**[!UICONTROL 完了]**」を選択します。

1. [Customer Journey Analytics の接続へのルックアップデータセットの追加](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics)に進みます。

## Customer Journey Analytics の接続へのルックアップデータセットの追加

[カスタムスキーマを作成](#create-a-custom-schema-to-use-with-the-lookup-dataset)し、[ルックアップデータセットを作成](#create-a-lookup-dataset)したら、Customer Journey Analytics の接続にルックアップデータセットを追加する必要があります。

分類するデータを含む各ディメンションに対して、このプロセスを繰り返します。

Customer Journey Analytics の接続にルックアップデータセットを追加するには：

1. Customer Journey Analyticsで、必要に応じて ]**データ管理**[!UICONTROL  から「**[!UICONTROL 接続]**」を選択します。

1. ルックアップデータセットを追加する接続の横にある ![その他アイコン](assets/More.svg) を選択してから、「**[!UICONTROL 編集]**」を選択します。

   <!-- add screenshot -->

1. 「**[!UICONTROL データセットを追加]**」を選択します。

1. **[!UICONTROL データセットを追加]**&#x200B;ダイアログボックスで、作成したルックアップデータセットを選択し、「**[!UICONTROL 次へ]**」を選択します。

1. 「**[!UICONTROL ユーザー ID]**」フィールドで、Experience Platform で設定したデータセットスキーマで定義されている使用可能な ID からユーザー ID を選択します。<!-- fill out other fields? -->

1. 「**[!UICONTROL データセットを追加]**」を選択し、「**[!UICONTROL 保存]**」を選択します。

   <!-- is there a step right in between here where you select the dataset -->

1. 「**[!UICONTROL キー]**」フィールドと「**[!UICONTROL 一致するキー]**」フィールドを使用して、ルックアップデータセットのフィールドとイベントデータセットまたは概要データセットのフィールドの間に相関性を作成します。

1. すべてのルックアップデータセットがCustomer Journey Analyticsの接続に追加されるまで、このプロセスを繰り返します。

{{upgrade-final-step}}

