---
description: Customer Journey Analyticsデータの送信先となるクラウドの書き出し場所を管理します
keywords: Analysis Workspace
title: クラウドの書き出し場所とアカウントを管理
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 3d4017ba36ac4b0c9ccb10a3e3127c6ea386fb1e
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 6%

---

# クラウドの書き出し場所とアカウントを管理

クラウドの書き出し場所を表示、編集、削除できます。

新しいロケーションの作成方法について詳しくは、 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

## フィルターと検索場所

必要な情報を検索するには、場所のリストをフィルターするか、場所を検索します。

### 場所のリストをフィルター

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] タブをクリックします。

1. を選択します。 **フィルター** アイコン。

   <!-- add screenshot -->

   次の条件でフィルタリングできます。

   | フィルター | 説明 |
   |---------|----------|
   | [!UICONTROL **場所タイプ**]<!--should this be changed to Account type?--> | 場所が関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP データランディングゾーン**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **アカウント**] | 場所が関連付けられているアカウントの名前。 |
   | [!UICONTROL **作成者**] | ロケーションを作成したユーザーの電子メールアドレス。 |

   {style="table-layout:auto"}

### 場所の検索

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] タブをクリックします。

1. 「検索」タブで、検索する場所に関連する情報を入力します。 テーブル内の任意の列からデータを検索できます。

## 場所の編集

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] 」タブをクリックし、編集する場所を選択します。

   <!-- add screenshot? -->

1. 「[!UICONTROL **編集**]」を選択します。

1. 必要に応じて変更を加え、「 」を選択します。 [!UICONTROL **保存**].

## 場所の削除

場所を削除すると、その場所を使用する書き出しもすべて削除されます。

ロケーションを削除する前に、まず、ロケーション名の横にある情報アイコンを選択して、そのロケーションがエクスポートで使用されているかどうかを確認します。

![接続されたエクスポート](assets/location-connected-exports.png)

場所を削除するには：

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] 」タブをクリックし、削除する 1 つ以上の場所を選択します。

   <!-- add screenshot? -->

1. 選択 [!UICONTROL **削除**]&#x200B;を選択し、「 [!UICONTROL **削除**] を再び確認ダイアログに表示します。

## アカウントの編集

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所のアカウント**] タブをクリックします。

   ![アカウントページ](assets/account-page.png)

1. 選択 [!UICONTROL **詳細を表示**] を編集するアカウントに設定します。

1. 必要に応じて変更を加え、「 」を選択します。 [!UICONTROL **保存**].

## アカウントの削除

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所のアカウント**] タブをクリックします。

   ![アカウントページ](assets/account-page.png)

1. 編集するアカウントの 3 ドットアイコンを選択し、「 」を選択します。 [!UICONTROL **アカウントを削除**].

1. 選択 [!UICONTROL **削除**] を再び確認ダイアログに表示します。
