---
title: 接続の作成
description: Customer Jeurney Analyticsでプラットフォームデータセットへの接続を作成する方法について説明します。
translation-type: tm+mt
source-git-commit: 674835d9c8b79850051729c875bc67f0e4052a66
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# 接続の作成

接続を使用すると、のデータセットを [!DNL Adobe Experience Platform] Workspace [!UICONTROL に統合できます]。 データセットに関するレポートを作成するに [!DNL Experience Platform] は、まず、と [!DNL Experience Platform] Workspaceのデータセット間の接続を確立する必要があり [!UICONTROL ます]。

ビデオの概要については [](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) 、ここをクリックしてください。

>[!IMPORTANT] 複数のデータセットを組み合わせて1つの接続 [!DNL Experience Platform] にすることができます。

1. https://analytics.adobe.comに移動し [ます](https://analytics.adobe.com)。

1. Click the **[!UICONTROL Connections]** tab.

1. 右上の **[!UICONTROL 「新しい接続を作成]** 」をクリックします。

   ![接続を作成](assets/create-connection.png)

1. 最初に、接続を作成するデータセットが含まれるExperience Platformのサンドボックスを選択します。 Adobe Experience Platform provides [sandboxes](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. サンドボックスは、データセットを含む「データサイロ」と考えることができます。 サンドボックスは、データセットへのアクセスを制御するために使用します。 サンドボックス全体のデータにアクセスすることはできません。

1. サンドボックスを選択すると、左側のレールに、取り出し元となるサンドボックス内のすべてのデータセットが表示されます。 Customer Jeurney Analyticsに取り込む1つ以上のデータセットを選択し、 [!UICONTROL 追加をクリックし]****&#x200B;ます。 (選択できるデータセットが多数ある場合は、データセットのリストの上にある検索バーを使用して、適切なデータセットを検索できます)。

1. 次に、この接続に追加した各データセットに対して、 [!UICONTROL Customer Jeurney Analytics] （カスタマージャーニー）が、入力されるデータに基づいてデータセットタイプを自動的に設定します。 データセットには次の3種類があります。 [!UICONTROL イベント] ・データ、 [!UICONTROL プロファイル] ・データ、 [!UICONTROL Lookup] データ。

   | データセットタイプ | 説明 | タイムスタンプ | スキーマ | ユーザー ID |
   |---|---|---|---|---|
   | [!UICONTROL イベント] | イベントを表すデータ(Web訪問、インタラクション、トランザクション、POSデータ、調査データ、広告インプレッションデータなど)。 例えば、これは、顧客IDまたはcookie IDを持つ一般的なクリックストリームデータと、タイムスタンプの場合があります。 イベントデータを使用すると、どのIDをPerson IDとして使用するかに柔軟性があります。 | は、 [UICONTROL Experience Platformのイベントベースのスキーマからデフォルトのタイムスタンプフィールドに自動的に設定されます]。 | 「Time Series」動作を持つXDMクラスに基づく組み込みスキーマまたはカスタムイベント。 「XDMエクスペリエンスのイベント」や「XDM Decisionイベント」などがあります。 | 含める個人IDを選択できます。 Experience Platformで定義された各データセットスキーマは、ID名前空間に関連付けられ、定義済みの1つ以上のIDのセットを持つことができます。 任意のIDを個人IDとして使用できます。 Cookie ID、関連付けID、ユーザーID、トラッキングコードなどがあります。 |
   | [!UICONTROL 参照] | 分類ファイルに似ています。 このデータは、イベントまたはプロファイルデータにある値やキーを検索するために使用されます。 例えば、イベントデータ内の数値IDを製品名にマップする参照データをアップロードできます。 | 該当なし | 「XDM個別プロファイル」クラスを除き、「Record」動作を持つXDMクラスに基づく、組み込みまたはカスタムスキーマです。 | 該当なし |
   | [!UICONTROL プロファイル] | 顧客属性 [!UICONTROL に類似] — 非変更属性および非一時属性。 訪問者、ユーザーまたは [!UICONTROL イベントデータの顧客に適用されるデータ] 。 例えば、顧客に関するCRMデータをアップロードできます。 | 該当なし | 「XDM個別プロファイル」クラスに基づく組み込みスキーマまたはカスタムイベント。 | 含める個人IDを選択できます。 内で定義された各データセット [!DNL Experience Platform] には、Cookie ID、Stitched ID、User ID、Tracking Codeなど、1つ以上の個人IDが定義されています。<br>![Person](assets/person-id.png)**IDNote **: 異なるIDを持つデータセットを含む接続を作成すると、レポートにはそれが反映されます。 データセットを実際に結合するには、同じPerson IDを使用する必要があります。 |

1. 「 **[!UICONTROL 次へ]** 」をクリックすると [!UICONTROL 、「接続を] 作成」ダイアログが表示されます。

   ![接続を作成](assets/create-connection2.png)

1. [ [!UICONTROL 接続を作成] ]ダイアログで、次の設定を定義します。

   | フィールド | 説明 |
   |---|---|
   | [!UICONTROL 名前の接続] | 接続にわかりやすい名前を付けます。 名前を指定しないと接続を保存できません。 |
   | [!UICONTROL 説明] | この追加接続を他の接続と区別するための詳細。 |
   | [!UICONTROL データセット] | この接続に含まれるデータセット。 |
   | [!UICONTROL この接続内のすべての新しいデータセットを、今日から自動的にインポートします。] | 継続的な接続を確立し、この接続のデータセットに追加される新しいデータバッチが自動的に [!UICONTROL Workspace]に流れるようにするには、このオプションを選択します。 |
   | [!UICONTROL 既存のデータをすべて読み込む] | このオプションを選択して接続を保存すると、この接続にあるすべてのデータセットの既存（履歴）データ [!DNL Experience Platform] がすべてインポートされます。 今後、この保存された接続に追加された新しいデータセットの既存の履歴データもすべて自動的にインポートされるようになります。 <br>**この接続が保存されると、この設定は変更できなくなります。** |

   **次の点に注意してください。**

   * 接続内のすべてのデータセットの履歴データの累積サイズが15億行を超える場合、エラーメッセージに、この量の履歴データをインポートできないことが示されます。 ただし、10億行の履歴データを含むデータセットを追加し、そのデータをインポートした後、1週間後に同じサイズのデータセットを追加して履歴データをインポートした場合は、これが有効です。
   * 接続中のデータセットに追加される新しいデータに優先順位を付けるので、このデータの待ち時間は最も短くなります。
   * バックフィル（履歴）データは、読み込み速度が遅くなります。

1. 「**[!UICONTROL 保存]**」をクリックします。

ワークフローの次の手順は、データ表示を [作成することです](/help/data-views/create-dataview.md)。
