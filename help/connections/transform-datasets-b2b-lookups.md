---
title: B2B ルックアップ用にデータセットを変換
description: 特定の B2B ルックアップスキーマのデータセットのデータを変換する方法について説明します
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: 4ce2eb397e15dcb081f7b9695ba2332a3eb17659
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 4%

---

# B2B ルックアップ用にデータセットを変換

B2B データ（アカウント、商談、マーケティングリスト、キャンペーンを含む）に対するユーザーベースの検索をサポートするには、B2B 検索データセットの変換が必要です。

この変換は、次のクラスに基づく、B2B ルックアップスキーマ用のデータを含んだデータセットでのみ使用できます。

* [XDM ビジネスアカウント人物関係 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM ビジネスオポチュニティ人物関係 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM ビジネスマーケティングリストメンバー &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM ビジネスキャンペーンメンバー &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>各 ID には、10,000 項目以下の制限があります。 つまり、特定のユーザー id に対して、10,000 個のアカウント、10,000 個のオポチュニティ、10,000 個のマーケティングリスト、10,000 個のキャンペーンのみを持つことができます。

>[!PREREQUISITES]
>
>取り込みが正しく機能するには、B2B ルックアップデータセットに次のフィールドのデータが入力されていることを検証する必要があります（B2B ルックアップスキーマで定義されている）。
>
>| スキーマに準拠するデータを含むデータセット | データが入力されたフィールド |
>|---|---|
>| XDM Business Account Person Relation | `accountPersonID` |
>| XDM ビジネスオポチュニティ担当者 | `opportunityPersonID` |
>| XDM Business Marketing List | `marketingListMemberID` |
>| XDM Business Campaign Members | `campaign.sourceKey` |
>

B2B ルックアップデータセットの変換を有効にするには：

![&#x200B; 変換データセットを有効にする &#x200B;](/help/connections/assets/transform.gif)

* 各データセットについて、**[!UICONTROL キー]** と **[!UICONTROL 一致するキー]** の推奨値を確認します。 推奨値を変更すると、続行を求める警告が表示されます。 次の点を確認する必要があります。

   * **キー** に対して選択する値は、ユーザー ID データタイプに基づいています。
   * **一致するキー** に選択した値は、イベントデータセットのプライマリ ID フィールドとして定義されています。

* 新しいデータの読み込みとデータセットのバックフィルに関するオプションを選択します。

* **[!UICONTROL B2B ルックアップ用のデータセットを変換]** を選択します。

  このオプションは、B2B シナリオでのユーザーベースの検索に使用できるように、データセットを変換します。


  >[!IMPORTANT]
  >
  >オンにした後、接続を保存すると、変換は元に戻せなくなります。 キー、一致するキーおよび変換データセットの設定は変更できません。 データセットの削除、追加、再設定のみ可能です。

既に既存の接続に含まれている 1 つ以上のデータセットの変換を有効にするには：

1. 接続からデータセットを削除します。
1. 接続を保存します。
1. データセットの変換を有効にしながら、データセットを接続に追加します。

## 背景情報

前述の 4 つのスキーマクラスに基づくスキーマの場合、変換されないデータセットには、1 つのユーザー識別子に対して複数の行を含めることができます。 ユーザーベースの検索は、そのユーザー ID の最新の出現箇所にのみ一致し、アカウント、機会、マーケティングリストまたはキャンペーンのユーザー ID ベースの適切な検索を防ぎます。

変換により、4 つのスキーマクラス（下図のオレンジ色）のデータセットが変更され、各個人識別子に対して、ルックアップデータセットに関連するデータ（アカウント、商談、マーケティングリストまたはキャンペーン）の（オブジェクト）配列（下図のピンク色）が作成されます。 この変換により、人物 ID ベースの検索を正しく機能させることができます。

![B2B スキーマ &#x200B;](./assets/b2b-schemas.svg)
