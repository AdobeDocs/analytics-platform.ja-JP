---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f09937e6babca5549b9b78e9c90462673750a4b3
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 98%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年8月）

**最終更新日**：2025年9月4日（PT）


このリリースノートは、2025年8月13日～9月16日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用インターフェイスの更新** | [ 使用状況インターフェイス ](/help/connections/manage-connections.md#usage) に、コアデータ量と平均行サイズに関する情報が追加されるようになりました。 | | 2025年9月4日（PT） |
| **マップビジュアライゼーション** | マップビジュアライゼーションは新しいビジュアライゼーションのタイプで、（計算指標を含む）指標のビジュアルマップを作成できます。様々な地域にまたがる指標データを識別および比較する場合に役立ちます。<p>以前は、マップビジュアライゼーションは Adobe Analytics でのみ使用できました。</p><p>Customer Journey Analytics のマップビジュアライゼーションには、Adobe Analytics のマップビジュアライゼーションから、次の改善点が含まれています。</p><ul><li>データビューの任意のセグメントをデータソースとして使用します。</li><li>データビューでディメンションを設定することで、最大 1 メートルの精度を実現します。</li><li>新しい選択ツールを使用すると、ビジュアライゼーションで選択した任意の領域からセグメント、オーディエンス、トレンドまたは分類を作成できます。</li></ul><p>詳しくは、[マップ](/help/analysis-workspace/visualizations/map.md)を参照してください。</p> | 2025年8月13日（PT） | 2025年8月25日（PT） |
| **B2B テンプレート** | Customer Journey Analytics B2B Edition のライセンスを取得する場合、Adobe テンプレート UI から次の追加 B2B テンプレートが使用できるようになりました。 <ul><li>B2B アカウントエンゲージメントの概要</li><li>B2B 商談エンゲージメントの概要</li><li>B2B 購買グループアクティビティ</li></ul><p>詳しくは、[テンプレートの使用](/help/analysis-workspace/templates/use-templates.md)の [B2B テンプレート](/help/analysis-workspace/templates/use-templates.md#b2b-templates)を参照してください。</p> |  | 2025年8月15日（PT） |
| **PDF としてダウンロードしたプロジェクトは、ワークステーションにダウンロードされます** | プロジェクトを PDF 形式でダウンロードすると、その PDF はワークステーションのダウンロードフォルダーにダウンロードされます。 <p>以前は、プロジェクトを PDF 形式でダウンロードすると、PDF が一意の URL を使用して新しいブラウザータブに表示されていました。</p><p>詳しくは、[プロジェクトとデータのダウンロード](/help/analysis-workspace/export/download-send.md)を参照してください。</p> |  | 2025年8月25日（PT） |
| **アドホックスキーマのサポート** | [アドホックスキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/ad-hoc)は、CSV ファイルの取り込みや特定の種類のソース接続の作成など、Experience Platform の様々なデータ取り込みワークフローで使用されます。 <p>この機能により、Customer Journey Analytics でのアドホックスキーマの使用がサポートされるようになります。接続の定義の一環として、アドホックスキーマに基づくデータセットを選択し、そのデータをデータビューおよびワークスペースプロジェクトで使用できるようになりました。</p> <p>（ドキュメントへのリンクを添付。）</p> |  | 2025年9月18日（PT）（当初は 2025年8月28日（PT）にリリースする予定でした） |
| **ルックアップキー制限の拡張** | Customer Journey Analytics パッケージに応じて、ルックアップデータセットには最大 10 億までの一意のキーを含めることができるようになりました。 <p>詳しくは、Customer Journey Analytics の[ガードレール](/help/technotes/guardrails.md#data-transfer-limits)ドキュメントの[データ転送の制限](/help/technotes/guardrails.md)を参照してください。</p> |  | 2025年8月29日（PT） |
| **Platform スキーマのユーザー定義マップフィールドに基づいてメトリクスおよびディメンションを作成** | Experience Platform スキーマで定義したユーザー定義のマップフィールドを、Customer Journey Analytics で使用できるようになりました。<p>Customer Journey Analytics でメトリクスとディメンションを作成する際には、次のマップフィールドを使用できます。</p><ul><li>文字列を文字列に</li><li>文字列を整数に</li></ul><p>詳しくは、[コンポーネントの設定](/help/data-views/component-settings/overview.md)を参照してください。</p><p>Experience Platform のマップフィールドについて詳しくは、[UI でのマップフィールドの定義](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/map)を参照してください。</p> |  | 2025年8月末 |
| **削除されたプロジェクトはすぐに URL からアクセスできなくなり、スケジュールされた配信から削除されます** | 削除されたプロジェクトはスケジュールされた配信からすぐに削除され、URL からアクセスできなくなります。<p>以前は、プロジェクトはスケジュールされた配信に含まれ、削除後 60 日間は URL からアクセスできました。</p><p>プロジェクトの削除について詳しくは、[プロジェクトの概要](/help/analysis-workspace/build-workspace-project/freeform-overview.md)を参照してください。</p> | | 2025年8月末 |
| **リアルタイムレポート** | Customer Journey Analytics のリアルタイムレポートでは、Analysis Workspace の 1 つ以上のパネル内のデータとビジュアライゼーションをリアルタイムで表示および更新します。<br/><br/>（ドキュメントのリンクは以下を参照。） | | 2025年9月18日（PT）（当初は 2025年8月15日（PT）にリリースする予定でした） |
| **ストリーミングメディア：Adobe Experience Platform へのストリーミングメディアデータ収集に XDM フィールドを更新しました** | ストリーミングメディアデータを Adobe Experience Platform に収集する際、ストリーミングメディアパラメーターのドキュメントの「XDM フィールドパス」の見出しの下に表示されている XDM フィールドパスは使用できなくなりました。代わりに、2025年5月9日（PT）より前にストリーミングメディアデータを Platform に収集するように Analytics ソースコネクタを実装したお客様は、ストリーミングメディアパラメーターに関するドキュメントの「XDM フィールドパスのレポート」の見出しで示されているように、既存の設定を mediaReporting フィールドパスに移行する必要があります。<p> これらのフィールドパスは、[オーディオおよびビデオパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[広告パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/ad-parameters)、[チャプターパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/chapter-parameters)、[プレーヤー状態パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/player-state-parameters)および[品質パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/quality-parameters)のページに表示されますが、「廃止」としてマークされています。（2025年5月9日（PT）以降に Analytics ソースコネクタを実装し、既に mediaReporting XDM パスのみを使用しているお客様は、アクションは必要ありません。）</p><p>廃止された XDM フィールドパスでのデータ取り込みは、2025年10月末まで継続されます。その後、廃止されたフィールドパスは完全に廃止され、Adobe Experience Platform スキーマ UI に表示されなくなります。データは mediaReporting フィールドパスを使用してのみ送信されるようになります。</p><p>詳しくは、[更新された XDM ストリーミングメディアフィールドへの Analytics ソースコネクタの実装の移行](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)を参照してください。</p><p>移行のサポートについて詳しくは、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。 </p> |  | 2025年10月 |
| **接続におけるステッチ** | Customer Journey Analytics のステッチが簡素化されます。データセットを複製し、その複製されたデータセットにステッチを適用する代わりに、Customer Journey Analytics にデータを取り込む際にステッチが行われるようになりました。これにより、複製されたデータセットとスキーマの必要性がなくなります。 <p>さらに、カスタマーサポートを通じてステッチをリクエストする代わりに、更新された接続 UI から自分でステッチを開始できるようになりました。</p><p> *追加の作業が必要となるので、以前お知らせしたリリース日は延期されます。新しいリリース日はホリデーシーズンと重なるので、リリース制限が追加されます。現在は、安定性を確保し、ホリデー期間中の中断を最小限に抑えるのに、段階的なロールアウトが予定されています。*</p> | 2025年10月末 | 2026年1月末 |

## Customer Journey Analytics の修正点

**Analysis Workspace**：AN-389683、AN-389534、AN-389207、AN-389066、AN-388687、AN-388478、AN-387089、AN-384865、AN-384560、AN-383486、AN-365768、AN-351639
**コンポーネント**：
**コンテンツ分析**：
**ガイド付き分析**：AN-384426
**プラットフォーム**：AN-384410
**Report Builder**：AN-389336; AN-382775
**レポート**：
**セグメント化**：
**共有指標およびディメンション**：
**その他**：AN-388222、AN-384898、AN-387169


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
