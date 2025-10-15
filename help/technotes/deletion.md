---
title: 削除の影響
description: Customer Journey Analytics または Adobe Experience Platform において、接続、データセット、バッチを削除した場合の影響。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 928c79f9ccf30cc33e0f334f715bf3190a257019
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 64%

---

# 削除の影響

Customer Journey Analytics または Adobe Experience Platform で接続、データセット、バッチを削除する際は、事前に次の点に注意してください。

| 新しい調査を作成... | 結果 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] の接続を削除する場合 | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除した接続用に作成されたデータビューは、機能しなくなります。</li><li> 同様に、削除した接続のデータビューに依存するワークスペースプロジェクトは動作しなくなります。</li></ul>次の場合は、Customer Journey Analytics接続を削除できません。 <ul><li>権限のないAdobe Experience Platform サンドボックスに関連付けられています。 これらの接続に基づいて作成されたデータビューに対する権限を持っている場合でも、基になるAdobe Experience Platform サンドボックスに対する権限が付与されるまで、接続を削除することはできません。</li><li>関連付けられているデータビューに対して、次の互換性オプションを選択します。**[!UICONTROL Adobe Journey Optimizerでデフォルトデータビューとして設定]**<p>この設定オプションについて詳しくは、[&#x200B; データビューの作成または編集 &#x200B;](/help/data-views/create-dataview.md#compatibility) の [&#x200B; 互換性 &#x200B;](/help/data-views/create-dataview.md) を参照してください</p></li></ul> |
| [!UICONTROL Adobe Experience Platform] のデータセットを削除する | AEP でデータセットを削除すると、そのデータセットからそのデータセットを含むすべての接続へのデータフローが停止します。そのデータセットのデータは、関連付けられたCustomer Journey Analytics接続から自動的に削除されます。 |
| [!UICONTROL Customer Journey Analytics] のデータセットを削除する場合 | Customer Journey Analyticsの接続からデータセットを削除すると、そのデータセットに依存するデータビューやプロジェクトは機能しなくなります。 |
| （[!UICONTROL Adobe Experience Platform] の）データセットからバッチを削除する場合 | バッチが [!UICONTROL Adobe Experience Platform] のデータセットから削除されると、そのバッチを含む [!UICONTROL Customer Journey Analytics] の接続から同じバッチが削除されます。[!UICONTROL Customer Journey Analytics] には、[!UICONTROL Adobe Experience Platform] で削除されたバッチについて通知されます。 |
| [!UICONTROL Customer Journey Analytics] への&#x200B;**取り込み中**&#x200B;にバッチを削除する場合 | データセットにバッチが 1 つしかない場合、そのバッチからのデータも部分的なデータも [!UICONTROL Customer Journey Analytics] には表示されません。取り込みがロールバックされます。例えば、データセットに 5 つのバッチがあり、そのうち 3 つがデータセットの削除時に既に取り込まれている場合、これら 3 つのバッチのデータは [!UICONTROL Customer Journey Analytics] に表示されます。 |
| [!UICONTROL Adobe Experience Platform] の参照データセットを削除 | データセットの削除は、他のソースコネクタでは可能ですが、[Analytics 分類データコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=ja)では現在サポートされていません。データセットを誤って削除した場合は、アドビカスタマーサポートにお問い合わせください。 |
