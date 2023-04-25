---
title: （B2B）ルックアップデータセットとしてアカウントレベルのデータを追加
description: アカウントベースのデータをルックアップデータセットとして CJA に追加する方法を学びます。
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 8e902022c07376fb3c13cad5fd5b1efa655c9424
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 96%

---

# （B2B）ルックアップデータセットとしてアカウントレベルのデータを追加

B2B のこのユースケースは、個人レベルではなくアカウントレベルのデータを分析用に指定する方法を示しています。アカウントレベルの分析は、以下のような質問に答えられます。

* このアカウントと一致する会社名
* このアカウントまたは会社に関連付けられている従業員の数
* このアカウントがどのような役割を示すか
* 別のアカウントと比較して、このアカウント全体が特定のマーケティングキャンペーンに対してどのように機能しているか
* 1 つのアカウントの特定の役割（IT マネージャーなど）が、別のアカウントの同じ役割とは異なる動作をしているか

これらをすべて実現するには、アカウントレベルの情報を[ルックアップ](/help/getting-started/cja-glossary.md)データセットとして取り込みます。

最初にAdobe Experience Platformでルックアップスキーマを作成し、次に.csv ベースのアカウントレベルのデータを取り込んでルックアップテーブルデータセットを作成します。 次に、Customer Journey Analytics（CJA）で、作成したルックアップデータセットを含む、様々なデータセットを組み合わせた接続を作成します。その後、データビューを作成し、最終的にワークスペースでこれらのデータをすべて利用できるようになります。

>[!NOTE]
>
>ルックアップテーブルのサイズは最大 1GB です。

## 1. ルックアップスキーマの作成（Experience Platform）

[ルックアップ](/help/getting-started/cja-glossary.md)表で独自のスキーマを作成すると、使用するデータセットが、正しい設定（レコードタイプ）で CJA で使用できるようになります。ベストプラクティスは、「Lookup」と呼ばれる、すべての要素が空ですべてのルックアップテーブルに再使用できる[カスタムスキーマクラスを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#create-new-class)することです。

![](../assets/create-new-class.png)

## 2.ルックアップデータセットの作成 (Experience Platform)

スキーマを作成したら、そのスキーマから、Experience Platform でルックアップデータセットを作成する必要があります。このルックアップデータセットには、会社名、従業員の合計数、ドメイン名、所属する業種、年間売上高、Experience Platform の現在の顧客かどうか、顧客の営業段階、アカウント内のどのチームが CJA を使用しているかなどの、アカウントレベルのマーケティング情報が含まれます。

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

この例では、3 つのデータセットを 1 つの CJA 接続に結合します。

| データセット名 | 説明 | AEP スキーマクラス | データセットの詳細 |
| --- | --- | --- | --- |
| B2B インプレッション | アカウントレベルのクリックストリーム、イベントレベルのデータが含まれます。例えば、マーケティング広告を実行するための電子メール ID と対応するアカウント ID、およびマーケティング名が含まれます。また、各ユーザーに対するこれらの広告のインプレッションも含まれます。 | XDM ExperienceEvent スキーマクラスに基づく | `emailID` はプライマリ ID として使用され、 `Customer ID` 名前空間が割り当てられています。その結果、この変数は Customer Journey Analytics でデフォルトの&#x200B;**[!UICONTROL ユーザー ID]** として表示されます。![インプレッション](../assets/impressions-mixins.png) |
| B2B プロファイル | このプロファイルデータセットは、役職、所属先のアカウント、LinkedIn プロファイルなど、アカウント内のユーザーに関する詳細情報を提供します。 | XDM 個人版プロファイルスキーマクラスに基づく | このスキーマでは `emailID` をプライマリ ID として選択する必要はありません。必ず「**[!UICONTROL プロファイル]**」を有効にしてください。そうしないと、CJA は B2B プロファイルで `emailID` を `emailID` に接続できなくなります。![プロファイル](../assets/profile-mixins.png) |
| B2B 情報 | 上記の「ルックアップデータセットの作成」を参照してください。 | B2BAccount（カスタムルックアップスキーマクラス） | `accountID` と B2B インプレッションデータセット間の関係 は、次の手順に従って、B2B 情報データセットを CJA の B2B インプレッションデータセットと結び付けることで自動的に作成されています。![ルックアップ](../assets/lookup-mixins.png) |

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
