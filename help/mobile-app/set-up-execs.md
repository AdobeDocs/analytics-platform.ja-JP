---
description: Adobe Analyticsダッシュボードのモバイルアプリを使用するようにユーザーを設定する方法
title: ダッシュボードを使用するエグゼクティブの設定
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/78Bp5YSZg7Qs-qBnCfIoS6mjxda7CAglDG19Qq07Fw4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b743a5d9-dc51-41ed-8b2f-86a1f8de430fid: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b21c7889-c659-4a99-a779-de1bae57e47eid: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 720
ht-degree: 65%

---

# ダッシュボードを使用するエグゼクティブユーザーの設定

場合によっては、エグゼクティブユーザーがアプリケーションにアクセスして使用するために追加の支援が必要になることがあります。 この節では、キュレーターが支援を提供するための情報を提供します。

## アプリユーザーが Adobe Analytics のアクセス権を持っていることを確認します

1. [CX Enterprise Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=ja)で新規ユーザーを設定します。

1. スコアカードを共有できるようにするには、Analysis Workspace、スコアカードの基になるデータビュー、セグメント、指標、ディメンションなどのスコアカードコンポーネントにアクセスする権限をアプリユーザーに付与する必要があります。

## アプリユーザーのシステム前提条件

エグゼクティブユーザーがアプリのスコアカードにアクセスできるようにするには、次の点を確認します。

* ユーザーのモバイル OS が、iOS バージョン 10 以上または Android バージョン 4.4（KitKat）以上である。
* Customer Journey Analyticsに有効なログイン情報があります。
* モバイルスコアカードを正しく作成し、共有している。
* ユーザーがスコアカードに含まれるコンポーネントにアクセスできる。 スコアカードを共有する際に、「**[!UICONTROL 埋め込みコンポーネントを共有]**」オプションを選択することもできます。

## エグゼクティブによるアプリのダウンロードとインストールの支援

>[!NOTE]
>
>モバイルアプリの名前はアプリストアのAdobe Analytics ダッシュボードですが、このアプリはCustomer Journey Analytics モバイルスコアカードでも同じように使用できます。

**iOS**：

次のリンク（**[!UICONTROL ツール]**/**[!UICONTROL Analytics ダッシュボード（モバイルアプリ）]**&#x200B;の下にあるCustomer Journey Analyticsでも使用できます）をクリックし、プロンプトに従ってアプリをダウンロード、インストール、開きます。

`[iOS link](https://apple.co/2zXq0aN)`

**Android**：

次のリンク（**[!UICONTROL ツール]**/**[!UICONTROL Analytics ダッシュボード（モバイルアプリ）]**&#x200B;の下にあるCustomer Journey Analyticsでも使用できます）をクリックし、プロンプトに従ってアプリをダウンロード、インストール、開きます。

`[Android link](https://bit.ly/2LM38Oo)`

ダウンロードしてインストールすると、エグゼクティブユーザーは既存のCustomer Journey Analytics資格情報を使用してアプリにサインインできます。アドビは、AdobeとEnterprise/Federated IDの両方をサポートしています。

![Adobe Analytics ダッシュボードようこそ画面](assets/welcome.png)

## エグゼクティブによるスコアカードへのアクセスの支援

1. エグゼクティブユーザーにアプリにログインしてもらいます。

   **[!UICONTROL 会社を選択]**&#x200B;画面が表示されます。 この画面には、エグゼクティブユーザーが所属するログイン会社が表示されます。

1. 共有したスコアカードに適用されるログイン会社またはCX Enterprise Orgの名前をタップしてもらいます。

   スコアカードリストに、そのログイン会社のエグゼクティブと共有されているすべてのスコアカードが表示されます。

1. 該当する場合は、**[!UICONTROL 最近変更された項目]**&#x200B;で、このリストを並べ替えてもらいます。

1. スコアカードの名前をタップして表示してもらいます。

   ![会社を選択](assets/accesscard.png)


### スコアカード UI の説明

共有するスコアカードにタイルが表示される仕方をエグゼクティブユーザーに説明します。

![選択した日付範囲、セグメント、指標およびディメンションを含むタイルを説明](assets/newexplain.png)

![スコアカードの例](assets/intro_scorecard.png)

タイルに関する追加情報：

* スパークラインの精度は、日付範囲の長さに依存します。
* 1 日 - 時間ごとの傾向を表示
   * 2 日以上 1 年未満 - 毎日の傾向を表示。
   * 1 年以上 - 毎週の傾向を表示。
   * 値の変化パーセントの式は、（指標合計（現在の日付範囲） - 指標合計（比較日付範囲））÷指標合計（比較日付範囲）です。
   * 画面をプルダウンして、スコアカードを更新できます。


1. タイルをタップすると、そのタイルの詳細な分類の仕組みを表示できます。

   ![分類ビュー](assets/sparkline.png)

   * スパークライン上の任意のポイントをタップすると、そのポイントに関連付けられたデータがライン上に表示されます。

   * タイルに追加されたディメンションのデータを表示するテーブルが含まれます。 下向き矢印をタップして、ディメンションを選択します。 タイルにディメンションが追加されていない場合は、テーブルにグラフデータが表示されます。

1. スコアカードの日付範囲を変更するには、「日付」ヘッダーをタップし、表示するプライマリと比較の日付範囲の組み合わせを選択します。

   ![日付変更](assets/changedate.png)

## アプリの環境設定の変更

環境設定を変更するには、上記の「**[!UICONTROL 環境設定]**」オプションをタップします。 環境設定で、生体認証ログインをオンにするか、次に示すようにアプリケーションのダークモードを設定できます。

![ダークモード](assets/darkmode.png)

## トラブルシューティング

エグゼクティブユーザーがログインし、何も共有されていないというメッセージが表示された場合、次の可能性があります。

![何も共有されていない](assets/nothing.png)

* エグゼクティブユーザーが間違ったCustomer Journey Analytics サンドボックスを選択した可能性があります。または
* スコアカードがエグゼクティブユーザーと共有されていない

エグゼクティブユーザーが適切なCustomer Journey Analytics サンドボックスにログインでき、スコアカードが共有されていることを確認します。
