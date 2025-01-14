---
description: プロジェクトコンポーネントが特定のしきい値に達した場合にアラートを受け取ります。
title: アラートの作成
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 21%

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
>異常値検出を使用したアラート（_インテリジェントアラート_ とも呼ばれます）は、Customer Journey AnalyticsのPrimeまたはUltimate パッケージを使用している組織でのみ使用できます。

Customer Journey Analyticsのアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受け取ることができます。 Customer Journey Analyticsパッケージによっては、異常値のしきい値に基づいてアラートをトリガーすることもできます。

アラートの概要について詳しくは、「[ アラートの概要 ](/help/components/c-intelligent-alerts/intelligent-alerts.md)」を参照してください。

アラートを作成するには：

1. Customer Journey Analyticsで、**[!UICONTROL コンポ <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" --> ネント]**/**[!UICONTROL アラート]** を選択します。 [ アラートマネージャー ](alert-manager.md) で、![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** を選択して新しいアラートを作成するか、リストに表示された任意のアラートを選択して既存のアラートを変更します。

   [ アラートビルダー ](#alert-builder) インターフェイスが表示されます。

1. 「**[!UICONTROL 保存]**」を選択して、アラートを保存します。 **[!UICONTROL 名前を付けて保存]** を選択して、アラートのコピーを保存します。


## アラートビルダー

Alert Builder インターフェイスは、Customer Journey Analyticsでフィルターや計算指標を作成したことがある方に適しています。

![](assets/alert-builder.png)

アラートのアラートビルダーで、次の詳細を指定します。

| 要素 | 説明 |
|---------|----------|
| **[!UICONTROL タイトル]** | アラート名を指定します。アラート名には、レポート名または指標のしきい値を含めることができます。 |
| **[!UICONTROL 説明（オプション）]** | アラートの説明を指定します。 |
| **[!UICONTROL 時間の精度]** | 指標のチェック頻度として、「毎日」、「毎週」、「毎月」のいずれかを選択します。<p><b> メモ：</b> カスタムカレンダーを使用したデータビューの場合、アラートビルダーの月ごとの精度はサポートされません。<!--true?--></p> |
| **[!UICONTROL 受信者]** | アラートの送信先を指定します。アラートは、Analytics ユーザー、Analytics グループ、生の電子メールアドレスまたは電話番号に送信できます。<p><b> 重要：</b> 電話番号の前には、「+」と [ 国コード ](https://countrycode.org/) が必要です。</p><p>アラートがトリガーされた後にユーザーが受け取るメールは、次のようになります。</p><p>![ アラートメール ](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 有効期限]** | アラートの有効期限を設定する日時を設定します。 |
| **[!UICONTROL 遅延]** | データが完了し、Customer Journey Analyticsでレポートできる状態になるまでの時間は、組織によって異なり、通常はデータイベント時刻から 3 ～ 9 時間後の範囲です。 アラートを正確にするには、特定のイベント範囲のイベントデータが完全である必要があります。つまり、Adobeは指定されたイベント範囲のイベントデータを受け取らなくなります。<p>この取り込み時間の遅延を考慮して、アラートを送信するまでのデフォルトの遅延は 9 時間になっています。</p><p>デフォルトの 9 時間の遅延は、0 ～ 24 時間の間に調整できます。 ただし、遅延を 9 時間未満に減らすと、不完全なデータに関するレポートを作成していることになり、アラート情報が不正確になる可能性があります。</p><p>遅延時間を減らす際は、次の点を考慮してください。</p><ul><li>**データの可用性と完全性について**：一部のデータはより早くレポートできる場合がありますが、すべてのバッチデータは 3～9 時間の期間の後にのみ Platform データセットに取り込まれます。 アラートを正確にするには、データ取り込みが完了し、データセットで使用可能なすべてのバッチデータが揃っている必要があります。</li><li>**データが完了してデータセットで使用できるようになるまでの時間を決定**：データ取り込み時間は、組織によって異なります。 アラート配信に選択した遅延時間が、Platform データセットでバッチデータを使用できるようになるまでにかかる時間と同じか、それよりも少ない頻度であることを確認してください <!--add link? --></li><p>**ヒント：** すべてのバッチデータが完了して Platform データセットに取り込まれるまでに必要な時間を把握する最も正確な方法は、組織のデータエンジニアに問い合わせることです。</p><p>または、Analysis Workspaceで次のフリーフォームテーブルを作成して、組織内のバッチ配信が Platform データセットで使用できるようになるまでに要する一般的な時間を把握することもできます。</p><ol><li>Analysis Workspaceのフリーフォームテーブルで、[!UICONTROL **イベント**] 指標と [!UICONTROL **日**] ディメンションを追加します。</li><li>[!UICONTROL **時間**] ディメンションを使用して [!UICONTROL **日**] ディメンションを分類します。<p>データのない時間は 0 と表示されます。</p></li></ol><li>**計算のエラーを考慮**: デフォルトの遅延時間を減らした場合、組織でのデータ取り込みの完了にかかる時間よりも少なくとも 1 時間長く、遅延を設定することをお勧めします。 例えば、データ取り込みが完了するまでに 3 時間の遅延がある場合、遅延を 4 時間に設定する必要があります。</li></ul><p>詳しくは、「[ アラート機能の比較：Customer Journey AnalyticsとAdobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) の記事の [ データ取り込み時間のCustomer Journey Analyticsが異なる ](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) を参照してください。 |
| **[!UICONTROL アラートを送信するタイミング]** | [!UICONTROL **次のいずれかの指標トリガー**]：指標（計算指標を含む）をここにドラッグ&amp;ドロップして、アラートのトリガーを作成します。<p>アラート内のすべての指標、ディメンション、またはセグメントが、現在選択されているデータビューと互換性がない場合、**「互換性のないコンポーネント」** というメッセージが表示されます。</p><p>アラートが設定される前に指標が超過している必要があるしきい値を指定します。この値をしきい値に設定し、以下のいずれかの条件にすることができます。</p><ul><li>異常値が存在する</li><li>異常値が予測より上</li><li>異常値が予測より下</li><li>以上</li><li>以下</li><li>変更（％）</li><li>90％、95％、99％、99.75％、99.9％ のしきい値を設定できます。</li></ul><p>[!UICONTROL **これらのフィルターを全て使用する場合**]：セグメントまたはディメンションをドラッグ&amp;ドロップして、フィルターを追加します。 例えば、「モバイルデバイスのみ」のセグメントを追加すると、ルールトリガーはモバイルデバイスのみに適用されます。 AND ステートメントを使用して、追加のフィルターを追加できます。 ギアアイコンをクリックして、AND または OR ルールを追加できます。</p><p>ユースケースなどの [ アラート – ユースケース ](/help/components/c-intelligent-alerts/alerts-use-cases.md) を参照してください。</p> |
| **[!UICONTROL プレビュー]** | インタラクティブアラートプレビューは、過去の経験に基づいて、アラートが実行されるおよその頻度を表示します。<p>例えば、時間の精度を毎日に設定すると、プレビューにより、最近の 30 または 31 日間で、特定の指標に対してアラートが何回トリガーされたかがわかります。</p><p>トリガーされるアラートが多すぎる場合は、[ アラートの管理 ](/help/components/c-intelligent-alerts/alert-manager.md) でしきい値を調整できます。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
