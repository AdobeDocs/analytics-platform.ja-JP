---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc22f2c83340bacb99fd08095c48585be9e5f1fe
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 19%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年8月）

**最終更新日**：2025年8月14日（PT）


これらのリリースノートは、2025 年 8 月 13 日（PT）から 9 月 16 日（PT）までのリリース期間に対応しています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **マップビジュアライゼーション** | マップビジュアライゼーションは、Analysis Workspace内のビジュアライゼーションで、任意の指標（計算指標を含む）の視覚的なマップを作成できます。 様々な地域をまたいだ指標データを識別および比較する際に役立ちます。<p>以前は、マップビジュアライゼーションはAdobe Analyticsでのみ使用できました。</p><p>Customer Journey Analyticsのマップビジュアライゼーションには、Adobe Analyticsのマップビジュアライゼーションの次の改善点が含まれています。</p><ul><li>データビューの任意のセグメントをデータソースとして使用します。</li><li>データビューでディメンションを設定することで、最大 1 つのメーターの精度が向上します。</li><li>新しい選択ツールを使用すると、ビジュアライゼーションで選択した任意の領域からセグメント、オーディエンス、トレンドまたは分類を作成できます。</li></ul><p>詳しくは、[Map](/help/analysis-workspace/visualizations/map.md) を参照してください。</p> | 2025年8月13日（PT） | 2025年8月25日（PT） |
| **B2B テンプレート** | Customer Journey Analytics B2B editionのライセンスを取得する場合、Adobe テンプレート UI から次の追加 B2B テンプレートが使用できるようになりました。 <ul><li>B2B アカウントエンゲージメントの概要</li><li>B2B 商談エンゲージメントの概要</li><li>B2B 購買グループアクティビティ</li></ul><p>詳しくは、「[ テンプレートの使用 ](/help/analysis-workspace/templates/use-templates.md#b2b-templates) の [B2B テンプレート ](/help/analysis-workspace/templates/use-templates.md) を参照してください。</p> |  | 2025年8月15日（PT） |
| **PDF としてダウンロードしたプロジェクトは、ワークステーションにダウンロードされます** | プロジェクトを as a PDFとしてダウンロードすると、PDFがワークステーションのダウンロードフォルダーにダウンロードされます。 <p>以前は、プロジェクトを as a PDFとしてダウンロードすると、PDFが一意の URL で新しいブラウザータブに表示されていました。</p><p>詳しくは、[ プロジェクトとデータのダウンロード ](/help/analysis-workspace/export/download-send.md) を参照してください。</p> |  | 2025年8月25日（PT） |
| **アドホックスキーマのサポート** | [ アドホックスキーマ ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/ad-hoc) は、CSV ファイルの取り込みや特定の種類のソース接続の作成など、Experience Platformの様々なデータ取り込みワークフローで使用されます。 <p>この機能により、Customer Journey Analyticsでのアドホックスキーマの使用がサポートされるようになります。 接続の定義の一環として、アドホックスキーマに基づくデータセットを選択し、そのデータをデータビューおよびワークスペースプロジェクトで使用できるようになりました。</p> <p>（ドキュメントへのリンクを添付。）</p> |  | 2025年8月28日（PT） |
| **参照キー制限の拡張** | Customer Journey Analytics パッケージに応じて、ルックアップデータセットには最大 10 億までの一意のキーを含めることができるようになりました。 <p>詳しくは、Customer Journey Analytics[ ガードレール ](/help/technotes/guardrails.md#data-transfer-limits) ドキュメントの [ データ転送の制限 ](/help/technotes/guardrails.md) を参照してください。</p> |  | 2025年8月29日（PT） |
| **Platform スキーマのユーザー定義マップフィールドに基づいて指標およびディメンションを作成する** | Experience Platform スキーマで定義したユーザー定義のマップフィールドを、Customer Journey Analyticsで使用できるようになりました。<p>Customer Journey Analyticsで指標とディメンションを作成する際には、次のマップフィールドを使用できます。</p><ul><li>文字列から文字列へ</li><li>文字列を整数に</li></ul><p>（ドキュメントへのリンクを添付。）</p><p>Experience Platformのマップフィールドについて詳しくは、[UI でのマップフィールドの定義 ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/map) を参照してください。</p> |  | 2025 年 8 月末 |
| **削除されたプロジェクトは URL からすぐに使用できなくなり、スケジュールされた配信から削除されます** | 削除されたプロジェクトはスケジュールされた配信から直ちに削除され、URL からアクセスできなくなります。<p>以前は、プロジェクトはスケジュールされた配信に含まれ、削除後 60 日間 URL でアクセスできていました。</p><p>プロジェクトの削除について詳しくは、[ プロジェクトの概要 ](/help/analysis-workspace/build-workspace-project/freeform-overview.md) を参照してください。</p> | | 2025 年 8 月末 |
| **リアルタイムレポート** | Customer Journey Analyticsのリアルタイムレポートでは、Analysis Workspaceの 1 つ以上のパネル内のデータとビジュアライゼーションをリアルタイムで表示および更新します。 | | 2025 年 9 月 17 日（PT）（当初は 2025 年 8 月 15 日にリリースする予定です） |
| **ストリーミングメディア：ストリーミングメディアデータをAdobe Experience Platformに収集するための更新された XDM フィールド** | ストリーミングメディアデータを Adobe Experience Platform に収集する際、ストリーミングメディアパラメーターのドキュメントの「XDM フィールドパス」の見出しの下に表示されている XDM フィールドパスは使用できなくなりました。代わりに、2025 年 5 月 9 日（PT）より前にストリーミングメディアデータを Platform に収集するように Analytics ソースコネクタを実装したお客様は、ストリーミングメディアパラメーターに関するドキュメントの「XDM フィールドパスのレポート」の見出しで示されているように、既存の設定を mediaReporting フィールドパスに移行する必要があります。<p> これらのフィールドパスは次のページにあり、「非推奨」としてマークされています。[ オーディオおよびビデオパラメーター ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[ 広告パラメーター ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/ad-parameters)、[ チャプターパラメーター ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/chapter-parameters)、[ プレーヤーステートパラメーター ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/player-state-parameters) および [ 品質パラメーター ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/quality-parameters)。 （2025 年 5 月 9 日（PT）以降に Analytics ソースコネクタを実装し、mediaReporting XDM パスのみを既に使用している顧客の場合は、アクションは必要ありません。）</p><p>非推奨（廃止予定）の XDM フィールドパスのデータ取り込みは、2025 年 10 月末まで継続されます。 その後、非推奨フィールドパスは完全に削除され、Adobe Experience Platform スキーマ UI に表示されなくなります。データは、mediaReporting フィールドパスを使用してのみ送信されます。</p><p>詳しくは、[ 更新された XDM ストリーミングメディアフィールドへの Analytics Source Connector 実装の移行 ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields) を参照してください。</p><p>移行サポートについては、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。 </p> |  | 2025年10月 |
| **接続のステッチ** | Customer Journey Analyticsのステッチを簡素化します。 データセットを複製し、複製されたデータセットにステッチを適用する代わりに、Customer Journey Analyticsへのデータの取り込みでステッチが行われるようになりました。これにより、重複したデータセットとスキーマの要件がなくなります。 <p>さらに、カスタマーサポートを通じてステッチをリクエストする代わりに、更新された接続 UI から自分でステッチを開始できるようになりました。</p><p> *以前お知らせしたリリース日は、追加の作業が必要となるため、プッシュされます。 新しいリリース日はホリデーシーズンと重なるので、リリース制限が追加されます。 現在は、安定性を確保し、休暇期間中の中断を最小限に抑えるために、段階的なロールアウトが計画されています。*</p> | 2025 年 10 月末 | 2026 年 1 月末 |

## Customer Journey Analytics の修正点

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**コンポーネント**:
**Content Analytics**:
**ガイド付き分析**: AN-384426
**Platform**: AN-384410
**Report Builder**: AN-389336; AN-382775
**レポート**:
**セグメント化**:
**共有指標およびディメンション**:
**その他**: AN-388222; AN-384898; AN-387169


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
