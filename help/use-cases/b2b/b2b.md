---
title: アカウントレベルのデータをルックアップデータセットとして追加
description: アカウントベースのデータをルックアップデータセットとしてCustomer Journey Analyticsに追加する方法を説明します
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: d2bb21939f861d83b6c306ac548e4fb35cbd19a4
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 74%

---

# アカウントレベルのデータをルックアップデータセットとして追加

B2B のこのユースケースは、個人レベルではなくアカウントレベルのデータを分析用に指定する方法を示しています。アカウントレベルの分析は、以下のような質問に答えられます。

* このアカウントと一致する会社名
* このアカウントまたは会社に関連付けられている従業員の数
* このアカウントがどのような役割を示すか
* 別のアカウントと比較して、このアカウント全体が特定のマーケティングキャンペーンに対してどのように機能しているか
* 1 つのアカウントの特定の役割（IT マネージャーなど）が、別のアカウントの同じ役割とは異なる動作をしているか

これらをすべて実現するには、アカウントレベルの情報を[ルックアップ](/help/getting-started/cja-glossary.md)データセットとして取り込みます。

最初にAdobe Experience Platformでルックアップスキーマを作成し、次に.csv ベースのアカウントレベルのデータを取り込んでルックアップテーブルデータセットを作成します。 次に、作成したルックアップデータなど、異なるデータセットを組み合わせた接続 (Customer Journey Analytics) の作成に進みます。 その後、データビューを作成し、最終的にワークスペースでこれらのデータをすべて利用できるようになります。

>[!NOTE]
>
>ルックアップテーブルのサイズは最大 1GB です。

## 1. ルックアップスキーマの作成（Experience Platform）

用に独自のスキーマを作成する [参照](/help/getting-started/cja-glossary.md) テーブルでは、使用するデータセットが、正しい設定（レコードタイプ）でCustomer Journey Analyticsして使用できることを確認します。 ベストプラクティスは、「Lookup」と呼ばれる、すべての要素が空ですべてのルックアップテーブルに再使用できる[カスタムスキーマクラスを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#create-new-class)することです。

![](../assets/create-new-class.png)

## 2.ルックアップデータセットの作成 (Experience Platform)

スキーマを作成したら、そのスキーマから、Experience Platform でルックアップデータセットを作成する必要があります。このルックアップデータセットには、会社名、従業員の総数、ドメイン名、所属業種、年間売上高、Experience Platformの現在の顧客かどうか、販売段階、アカウント内のどのチームがCustomer Journey Analyticsを使用しているかなど、アカウントレベルのマーケティング情報が含まれます。

1. Adobe Experience Platform で、**[!UICONTROL データ管理／データセット]**&#x200B;に移動します。
1. 「**[!UICONTROL + データセットを作成]**」をクリックします。
1. 「**[!UICONTROL スキーマからのデータセットの作成]**」をクリックします。
1. 作成したルックアップスキーマクラスを選択します。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. データセットに名前を付け（この例では「B2B Info」）、説明を入力します。
1. 「**[!UICONTROL 完了]**」をクリックします。

## 3. Experience Platform へのデータの取得

CSV ファイルを使用している場合は、[CSV ファイルを XDM スキーマにマップ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=ja)する方法に関する説明が役立ちます。

[その他の方法](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja)も利用できます。

データのオンボーディングとルックアップの確立には、ルックアップテーブルのサイズに応じて、約 2 ～ 4 時間かかります。

## 4. データセットを結合した接続（Customer Journey Analytics）

この例では、3 つのデータセットを 1 つのCustomer Journey Analytics接続に組み合わせます。

| データセット名 | 説明 | Adobe Experience Platform Schema クラス | データセットの詳細 |
| --- | --- | --- | --- |
| B2B インプレッション | アカウントレベルのクリックストリーム、イベントレベルのデータが含まれます。例えば、マーケティング広告を実行するための電子メール ID と対応するアカウント ID、およびマーケティング名が含まれます。また、各ユーザーに対するこれらの広告のインプレッションも含まれます。 | XDM ExperienceEvent スキーマクラスに基づく | `emailID` はプライマリ ID として使用され、 `Customer ID` 名前空間が割り当てられています。その結果、この変数は Customer Journey Analytics でデフォルトの&#x200B;**[!UICONTROL ユーザー ID]** として表示されます。![インプレッション](../assets/impressions-mixins.png) |
| B2B プロファイル | このプロファイルデータセットは、役職、所属先のアカウント、LinkedIn プロファイルなど、アカウント内のユーザーに関する詳細情報を提供します。 | XDM 個人版プロファイルスキーマクラスに基づく | 選択 `emailID` をプライマリ ID として設定します。 |
| B2B 情報 | 上記の「ルックアップデータセットの作成」を参照してください。 | B2BAccount（カスタムルックアップスキーマクラス） | A と B の関係 `accountID` と B2B インプレッションデータセットは、次の手順に従って、Customer Journey Analyticsの B2B 情報データセットと B2B インプレッションデータセットを接続することで、自動的に作成されています。 ![ルックアップ](../assets/lookup-mixins.png) |

データセットを組み合わせる方法を次に示します。

1. Customer Journey Analytics で、「 **[!UICONTROL 接続]**」タブをクリックします。
1. 結合するデータセット（この例では、上記の 3 つ）を選択します。
1. B2B 情報データセットの場合、ルックアップテーブルで使用される `accountID` キーを選択します。次に、一致するキー（対応するディメンション）と、イベントデータセットで `accountID` を選択します。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. [これらの手順](/help/connections/create-connection.md)に従って、接続に名前を付けて説明し、設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## 5. 接続に基づくデータビューの作成

手順に従い、[データビューを作成します](/help/data-views/create-dataview.md)。

* データセットから必要なすべてのコンポーネント（ディメンションおよび指標）を追加します。

## 6. ワークスペースでのデータの分析

3 つのすべてのデータセットのデータに基づいてワークスペースプロジェクトを作成できるようになりました。

例えば、「はじめに」に記載されている問題への回答を検索できます。

* 電子メール ID を accountID で分類し、電子メール ID が属する会社を特定します。
* 特定のアカウント ID にマッピングされる従業員の数は？
* アカウント ID はどの業種に属していますか。

![project-lookup2](assets/analyze.png)
