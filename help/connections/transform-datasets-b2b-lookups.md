---
title: B2B ルックアップ用のデータセットの変換
description: 特定の B2B ルックアップスキーマのデータセットのデータを変換する方法について説明します
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: eef9b420f1016254dece0a916b82bc99e2ca866e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# B2B ルックアップ用のデータセットの変換

B2B データ（アカウント、商談、マーケティングリスト、キャンペーンを含む）に対するユーザーベースの検索をサポートするには、B2B 検索データセットの変換が必要です。

この変換は、次のクラスに基づく、B2B ルックアップスキーマ用のデータを含んだデータセットでのみ使用できます。

* [XDM ビジネスアカウント人物関係 ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM ビジネスオポチュニティ人物関係 ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM ビジネスマーケティングリストメンバー ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM ビジネスキャンペーンメンバー ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>各 ID には、10,000 項目以下の制限があります。 つまり、特定のユーザー id に対して、10,000 個のアカウント、10,000 個のオポチュニティ、10,000 個のマーケティングリスト、10,000 個のキャンペーンのみを持つことができます。


このようなデータセットの変換を有効にするには：

![ 変換データセットを有効にする ](assets/transform-dataset.gif)

* **[!UICONTROL キー]** および **[!UICONTROL 一致するキー]** に対して適切な識別子（例：`personKey.sourceKey`）を選択してください。

* 新しいデータの読み込みとデータセットのバックフィルに関するオプションを選択します。

* **[!UICONTROL B2B ルックアップ用のデータセットを変換]** を選択します。

  このオプションは、B2B シナリオでのユーザーベースの検索に使用できるように、データセットを変換します。


  >[!IMPORTANT]
  >
  >オンにした後、接続を保存すると、変換は元に戻せなくなります。 接続を保存した後は、データセットを削除して接続にもう一度追加する以外に、データセットの変換設定を変更することはできません。

既に既存の接続に含まれている 1 つ以上のデータセットの変換を有効にするには：

1. 接続からデータセットを削除します。
1. 接続を保存します。
1. データセットの変換を有効にしながら、データセットを接続に追加します。

## 背景情報

前述の 4 つのスキーマクラスに基づくスキーマの場合、変換されないデータセットには、1 つのユーザー識別子に対して複数の行を含めることができます。 ユーザーベースの検索は、そのユーザー ID の最新の出現箇所にのみ一致し、アカウント、機会、マーケティングリストまたはキャンペーンのユーザー ID ベースの適切な検索を防ぎます。

変換により、4 つのスキーマクラス（下図のオレンジ色）のデータセットが変更され、各個人識別子に対して、ルックアップデータセットに関連するデータ（アカウント、商談、マーケティングリストまたはキャンペーン）の（オブジェクト）配列（下図のピンク色）が作成されます。 この変換により、人物 ID ベースの検索を正しく機能させることができます。

![B2B スキーマ ](./assets/b2b-schemas.svg)
