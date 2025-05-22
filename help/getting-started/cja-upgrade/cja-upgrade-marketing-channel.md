---
title: Customer Journey Analytics のマーケティングチャネル派生フィールドの作成
description: Customer Journey Analytics のマーケティングチャネル派生フィールドの作成方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '289'
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

Analytics ソースコネクタを使用すると、マーケティングチャネルデータがそのコネクタを通じて Customer Journey Analytics に送られます。従来の Adobe Analytics でマーケティングチャネルのルールを設定します。一部のルールはサポートされません。詳しくは、[マーケティングチャネルディメンションの使用](/help/use-cases/aa-data/marketing-channels.md)を参照してください。

Experience Platform Web SDK を使用する際に Customer Journey Analytics でマーケティングチャネルを使用するには、データビューで派生フィールドを使用して、Customer Journey Analytics に同じマーケティングチャネルと処理ルールを再作成できます。

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

   新しい派生フィールドは、データビューの左側のパネルのスキーマフィールドの一部として、派生フィールド／コンテナーに追加されます。

{{upgrade-final-step}}
