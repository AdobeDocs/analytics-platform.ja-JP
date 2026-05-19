---
title: B2B検索のためのデータセット変換
description: 特定のB2B ルックアップスキーマのデータセット内のデータを変換する方法について説明します
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
autotag-review: '2026-05-19T08:48:44.273Z'
TQID: 'https://experienceleague.adobe.com/hE-nAiD8K4lHdZkC2YJpqpqfh2d3CY6tq4KiTJjEXs0'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: bfef374d-acfd-4c57-bf74-a2b36053c545id: cf731116-8803-4027-85aa-9c0a126e8321id: e0cfe18a-f68c-495b-bafc-f6bcc0392d6c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 521
ht-degree: 10%

---

# B2B ルックアップ用にデータセットを変換

B2B データ（アカウント、商談、マーケティングリスト、キャンペーンなど）での個人ベースの検索をサポートするために、B2B ルックアップデータセットの変換を行うことで、データ精度を向上させることができます。

この変換は、次のクラスに基づくB2B ルックアップスキーマのデータを含むデータセットでのみ使用できます。

* [XDM Business Account Person Relation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM Business Opportunity Person Relation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM Business Marketing List Members](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM Business Campaign Members](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>各IDには、最大10,000個の項目の制限があります。 この制限は、任意の個人IDに対して、10,000個のアカウント、10,000個の商談、10,000個のマーケティングリスト、または10,000個のキャンペーンのみを持つことができることを意味します。

>[!PREREQUISITES]
>
>取り込みを正しく機能させるには、B2B ルックアップデータセットに次のフィールド（B2B ルックアップスキーマで定義されているもの）のデータが入力されていることを検証する必要があります。
>
>| スキーマに準拠するデータを含むデータセット | データが入力されたフィールド |
>|---|---|
>| XDM Business Account Person Relation | `accountPersonID` |
>| XDM ビジネスオポチュニティ人物 | `opportunityPersonID` |
>| XDM Business Marketing List | `marketingListMemberID` |
>| XDM Business Campaign Members | `campaign.sourceKey` |
>

B2B ルックアップデータセットの変換を有効にするには：

![変換データセットを有効にする](/help/connections/assets/transform.gif)

* 各データセットについて、**[!UICONTROL キー]**&#x200B;と&#x200B;**[!UICONTROL 一致するキー]**&#x200B;の推奨値を確認します。 推奨値から値を変更すると、続行を求める警告が表示されます。 次のことを確認する必要があります。

   * **Key**&#x200B;に選択する値は、Person ID データタイプに基づいています。
   * **一致するキー**&#x200B;に対して選択した値は、イベントデータセットのプライマリ ID フィールドとして定義されます。

* 新しいデータとデータセットのバックフィルを読み込むオプションを選択します。

* 「**[!UICONTROL B2B参照のデータセットを変換]**」を選択します。

  このオプションは、B2B シナリオでのユーザーベースの検索に使用できるようにデータセットを変換します。


  >[!IMPORTANT]
  >
  >一度オンにすると、接続が保存されると、変換は元に戻せません。 キー、一致するキーおよび変換データセット設定を変更することはできません。 データセットを削除、追加、再設定することしかできません。

既存の接続の一部となっている1つ以上のデータセットの変換を有効にするには：

1. 接続からデータセットを削除します。
1. 接続を保存します。
1. データセットの変換をオンにして、データセットを接続に追加します。

## 背景情報

上記の4つのスキーマクラスに基づくスキーマの変換されていないデータセットには、1つの人識別子に対して複数の行を含めることができます。 個人ベースの検索は、その人物IDの最新の発生にのみ一致するため、アカウント、商談、マーケティングリスト、またはキャンペーンの適切な人物IDの検索が妨げられます。

この変換により、4つのスキーマクラスのそれぞれのデータセットが変更され（下の図ではオレンジ色）、各人識別子に対して、ルックアップデータセット内の関連データ（アカウント、商談、マーケティングリスト、またはキャンペーン）用の（オブジェクト）配列が作成されます（下の図ではピンク色）。 この変換により、個人ID ベースの検索を正しく処理できるようになります。

![B2B スキーマ ](./assets/b2b-schemas.png)
