---
title: 接続の管理
description: Platform データセットへの接続を管理する方法について説明します。
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---


# 接続の管理

1 つ以上の接続を作成したら、[!UICONTROL 接続]マネージャでそれらを管理できます。次のことが可能です。

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
   | [!UICONTROL データビューの作成] | このリンクをクリックすると、[データビュービルダー](/help/data-views/create-dataview.md)に移動します。 |
   | [!UICONTROL データストリーミングの開始または停止] | 「ストリーミング」とは、接続内のデータセットに新しいバッチが追加されると、その新しいデータがレポート用に [!UICONTROL Customer Journey Analytics] へと取り込まれることを意味します。 |

## 接続の削除

| 操作 | 結果 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] の接続を削除した場合 | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除した接続用に作成されたデータビューは、機能しなくなります。</li><li> 同様に、削除した接続のデータビューに依存する Workspace プロジェクトは動作しなくなります。</li></ul> |
| [!UICONTROL Adobe Experience Platform] のデータセットを削除した場合 | AEP でデータセットを削除すると、そのデータセットからそのデータセットを含むすべての接続へのデータフローが停止します。データセットのデータは、関連付けられた CJA 接続からは自動的に削除されません。 |
| [!UICONTROL Customer Journey Analytics] のデータセットを削除した場合 | 現在、保存された接続内のデータセットを削除することはできません。接続全体を削除して、操作をやり直す必要があります。（ただし、[!UICONTROL Adobe Experience Platform] のデータセットは削除できます） |
| [!UICONTROL Adobe Experience Platform] のデータセットからバッチを削除した場合 | バッチが [!UICONTROL Adobe Experience Platform] のデータセットから削除されると、そのバッチを含む [!UICONTROL Customer Journey Analytics] の接続から同じバッチが削除されます。[!UICONTROL Customer Journey Analytics] には、[!UICONTROL Adobe Experience Platform] で削除されたバッチについて通知されます。 |
| [!UICONTROL Customer Journey Analytics] への&#x200B;**取り込み中**&#x200B;にバッチを削除した場合 | データセットにバッチが 1 つしかない場合、そのバッチからのデータも部分的なデータも [!UICONTROL Customer Journey Analytics] には表示されません。取り込みがロールバックされます。例えば、データセットに 5 つのバッチがあり、そのうち 3 つがデータセットの削除時に既に取り込まれている場合、これら 3 つのバッチのデータは [!UICONTROL Customer Journey Analytics] に表示されます。 |
