---
title: Customer Journey Analytics用マーケティングチャネル派生フィールドの作成
description: Customer Journey Analytics用のマーケティングチャネル派生フィールドの作成方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 4%

---

# Customer Journey Analytics用マーケティングチャネル派生フィールドの作成 {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="マーケティングチャネル派生フィールドの作成"
>abstract="派生フィールドは、データビュー内で作成されます。<br><br> デフォルトのマーケティングチャネル設定の使用は数分で済みます。高度にカスタマイズされたマーケティングチャネル設定の作成には数時間かかる場合があります。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Analytics ソースコネクタを使用する場合、マーケティングチャネルのデータは、そのコネクタを通じてCustomer Journey Analyticsに送られます。 従来の Adobe Analytics でマーケティングチャネルのルールを設定します。一部のルールはサポートされません。詳しくは、[ マーケティングチャネルディメンションの使用 ](/help/use-cases/aa-data/marketing-channels.md) を参照してください。

Experience Platform Web SDKを使用する際に、Customer Journey Analyticsでマーケティングチャネルを使用するために、データビューで派生フィールドを使用して、Customer Journey Analyticsと同じマーケティングチャネルと処理ルールを再作成できます。

1. Customer Journey Analyticsで、マーケティングチャネルを追加するデータビューを選択します。

1. データビューで、**[!UICONTROL コンポーネント]** タブを選択します。

1. 左パネルで「**[!UICONTROL 派生フィールドを作成]**」を選択します。

1. **[!UICONTROL 派生フィールドを作成]** ダイアログボックスで、ドロップダウンメニューから **[!UICONTROL 関数テンプレート]** を選択します。

   ![ 派生フィールド関数テンプレートの作成 ](assets/derived-field-create.png)

1. **[!UICONTROL マーケティングチャネル]** テンプレートを空白のキャンバスにドラッグします。

1. 各マーケティングチャネルのロジックをカスタマイズし、Adobe Analytics環境で各チャネルを識別するために使用するロジックと一致するようにします。

   出力チャネル名を変更したり、ロジックを追加して組織に固有の追加チャネルを識別したりできます。

1. 右側の列で、マーケティングチャネルの名前と説明を指定します。

1. 「**[!UICONTROL 保存]**」を選択します。

   新しい派生フィールドが、データビューの左側のパネルのスキーマフィールドの一部として、派生フィールド/コンテナに追加されます。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
