---
title: 接続への Analytics ソースコネクタデータセットの追加
description: 接続に Analytics ソースコネクタデータセットを追加する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: d30a1a7cbe441529f5b094215c0ea1131c1f67fc
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 38%

---

# 接続への Analytics ソースコネクタデータセットの追加

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

[ 履歴データ用の Analytics ソースコネクタを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md) すると、Analytics データ用のデータセットが自動的に作成されます。

この自動作成されたデータセットを、Web SDK 実装用に作成したのと同じ接続に追加する必要があります。 これにより、Analytics データが、Web SDK データとCustomer Journey Analyticsが同じデータビューになります。

自動的に作成されたデータセットを Web SDK 実装用に作成したのと同じ接続に追加するには：

1. Customer Journey Analytics で、「**[!UICONTROL 接続]**」タブをクリックします。

1. [Web SDK 実装用に作成した ](/help/getting-started/cja-upgrade/cja-upgrade-connection.md) 接続を選択します。

1. 「**[!UICONTROL 編集]**」を選択します。

   ![接続を編集](assets/connection-add-dataset.png)

1. 右上の「**[!UICONTROL データセットを追加]**」を選択します。

   ![接続を編集](assets/connection-add-dateset2.png)

1. スクロールして、Analytics ソースコネクタの作成時に自動的に作成されたデータセットを探します。

   このデータセットの名前は、レポートスイートの名前の後に `midValues` を付けたものです。 例：`My report suite midValues`

1. データセット名の横にあるチェックボックスをオンにし、「**[!UICONTROL 次へ]**」を選択します。

   ![接続を編集](assets/connection-add-dataset3.png)

1. 次の情報を指定します。

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL ユーザー ID]** | イベントデータセットとプロファイルデータセットでのみ使用できます。 使用可能な ID のドロップダウンリストからユーザー ID を選択します。 これらの ID は、Experience Platform 内のデータセットスキーマで定義されています。 ユーザー ID として ID マップを使用する方法については、次を参照してください。<p>選択するユーザー ID がない場合は、1 つ以上のユーザー ID がスキーマで定義されていないことを意味します。 詳しくは、[UI で ID フィールドを定義](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity)を参照してください。 <p>選択したユーザー ID の値は、大文字と小文字が区別されると見なされます。 例えば、`abc123` と `ABC123` は 2 つの異なる値です。 |
   | **[!UICONTROL タイムスタンプ]** | イベントおよび概要データセットの場合のみ、この設定は、Experience Platform のイベントベースのスキーマからデフォルトのタイムスタンプフィールドに自動的に設定されます。 |
   | **[!UICONTROL タイムゾーン]** | 概要データでのみ使用できます。 時系列の概要データに適したタイムゾーンを選択します。 |
   | **[!UICONTROL データソースタイプ]** | データソースのタイプを選択します。 <br/>データソースのタイプを以下に示します。 <ul><li>[!UICONTROL Web データ]</li><li>[!UICONTROL モバイルアプリデータ]</li><li>[!UICONTROL POS データ]</li><li>[!UICONTROL CRM データ]</li><li>[!UICONTROL サーベイデータ]</li><li>[!UICONTROL コールセンターデータ]</li><li>[!UICONTROL 製品データ]</li><li> [!UICONTROL アカウントデータ]</li><li> [!UICONTROL トランザクションデータ]</li><li>[!UICONTROL 顧客フィードバックデータ]</li><li> [!UICONTROL その他]</li></ul>このフィールドは、使用中のデータソースのタイプを調査するために使用します。 |

   {style="table-layout:auto"}

1. 「**[!UICONTROL 新しいデータをインポート]**」セクションで、「**[!UICONTROL すべての新しいデータをインポート]**」オプションを無効のままにします。

   履歴データに Analytics ソースコネクタデータセットを使用しているので、収集された将来のデータをこのデータセットに取り込みたくない場合があります。

1. 「**[!UICONTROL データセットのバックフィル]**」セクションで、「**[!UICONTROL バックフィルをリクエスト]**」を選択します。

1. 開始日と終了日を入力するか、カレンダーアイコン ![ カレンダー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) を選択して、バックフィルに含める期間を定義します。

   Analytics ソースコネクタは、実稼動用サンドボックスに（サイズに関係なく）最大 13 か月分のデータを読み込みます。 非実稼動用サンドボックスのバックフィルは、3 か月に制限されています。

   >[!IMPORTANT]
   >
   >バックフィルをリクエストする日付を指定する場合は、明示的に指定します。 終了日は、Web SDK 実装でデータの収集を最初に開始した日付にする必要があります。
   >
   >または、Web SDK 実装でデータの収集を初めて開始した日付の直後の日付を選択し、セグメントを使用して重複するデータを除外することもできます。

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. 「**[!UICONTROL キューのバックフィル]**」を選択します。

1. **[!UICONTROL データセットを追加]** を選択してから、「**[!UICONTROL 保存]** を選択して接続を保存します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。

