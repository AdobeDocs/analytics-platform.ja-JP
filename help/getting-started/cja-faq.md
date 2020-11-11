---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 43%

---


# よくある質問

## 前提条件

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]に[!UICONTROL プライベートデバイスグラフ]または[!UICONTROL デバイスコープ]が必要ですか？ | いいえ、[!UICONTROL プライベートデバイスグラフ]または[!UICONTROL Customer Journey AnalyticsCoop]は[!UICONTROL デバイス]には必要ありません。 実際、それらはまだサポートされていません。 |
| [!UICONTROL Customer Journey Analytics]に[!UICONTROL Experience CloudID] (ECID)が必要ですか？ | いいえ。[!UICONTROL Customer Journey Analytics] は、データセット内の任意の ID（ECID か選択した他の ID かに関わらず）をサポートします。 |
| [!UICONTROL Customer Journey Analytics]の前にデータをETL (Extract, Transform, Load)する必要がある場合はどうなりますか？ | 現在、AEP に取り込む前にデータを変換する必要がある場合は、ETL パートナー（Unifi または Informatica）と連携する必要があります。データが既に取り込まれた後にETLが必要な場合、[!UICONTROL Adobe Experience Platformクエリサービス]はいくつかの制限されたオプションを提供します。 |

## データのステッチ

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] は、デバイスやデータセットをまたいで「ステッチ」することはできますか。 | はい。[!UICONTROL Customer Journey Analytics] は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。私たちは2020年11月に縫い合わせの解決策を発表しました。 詳細情報. |
| 匿名の行動を、サポートされている認証済みの行動にステッチすることはサポートされていますか。 | いいえ、まだサポートされていません。 |

## [!UICONTROL Customer Journey Analytics] へのデータの取得

| 質問 | 回答 |
| --- | --- |
| 異なる[!UICONTROL Adobe Experience Platform]サンドボックスのデータを1つの[!UICONTROL Customer Journey Analytics]接続に組み合わせることはできますか。 | いいえ。サンドボックス全体のデータにアクセスすることはできません。同じサンドボックス内にあるデータセットのみを組み合わせることができます。[詳細情報...](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| [!UICONTROL Adobe Experience Platform]の[!UICONTROL Customer Journey Analytics]に予想される遅延は何ですか？ | <ul><li>標準の負荷の場合：60 分未満 <br>**注：** パイプラインを通じたデータフローが異常に多い場合は、最長 24 時間かかる場合があります。</li><li>データのバックフィル（サイズにかかわらず、最大 13 ヶ月分のデータ）：4 週間未満</li></ul> |
| [!UICONTROL Customer Journey Analytics] でオンラインデータをオフラインデータに接続する方法を教えてください。 | [!UICONTROL Customer Journey Analytics] は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。データセット間でユーザー ID が一致している限り、[!UICONTROL Customer Journey Analytics] は、セグメント、アトリビューション、フロー、フォールアウトなどを接続できます。 |
| オフラインデータを[!UICONTROL Customer Journey Analytics]に取り込む方法を教えてください。 | [!UICONTROL Customer Journey Analytics]で使用する前に、Experience Platformに任意のデータを持ち込む必要があります。 Experience Platform のデータは、オンボーディングチームが必要に応じて、レコメンデーションやコンサルティングを提供するのに役立ちます。 |
| [!UICONTROL Adobe Analytics]データを[!UICONTROL Customer Journey Analytics]に入れる方法を教えてください。 | [!UICONTROL Adobe] 解析データは、 [Adobe Analyticsソースコネクタを介してExperience Platformに接続できます](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/analytics.html)。ほとんどの[!UICONTROL Adobe Analytics]フィールドはXDM形式で持ち込まれますが、他のフィールドはまだ利用できません([!UICONTROL マーケティングチャネル]ディメンションなど)。 |
| データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか。 | 開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。 |
| PII データを取り込んでデータ間の接続を確立する必要がありますか。 | いいえ。PII ではない顧客 ID のハッシュを含む、任意の ID を使用できます。 |

## 従来の[!UICONTROL Adobe Analytics]コンポーネント

| 質問 | 回答 |
| --- | --- |
| これは我々の従来の[!UICONTROL Adobe Analytics]製品にとって何を意味するのか？ | [!UICONTROL Customer Journey Analytics は、次世代の分析製品です。]現在の製品から[!UICONTROL Customer Journey Analytics]への進化には、何年もかかり、多くの調整が必要になります。 詳しくは、[Customer Journey Analytics 機能のサポート](/help/getting-started/cja-aa.md)を参照してください。 |
| [!UICONTROL Customer Journey Analytics]のセグメントをAEPや他のソリューションと共有できますか。 | まだできません。[!UICONTROL Customer Journey Analytics]からAEPにセグメントを共有する新しい革新的な方法を検討していますが、それほど長い遅延はありません。 潜在的な解決策として、クエリサービスの出力を統合プロファイルに共有できます。 |
| 古い eVar 設定はどうなりましたか。 | 従来のAdobe Analyticsの感覚で使用されるeVar、prop、イベントは、[!UICONTROL Customer Journey Analytics]には存在しなくなりました。 スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。 |
| すべてのセッションと変数の永続性の設定は、どこにありますか。 | [!UICONTROL Customer Journey Analytics では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。]これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント／計算指標はどうなりますか。 | [!UICONTROL Customer Journey Analytics は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。]つまり、既存のセグメントまたは計算指標が[!UICONTROL Customer Journey Analytics]と互換性がないことを意味します。 |
| [!UICONTROL Customer Journey Analytics]は`Uniques Exceeded`の制限をどのように処理しますか？ | [!UICONTROL Customer Journey Analytics には一意の値に関する制限がないので、ご心配は不要です。] |
| 既存の [!DNL Data Workbench] のユーザーであれば、今すぐ Customer Journey Analytics に移行できますか。 | 場合によります。Unified Customer Process（UCP）を多用している場合は、ステッチが実装されるまで待つ必要があります。既に顧客認証率が高い場合や、すべてのデータを一元管理したい場合、または eVar を排除したい場合は、Customer Journey Analytics が最適です。 |

## データコンポーネントの削除の影響

削除に関しては、次の6つのコンポーネントが関心を持ちます。サンドボックス、スキーマ、データセット、接続、データ表示、Workspaceプロジェクト。 次に、これらのコンポーネントの削除に関して考えられるシナリオを示します。

| もし私が… | こうなる… |
| --- | --- |
| [!UICONTROL Adobe Experience Platform]のサンドボックスを削除しますか？ | サンドボックスを削除すると、そのサンドボックス内のデータセットへの[!UICONTROL Customer Journey Analytics]接続へのデータフローが停止します。 現在、そのサンドボックスに関連付けられたCJA内の接続は自動的に削除されません。 |
| [!UICONTROL Adobe Experience Platform]のスキーマーを削除します。このスキーマーに関連付けられているデータセットは削除しませんか？ | [!UICONTROL Adobe Experience ] Platformでは、1つ以上のデータセットが関連付けられているスキーマを削除できません。ただし、適切な権限セットを持つ管理者は、まずデータセットを削除してからスキーマを削除できます。 |
| [!UICONTROL Adobe Experience Platform]のデータセットを削除しますか？ | AEPでデータセットを削除すると、そのデータセットからそのデータセットを含むすべてのConnectionsへのデータフローが停止します。 データセットのデータは、関連付けられたCJA接続から自動的に削除されません。 |
| [!UICONTROL Customer Journey Analytics]内のデータセットを削除しますか？ | 現在、保存された接続内のデータセットを削除することはできません。 接続全体を削除して開始を終了する必要があります。 (ただし、[!UICONTROL Adobe Experience Platform]のデータセットは削除できます)。 |
| データセット([!UICONTROL Adobe Experience Platform]内)からバッチを削除しますか？ | [!UICONTROL Adobe Experience Platform]データセットからバッチを削除すると、そのバッチを含むCJA接続からも同じバッチが削除されます。  [!UICONTROL Adobe Experience Platform]のバッチ削除がCJAに通知されます。 |
| バッチ&#x200B;**を削除して、**&#x200B;を[!UICONTROL Customer Journey Analytics]に取り込みますか？ | データセットにバッチが1つしかない場合、そのバッチからのデータも部分的なデータも[!UICONTROL Customer Journey Analytics]には表示されません。 取り込みがロールバックされます。 例えば、データセットに5つのバッチがあり、そのうち3つがデータセットの削除時に既に取り込まれている場合、これら3つのバッチのデータは[!UICONTROL Customer Journey Analytics]に表示されます。 |
| [!UICONTROL Customer Journey Analytics]の接続を削除しますか？ | 次のことを示すエラーメッセージが表示されます。<ul><li>削除した接続に対して作成されたデータ表示は、機能しなくなります。</li><li> 同様に、削除した接続のデータ表示に依存するWorkspaceプロジェクトは動作しなくなります。</li></ul> |
| [!UICONTROL Customer Journey Analytics]のデータ表示を削除しますか？ | エラーメッセージは、この削除されたデータ表示に依存するWorkspaceプロジェクトが動作しなくなることを示します。 |
