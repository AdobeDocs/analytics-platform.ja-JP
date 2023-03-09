---
title: 削除の影響
description: Customer Journey Analytics または Adobe Experience Platform において、接続、データセット、バッチを削除した場合の影響。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f56d56d65491ab14c5d0e6d3005c0e5e13127c9b
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 92%

---

# 削除の影響

Customer Journey Analytics または Adobe Experience Platform で接続、データセット、バッチを削除する際は、事前に次の点に注意してください。

| 新しい調査を作成... | 結果 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] の接続を削除する場合 | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除した接続用に作成されたデータビューは、機能しなくなります。</li><li> 同様に、削除した接続のデータビューに依存するワークスペースプロジェクトは動作しなくなります。</li></ul> |
| [!UICONTROL Adobe Experience Platform]（AEP）のデータセットを削除した場合 | AEP でデータセットを削除すると、そのデータセットからそのデータセットを含むすべての接続へのデータフローが停止します。データセットのデータは、関連付けられた CJA 接続からは自動的に削除されません。 |
| [!UICONTROL Customer Journey Analytics] のデータセットを削除する場合 | CJA の接続からデータセットを削除すると、そのデータセットに依存するデータビューとプロジェクトは機能しなくなります。 |
| （[!UICONTROL Adobe Experience Platform] の）データセットからバッチを削除する場合 | バッチが [!UICONTROL Adobe Experience Platform] のデータセットから削除されると、そのバッチを含む [!UICONTROL Customer Journey Analytics] の接続から同じバッチが削除されます。[!UICONTROL Customer Journey Analytics] には、[!UICONTROL Adobe Experience Platform] で削除されたバッチについて通知されます。 |
| [!UICONTROL Customer Journey Analytics] への&#x200B;**取り込み中**&#x200B;にバッチを削除する場合 | データセットにバッチが 1 つしかない場合、そのバッチからのデータも部分的なデータも [!UICONTROL Customer Journey Analytics] には表示されません。取り込みがロールバックされます。例えば、データセットに 5 つのバッチがあり、そのうち 3 つがデータセットの削除時に既に取り込まれている場合、これら 3 つのバッチのデータは [!UICONTROL Customer Journey Analytics] に表示されます。 |
| [!UICONTROL Adobe Experience Platform] のルックアップデータセットを削除した場合 | データセットの削除は、他のソースコネクタでは可能ですが、[Analytics 分類データコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=ja)では現在サポートされていません。データセットを誤って削除した場合は、アドビカスタマーサポートにお問い合わせください。 |
