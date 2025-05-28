---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: df8a10c674ed64d0341209fbe0a700a5c94b3b75
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 36%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年5月）

**最終更新日**：2025年5月22日（PT）


これらのリリースノートは、2025 年 4 月 22 日（PT）から 6 月 18 日（PT）までのリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Experience Platform にストリーミングメディアデータを収集するための XDM フィールドを更新** | ストリーミングメディアデータをAdobe Experience Platformに収集する場合、ストリーミングメディアパラメーターのドキュメントの「XDM フィールドパス」の見出しの下に表示されている XDM フィールドパスは使用しないでください。 これらのフィールドパスは次のページにあり、「非推奨」としてマークされています。[ オーディオおよびビデオパラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[ 広告パラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters)、[ チャプターパラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters)、[ プレーヤーステートパラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) および [ 品質パラメーター ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters)。 <p>代わりに、上記のストリーミングメディアパラメータードキュメントの「XDM フィールドパスのレポート」の見出しの下で示されているように、お客様は `mediaReporting` フィールドパスに移行する必要があります。<p>3 か月の移行期間に、非推奨（廃止予定）の XDM フィールドパスでのデータ取り込みは継続されます。 ただし、2025 年 7 月末に、非推奨フィールドパスは完全に削除され、Adobe Experience Platform スキーマ UI に表示されなくなり、データは `mediaReporting` フィールドパスを使用してのみ送信されます。<p>2025 年 4 月 22 日（PT）より前にストリーミングメディアデータを Platform に収集するために Analytics ソースコネクタを実装したお客様は、新しいフィールドパスを使用するように既存の設定を移行する必要があります。 この移行は、2025年7月末までに完了する必要があります。移行サポートについては、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。2025年4月22日（PT）以降に Analytics ソースコネクタを実装するお客様については、アクションは必要ありません。</p> |  | 2025年4月22日（PT） |
| **ステッチ：XDM IdentityMap から永続 ID と一時 ID を取得** | この機能を活用すると、ステッチプロセスで XDM identityMap に保存されている ID を使用できるようになります。identityMap は、フィールドベースのステッチの永続 ID または一時 ID として使用するか、グラフベースのステッチの永続 ID として使用できます。identityMap に含まれる特定の名前空間またはプライマリ ID のいずれかを使用できます。詳しくは、[こちら](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap)と[こちら](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap)を参照してください |  | 2025年4月28日（PT） |
| **データビュー全体で指標とディメンションを共有** | 複数のデータビューをまたいでディメンションと指標の設定を適用できます。共有ディメンションまたは指標に対する変更は、適用可能なすべてのデータビュー全体で、そのディメンションまたは指標のすべてのインスタンスに適用されます。このインターフェイスにより、Customer Journey Analytics 管理者は、多くのデータビューが使用される場合に、コンポーネントをより簡単に管理できます。[詳細情報](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025年4月30日（PT） |
| **完全テーブルの書き出し制限の増加** | Adobeでは、[ 完全なテーブルの書き出し ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) で使用できる列の数が、5 つのディメンションと 5 つの指標から 10 のディメンションと 10 の指標に増えました。 これは、すべてのCustomer Journey Analytics層に適用されます。 書き出し可能な行数の使用権限に変更はありません。 |  | 2025年4月30日（PT） |
| **イベントの深度ディメンション** | 新しい [ イベントの深度 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) ディメンションが、データビューに必要な標準コンポーネントのリストに追加されました。 |  | 2025年5月8日（PT） |
| **完全なテーブルを書き出す場合は、マニフェストファイルを無効にします** | Analysis Workspaceから完全なテーブルを書き出す際に、デフォルトで含まれるマニフェストファイルを無効にできます。 [詳細情報](/help/analysis-workspace/export/export-cloud.md) |  | 2025年5月20日（PT） |
| **Data Insights Agent** | Data Insights Agentは、Customer Journey Analyticsの AI アシスタントの一部で、ジェネレーティブ AI コンバージョンエージェントです。 データビューと実際のデータのコンポーネントを使用して、Analysis Workspaceで関連するビジュアライゼーションを構築することで、データ中心の質問にすばやく効率的に回答します。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | 2025年5月28日（PT） |
| 倍精度浮動小数点数型のディメンションの場合、**Dimension形式のデフォルトは 2 です** | Double データタイプを持つスキーマの場合、ディメンション形式はデフォルトで小数点以下 2 桁になりました。 この数値は、小数点以下 0 ～ 5 桁まで変更できます。<p>以前は、この形式はデフォルトで小数点以下 0 桁に設定されていました。</p><p>つまり、Analysis Workspace レポートで倍精度浮動小数点数型寸法を使用している場合、デフォルトでは小数点以下の桁数は表示されません。 これらの同じレポートで、小数点以下 2 桁が表示されるようになりました。</p><p>ダブルタイプの寸法に表示される小数点以下の桁数を更新する方法について詳しくは、[ 形式コンポーネント設定 ](/help/data-views/component-settings/format.md) を参照してください。</p> | | 2025年5月29日（PT） |
| **Analysis Workspace の左パネルが開かなくなり、マウスポインターを置くと閉じる** | Analysis Workspace の左パネルを使用すると、コンポーネント、パネル、ビジュアライゼーションなどをプロジェクトに追加できます。左端のいずれかのアイコンにマウスポインターを置いて、一時的に左パネルを開くオプションは使用できなくなりました。代わりに、これらのアイコンのいずれかをクリックしてパネルを開いたままにし、同じアイコンをクリックして閉じます。 |  | 2025年6月2日（PT） <p>（当初は 2025 年 5 月 29 日にリリースする予定です）</p> |
| **Customer Journey AnalyticsB2B edition** | Customer Journey Analytics B2B editionは、売上高の増加を促す実用的なアカウントインサイトを提供することで、B2B 企業がマーケティング、セールス、製品の各チームを連携させるのに役立ちます。 アカウントがデータモデルの中心に配置されるので、すべての分析はアカウントジャーニーに焦点を当てます。 人物および時間ベースのイベントの上に新しいエンティティのレイヤー（アカウント、機会、購入グループ）を追加すると、B2B マーケティングと収益のライフサイクルの全体像が作成されます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025年6月18日（PT） |
| **Analysis Workspace プロジェクトでのコメントの追加と表示** | Analysis Workspaceの新しい [ コメント機能 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) を使用すると、Analysis Workspace プロジェクトのコンテキスト内でインサイトを共有し、質問することができます。 これにより、データに関する話し合いが合理化され、話し合うデータのコンテキスト内で会話を維持できます。 次のことが可能です。 <ul><li>アクセス権のあるAnalysis Workspace プロジェクトにコメントします</li><li>ビジュアライゼーション内の特定のポイントにコメントする、またはプロジェクトに関して一般的なコメントを作成する</li><li>他のユーザーにタグを付けて、コメントについて通知します</li><li>既存のコメントを管理（編集、ピン留め、解決など）</li></ul>Customer Journey Analytics管理者は [ 組織レベルでコメントを無効にする ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences) ことができます。 プロジェクト所有者は [ プロジェクトレベルでコメントを無効にする ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects) ことができます。 |  | 2025年6月25日（PT） <p>（当初は 2025 年 5 月 29 日にリリースする予定です）</p> |

## Customer Journey Analytics の修正点

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**オーディエンス**: AN-372343
**監査ログ**: AN-378168
**接続**: AN-373121; AN-372996
**データ削除**: AN-375450
**派生フィールド**:AN-373689; AN-377852
**書き出し場所**:AN-374167
**ジャーニーキャンバス**: AN-373319
**Report Builder**: AN-369786
**レポート**: AN-377326; AN-378051
**レポートアクティビティマネージャー**:AN-377148


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
