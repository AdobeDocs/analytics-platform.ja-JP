---
title: Customer Journey Analytics の FAQ
description: Customer Journey Analytics - よくある質問。
translation-type: tm+mt
source-git-commit: b0069e0f3528942620a6a69aaae1447f7452956f
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 40%

---


# よくある質問

## 前提条件

| 質問 | 回答 |
| --- | --- |
| 必要な機能 [!UICONTROL プライベートデバイスグラフ] または [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]? | いいえ、 [!UICONTROL プライベートデバイスグラフ] または [!UICONTROL Device Coop] は、 [!UICONTROL Customer Journey Analytics]. 実際、それらはまだサポートされていません。 |
| 必要な機能 [!UICONTROL Experience CloudID] (ECID) [!UICONTROL Customer Journey Analytics]? | いいえ。[!UICONTROL Customer Journey Analytics] は、データセット内の任意の ID（ECID か選択した他の ID かに関わらず）をサポートします。 |
| データを [!UICONTROL Customer Journey Analytics]? | 現在、AEP に取り込む前にデータを変換する必要がある場合は、ETL パートナー（Unifi または Informatica）と連携する必要があります。データが既に取り込まれた後にETLが必要な場合、 [!UICONTROL Adobe Experience Platformクエリサービス] には、一部の限定的なオプションがあります。 |

## データのステッチ

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] は、デバイスやデータセットをまたいで「ステッチ」することはできますか。 | はい。[!UICONTROL Customer Journey Analytics] は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。私たちは2020年11月に縫い合わせの解決策を発表しました。 詳細情報. |
| 匿名の行動を、サポートされている認証済みの行動にステッチすることはサポートされていますか。 | いいえ、まだサポートされていません。 |

## [!UICONTROL Customer Journey Analytics] へのデータの取得

| 質問 | 回答 |
| --- | --- |
| 異なる [!UICONTROL Adobe Experience Platform] 一つの箱 [!UICONTROL Customer Journey Analytics] 接続？ | いいえ。サンドボックス全体のデータにアクセスすることはできません。同じサンドボックス内にあるデータセットのみを組み合わせることができます。[詳細情報...](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| 予想される遅延 [!UICONTROL Customer Journey Analytics] on [!UICONTROL Adobe Experience Platform]? | <ul><li>標準の負荷の場合：60 分未満 <br>**注：** パイプラインを通じたデータフローが異常に多い場合は、最長 24 時間かかる場合があります。</li><li>データのバックフィル（サイズにかかわらず、最大 13 ヶ月分のデータ）：4 週間未満</li></ul> |
| [!UICONTROL Customer Journey Analytics] でオンラインデータをオフラインデータに接続する方法を教えてください。 | [!UICONTROL Customer Journey Analytics] は、bring-your-own-ID（個人 ID の持ち込み）分析システムです。データセット間でユーザー ID が一致している限り、[!UICONTROL Customer Journey Analytics] は、セグメント、アトリビューション、フロー、フォールアウトなどを接続できます。 |
| オフラインデータを [!UICONTROL Customer Journey Analytics]? | データを [!UICONTROL Customer Journey Analytics]. Experience Platform のデータは、オンボーディングチームが必要に応じて、レコメンデーションやコンサルティングを提供するのに役立ちます。 |
| 入手方法 [!UICONTROL Adobe Analytics] データを [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] データは、 [Adobe Analyticsソースコネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/analytics.html). 最も多い [!UICONTROL Adobe Analytics] フィールドはXDM形式で持ち越されますが、他のフィールドはまだ利用できません( [!UICONTROL マーケティングチャネル] ディメンションを参照)。 |
| データセット要素をデータビューに組み込むにはどの程度の時間がかかりますか。 | 開始するまでに数時間かかり、過去 13 か月のデータをバックフィルするのに数日かかります。 |
| PII データを取り込んでデータ間の接続を確立する必要がありますか。 | いいえ。PII ではない顧客 ID のハッシュを含む、任意の ID を使用できます。 |

## 従来の [!UICONTROL Adobe Analytics] コンポーネント

| 質問 | 回答 |
| --- | --- |
| これが従来の [!UICONTROL Adobe Analytics] 製品？ | [!UICONTROL Customer Journey Analytics は、次世代の分析製品です。]現在の製品から [!UICONTROL Customer Journey Analytics] 何年もかかり多くの協調が必要になるでしょう 詳しくは、[Customer Journey Analytics 機能のサポート](/help/getting-started/cja-aa.md)を参照してください。 |
| セグメントを [!UICONTROL Customer Journey Analytics] AEPや他のソリューションに | まだできません。新しい革新的な方法でセグメントを [!UICONTROL Customer Journey Analytics] をAEPに送信する必要があります。 潜在的な解決策として、クエリサービスの出力を統合プロファイルに共有できます。 |
| 古い eVar 設定はどうなりましたか。 | 従来のAdobe Analyticsの意味で使用されていたeVar、prop、イベントは、 [!UICONTROL Customer Journey Analytics]. スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。 |
| すべてのセッションと変数の永続性の設定は、どこにありますか。 | [!UICONTROL Customer Journey Analytics では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。]これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント／計算指標はどうなりますか。 | [!UICONTROL Customer Journey Analytics は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。]つまり、既存のセグメントまたは計算指標が [!UICONTROL Customer Journey Analytics]. |
| 方法 [!UICONTROL Customer Journey Analytics] 取り扱う `Uniques Exceeded` 制限事項 | [!UICONTROL Customer Journey Analytics には一意の値に関する制限がないので、ご心配は不要です。] |
| 既存の [!DNL Data Workbench] のユーザーであれば、今すぐ Customer Journey Analytics に移行できますか。 | 場合によります。Unified Customer Process（UCP）を多用している場合は、ステッチが実装されるまで待つ必要があります。既に顧客認証率が高い場合や、すべてのデータを一元管理したい場合、または eVar を排除したい場合は、Customer Journey Analytics が最適です。 |

## データコンポーネントの削除の影響

削除に関しては、次の6つのコンポーネントが関心を持ちます。サンドボックス、スキーマ、データセット、接続、データ表示、Workspaceプロジェクト。 次に、これらのコンポーネントの削除に関して考えられるシナリオを示します。

| 誰かが… | こうなる… |
| --- | --- |
| サンドボックスを [!UICONTROL Adobe Experience Platform]? | サンドボックスを削除すると、 [!UICONTROL Customer Journey Analytics] そのサンドボックス内のデータセットへの接続。 ただし、CJA内のデータセットは現在は削除されません。 |
| スキーマを [!UICONTROL Adobe Experience Platform]ですが、このスキーマに関連付けられているデータセットはありませんか。 | [!UICONTROL Adobe Experience Platform] は、1つ以上のデータセットが関連付けられているスキーマの削除を許可しません。 ただし、適切な権限セットを持つ管理者は、まずデータセットを削除してからスキーマを削除できます。 |
| データセットを [!UICONTROL Adobe Experience Platform]? | ～には通知はない。 [!UICONTROL Customer Journey Analytics];ただし、ストリーミングデータを有効にした場合、データセットが削除された後に新しいデータが取り込まれることはありません。<br>つまり、 **[!UICONTROL この接続の新しいデータセットをすべて自動的にインポートします（今日から）]** 接続が有効になっている場合、データセットが削除された後、新しいデータが入ってこなくなります。 |
| データセットを [!UICONTROL Customer Journey Analytics]? | 現在、保存された接続内のデータセットを削除することはできません。 接続全体を削除して開始を終了する必要があります。 (ただし、 [!UICONTROL Adobe Experience Platform].) |
| データセット( [!UICONTROL Adobe Experience Platform])? | バッチが既に [!UICONTROL Customer Journey Analytics], [!UICONTROL Customer Journey Analytics] バッチが削除されたことを現在認識していません。 バッチが取り込まれていない場合は、 [!UICONTROL Adobe Experience Platform]. |
| バッチを削除します **摂取中に** into [!UICONTROL Customer Journey Analytics]? | データセットにバッチが1つしかない場合、そのバッチのデータもデータの一部も [!UICONTROL Customer Journey Analytics]. 取り込みがロールバックされます。 例えば、データセットに5つのバッチが含まれ、そのうち3つがデータセットの削除時に既に取り込まれている場合、これら3つのバッチのデータは、 [!UICONTROL Customer Journey Analytics]. |
| 接続を [!UICONTROL Customer Journey Analytics]? | 次のことを示すエラーメッセージが表示されます。<ul><li>削除した接続に対して作成されたデータ表示は、機能しなくなります。</li><li> 同様に、削除した接続のデータ表示に依存するWorkspaceプロジェクトは動作しなくなります。</li></ul> |
| データ表示を [!UICONTROL Customer Journey Analytics]? | エラーメッセージは、この削除されたデータ表示に依存するWorkspaceプロジェクトが動作しなくなることを示します。 |
| Workspaceプロジェクトを [!UICONTROL Customer Journey Analytics]? | プロジェクトを再作成するか、回避策を使用してプロジェクトを回復できます。 次に移動 [!UICONTROL /管理者/ログ/使用状況およびアクセスログ]で、削除したプロジェクトを見つけて、そのIDをコピーします。 次に、任意のWorkspaceプロジェクトを開き、URL内のIDをコピーしたIDで更新します。 次に、プロジェクトを保存します。 |

