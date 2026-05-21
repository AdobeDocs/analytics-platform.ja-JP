---
description: Analysis Workspaceでのアラートの作成方法について説明します。
title: アラートの作成
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
TQID: https://experienceleague.adobe.com/DALPpXgGDOoMJT8kv5xsDmZWapk4rDXhQmtTTvV0-TA
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 997
ht-degree: 67%

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

Customer Journey Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。 また、Customer Journey Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。

アラートについて詳しくは、[アラートの概要](/help/components/c-intelligent-alerts/intelligent-alerts.md)を参照してください。

アラートを作成するには：

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. Customer Journey Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]**&#x200B;を選択します。 [アラートマネージャー](alert-manager.md)で、![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]** を選択して新しいアラートを作成するか、リストされているアラートのいずれかを選択して既存のアラートを変更します。

1. Analysis Workspaceで、フリーフォームテーブル内の1つ以上の行項目を選択し、コンテキストメニューから「**[!UICONTROL 選択範囲からアラートを作成]**」を選択します。 このアクションでは、アラートビルダーに情報が瞬時に自動入力され、適切な指標とセグメントを含むアラートが作成されます。

[アラートビルダー](#alert-builder)インターフェイスが表示されます。


## アラートビルダー

アラートビルダーインターフェイスは、Customer Journey Analyticsでセグメントや計算指標を構築する際に使用するインターフェイスに慣れ親しんでいます。

![アラートビルダーインターフェイス](assets/alert-builder.png)

アラートのアラートビルダーで次の詳細を指定します。

| 要素 | 説明 |
|---------|----------|
| **[!UICONTROL タイトル]** | アラートの名前を指定します。 アラート名には、レポートの名前や指標のしきい値が含まれている場合があります。 |
| **[!UICONTROL 説明（オプション）]** | アラートの説明を指定します。 |
| **[!UICONTROL 時間の精度]** | 指標を確認する頻度を日単位、週単位、または月単位で選択します。<p><b>注意</b>: [ カスタムカレンダー](/help/data-views/create-dataview.md#calendar)のデータビューの場合、アラートビルダーでは月次粒度はサポートされていません。<!--true?--></p> |
| **[!UICONTROL 受信者]** | アラートの送信先を指定します。 アラートは、Analytics ユーザー、Analytics グループ、未加工の電子メールアドレス、または電話番号に送信できます。<p><b>重要</b>：電話番号には、先頭に `+` と[国コード](https://countrycode.org/)を付ける必要があります。</p><p>アラートの後にユーザーが受信する電子メール：</p><p>![アラートメール](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 有効期限]** | アラートの有効期限が切れる日時を設定します。 |
| **[!UICONTROL 遅延]** | データが完了し、Customer Journey Analytics でレポートできるようになるまでに必要な時間は組織によって異なりますが、通常はデータイベント時間から 3～9 時間です。 アラートを正確にするには、特定のイベント範囲のイベントデータを完全にする必要があります。つまり、アドビでは指定されたイベント範囲のイベントデータを受信しなくなります。<p>この取り込み時間の遅延を考慮して、アラートを送信する前にデフォルトで 9 時間の遅延が設定されます。</p><p>デフォルトの 9 時間の遅延を 0～24 時間の間で調整できます。 ただし、遅延を 9 時間未満に短縮すると、不完全なデータをレポートすることになり、アラート情報が不正確になる場合があります。</p><p>遅延時間を短縮する際は、次の点を考慮します。</p><ul><li>**データの可用性と完全性について**: バッチデータは、3 ～ 9時間後にのみExperience Platform データセットに取り込まれます。 アラートを正確にするには、データの取り込みが完了し、データセット内のすべてのバッチデータが使用可能になっている必要があります。</li><li>**データが完了してデータセットで使用できるようになるまでにかかる時間を判断**：データの取り込み時間は組織によって異なります。 アラート配信に選択する遅延時間は、バッチデータが Platform データセットで使用可能になるまでの時間と同じか、それよりも少ない頻度であることを確認します<!--add link? -->。</li><p>**ヒント：**&#x200B;すべてのバッチデータを完了してExperience Platform データセットに取り込むのに必要な時間を把握する最も正確な方法は、組織内のデータエンジニアに相談することです。</p><p>または、組織内のバッチ配信がPlatform データセットで使用可能になるまでにかかる時間の一般的なアイデアを得ることができます。 Analysis Workspaceで次のフリーフォームテーブルを作成します。</p><ol><li>Analysis Workspace のフリーフォームテーブルに、[!UICONTROL **イベント**]&#x200B;指標と&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを追加します。</li><li>[!UICONTROL **時間**]&#x200B;ディメンションを使用して&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを分類します。<p>データがない時間は 0 として表示されます。</p></li></ol><li>**計算のエラーを考慮**：デフォルトの遅延時間を短縮する場合は、組織でのデータ取り込みの完了にかかる時間よりも1 時間以上長く遅延を設定します。 例えば、データ取り込みの完了までに 3 時間の遅延がある場合は、遅延を 4 時間に設定する必要があります。</li></ul><p>詳しくは、[アラート機能の比較：Customer Journey Analytics と Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) の記事の [Customer Journey Analytics でのデータ取り込み時間が異なる](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)を参照してください。 |
| **[!UICONTROL 次の場合にアラートを送信]** | [!UICONTROL **これらの指標のいずれかがトリガー**]: <ol><li>指標（計算指標を含む）をドラッグ&amp;ドロップして、アラートのトリガーを作成します。<p>アラート内のすべての指標、ディメンションまたはセグメントが、現在選択されているレポートスイートと互換性がない場合、*互換性のないコンポーネント*&#x200B;のメッセージが表示されます。</p><p>アラートを設定する前に、指標が値（上記の場合、以下の場合、等しいまたはパーセンテージの変更）を超える必要があるしきい値（異常値の場合）を決定します。</li><li>次のいずれかの条件を選択します。<ul><li>異常値が存在する</li><li>異常値が予測より上</li><li>異常値が予測より下</li><li>以上</li><li>以下</li><li>変更者</li></ul></li><li>基準値を選択するか、値を入力します。</li></ol>[!UICONTROL **これらすべてのフィルターを使用**]：セグメントまたはディメンションをドラッグ＆ドロップして、アラートにフィルターを追加します。 例えば、*モバイルデバイスのみ*&#x200B;セグメントを追加すると、ルールはモバイルデバイスに対してのみトリガーされます。 AND ステートメントを使用して、その他のフィルターを追加できます。 ギアアイコンをクリックして、AND または OR ルールを追加できます。</p><p>ユースケースの例について詳しくは、[アラート - ユースケース](alerts-use-cases.md)を参照してください。</p> |
| **[!UICONTROL プレビュー]** | インタラクティブアラートプレビューは、過去の経験に基づいて、アラートが実行されるおよその頻度を表示します。<p>例えば、時間の精度を毎日に設定すると、プレビューにより、最近の 30 または 31 日間で、特定の指標に対してアラートが何回トリガーされたかがわかります。</p><p>トリガーされているアラートが多すぎる場合は、[アラートの管理](/help/components/c-intelligent-alerts/alert-manager.md)でしきい値を調整できます。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
