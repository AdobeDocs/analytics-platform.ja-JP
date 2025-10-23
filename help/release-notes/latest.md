---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0fff87aea456ca34169b63601e0cf239e178ebf8
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 92%

---

# 現在の Customer Journey Analytics リリースノート（2025年10月）

**最終更新日**：2025年10月14日（PT）

これらのリリースノートは、2025年10月～11月上旬（PT）のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **折れ線グラフビジュアライゼーションとスパークラインに含まれるフィルター条件** | フリーフォームテーブルフィルターに適用するすべての検索フィルター条件がスパークラインに常に含まれるようになりました。 さらに、接続された折れ線グラフビジュアライゼーションに検索フィルター条件を含めることもできます。<p>接続されたテーブルの指標列ヘッダーのスパークラインを選択すると、折れ線グラフビジュアライゼーションに検索フィルター条件を含めることができます。</p><p>以前は、検索フィルター条件は、スパークラインまたは接続された折れ線グラフビジュアライゼーションに含まれていませんでした。</p><p>詳しくは、[フリーフォームテーブルのトレンドデータの表示](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)を参照してください。</p> | | 2025年10月15日（PT） |
| **データストーリーテリング：Workspace レポートからスライドプレゼンテーションを生成する** | Analysis Workspace レポートに基づくスライドプレゼンテーション（.pptx 形式）を自動生成できるようになりました。 Workspace は、レポート内で主要なインサイトを検出し、関係者が利用できるスライドに変換します。<p>この機能により、結果を明らかにし、エグゼクティブ向けの説明文を作成し、ビジネスへの影響を伝えるために必要な時間と労力が削減されます。</p><p>詳しくは、[Data storytelling:Workspace レポートからスライドプレゼンテーションを生成する &#x200B;](/help/analysis-workspace/curate-share/generate-slides.md) を参照してください。</p> | 2025年10月22日（PT） | 2026年1月 |
| **リアルタイムレポート** | [Customer Journey Analyticsのリアルタイムレポート &#x200B;](/help/components/real-time/real-time.md) では、Analysis Workspaceの 1 つ以上のパネル内のデータとビジュアライゼーションをリアルタイムで表示および更新します。 | 2025年9月18日（PT）（当初は 2025年8月15日（PT）にリリースする予定でした） | 2025年10月22日（PT） |
| **データミラーのサポート** | Experience Platformでは、特定のソースコネクタに対してモデルベースのスキーマと Change Data Capture （CDC）機能がサポートされるようになり、Customer Journey Analyticsは、[、](/help/data-mirror/data-mirror.md)、[!DNL Snowflake] などの Data Warehouse ソリューションの [!DNL Azure Databricks] データミラー [!DNL Google BigQuery] 機能をサポートできるようになります。<p>ベータ版にアクセスするには、アドビのアカウントチームにお問い合わせください。</p> | ベータ版リリース：2025年9月24日（PT） | 未定 |
| **接続におけるステッチ** | Customer Journey Analytics のステッチが簡素化されます。 データセットを複製し、その複製されたデータセットにステッチを適用する代わりに、Customer Journey Analytics にデータを取り込む際にステッチが行われるようになりました。これにより、複製されたデータセットとスキーマの必要性がなくなります。 <p>さらに、カスタマーサポートを通じてステッチをリクエストする代わりに、更新された接続 UI から自分でステッチを開始できるようになりました。</p><p> *追加の作業が必要となるので、以前お知らせしたリリース日は延期されます。 新しいリリース日はホリデーシーズンと重なるので、リリース制限が追加されます。 現在は、安定性を確保し、ホリデー期間中の中断を最小限に抑えるのに、段階的なロールアウトが予定されています。*</p> <p>（ドキュメントのリンクは以下を参照。）</p> | 2025年10月28日（PT） | 2026年4月30日（PT） |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>（ドキュメントへのリンクを添付）<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025年10月29日（PT） |
| **Analytics ソースコネクタ：Experience Platform でのレポートスイートの検索** | レポートスイートが多数ある顧客は、Analytics ソースコネクタのデータフローワークフロー内で、接続先のレポートスイートを検索できるようになりました。 <p>以前は、顧客は、長くなる可能性があるレポートスイートのリストをページ分割する必要がありました。</p><p>（ドキュメントのリンクは以下を参照。） | | 2025年10月30日（PT） |
| **ストリーミングメディア：Adobe Experience Platform へのストリーミングメディアデータ収集に XDM フィールドを更新しました** | ストリーミングメディアデータを Adobe Experience Platform に収集する際、ストリーミングメディアパラメーターのドキュメントの「XDM フィールドパス」の見出しの下に表示されている XDM フィールドパスは使用できなくなりました。 代わりに、2025年5月9日（PT）より前にストリーミングメディアデータを Platform に収集するように Analytics ソースコネクタを実装したお客様は、ストリーミングメディアパラメーターに関するドキュメントの「XDM フィールドパスのレポート」の見出しで示されているように、既存の設定を mediaReporting フィールドパスに移行する必要があります。<p> これらのフィールドパスは、[オーディオおよびビデオパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[広告パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/ad-parameters)、[チャプターパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/chapter-parameters)、[プレーヤー状態パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/player-state-parameters)および[品質パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/quality-parameters)のページに表示されますが、「廃止」としてマークされています。 （2025年5月9日（PT）以降に Analytics ソースコネクタを実装し、既に mediaReporting XDM パスのみを使用しているお客様は、アクションは必要ありません。）</p><p>廃止された XDM フィールドパスでのデータ取り込みは、2025年10月末まで継続されます。 その後、廃止されたフィールドパスは完全に廃止され、Adobe Experience Platform スキーマ UI に表示されなくなります。データは mediaReporting フィールドパスを使用してのみ送信されるようになります。</p><p>詳しくは、[更新された XDM ストリーミングメディアフィールドへの Analytics ソースコネクタの実装の移行](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)を参照してください。</p><p>移行のサポートについて詳しくは、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。 </p> |  | 2025年10月 |

## Customer Journey Analytics の修正点

**Analysis Workspace**：AN-400507、AN-400265、AN-399209、AN-397146、AN-394992、AN-390795
**コンポーネント**：
**コンテンツ分析**：
**書き出し**：AN-399012、AN-388578
**ガイド付き分析**：
**実装**：AN-397551、AN-397550、AN-397190、AN-396127
**Report Builder**：AN-401127、AN-400618、AN-392971、AN-391692
**レポート**：
**セグメント化**：
**予定レポート**：
**共有指標およびディメンション**：
**その他**：


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
