---
title: Customer Journey Analytics のマーケティングチャネル派生フィールドの作成
description: Customer Journey Analytics のマーケティングチャネル派生フィールドの作成方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
TQID: 'https://experienceleague.adobe.com/nwxJ3KEss3SlZxpGB-CW4qDW9QpQqXL1kN-VslhuAVE'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 100%
---
# Customer Journey Analytics のマーケティングチャネル派生フィールドの作成 {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="マーケティングチャネル派生フィールドの作成"
>abstract="派生フィールドは、データビュー内で作成されます。<br><br>デフォルトのマーケティングチャネル設定を使用する場合は数分しかかかりませんが、高度にカスタマイズされたマーケティングチャネル設定を作成するには数時間かかる可能性があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Analytics ソースコネクタを使用すると、マーケティングチャネルデータがそのコネクタを通じて Customer Journey Analytics に送られます。 マーケティングチャネルのルールは従来の Adobe Analytics で構成されており、一部のルールはサポートされません。 詳しくは、[マーケティングチャネルディメンションの使用](/help/use-cases/aa-data/marketing-channels.md)を参照してください。

Experience Platform Web SDK を使用する際に Customer Journey Analytics でマーケティングチャネルを利用するには、データビューで派生フィールドを使用して、Customer Journey Analytics 用に同じマーケティングチャネルと処理ルールを再作成できます。

1. Customer Journey Analytics で、マーケティングチャネルを追加するデータビューを選択します。

1. データビューで、「**[!UICONTROL コンポーネント]**」タブを選択します。

1. 左側のパネルで、「**[!UICONTROL 派生フィールドを作成]**」を選択します。

1. **[!UICONTROL 派生フィールドを作成]**&#x200B;ダイアログボックスで、ドロップダウンメニューから「**[!UICONTROL 関数テンプレート]**」を選択します。

   ![派生フィールド関数テンプレートを作成](assets/derived-field-create.png)

1. **[!UICONTROL マーケティングチャネル]**&#x200B;テンプレートを空白のキャンバスにドラッグします。

1. 各マーケティングチャネルのロジックをカスタマイズし、Adobe Analytics 環境で各チャネルの識別に使用するロジックと一致するようにします。

   組織に固有の追加チャネルを識別するには、出力チャネル名を変更するか、ロジックを追加します。

1. 右側の列で、マーケティングチャネルの名前と説明を指定します。

1. 「**[!UICONTROL 保存]**」を選択します。

   新しい派生フィールドは、データビューの左側のパネルにあるスキーマフィールドの一部として、派生フィールド／コンテナに追加されます。

{{upgrade-final-step}}
