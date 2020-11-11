---
title: 接続の管理
description: Platform データセットへの接続を管理する方法について説明します。
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 22%

---


# 接続の管理

1つ以上の接続を作成したら、[!UICONTROL 接続]マネージャでそれらを管理できます。 次のことが可能です。

* 接続を削除する。
* 接続名を変更する。
* 接続からデータビューを作成する。
* データストリーミングを開始および停止する。

![接続マネージャ](assets/connections-manager.png)

1. 「**[!UICONTROL 接続]**」タブをクリックします。

2. 編集または管理する接続を選択します。

3. 次のいずれかのアクションを実行します。

   | アクション | 説明 |
   |---|---|
   | [!UICONTROL 削除] | [!DNL Adobe Experience Platform] 内にまだデータが残っているので、接続を削除してもデータセットは削除されません。以下の「接続の削除」を参照してください。 |
   | [!UICONTROL 名前変更] | 接続の名前は、わかりやすい名前に変更できます。 |
   | [!UICONTROL 「Create Data」表示] | このリンクをクリックすると、[データビュービルダー](/help/data-views/create-dataview.md)に移動します。 |
   | [!UICONTROL データストリーミングの開始または停止] | &quot;ストリーミング&quot;とは、接続内の任意のデータセットに新しいバッチが追加された場合に、その新しいデータが[!UICONTROL Customer Journey Analytics]に取り込まれ、レポートされることを意味します。 |

## 接続の削除

| もし私が… | これが起こる |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]の接続を削除しますか？ | 次のことを示すエラーメッセージが表示されます。<ul><li>削除した接続に対して作成されたデータ表示は、機能しなくなります。</li><li> 同様に、削除した接続のデータ表示に依存するWorkspaceプロジェクトは動作しなくなります。</li></ul> |
| [!UICONTROL Adobe Experience Platform]のデータセットを削除しますか？ | AEPでデータセットを削除すると、そのデータセットからそのデータセットを含むすべての接続へのデータフローが停止します。 データセットのデータは、関連付けられたCJA接続から自動的に削除されません。 |
| [!UICONTROL Customer Journey Analytics]内のデータセットを削除しますか？ | 現在、保存された接続内のデータセットを削除することはできません。 接続全体を削除して開始を終了する必要があります。 (ただし、[!UICONTROL Adobe Experience Platform]のデータセットは削除できます)。 |
| データセット([!UICONTROL Adobe Experience Platform]内)からバッチを削除しますか？ | バッチが[!UICONTROL Adobe Experience Platform]データセットから削除されると、そのバッチを含む[!UICONTROL Customer Journey Analytics]接続から同じバッチが削除されます。 [!UICONTROL 顧客の遍歴] 分析は、 [!UICONTROL Adobe Experience Platformで削除されたバッチを通知しました]。 |
| バッチ&#x200B;**を削除して、**&#x200B;を[!UICONTROL Customer Journey Analytics]に取り込みますか？ | データセットにバッチが1つしかない場合、そのバッチからのデータも部分的なデータも[!UICONTROL Customer Journey Analytics]には表示されません。 取り込みがロールバックされます。 例えば、データセットに5つのバッチがあり、そのうち3つがデータセットの削除時に既に取り込まれている場合、これら3つのバッチのデータは[!UICONTROL Customer Journey Analytics]に表示されます。 |
