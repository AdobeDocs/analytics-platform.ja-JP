---
title: 接続の作成
description: Customer Jeurney Analyticsでプラットフォームデータセットへの接続を作成する方法について説明します。
translation-type: tm+mt
source-git-commit: fa7898d73756c33a0bae22c8758bc9f0a649626a

---


# 接続の作成

接続を使用すると、からにデータセットを統合 [!DNL Adobe Experience Platform] できま [!UICONTROL Workspace]す。 プラットフォームデータセットに関するレポートを作成するには、まず、PlatformとWorkspaceのデータセット間の接続を確立する必要があります。

ビデオの [概要について](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) 、ここをクリックしてください。

>[!IMPORTANT] 複数のプラットフォームデータセットを組み合わせて1つの接続にすることができます。

1. https://analytics.adobe.comに移動し [ます](https://analytics.adobe.com)。

1. タブをクリッ **[!UICONTROL Connections]** クします。

1. 右上の **[!UICONTROL Create new connection]** をクリックします。

![接続を作成](assets/create-connection.png)

1. 左側のレールには、取り込み元となるプラットフォーム内のすべてのデータセットが表示されます。 取り込むデータセットを1つ以上選択し、をクリッ [!UICONTROL Customer Journey Analytics] クします **[!UICONTROL Add]**。 (選択するデータセットが多数ある場合は、データセットのリストの上にある検索バーを使用して、適切なデータセットを検索できます)。

1. 次に、この接続に追加した各データセットに対して、受信する [!UICONTROL Customer Journey Analytics] データに基づいてデータセットタイプが自動的に設定されます。 データセットには次の3種類があります。イベントデータ、プロファイルデータ、参照データ。

   | データセットタイプ | 説明 | タイムスタンプ | スキーマ | ユーザー ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | イベントを時間で表すデータ(例：Web訪問、インタラクション、トランザクション、POSデータ、調査データ、広告インプレッションデータなど)。 これは、顧客IDまたはcookie IDとタイムスタンプを持つ一般的なクリックストリームデータです。 イベントデータを使用すると、任意のIDを使用できます。 | タイムスタンプに設定されます。 | このデータセットタイプのスキーマの基となるプラットフォームデータです。 | 該当なし |
   | [!UICONTROL Lookup] | 分類ファイルに類似しています。 このデータは、イベントまたはデータ内の値やキーを参照するために使用されます。 例えば、製品データ内の数値IDを製品名にマップする参照イベントをアップロードできます。 | 該当なし | このデータセットタイプのスキーマの基となるプラットフォームデータです。 | 該当なし |
   | [!UICONTROL Profile] |  — 非変更 [!UICONTROL Customer Attributes] および非一時属性に類似しています。 データ内のユーザー、訪問者または顧客に適用されるデ [!UICONTROL Event] ータ。 例えば、顧客に関するCRMデータをアップロードできます。 | 該当なし | このデ [!UICONTROL Platform] ータセットタイプの基になるスキーマです。 | 含める個人IDを選択できます。 Adobe Experience Platformで定義された各データセットには、Cookie ID、Stitched ID、User ID、Tracking Codeなど、1つ以上の個人IDが独自に定義されています。<br>![Person](assets/person-id.png)**ID注&#x200B;**:異なるIDを持つデータセットを含む接続を作成すると、レポートに反映されます。 データセットを実際に結合するには、同じPerson IDを使用する必要があります。 |

1. をクリック **[!UICONTROL Next]** すると、ダイアログが表示 [!UICONTROL Create Connection] されます。

   ![接続を作成](assets/create-connection2.png)

1. ダイアログで [!UICONTROL Create Connection] 、次の設定を定義します。

   | フィールド | 説明 |
   |---|---|
   | [!UICONTROL Name Connection] | 接続にわかりやすい名前を付けます。 名前を付けずに接続を保存することはできません。 |
   | [!UICONTROL Description] | こ追加の接続を他の接続と区別するための詳細。 |
   | [!UICONTROL Datasets] | この接続に含まれるデータセット。 |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | 継続的な接続を確立し、この接続のデータセットに追加される新しいデータバッチが自動的ににに送られるようにする場合は、このオプションを選択しま [!UICONTROL Workspace]す。 |
   | [!UICONTROL Import all existing data] | このオプションを選択して接続を保存すると、この接続に含まれるすべてのデータセットに関する、プラットフォームの既存の（履歴）データがすべてインポートされます。 今後、この保存された接続に追加された新しいデータセットの既存の履歴データもすべて自動的に読み込まれます。 <br>**この接続が保存されると、この設定は変更できなくなります。** |

   **次の点に注意してください。**

   * 接続内のすべてのデータセットの履歴データの累積サイズが15億行を超える場合、この量の履歴データをインポートできないことを示すエラーメッセージが表示されます。 ただし、10億行の履歴データを含むデータセットを追加し、そのデータを読み込んでから1週間後に同じサイズの別のデータセットを追加し、履歴データを読み込むと、この処理は正常に行われます。
   * 接続中のデータセットに追加された新しいデータに優先順位を付けるので、このデータの待ち時間は最も短くなります。
   * バックフィル（履歴）データは、読み込み速度が遅くなります。

1. クリック **[!UICONTROL Save]**.

ワークフローの次の手順は、データ [表示](/help/data-views/create-dataview.md)。
