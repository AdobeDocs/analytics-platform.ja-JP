---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 04a681df29438de8d7c48fba394f607819997578
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 46%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年4月）

**最終更新日**：2025年4月16日（PT）

これらのリリースノートは、2025 年 3 月 27 日（PT）から 5 月 15 日（PT）のリリース期間に対応しています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **数値ディメンションの「値なし」行項目の更新** | 数値ディメンションの場合、この更新により次のことが可能になります<ul><li>フィルターで「値なし」ディメンション項目を使用する。</li><li>「値なし」行項目に関するレポートで分類を実行する。</li></ul> [詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | 2025年3月27日（PT） |
| **Adobe Content Analytics** | Adobe Content Analytics を使用すると、大量のコンテンツデータをすばやく簡単に調査して、トレンドを明らかにし、異常を発見し、コンテンツの疲労を特定し、コンテンツの閲覧状況からインサイトを取得できます。<p>標準の事前定義済みのレポートテンプレートやアセットインスペクターなどの新機能を使用して時間を節約できます。この機能を使用すると、データに合わせてアセットを視覚化できるだけでなく、各アセットを開いて、パフォーマンス、配置、属性などの詳細の概要を確認することもできます。<p>完全なカスタマージャーニーのコンテキスト内でこの新しいコンテンツデータセットを調査して、重要なビジネス上の質問に回答し、コンテンツのパフォーマンスを評価し、セグメント化を強化し、最適化の機会を特定し、アクティベーション用の新しいオーディエンスを定義できます。<p>Content Analytics は、Customer Journey Analytics のアドオンです。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/content-analytics/content-analytics) |  | 2025年3月27日（PT） |
| **メディアコレクション：新しいメディアレポート XDM 用の Adobe ソースコネクタの更新** | Analytics ソースコネクタは、Adobe Analytics のストリーミングメディアデータを、Web SDK で使用される同じフィールドに自動的にマッピングします。以前は、データは古い場所と新しい場所の両方にマッピングされていましたが、今後は新しい場所のみが使用されます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 2025年3月31日（PT） |
| **ストリーミングメディアデータをAdobe Experience Platformに収集するための XDM フィールドを更新しました** | 新しい XDM フィールドグループ `mediaReporting` を使用して、ストリーミングメディアデータをAdobe Experience Platformに収集できます。 新しい `mediaReporting` フィールドグループは、以前に使用した `media.mediaTimed` フィールドグループを置き換えます。<p>3 か月の移行期間中、`media.mediaTimed` フィールドへのデータ取り込みは続行されます。 ただし、2025 年 7 月末で、`the media.mediaTimed` フィールドは完全に非推奨となり、Adobe Experience Platform スキーマ UI に表示されなくなります。また、データは `mediaReporting` フィールドを使用してのみ送信されます。<p>2025 年 4 月 22 日（PT）より前にストリーミングメディアデータを Platform に収集する Analytics ソースコネクタを実装したお客様は、新しいフィールドグループを使用してデータを送信するように既存の設定を移行する必要があります。 この移行は、2025 年 7 月末までに完了する必要があります。 移行サポートについては、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。 2025 年 4 月 22 日（PT）以降に Analytics ソースコネクタを実装する顧客には、アクションは必要ありません。 |  | 2025年4月22日（PT） |
| **用語の変更：「フィルター」から「セグメント」へ** | 以前、Adobe Customer Journey Analyticsは、セグメントを「フィルター」と呼んでいました。 この用語は、Adobe Analyticsと共に導入されました。 「フィルター」は「セグメント」になりました。 （もちろん、検索フィルターは引き続き「フィルター」と呼ばれます）。UI が更新され、ドキュメントが更新中です。 |  | 2025年4月16日（PT） |
| **ステッチ：XDM IdentityMap から永続 ID と一時 ID を取得する** | この機能により、XDM identityMap に保存された ID をステッチプロセスで使用できるようになります。 identityMap は、フィールドベースのステッチに永続 ID または一時的な ID に使用でき、グラフベースのステッチに永続 ID として使用できます。  identityMap から特定の名前空間またはプライマリ ID を使用できます。 （ドキュメントへのリンクを添付） |  | 2025年4月25日（PT） |
| **データビュー全体で指標とディメンションを共有** | 複数のデータビューにわたってディメンションと指標の設定を適用できます。 共有ディメンションまたは指標に加えた変更は、適用可能なすべてのデータビューにわたる、そのディメンションまたは指標のすべてのインスタンスに適用されます。 このインターフェイスを使用すると、Customer Journey Analytics管理者は、多くのデータビューが使用されている場合に、コンポーネントをより簡単に管理できます。 （ドキュメントへのリンクを添付） |  | 2025年4月30日（PT） |


## Customer Journey Analytics の修正点

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN-371933; AN-371979
**オーディエンス**: AN-373032
**コンポーネント設定**: AN-367400
**派生フィールド**:AN-370614; AN-370959
**書き出し場所**:AN-371670
**完全テーブルのエクスポート**: AN-360492; AN-369204; AN-370755; AN-372294; AN-372363; AN-372754; AN-373040; AN-373081; AN-373168
**ジャーニーキャンバス**: AN-373294
**モバイルアプリ**: AN-363169; AN-368496; AN-371766
**製品使用例**: AN-369501
**レポート**: AN-369085; AN-371094; AN-372580


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
