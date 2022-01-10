---
title: CJA 接続のサイズの見積り方法
description: Customer Journey Analytics の現在の使用状況を報告する
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: ht
source-wordcount: '615'
ht-degree: 100%

---

# 接続サイズの予測

現在 [!UICONTROL Customer Journey Analytics] にあるデータの行数を知る必要がある場合があります。このトピックでは、[!UICONTROL Customer Journey Analytics] の現在の使用状況の報告方法について説明しています。

1. [!UICONTROL Customer Journey Analytics] で、「**[!UICONTROL 接続]**」タブをクリックします。
1. [!UICONTROL 接続を編集]画面で、使用状況および接続の規模を確認する接続を選択します。

   ![接続を編集](assets/edit-connection.png)

1. 左側のパネルから、接続に含まれるデータセットを選択します。この場合は、「B2B Impression」データセットです。

   ![データセット](assets/dataset.png)

1. 名前の横にある青い（i）アイコン（情報）をクリックします。データセットの行数/イベントが 3.8 k であることがわかります。また、正確な行数を知るには、プレビューテーブルの下の「**[!UICONTROL Experience Platform で編集]**」をクリックします。これにより、[!UICONTROL Adobe Experience Platform] のデータセットにリダイレクトされます。

   ![AEP データセット情報](assets/data-size.png)

1. このデータセットの&#x200B;**[!UICONTROL 合計レコード数]**&#x200B;は 3.83 k レコードで、データのサイズは 388.59 KB です。

1. 接続の他のデータセットに対して手順 1～5 を繰り返し、レコード数/行数を合計します。最終的な集計数が接続の使用状況の指標になります。これは、[!UICONTROL Adobe Experience Platform] から取り込まれる接続のデータセットの行数です。

## 取り込まれる行数の確認

[!UICONTROL Customer Journey Analytics] で実際に取り込まれるイベントの数は、接続設定によって異なります。また、誤ったユーザー ID を選択した場合や、データセット内の一部の行でこの ID を使用できない場合、[!UICONTROL Customer Journey Analytics] ではそれらの行が無視されます。取り込まれるイベントの実際の行を確認するには、次の手順を実行します。

1. 接続を保存したら、フィルターを使用せずに、同じ接続のデータビューを作成します。
1. ワークスペースプロジェクトを作成し、正しいデータビューを選択します。フリーフォームテーブルを作成し、**[!UICONTROL 年]**&#x200B;ディメンションを持つ&#x200B;**[!UICONTROL イベント]**&#x200B;指標をドラッグ＆ドロップします。日付選択カレンダーから十分な日付範囲を選択し、接続のすべてのデータをカプセル化します。これで、[!UICONTROL Customer Journey Analytics] に取り込まれるイベントの数を確認できます。

   ![ワークスペースプロジェクト](assets/event-number.png)

   >[!NOTE]
   >
   >これで、イベントデータセットから取り込まれるイベントの数を確認できます。プロファイルおよび参照タイプのデータセットは含まれません。この接続の合計行数を取得するには、プロファイルおよび参照のデータセットで「接続サイズの予測」の手順 1～3 を実行し、数値を合計します。

## 不一致の診断

場合によっては、接続によって取り込まれるイベントの合計数が [!UICONTROL Adobe Experience Platform] のデータセットの行数と異なることがあります。この例の場合、データセット「B2B Impression」には 7650 の行がありますが、[!UICONTROL Adobe Experience Platform] のデータセットの行数は 3830 です。不一致が発生する理由はいくつかあり、次の手順を実行して診断できます。

1. このディメンションを **[!UICONTROL プラットフォームデータセット ID]** で分類すると、サイズは同じでも、**[!UICONTROL プラットフォームデータセット ID]** が異なる 2 つのデータセットがあることがわかります。各データセットには 3825 件のレコードがあります。つまり、[!UICONTROL Customer Journey Analytics] では、ユーザー ID またはタイムスタンプが欠落していることにより、5 件のレコードが無視されています。

   ![分類](assets/data-size2.png)

1. また、[!UICONTROL Adobe Experience Platform] にチェックインすると、ID「5f21c12b732044194bffc1d0」のデータセットがありません。つまり、他のユーザーが最初の接続の作成時に [!UICONTROL Adobe Experience Platform] からこのデータセットを削除しています。その後、そのデータセットは [!UICONTROL Customer Journey Analytics] に再び追加されましたが、[!UICONTROL Adobe Experience Platform] によって、異なる[!UICONTROL プラットフォームデータセット ID] が生成されました。

[!UICONTROL Customer Journey Analytics] と [!UICONTROL Adobe Experience Platform] におけるデータセットと接続の削除の影響については、[こちら](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components)を参照してください。
