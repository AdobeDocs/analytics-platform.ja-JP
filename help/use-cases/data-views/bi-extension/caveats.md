---
title: 注意事項
description: Customer Journey Analyticsの様々なBI ツールでのBI拡張機能の注意事項
solution: Customer Journey Analytics
feature: Data Views
role: User
exl-id: b6e8ebd9-4fda-41d1-ac37-ca869f5ee57c
autotag-review: '2026-05-19T08:03:31.717Z'
TQID: 'https://experienceleague.adobe.com/Af1iqNrfI24QsDCofUyHmiGCluNz7lW0mhkH5ObNUZI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: f24857a4-4b64-4b25-b237-d43026362144
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 743
ht-degree: 0%

---

# 注意事項


サポートされている各BI ツールには、Customer Journey Analytics BI拡張機能の操作に関するいくつかの注意事項があります。

+++ BI ツール

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

* Power BI デスクトップの高度な日付範囲フィルタリングは排他的です。  終了日には、レポートを作成する日付の過ぎた日を1つ選択する必要があります。 例えば、**[!UICONTROL は]** `1/1/2023` **[!UICONTROL 以降]** `1/2/2023`までです。
* Power BI デスクトップは、接続を作成する際に、デフォルトで&#x200B;**[!UICONTROL インポート]**&#x200B;になります。 **[!UICONTROL 直接問い合わせ]**&#x200B;を使用してください。
* Power BI Desktopは、Power Queryを通じてデータ変換を公開します。  Power Queryは主にタイプの読み込み接続で動作するので、日付や文字列関数のように適用する多くの変換では、タイプの読み込み接続に切り替える必要があるというエラーが発生します。  クエリ時にデータを変換する必要がある場合は、派生ディメンションと指標を使用する必要があります。これにより、Power BIで変換を実行する必要がなくなります。
* Power BI Desktopは日時タイプ列の処理方法を理解していないため、**[!UICONTROL daterangehour]**&#x200B;や&#x200B;**[!UICONTROL daterangeminute]**&#x200B;などの&#x200B;**[!UICONTROL daterange *X *]**のディメンションはサポートされていません。
* Power BI デスクトップは、デフォルトで、より多くのクエリサービスセッションを使用して複数の接続を作成しようとします。  プロジェクトのPower BI設定に移動し、並行クエリを無効にします。
* Power BI Desktopは、クライアントサイドの並べ替えと制限をすべて行います。 Power BI Desktopには、関連付けられた値を含む上位&#x200B;*X* フィルタリングに対する異なるセマンティクスもあります。 そのため、Analysis Workspaceと同じ並べ替えや制限を行うことはできません。
* 以前のバージョンのPower BI Desktop 2024年10月リリースのPostgreSQL データソースは無効です。 この記事に記載されているバージョンを使用していることを確認してください。

>[!TAB Tableau Desktop]

* Tableau Desktopの日付範囲フィルタリングは排他的です。 終了日には、レポートを作成する日付の過ぎた日を1つ選択する必要があります。
* デフォルトでは、**[!UICONTROL Daterangemonth]**&#x200B;のような日付または日時ディメンションをシートの行に追加すると、Tableau Desktopは&#x200B;**[!UICONTROL YEAR （）]**&#x200B;関数でフィールドをラップします。  目的のものを取得するには、そのディメンションを選択し、ドロップダウンメニューから使用する日付関数を選択する必要があります。  例えば、**[!UICONTROL Daterangemonth]**&#x200B;を使用する場合は、**[!UICONTROL 年]**&#x200B;を&#x200B;**[!UICONTROL 月]**&#x200B;に変更します。
* 検索結果を上位&#x200B;*X*&#x200B;に制限することは、Tableau デスクトップでは明らかではありません。 結果を明示的に制限するか、計算フィールドと&#x200B;**[!UICONTROL INDEX （）]**&#x200B;関数を使用して制限できます。  ディメンションに上位&#x200B;*X* フィルターを追加すると、サポートされていない内部結合を使用して複雑なSQLが生成されます。

>[!TAB Looker]

* Lookerには、ノードごとの最大接続数が5 ～ 100の範囲で設定されている必要があります。  この値を1に設定することはできません。  この設定は、Looker接続が常に、使用可能なクエリサービスセッションのうち5つ以上を使用することを意味します。
* Lookerでは、Customer Journey Analytics データビューに基づいたビューを使用してプロジェクトを作成できます。 次に、LookerMLを使用して、データビューで使用できるディメンションと指標に基づいてモデルを作成します。  このプロジェクト ビューは、ソースに一致するように自動的に更新されません。  CJA データビューのディメンション、指標、計算指標、またはセグメントに変更や追加を加えた場合、これらの変更はLookerに自動的に表示されません。  プロジェクトビューを手動で更新するか、新しいプロジェクトを作成する必要があります。
* 日付または日時フィールド（**[!UICONTROL Daterange Date]**&#x200B;または&#x200B;**[!UICONTROL Daterangeday Date]**&#x200B;など）でのLookerのユーザーエクスペリエンスは混乱します。
* Lookerの日付範囲は、包括的ではなく排他的です。  **[!UICONTROL の前]**&#x200B;はグレーで表示されているため、その側面を見逃すことがあります。  終了日には、レポートを作成する日付を1つ選択する必要があります。
* Lookerは、指標を自動的に指標として扱うわけではありません。  指標を選択すると、デフォルトでは、Lookerは指標をクエリ内のディメンションとして扱おうとします。  指標を指標として扱うには、上記のようにカスタムフィールドを作成する必要があります。 ショートカットとして、**[!UICONTROL ⋮]**&#x200B;を選択し、**[!UICONTROL 集計]**&#x200B;を選択してから、**[!UICONTROL 合計]**&#x200B;を選択できます。

>[!TAB Jupyter Notebook]

* Jupyter Notebookの主な注意点は、このツールが他のBI ツールのようにドラッグ&amp;ドロップ操作のユーザーインターフェイスではないことです。 優れたビジュアルを作成することはできますが、それを実現するにはコードを記述する必要があります。

>[!TAB RStudio]

* R dplyrはフラットスキーマで動作するので、**[!UICONTROL FLATTEN]** オプションが必要です。
* RStudioの主な注意点は、このツールが他のBI ツールのようにドラッグ&amp;ドロップ操作のユーザーインターフェイスではないことです。 優れたビジュアルを作成することはできますが、それを実現するにはコードを記述する必要があります。

>[!ENDTABS]

+++
