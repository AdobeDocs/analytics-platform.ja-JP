---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4cea79a6ba26a2e4f06bfc9c60fdfc03341a7d60
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 93%

---

# 現在の Customer Journey Analytics リリースノート（2025年9月）

**最終更新日**：2025年9月23日（PT）


これらのリリースノートは、2025年9月～10月上旬のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用状況インターフェイスの更新** | [使用状況インターフェイス](/help/connections/manage-connections.md#usage)に、コアデータ量と平均行サイズに関する情報が追加されました。<p>詳しくは、[接続の管理](/help/connections/manage-connections.md#usage)を参照してください。</p> | | 2025年9月4日（PT） |
| **プロジェクトとコンポーネントを Customer Journey Analytics に移行する際の改善点** | プロジェクトとコンポーネントを Adobe Analytics から Customer Journey Analytics に移行する際に、次の改善が利用できるようになりました。<ul><li>複数のプロジェクトを一度に移行します。<br/>一度に最大 20 個のプロジェクトを移行できます。<br/>以前は、一度に 1 個のプロジェクトのみを移行できました。</li><li>以前のプロジェクト移行で既にマッピングされているディメンションと指標のマッピングを更新します。<br/>以前の移行で同じディメンションと指標がマッピングされていた場合でも、プロジェクトを移行するたびにこれらのマッピングを更新できるようになりました。<br/>以前は、選択したマッピングは今後のすべてのプロジェクト移行に対して永続的でした。</li><li>プロジェクト数が多い組織のパフォーマンスが向上しました。</li></ul><p>この機能は、Adobe Analytics インターフェイスから使用できます。詳しくは、[Adobe Analytics から Customer Journey Analytics へのコンポーネントとプロジェクトの移行](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/component-migration/component-migration)を参照してください。</p> | 2025年9月15日（PT） | 2025年9月18日（PT） |
| **ルックアップキーの制限が最大 10 億に増加** | ルックアップデータセットの一意のキーの最大数は、Customer Journey Analytics の使用権限に応じて、最大 10 億になりました。 <p>以前は、すべての使用権限で最大数は 1,000 万でした。<p>詳しくは、[ガードレール](/help/technotes/guardrails.md)を参照してください。</p> | | 2025年9月25日（PT） |
| **アドホックスキーマとモデルベースのスキーマのサポート** | [アドホック](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/ad-hoc)スキーマとモデルベースのスキーマは、Experience Platform ではデータ取り込みワークフローとデータミラーワークフローで使用されます。 |  | 2025年9月23日（PT）（当初は 2025年8月28日（PT）にリリースする予定でした） |
| **リアルタイムレポート** | Customer Journey Analytics のリアルタイムレポートでは、Analysis Workspace の 1 つ以上のパネル内のデータとビジュアライゼーションをリアルタイムで表示および更新します。<br/><br/>（ドキュメントへのリンクを添付。） | 2025年9月18日（PT）（当初は 2025年8月15日（PT）にリリースする予定でした） | 2025年10月27日（PT） |
| **データミラーのサポート** | Experience Platform の特定のソースコネクタに対するモデルベースのスキーマと変更データキャプチャ（CDC）機能のサポートにより、Customer Journey Analytics では、[!DNL Snowflake]、[!DNL Azure Databrick]s、[!DNL Google BigQuery] のデータウェアハウスソリューションのデータミラー機能をサポートできます。<p>ベータ版にアクセスするには、アドビのアカウントチームにお問い合わせください。</p><p>（ドキュメントへのリンクを添付。）</p> | 2025年9月24日（PT）以降のベータ版リリース | 未定 |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツの予定データをアップロードして、より簡単かつ正確に視聴者を追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。特定のトピックやプログラムセグメントの視聴者データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に関連付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに関連付けることはできませんでした。</p><p>（ドキュメントへのリンクを添付。）<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025年10月29日（PT） |
| **ストリーミングメディア：Adobe Experience Platform へのストリーミングメディアデータ収集に XDM フィールドを更新しました** | ストリーミングメディアデータを Adobe Experience Platform に収集する際、ストリーミングメディアパラメーターのドキュメントの「XDM フィールドパス」の見出しの下に表示されている XDM フィールドパスは使用できなくなりました。代わりに、2025年5月9日（PT）より前にストリーミングメディアデータを Platform に収集するように Analytics ソースコネクタを実装したお客様は、ストリーミングメディアパラメーターに関するドキュメントの「XDM フィールドパスのレポート」の見出しで示されているように、既存の設定を mediaReporting フィールドパスに移行する必要があります。<p> これらのフィールドパスは、[オーディオおよびビデオパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[広告パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/ad-parameters)、[チャプターパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/chapter-parameters)、[プレーヤー状態パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/player-state-parameters)および[品質パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/quality-parameters)のページに表示されますが、「廃止」としてマークされています。（2025年5月9日（PT）以降に Analytics ソースコネクタを実装し、既に mediaReporting XDM パスのみを使用しているお客様は、アクションは必要ありません。）</p><p>廃止された XDM フィールドパスでのデータ取り込みは、2025年10月末まで継続されます。その後、廃止されたフィールドパスは完全に廃止され、Adobe Experience Platform スキーマ UI に表示されなくなります。データは mediaReporting フィールドパスを使用してのみ送信されるようになります。</p><p>詳しくは、[更新された XDM ストリーミングメディアフィールドへの Analytics ソースコネクタの実装の移行](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)を参照してください。</p><p>移行のサポートについて詳しくは、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。 </p> |  | 2025年10月 |
| **接続におけるステッチ** | Customer Journey Analytics のステッチが簡素化されます。データセットを複製し、その複製されたデータセットにステッチを適用する代わりに、Customer Journey Analytics にデータを取り込む際にステッチが行われるようになりました。これにより、複製されたデータセットとスキーマの必要性がなくなります。 <p>さらに、カスタマーサポートを通じてステッチをリクエストする代わりに、更新された接続 UI から自分でステッチを開始できるようになりました。</p><p> *追加の作業が必要となるので、以前お知らせしたリリース日は延期されます。新しいリリース日はホリデーシーズンと重なるので、リリース制限が追加されます。現在は、安定性を確保し、ホリデー期間中の中断を最小限に抑えるのに、段階的なロールアウトが予定されています。*</p> <p>（ドキュメントへのリンクを添付。）</p> | 2025年10月末 | 2026年1月末 |

## Customer Journey Analytics の修正点

**Analysis Workspace**：AN-391719、AN-380838、AN-389402、AN-389373、AN-390851、AN-391593、AN-391404、AN-393064、AN-379337
**コンポーネント**：AN-393810
**Content Analytics**：
**ガイド付き分析**：
**プラットフォーム**：
**Report Builder**：AN-387741、AN-386777、AN-388720、AN-389343
**レポート**：AN-391439、AN-391228、AN-393620、AN-393640、AN-391334、AN-393304
**セグメント化**：
**予定レポート**：AN-391150、AN-390474
**共有指標およびディメンション**：
**その他**：AN-387858


## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
