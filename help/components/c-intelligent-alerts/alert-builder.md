---
description: Analysis Workspaceでアラートを作成する方法を説明します。
title: アラートの作成
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 65%

---

# アラートの作成 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="時間の精度"
>abstract="時間の精度は、アラートのチェック頻度を指定します。"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>異常値検出を使用したアラート（_インテリジェントアラート_&#x200B;とも呼ばれる）の使用は、Customer Journey Analytics Prime または Ultimate パッケージを使用している組織でのみ使用できます。

Customer Journey Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。また、Customer Journey Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。

アラートについて詳しくは、[アラートの概要](/help/components/c-intelligent-alerts/intelligent-alerts.md)を参照してください。

アラートを作成するには：

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. Customer Journey Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択します。 [アラートマネージャー](alert-manager.md)で、![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]** を選択して新しいアラートを作成するか、リストされているアラートのいずれかを選択して既存のアラートを変更します。

1. Analysis Workspaceのフリーフォームテーブルで 1 つ以上の行項目を選択し、コンテキストメニューから **[!UICONTROL 選択からアラートを作成]** を選択します。 このアクションにより、アラートビルダーに即座に事前入力して、正しい指標とセグメントでアラートを作成できます。

[アラートビルダー](#alert-builder)インターフェイスが表示されます。


## アラートビルダー

Alert Builder インターフェイスは、Customer Journey Analyticsでセグメントや計算指標を作成する際に使用するインターフェイスに精通しています。

![アラートビルダーインターフェイス](assets/alert-builder.png)

アラートのアラートビルダーで次の詳細を指定します。

| 要素 | 説明 |
|---------|----------|
| **[!UICONTROL タイトル]** | アラートの名前を指定します。 アラート名には、レポートの名前や指標のしきい値が含まれる場合があります。 |
| **[!UICONTROL 説明（オプション）]** | アラートの説明を指定します。 |
| **[!UICONTROL 時間の精度]** | 指標を確認する頻度を日単位、週単位、または月単位で選択します。<p><b> メモ </b>:[&#x200B; カスタムカレンダー &#x200B;](/help/data-views/create-dataview.md#calendar) を使用したデータビューの場合、アラートビルダーでは月単位の精度はサポートされていません。<!--true?--></p> |
| **[!UICONTROL 受信者]** | アラートの送信先を指定します。アラートは、Analytics ユーザー、Analytics グループ、生のメールアドレス、または電話番号に送信できます。<p><b>重要</b>：電話番号には、先頭に `+` と[国コード](https://countrycode.org/)を付ける必要があります。</p><p>アラート後にユーザーが受け取るメール：</p><p>![アラートメール](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 有効期限]** | アラートの有効期限が切れる日時を設定します。 |
| **[!UICONTROL 遅延]** | データが完了し、Customer Journey Analytics でレポートできるようになるまでに必要な時間は組織によって異なりますが、通常はデータイベント時間から 3～9 時間です。アラートを正確にするには、特定のイベント範囲のイベントデータを完全にする必要があります。つまり、アドビでは指定されたイベント範囲のイベントデータを受信しなくなります。<p>この取り込み時間の遅延を考慮して、アラートを送信する前にデフォルトで 9 時間の遅延が設定されます。</p><p>デフォルトの 9 時間の遅延を 0～24 時間の間で調整できます。ただし、遅延を 9 時間未満に短縮すると、不完全なデータをレポートすることになり、アラート情報が不正確になる場合があります。</p><p>遅延時間を短縮する際は、次の点を考慮します。</p><ul><li>**データの可用性とデータの完全性について**：バッチデータは、3～9 時間後にのみExperience Platform データセットに取り込まれます。 アラートを正確にするには、データの取り込みが完了し、データセット内のすべてのバッチデータが使用可能になっている必要があります。</li><li>**データが完了してデータセットで使用できるようになるまでにかかる時間を判断**：データの取り込み時間は組織によって異なります。アラート配信に選択する遅延時間は、バッチデータが Platform データセットで使用可能になるまでの時間と同じか、それよりも少ない頻度であることを確認します<!--add link? -->。</li><p>**ヒント：** すべてのバッチデータが完了してExperience Platform データセットに取り込まれるまでに必要な時間を把握する最も正確な方法は、組織内のデータエンジニアに問い合わせることです。</p><p>または、組織内のバッチ配信が Platform データセットで使用できるようになるまでに要する一般的な時間を把握できます。 Analysis Workspaceで、次のフリーフォームテーブルを作成します。</p><ol><li>Analysis Workspace のフリーフォームテーブルに、[!UICONTROL **イベント**]&#x200B;指標と&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを追加します。</li><li>[!UICONTROL **時間**]&#x200B;ディメンションを使用して&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを分類します。<p>データがない時間は 0 として表示されます。</p></li></ol><li>**計算のエラーを考慮**：デフォルトの遅延時間を短縮する場合は、組織でのデータ取り込みの完了にかかる時間よりも1 時間以上長く遅延を設定します。例えば、データ取り込みの完了までに 3 時間の遅延がある場合は、遅延を 4 時間に設定する必要があります。</li></ul><p>詳しくは、[アラート機能の比較：Customer Journey Analytics と Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) の記事の [Customer Journey Analytics でのデータ取り込み時間が異なる](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)を参照してください。 |
| **[!UICONTROL 次の場合にアラートを送信]** | [!UICONTROL **次のいずれかの指標トリガー**]: <ol><li>指標（計算指標を含む）をドラッグ&amp;ドロップして、アラートのトリガーを作成します。<p>アラート内のすべての指標、ディメンション、またはセグメントが、現在選択されているレポートスイートと互換性がない場合、*互換性のないコンポーネント* メッセージが表示されます。</p><p>アラートを設定する前に、指標がしきい値（異常値）を超える必要があるか、値（超過、未満、等しい、または変更率の場合）を決定します。</li><li>次のいずれかの条件を選択します。<ul><li>異常値が存在する</li><li>異常値は想定を上回っています</li><li>異常値が期待値を下回る</li><li>次より上または等しい</li><li>次より小さいまたは等しい</li><li>変更者</li></ul></li><li>しきい値を選択するか、値を入力してください。</li></ol>[!UICONTROL **これらすべてのフィルターを使用**]：セグメントまたはディメンションをドラッグ＆ドロップして、アラートにフィルターを追加します。例えば、*モバイルデバイスのみ*&#x200B;セグメントを追加すると、ルールはモバイルデバイスに対してのみトリガーされます。AND ステートメントを使用して、その他のフィルターを追加できます。ギアアイコンをクリックして、AND または OR ルールを追加できます。</p><p>ユースケースの例について詳しくは、[アラート - ユースケース](alerts-use-cases.md)を参照してください。</p> |
| **[!UICONTROL プレビュー]** | インタラクティブアラートプレビューは、過去の経験に基づいて、アラートが実行されるおよその頻度を表示します。<p>例えば、時間の精度を毎日に設定すると、プレビューにより、最近の 30 または 31 日間で、特定の指標に対してアラートが何回トリガーされたかがわかります。</p><p>トリガーされているアラートが多すぎる場合は、[アラートの管理](/help/components/c-intelligent-alerts/alert-manager.md)でしきい値を調整できます。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
