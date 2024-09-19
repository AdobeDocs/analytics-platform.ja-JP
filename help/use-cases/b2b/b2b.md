---
title: アカウントデータをルックアップデータセットとして追加
description: アカウントデータをルックアップデータセットとしてCustomer Journey Analyticsに追加する方法を説明します
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 36%

---

# アカウントデータをルックアップデータセットとして追加

B2B のこのユースケースは、アカウントデータをユーザーレベルおよびイベントレベルの分析に追加する方法を示しています。 アカウントデータを追加すると、次のような質問に答えることができます。

* このアカウントと一致する会社名
* このアカウントがどのような役割を示すか
* 1 つのアカウントの特定の役割（IT マネージャーなど）が、別のアカウントの同じ役割とは異なる動作をしているか

アカウントデータ情報を追加するには、この情報を含む [lookup](/help/technotes/glossary.md) データセットを追加して使用します。

使用される手順は次のとおりです。

1. [ ルックアップスキーマを作成 ](#create-lookup-schema)Experience Platformで行います。
1. CSV ベースのアカウントデータを取り込めるExperience Platformで [ ルックアップデータセットを作成 ](#create-lookup-dataset) します。
1. Customer Journey Analyticsでの [ 接続内のデータセットの組み合わせ ](#combine-datasets-in-a-connection) には、作成したルックアップデータセットを含めます。
1. Customer Journey Analyticsで [ データビューを作成 ](#create-a-data-view-from-this-connection) します。
1. Customer Journey AnalyticsのWorkspaceで [ このデータを分析 ](#analyze-the-data-in-workspace) します。

>[!NOTE]
>
>ルックアップテーブルのサイズは最大 1GB です。
>

## ルックアップスキーマの作成

[ ルックアップ ](/help/technotes/glossary.md) テーブル用に独自のスキーマを作成すると、使用するデータセットに正しい設定（レコードタイプ）がCustomer Journey Analyticsされます。 ベストプラクティスは、すべてのルックアップテーブルで再利用できる [ カスタムスキーマクラスを作成 ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) することです。

![ 新しいクラスを作成ダイアログ ](../assets/create-new-class.png)

## ルックアップデータセットの作成

スキーマを作成したら、そのスキーマに基づいて、Experience Platformでルックアップデータセットを作成する必要があります。 このルックアップデータセットには、アカウント情報が含まれています。 例えば、会社名、従業員の総数、ドメイン名、会社が属する業界、年間収益などがあります。 イベントデータで使用される人物識別子と一致させる可能性のある人物識別子をデータに含めてください。

1. Experience Platformで、**[!UICONTROL データ管理/データセット]** に移動します。
1. 「**[!UICONTROL + データセットを作成]**」をクリックします。
1. 「**[!UICONTROL スキーマからのデータセットの作成]**」をクリックします。
1. 作成したルックアップスキーマクラスを選択します。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. データセットに名前を付け（例：`B2B Info`）、説明を入力します。
1. 「**[!UICONTROL 完了]**」をクリックします。

## データの取得

CSV ファイルを使用している場合は、[CSV ファイルを XDM スキーマにマップ](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)する方法に関する説明が役立ちます。

[その他の方法](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)も利用できます。

データのオンボーディングとルックアップの確立には、ルックアップテーブルのサイズに応じて、約 2 ～ 4 時間かかります。

## 接続内のデータセットの結合

この例では、3 つのデータセットを 1 つのCustomer Journey Analytics接続に組み合わせます。

| データセット名 | 説明 | Adobe Experience Platform スキーマクラス | データセットの詳細 |
| --- | --- | --- | --- |
| B2B インプレッション | アカウントレベルのクリックストリーム、イベントレベルのデータが含まれます。例えば、マーケティング広告を実行するための電子メール ID と対応するアカウント ID、およびマーケティング名が含まれます。また、ユーザーごとの広告のインプレッション数も含まれます。 | XDM ExperienceEvent スキーマクラスに基づく | `emailID` はプライマリ ID として使用され、 `Customer ID` 名前空間が割り当てられています。その結果、この変数はCustomer Journey Analyticsではデフォルトの **[!UICONTROL ユーザー ID]** として表示されます。 ![インプレッション](../assets/impressions-mixins.png) |
| B2B プロファイル | このプロファイルデータセットは、役職、所属先のアカウント、LinkedIn プロファイルなど、アカウント内のユーザーに関する詳細情報を提供します。 | XDM 個人版プロファイルスキーマクラスに基づく | このスキーマのプライマリ ID として `emailID` を選択します。 |
| B2B 情報 | 上記の「ルックアップデータセットの作成」を参照してください。 | B2B アカウント（カスタムルックアップスキーマクラス） | `accountID` と B2B インプレッションデータセット間の関係は、以下の手順で説明されているように、B2B 情報データセットをCustomer Journey Analyticsの B2B インプレッションデータセットに接続すると自動的に作成されます。 ![ルックアップ](../assets/lookup-mixins.png) |

データセットを組み合わせる方法を次に示します。

1. Customer Journey Analytics で、「 **[!UICONTROL 接続]**」タブをクリックします。
1. 結合するデータセットを選択します。
1. B2B 情報データセットには、ルックアップテーブルで使用するキー（例：`personKey.sourceKey`）を選択します。 次に、一致するキー（対応するディメンション）と、イベントデータセット内（例：p`ersonKey.sourceKey`）を選択します。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. [これらの手順](/help/connections/create-connection.md)に従って、接続に名前を付けて説明し、設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## この接続からデータビューを作成

[ データビューの作成 ](/help/data-views/create-dataview.md) の手順に従います。

* 必要なすべてのコンポーネント（ディメンションと指標）をデータセットから追加します。 オーバーカウントに重複排除を必要とする指標の場合は、それに応じてこれらの指標を設定します（[ 指標の重複排除コンポーネントの設定 ](/help/data-views/component-settings/metric-deduplication.md) を参照）。 このような指標の例としては、従業員数や売上高があります。

## Workspace でのデータの分析

3 つのすべてのデータセットのデータに基づいて Workspace プロジェクトを作成できるようになりました。

例えば、「はじめに」に記載されている問題への回答を検索できます。

* 電子メール ID を accountID で分類し、電子メール ID が属する会社を特定します。
* 特定のアカウント ID にマッピングされる従業員の数は？
* アカウント ID はどの業種に属していますか。

>[!MORELIKETHIS]
>
>詳しくは、[B2B プロジェクトの例 ](example.md) を参照してください。

