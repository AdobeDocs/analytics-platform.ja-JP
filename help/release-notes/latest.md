---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7930ca9a124f4a82cbe0fb08e8766f04109ccd87
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 70%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年4月）

**最終更新日**：2025年4月30日（PT）

このリリースノートは、2025年3月27日（PT）～2025年5月15日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **イベントの深度ディメンション** | データビューの [ 必要な標準コンポーネント ](/help/data-views/component-reference.md#required-standard-components) のリストに、新しいイベントの深度ディメンションが追加されます。 |  | 2025年5月8日（PT） |
| **完全テーブルの書き出し制限の増加** | 完全なテーブルの書き出しで使用できる列数は、5 つのディメンションと 5 つの指標から 10 のディメンションと 10 の指標に増えました。 この増加は、すべてのCustomer Journey Analytics層に適用されます。 書き出し可能な行数の使用権限に変更はありません。 |  | 2025年4月30日（PT） |
| **数値ディメンションの「値なし」行項目の更新** | 数値ディメンションの場合、この更新により次のことが可能になります<ul><li>セグメントで「値なし」ディメンション項目を使用します。</li><li>「値なし」行項目に関するレポートで分類を実行する。</li></ul> [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | | 2025年3月27日（PT） |
| **Adobe Content Analytics** | Adobe Content Analytics を使用すると、大量のコンテンツデータをすばやく簡単に調査して、トレンドを明らかにし、異常を発見し、コンテンツの疲労を特定し、コンテンツの閲覧状況からインサイトを取得できます。<p>標準の事前定義済みのレポートテンプレートやアセットインスペクターなどの新機能を使用して時間を節約できます。この機能を使用すると、データに合わせてアセットを視覚化できるだけでなく、各アセットを開いて、パフォーマンス、配置、属性などの詳細の概要を確認することもできます。<p>完全なカスタマージャーニーのコンテキスト内でこの新しいコンテンツデータセットを調査して、重要なビジネス上の質問に回答し、コンテンツのパフォーマンスを評価し、セグメント化を強化し、最適化の機会を特定し、アクティベーション用の新しいオーディエンスを定義できます。<p>Content Analytics は、Customer Journey Analytics のアドオンです。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/content-analytics/content-analytics) |  | 2025年3月27日（PT） |
| **メディアコレクション：新しいメディアレポート XDM 用の Adobe ソースコネクタの更新** | Analytics ソースコネクタは、Adobe Analytics のストリーミングメディアデータを、Web SDK で使用される同じフィールドに自動的にマッピングします。以前は、データは古い場所と新しい場所の両方にマッピングされていましたが、今後は新しい場所のみが使用されます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 2025年3月31日（PT） |
| **Adobe Experience Platform にストリーミングメディアデータを収集するための XDM フィールドを更新** | ストリーミングメディアデータをAdobe Experience Platformに収集する場合、ストリーミングメディアパラメーターのドキュメントの「XDM フィールドパス」の見出しの下に表示されている XDM フィールドパスは使用しないでください。 これらのフィールドパスは次のページにあり、「非推奨」としてマークされています。[ オーディオおよびビデオパラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[ 広告パラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters)、[ チャプターパラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters)、[ プレーヤーステートパラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) および [ 品質パラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters)。 <p>代わりに、上記のストリーミングメディアパラメータードキュメントの「XDM フィールドパスのレポート」の見出しの下で示されているように、お客様は `mediaReporting` フィールドパスに移行する必要があります。<p>3 か月の移行期間に、非推奨（廃止予定）の XDM フィールドパスでのデータ取り込みは継続されます。 ただし、2025 年 7 月末に、非推奨フィールドパスは完全に削除され、Adobe Experience Platform スキーマ UI に表示されなくなり、データは `mediaReporting` フィールドパスを使用してのみ送信されます。<p>2025 年 4 月 22 日（PT）より前にストリーミングメディアデータを Platform に収集するために Analytics ソースコネクタを実装したお客様は、新しいフィールドパスを使用するように既存の設定を移行する必要があります。 この移行は、2025年7月末までに完了する必要があります。移行サポートについては、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。2025年4月22日（PT）以降に Analytics ソースコネクタを実装するお客様については、アクションは必要ありません。</p> |  | 2025年4月22日（PT） |
| **用語の変更：「フィルター」から「セグメント」へ** | 以前、Adobe Customer Journey Analytics では、セグメントを「フィルター」と呼んでいました。この用語は Adobe Analytics の用語と統一されました。「フィルター」は「セグメント」と呼ばれるようになりました。（もちろん、検索フィルターは引き続き「フィルター」と呼ばれます。） UI とドキュメントが更新されました。 | | 2025年4月16日（PT） |
| **ステッチ：XDM IdentityMap から永続 ID と一時 ID を取得** | この機能を活用すると、ステッチプロセスで XDM identityMap に保存されている ID を使用できるようになります。identityMap は、フィールドベースのステッチの永続 ID または一時 ID として使用するか、グラフベースのステッチの永続 ID として使用できます。identityMap に含まれる特定の名前空間またはプライマリ ID のいずれかを使用できます。詳しくは、[こちら](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap)と[こちら](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap)を参照してください |  | 2025年4月28日（PT） |
| **データビュー全体で指標とディメンションを共有** | 複数のデータビューをまたいでディメンションと指標の設定を適用できます。共有ディメンションまたは指標に対する変更は、適用可能なすべてのデータビュー全体で、そのディメンションまたは指標のすべてのインスタンスに適用されます。このインターフェイスにより、Customer Journey Analytics 管理者は、多くのデータビューが使用される場合に、コンポーネントをより簡単に管理できます。[詳細情報](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025年4月30日（PT） |


## Customer Journey Analytics の修正点

**Admin Console**：AN-370228
**Analysis Workspace**：AN-371933、AN-371933、AN-371979
**オーディエンス**：AN-373032
**コンポーネント設定**：AN-367400
**派生フィールド**：AN-370614、AN-370959
**書き出し場所**：AN-371670
**完全なテーブルの書き出し**：AN-360492、AN-369204、AN-370755、AN-372294、AN-372363、AN-372754、AN-373040、AN-373081、AN-373168
**ジャーニーキャンバス**：AN-373294
**モバイルアプリ**：AN-363169、AN-368496、AN-371766
**製品の使用状況**：AN-369501
**レポート**：AN-369085、AN-371094、AN-372580


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
