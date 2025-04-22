---
description: プロジェクトコンポーネントが特定のしきい値に達した場合にアラートを受け取ります。
title: アラートの作成
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 94%

---

# アラートの作成 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="時間の精度"
>abstract="時間の精度とは、アラートのチェック頻度とアラートに含まれる内容の両方を指します"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>異常値検出を使用したアラート（_インテリジェントアラート_&#x200B;とも呼ばれる）の使用は、Customer Journey Analytics Prime または Ultimate パッケージを使用している組織でのみ使用できます。

Customer Journey Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。また、Customer Journey Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。

アラートの概要について詳しくは、[アラートの概要](/help/components/c-intelligent-alerts/intelligent-alerts.md)を参照してください。

アラートを作成するには：

1. Customer Journey Analytics で<!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" -->、**[!UICONTROL コンポーネント]**／**[!UICONTROL アラート]**&#x200B;を選択します。[アラートマネージャー](alert-manager.md)で、![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]** を選択して新しいアラートを作成するか、リストされているアラートのいずれかを選択して既存のアラートを変更します。

   [アラートビルダー](#alert-builder)インターフェイスが表示されます。

1. 「**[!UICONTROL 保存]**」を選択してアラートを保存します。「**[!UICONTROL 名前を付けて保存]**」を選択してアラートのコピーを保存します。


## アラートビルダー

Alert Builder インターフェイスは、Customer Journey Analyticsでセグメントや計算指標を作成したことがあるユーザーにとって便利な機能です。

![ アラートビルダーインターフェイス ](assets/alert-builder.png)

アラートのアラートビルダーで次の詳細を指定します。

| 要素 | 説明 |
|---------|----------|
| **[!UICONTROL タイトル]** | アラート名を指定します。アラート名には、レポート名または指標のしきい値を含めることができます。 |
| **[!UICONTROL 説明（オプション）]** | アラートの説明を指定します。 |
| **[!UICONTROL 時間の精度]** | 指標を確認する頻度を日単位、週単位、または月単位で選択します。<p><b>メモ：</b>カスタムカレンダーを含むデータビューの場合、アラートビルダーの月単位の精度をサポートしません。<!--true?--></p> |
| **[!UICONTROL 受信者]** | アラートの送信先を指定します。アラートは、Analytics ユーザー、Analytics グループ、生の電子メールアドレスまたは電話番号に送信できます。<p><b>重要：</b>電話番号には、先頭に「+」と[国コード](https://countrycode.org/)を付ける必要があります。</p><p>アラートをトリガーすると、ユーザーが受信するメールは次のようになります。</p><p>![アラートメール](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 有効期限]** | アラートの有効期限が切れる日時を設定します。 |
| **[!UICONTROL 遅延]** | データが完了し、Customer Journey Analytics でレポートできるようになるまでに必要な時間は組織によって異なりますが、通常はデータイベント時間から 3～9 時間です。アラートを正確にするには、特定のイベント範囲のイベントデータを完全にする必要があります。つまり、アドビでは指定されたイベント範囲のイベントデータを受信しなくなります。<p>この取り込み時間の遅延を考慮して、アラートを送信する前にデフォルトで 9 時間の遅延が設定されます。</p><p>デフォルトの 9 時間の遅延を 0～24 時間の間で調整できます。ただし、遅延を 9 時間未満に短縮すると、不完全なデータをレポートすることになり、アラート情報が不正確になる場合があります。</p><p>遅延時間を短縮する際は、次の点を考慮します。</p><ul><li>**データの可用性とデータの完全性について**：一部のデータはより早くレポートできる可能性がありますが、すべてのバッチデータは 3～9 時間後にのみ Platform データセットに取り込まれます。アラートを正確にするには、データの取り込みが完了し、データセット内のすべてのバッチデータが使用可能になっている必要があります。</li><li>**データが完了してデータセットで使用できるようになるまでにかかる時間を判断**：データの取り込み時間は組織によって異なります。アラート配信に選択する遅延時間は、バッチデータが Platform データセットで使用可能になるまでの時間と同じか、それよりも少ない頻度であることを確認します<!--add link? -->。</li><p>**ヒント：**&#x200B;すべてのバッチデータが完了し、Platform データセットに取り込まれるまでに必要な時間を把握する最も正確な方法は、組織のデータエンジニアに相談することです。</p><p>または、Analysis Workspace で次のフリーフォームテーブルを作成して、組織内のバッチ配信が Platform データセットで使用できるようになるまでにかかる時間を大まかに把握できます。</p><ol><li>Analysis Workspace のフリーフォームテーブルに、[!UICONTROL **イベント**]&#x200B;指標と&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを追加します。</li><li>[!UICONTROL **時間**]&#x200B;ディメンションを使用して&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを分類します。<p>データがない時間は 0 として表示されます。</p></li></ol><li>**計算のエラーを考慮**：デフォルトの遅延時間を短縮する場合は、組織でのデータ取り込みの完了にかかる時間よりも1 時間以上長く遅延を設定することをお勧めします。例えば、データ取り込みの完了までに 3 時間の遅延がある場合は、遅延を 4 時間に設定する必要があります。</li></ul><p>詳しくは、[アラート機能の比較：Customer Journey Analytics と Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) の記事の [Customer Journey Analytics でのデータ取り込み時間が異なる](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)を参照してください。 |
| **[!UICONTROL 次の場合にアラートを送信]** | [!UICONTROL **これらの指標のいずれかがトリガーとなる場合**]：指標（計算指標を含む）をここにドラッグ＆ドロップして、アラートのトリガーを作成します。<p>アラート内のすべての指標、ディメンション、セグメントが現在選択されているデータビューと互換性がない場合は、**「互換性のないコンポーネント」**&#x200B;というメッセージが表示されます。</p><p>アラートが設定される前に指標が超過している必要があるしきい値を指定します。この値をしきい値に設定し、以下のいずれかの条件にすることができます。</p><ul><li>異常値が存在する</li><li>異常値が予測より上</li><li>異常値が予測より下</li><li>以上</li><li>以下</li><li>変更（％）</li><li>90％、95％、99％、99.75％、99.9％ のしきい値を設定できます。</li></ul><p>[!UICONTROL **これらのフィルターを全て使用する場合**]：セグメントまたはディメンションをドラッグ&amp;ドロップして、アラートにフィルターを追加します。 例えば、「モバイルデバイスのみ *のセグメントを追加すると* ルールトリガーがモバイルデバイスに対してのみ適用されます。 AND ステートメントを使用して、その他のフィルターを追加できます。ギアアイコンをクリックして、AND または OR ルールを追加できます。</p><p>ユースケースの例について詳しくは、[アラート - ユースケース](/help/components/c-intelligent-alerts/alerts-use-cases.md)を参照してください。</p> |
| **[!UICONTROL プレビュー]** | インタラクティブアラートプレビューは、過去の経験に基づいて、アラートが実行されるおよその頻度を表示します。<p>例えば、時間の精度を毎日に設定すると、プレビューにより、最近の 30 または 31 日間で、特定の指標に対してアラートが何回トリガーされたかがわかります。</p><p>トリガーされているアラートが多すぎる場合は、[アラートの管理](/help/components/c-intelligent-alerts/alert-manager.md)でしきい値を調整できます。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
