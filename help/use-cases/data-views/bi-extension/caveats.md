---
title: 注意事項
description: Customer Journey Analyticsの様々な BI ツールでの BI 拡張機能の注意事項
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# 注意事項


サポートされている各 BI ツールには、Customer Journey Analytics BI 拡張機能の操作に関する注意事項があります。

+++ BI ツール

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

* Power BI Desktop の高度な日付範囲フィルタリングは排他的です。  終了日には、レポートする日付の後の日付を選択する必要があります。 例えば、「**[!UICONTROL が次の日付以降である]**`1/1/2023`**[!UICONTROL および次の日付以前である]**`1/2/2023` などです。
* Power BI Desktop では、接続作成時にデフォルトで **[!UICONTROL 読み込み]** が設定されます。 必ず **[!UICONTROL 直接クエリ]** を使用してください。
* Power BI Desktop は、Power Query を使用してデータ変換を公開します。  Power Query は主にインポート型接続で動作するので、日付や文字列関数などの多くの変換を適用すると、インポート型接続に切り替える必要があるというエラーがスローされます。  クエリ時にデータを変換する必要がある場合は、Power BIが変換自体を行う必要がないように、派生ディメンションと指標を使用する必要があります。
* Power BI Desktop は、日時型の列の処理方法を理解していません。そのため、**[!UICONTROL daterange *hour *]**&#x200B;や&#x200B;**[!UICONTROL daterangeminute &#x200B;]**&#x200B;などの&#x200B;**[!UICONTROL daterange &#x200B;]**&#x200B;X ディメンションはサポートされていません。
* Power BI デスクトップは、デフォルトで、より多くのクエリサービスセッションを使用して複数の接続を確立しようとします。  プロジェクトのPower BI設定に移動し、並列クエリを無効にします。
* Power BI デスクトップは、クライアントサイドのすべての並べ替えと制限を行います。 Power BI Desktop には、結び付けられた値を含む上位 *X* フィルタリング用の異なるセマンティクスもあります。 そのため、Analysis Workspaceで行うのと同じ並べ替えと制限を作成することはできません。
* 2024 年 10 月リリースの以前のバージョンのPower BI デスクトップでは、PostgreSQL データソースが破損しています。 この記事で説明されているバージョンを使用してください。

>[!TAB Tableau Desktop]

* Tableau Desktop の日付範囲フィルタリングは排他的です。 終了日には、レポートする日付の後の日付を選択する必要があります。
* 既定では、シートの行に **[!UICONTROL Daterangemonth]** のような日付または日時次元を追加すると、Tableau Desktop はフィールドを **[!UICONTROL YEAR （）]** 関数でラップします。  目的のデータを取得するには、そのディメンションを選択し、ドロップダウンメニューから、使用する日付関数を選択する必要があります。  例えば、**[!UICONTROL Daterangemonth]** を使用しようとする場合は、**[!UICONTROL 年]** を **[!UICONTROL 月]** に変更します。
* Tableau Desktop では、結果を上位 *X* に制限することは明確ではありません。 結果を明示的に制限するか、計算フィールドと **[!UICONTROL INDEX （）]** 関数を使用することができます。  上位 *X* フィルターをディメンションに追加すると、サポートされていない内部結合を使用して複雑な SQL が生成されます。

>[!TAB Looker]

* Looker には、ノード設定ごとの最大接続数があり、5～100 にする必要があります。  この値を 1 に設定することはできません。  この設定は、Looker 接続が、常に使用可能なクエリサービスセッションを 5 つ以上使用することを意味します。
* Looker は、Customer Journey Analytics データビューに基づくビューを持つプロジェクトを作成できます。 次に、Looker は、LookerML を使用して、データビューで使用できるディメンションと指標に基づいてモデルを作成します。  このプロジェクト ビューは、ソースと一致するように自動的に更新されません。  CJA データビューのディメンション、指標、計算指標またはセグメントに変更や追加を加えても、その変更内容は Looker に自動的には表示されません。  プロジェクトビューを手動で更新するか、新しいプロジェクトを作成する必要があります。
* **[!UICONTROL Daterange Date]** や **[!UICONTROL Daterangeday Date]** などの日付または日時フィールドにおける Looker のユーザーエクスペリエンスは、混乱を招きます。
* Looker の日付範囲は、包括的ではなく排他的です。  （前の **[!UICONTROL まで]** はグレーで表示されるので、その側面を見逃すことがあります。  終了日には、レポートする日付の後の日付を選択する必要があります。
* Looker では、指標を指標として自動的に処理しません。  指標を選択すると、デフォルトでは、Looker は指標をクエリ内のディメンションとして扱おうとします。  指標を指標として扱うには、上記のようにカスタムフィールドを作成する必要があります。 ショートカットとして、「**[!UICONTROL ⋮]**」を選択し、「**[!UICONTROL 集計]**」を選択してから「**[!UICONTROL 合計]**」を選択できます。

>[!TAB Jupyter Notebook]

* Jupyter Notebook の主な注意点は、他の BI ツールのように、ツールがドラッグ&amp;ドロップによるユーザーインターフェイスを持っていないことです。 優れたビジュアルを作成できますが、それにはコードを記述する必要があります。

>[!TAB RStudio]

* R dplyr はフラット スキーマで動作するため、**[!UICONTROL FLATTEN]** オプションが必要です。
* RStudio の主な注意点は、他の BI ツールのように、ツールがドラッグ&amp;ドロップのユーザーインターフェイスではないことです。 優れたビジュアルを作成できますが、それにはコードを記述する必要があります。

>[!ENDTABS]

+++
