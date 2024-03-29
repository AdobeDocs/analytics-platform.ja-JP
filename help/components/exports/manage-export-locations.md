---
description: Customer Journey Analyticsデータの送信先となるクラウドの書き出し場所を管理します
keywords: Analysis Workspace
title: クラウドの書き出し場所とアカウントを管理
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 2%

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
   | [!UICONTROL **場所のタイプ**]<!--should this be changed to Account type?--> | 場所が関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP データランディングゾーン**]</li><li>[!UICONTROL **Amazon S3 ロール ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **アカウント**] | 場所が関連付けられているアカウントの名前。 |
   | [!UICONTROL **作成者**] | ロケーションを作成したユーザーの電子メールアドレス。 |

   {style="table-layout:auto"}

### 場所の検索

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] タブをクリックします。

1. 検索フィールドに、検索する場所に関連する情報を入力します。 テーブル内の任意の列からデータを検索できます。

## 場所の編集

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] 」タブをクリックし、編集する場所を選択します。

   ![「ロケーション」タブとロケーションのリストを示すエクスポートウィンドウ。](assets/locations-edit.png)

1. 「[!UICONTROL **編集**]」を選択します。

1. 必要に応じて変更を加え、「 」を選択します。 [!UICONTROL **保存**].

## 場所の削除

場所を削除すると、その場所を使用する書き出しもすべて削除されます。 削除時に確認ダイアログをチェックして、その場所にエクスポートが関連付けられていないことを確認します。

場所を削除するには：

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] 」タブをクリックし、削除する 1 つ以上の場所を選択します。

   ![「ロケーション」タブとロケーションのリストを表示するエクスポートウィンドウ](assets/locations-edit.png)

1. 「[!UICONTROL **削除**]」を選択します。

   [ 場所を削除 ] ダイアログボックスが表示されます。

1. [ 場所の削除 ] ダイアログボックスで、削除を確認する前に、場所が書き出しに関連付けられていないことを確認します。

   ![場所の削除確認ダイアログ](assets/delete-location-confirmation-dialog.png)

1. 選択 [!UICONTROL **削除**] 再び確認します。

## アカウントの編集

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所のアカウント**] タブをクリックします。

   ![「ロケーションアカウント」タブを表示する「エクスポート」ウィンドウ](assets/account-add.png)

1. 選択 [!UICONTROL **詳細を表示**] を編集するアカウントに設定します。

1. 必要に応じて変更を加え、「 」を選択します。 [!UICONTROL **保存**].

## アカウントキーを表示

アカウントを作成した後は、そのアカウントに関連付けられているすべてのアカウントキーを表示できます。 クラウドプロバイダーとのアカウント設定を完了していない場合は、この情報を表示する必要がある場合があります [アカウントを最初に設定したとき](/help/components/exports/cloud-export-accounts.md).

エクスポートアカウントに関連付けられたキーを表示するには：

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所のアカウント**] タブをクリックします。

   ![「ロケーションアカウント」タブを表示する「エクスポート」ウィンドウ](assets/account-add.png)

1. 編集するアカウントの 3 ドットアイコンを選択し、「 」を選択します。 [!UICONTROL **アカウントキー**].

## アカウントの削除

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所のアカウント**] タブをクリックします。

   ![「ロケーションアカウント」タブを表示する「エクスポート」ウィンドウ](assets/account-add.png)

1. 編集するアカウントの 3 ドットアイコンを選択し、「 」を選択します。 [!UICONTROL **アカウントを削除**].

1. 選択 [!UICONTROL **削除**] を再び確認ダイアログに表示します。
