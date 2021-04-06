---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 95%

---

# よくある質問

## 前提条件

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスのグラフ]または [!UICONTROL Device Co-op] は必要ですか？ | いいえ。[!UICONTROL Customer Journey Analytics] には、[!UICONTROL プライベートデバイスのグラフ]や [!UICONTROL Device Co-op] は必要ありません。実際、それらはまだサポートされていません。 |
| [!UICONTROL Customer Journey Analytics] には、[!UICONTROL Experience Cloud ID]（ECID）は必要ですか？ | いいえ。[!UICONTROL Customer Journey Analytics] は、データセット内の任意の ID（[!UICONTROL ECID] か選択した他の ID かに関わらず）をサポートします。 |
| [!UICONTROL Customer Journey Analytics] の前に、データの ETL（抽出、変換、読み込み）が必要になった場合、どうしたらいいですか？ | 現在、AEP に取り込む前にデータを変換する必要がある場合は、ETL パートナー（Unifi または Informatica）と連携する必要があります。データの取り込み後に ETL が必要になった場合に備えて、 [!UICONTROL Adobe Experience Platform Query Services] にはいくつかの制限付きオプションが用意されています。 |

## データのステッチ

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] は、デバイスやデータセットをまたいで「ステッチ」することはできますか。 | はい。[!UICONTROL Customer Journey Analytics] は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。アドビは、2020 年 11 月にステッチに関するソリューションを発表しました。詳細情報. |
| 匿名の行動を、サポートされている認証済みの行動にステッチすることはサポートされていますか。 | いいえ、まだサポートされていません。 |

## [!UICONTROL Customer Journey Analytics] へのデータの取得

| 質問 | 回答 |
| --- | --- |
| 異なる [!UICONTROL Adobe Experience Platform] サンドボックスのデータを 1 つの [!UICONTROL Customer Journey Analytics] 接続に結合することはできますか？ | いいえ。サンドボックス全体のデータにアクセスすることはできません。同じサンドボックス内にあるデータセットのみを組み合わせることができます。[詳細情報...](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| [!UICONTROL Adobe Experience Platform] の [!UICONTROL Customer Journey Analytics] では、どの程度の遅延が予想されますか？ | <ul><li>標準の負荷の場合：60 分未満 <br>**注：** パイプラインを通じたデータフローが異常に多い場合は、最長 24 時間かかる場合があります。</li><li>データのバックフィル（サイズにかかわらず、最大 13 ヶ月分のデータ）：4 週間未満</li></ul> |
| [!UICONTROL Customer Journey Analytics] でオンラインデータをオフラインデータに接続する方法を教えてください。 | [!UICONTROL Customer Journey Analytics] は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。データセット間で人物IDが一致する限り、[!UICONTROL Customer Journey Analytics]はフィルター、アトリビューション、フロー、フォールアウトなどを接続できます。 接続できます。 |
| オフラインデータを [!UICONTROL Customer Journey Analytics] に取り込む方法を教えてください。 | [!UICONTROL Customer Journey Analytics] でデータを使用するには、事前にそのデータを Experience Platform に取り込む必要があります。Experience Platform のデータは、オンボーディングチームが必要に応じて、レコメンデーションやコンサルティングを提供するのに役立ちます。 |
| [!UICONTROL Adobe Analytics] データを [!UICONTROL Customer Journey Analytics] に取り込む方法を教えてください。 | [!UICONTROL Adobe Analytics] のデータは、[Adobe Analytics ソースコネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/analytics.html)を通じて Experience Platform に接続できます。[!UICONTROL Adobe Analytics] のフィールドは XDM 形式で取り込まれますが、他のフィールド（[!UICONTROL マーケティングチャネル]ディメンションなど）はまだ使用できません。 |
| データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか。 | 開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。 |
| PII データを取り込んでデータ間の接続を確立する必要がありますか。 | いいえ。PII ではない顧客 ID のハッシュを含む、任意の ID を使用できます。 |

## 従来の [!UICONTROL Adobe Analytics] コンポーネント

| 質問 | 回答 |
| --- | --- |
| 従来の [!UICONTROL Adobe Analytics] 製品とは何を表していますか？ | [!UICONTROL Customer Journey Analytics] は、次世代の分析製品です。現在の製品から [!UICONTROL Customer Journey Analytics] に進化するには、数年の時間がかかり、多くの調整がおこなわれます。詳しくは、[Customer Journey Analytics 機能のサポート](/help/getting-started/cja-aa.md)を参照してください。 |
| [!UICONTROL Customer Journey Analytics]のフィルターをAEPや他のソリューションと共有できますか？ | まだできません。[!UICONTROL Customer Journey Analytics]からAEPにフィルターを共有する新しい革新的な方法を探していますが、それほど長い遅れはありません。 潜在的な解決策として、クエリサービスの出力を統合プロファイルに共有できます。 |
| 古い eVar 設定はどうなりましたか。 | 従来の Adobe Analytics の eVar、prop およびイベントは、[!UICONTROL Customer Journey Analytics] にはもはや存在しません。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。 |
| すべてのセッションと変数の永続性の設定は、どこにありますか。 | [!UICONTROL Customer Journey Analytics] では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント／計算指標はどうなりますか。 | [!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存のセグメントや計算指標には、いずれも [!UICONTROL Customer Journey Analytics] との互換性はありません。 |
| [!UICONTROL Customer Journey Analytics] での `Uniques Exceeded` 制限の処理方法を教えてください。 | [!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。 |
| 既存の [!DNL Data Workbench] のユーザーであれば、今すぐ [!UICONTROL Customer Journey Analytics] に移行できますか。 | 場合によります。Unified Customer Process（UCP）を多用している場合は、ステッチが実装されるまで待つ必要があります。既に顧客認証率が高い場合や、すべてのデータを一元管理したい場合、または eVar を排除したい場合は、Customer Journey Analytics が最適です。 |

## データコンポーネントの削除の影響

サンドボックス、スキーマ、データセット、接続、データビュー、Workspace プロジェクト の 6 つのコンポーネントを削除する場合には注意が必要です。次に、これらのコンポーネントを削除した場合に考えられるシナリオを示します。

| 操作 | 結果 |
| --- | --- |
| [!UICONTROL Adobe Experience Platform] のサンドボックスを削除した場合 | サンドボックスを削除すると、そのサンドボックス内のデータセットへの [!UICONTROL Customer Journey Analytics] 接続に対するデータフローが停止します。現在、そのサンドボックスに関連付けられている CJA 内の接続は自動的に削除されません。 |
| [!UICONTROL Adobe Experience Platform] のスキーマを削除した一方で、このスキーマに関連付けられているデータセットは削除しなかった場合 | [!UICONTROL Adobe Experience Platform] では、1 つ以上のデータセットが関連付けられているスキーマを削除することはできません。ただし、適切な権限を持つ管理者は、データセットを削除してからスキーマを削除できます。 |
| [!UICONTROL Adobe Experience Platform] のデータセットを削除した場合 | AEP でデータセットを削除すると、そのデータセットから、そのデータセット自体を含むすべての接続へのデータフローが停止します。データセットのデータは、関連付けられた CJA 接続からは自動的に削除されません。 |
| [!UICONTROL Customer Journey Analytics] のデータセットを削除した場合 | 現在、保存された接続内のデータセットを削除することはできません。接続全体を削除して、操作をやり直す必要があります。（ただし、[!UICONTROL Adobe Experience Platform] のデータセットは削除できます） |
| [!UICONTROL Adobe Experience Platform] のデータセットからバッチを削除した場合 | [!UICONTROL Adobe Experience Platform] のデータセットからバッチを削除すると、そのバッチを含む CJA 接続からも同じバッチが削除されます。  CJA には、[!UICONTROL Adobe Experience Platform] のバッチが削除されたことが通知されます。 |
| [!UICONTROL Customer Journey Analytics] への&#x200B;**取り込み中に**&#x200B;バッチを削除した場合 | データセットにバッチが 1 つしかない場合、そのバッチからのデータも部分的なデータも [!UICONTROL Customer Journey Analytics] には表示されません。取り込みがロールバックされます。例えば、データセットに 5 つのバッチがあり、そのうち 3 つがデータセットの削除時に既に取り込まれている場合、これら 3 つのバッチのデータは [!UICONTROL Customer Journey Analytics] に表示されます。 |
| [!UICONTROL Customer Journey Analytics] の接続を削除した場合 | 次の内容を示すエラーメッセージが表示されます。<ul><li>削除した接続用に作成されたデータビューは、機能しなくなります。</li><li> 同様に、削除した接続のデータビューに依存する Workspace プロジェクトは動作しなくなります。</li></ul> |
| [!UICONTROL Customer Journey Analytics] のデータビューを削除した場合 | この削除されたデータビューに依存する Workspace プロジェクトが動作しなくなることを示すエラーメッセージが表示されます。 |
