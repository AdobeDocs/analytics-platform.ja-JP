---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9c89f05c85ce7232bece6de08efbab222d51a644
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 48%

---

# 最新のAdobe Customer Journey Analytics リリースノート（2024 年 4 月）

**最終更新日**：2024年4月17日（PT）

これらのリリースノートは、2024 年 4 月 10 日（PT）から 2024 年 5 月のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **ストリーミングメディア：Adobe Experience Platform Edge への Roku データの送信** | 次の場合 [media Analytics とExperience Platform Edge のインストール](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)Adobe Experience Platform Roku SDK を使用すると、ストリーミングメディアデータをAdobe Experience Platformに送信できます。 |  | 2024年4月12日（PT） |
| **レポートアクティビティマネージャーで公開された月次レポート** | レポートアクティビティマネージャーですべての接続のレポートアクティビティを表示すると、を表示するグラフが利用できるようになりました [月次レポート/リクエスト](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) 今月と先月の両方について、IMS 組織レベルで実行された<p>**注意：** データは、2024 年 3 月の中旬から利用可能です。 | | 2024年4月15日（PT） |
| **モバイルスコアカードのインテリジェントキャプション** | [インテリジェントキャプション](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)は、アナリスト以外のユーザーがアナリストの助けを借りずにデータをより深く理解するのに役立ちます。これが Customer Journey Analytics スコアカードで使用できるようになりました。 |  | 2024年4月17日（PT） |
| **プロジェクトのみの権限強化 [!UICONTROL ワークスペース] components** | 以前は、あるユーザー（ユーザー A）が別のユーザー（ユーザー B）とプロジェクトを共有し、ユーザー B にそのプロジェクトへの編集アクセス権を付与した場合、ユーザー B はプロジェクトを編集できます。 ただし、ユーザー B はを編集できません [!UICONTROL クイックセグメント] プロジェクトに埋め込まれています。 この制限は削除されました – ユーザー B は編集できます [!UICONTROL クイックセグメント] および共有プロジェクトに埋め込まれた、その他のプロジェクト専用コンポーネント。 |  | 2024年4月17日（PT） |
| **管理者は組織内のすべての場所を管理できます** | の新しいオプション [場所ページ](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) を使用すると、管理者は組織内のすべての場所を表示および管理できます。 以前は、管理者は作成した場所のみを表示および管理できました。 |  | 2024年4月17日（PT） |
| **Adobe Product Analytics：機能マトリックス** | お客様のコア、機能、1 回限りの機能、および疑問の残る機能を理解することにより、投資に関する意思決定を促進します。 [!UICONTROL 機能マトリックス] は、アクティブユーザーの % に対する使用頻度別にイベントを測定し、使用中央値と比較します。 | 2024年4月17日（PT） | 2024年4月30日（PT） |
| **Adobe Product Analytics：ファネルのインサイトの強化** | が含まれる [摩擦](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 表示に関するインサイトが強化され、カテゴリ、差分および説明が追加されて、グラフとテーブルがよりわかりやすくなりました。 | 2024年4月17日（PT） | 2024年4月26日（PT） |
| **Adobe Product Analytics：リテンション・ビューの強化** | いくつかの機能が「」に追加されました [保持](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) レート表示により、より深くカスタマイズ可能な保持インサイトを引き出すことができます。<ul><li>開始および再来訪イベントをリンク解除</li><li>単一ビューでの複数のリターンイベントの比較</li><li>各（境界付き）および括弧で囲まれた設定で、on または after （境界付きなし）で適用される保持モデルをカスタマイズします</li><li>グラフ内の個々のコホート行の表示/非表示</li></ul> | 2024年4月10日（PT） | 2024年4月26日（PT） |
| **Adobe Product Analytics：1 つのファネルステップ内のイベントを比較** | で、1 つのファネルステップ内のイベントを比較できるようになりました [摩擦](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 表示。 ジャーニーにステップオプションがある場合や、A/B 実験が実行されるステップがある場合に特に便利です。 | 2024年4月12日（PT） | 2024年4月26日（PT） |
| **ユーザーからアカウントへの B2B スキーマ変換** | データセットを変換すると、Customer Journey Analytics B2B レポートシナリオにおけるユーザーベースのルックアップをより適切にサポートできます。この機能は、次のクラスに基づく B2B スキーマのデータセットで使用できます。<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul> | | 2024年5月1日（PT） |
| **Experience Edge ボット検出** | [ボット検出](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ja)を使用すると、Web SDK、Mobile SDK、Server API で生成されたイベントが、既知のスパイダーやボットで生成されたものとして識別できます。 | | 2024年5月1日（PT） |
| **派生フィールド：Next 関数または Previous 関数** | これらの新機能により、フィールドを入力として取得し、n-previous 値または n-next 値を識別することで、ユーザージャーニーをより詳細に把握できるようになります。 この機能は、の他の機能と組み合わせることもできます [!UICONTROL 派生フィールド]（例：） [!UICONTROL 連結]新しいディメンションを作成します。 |  | 2024年5月1日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN-342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-344677;

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **データビューと接続 UI のリンクを更新しました** | 2月15日 | 3 月初旬に、アドビは Customer Journey Analytics 製品のユーザーインターフェイスで、次のリンクを更新する予定です。ブックマークを必要に応じて更新してください。<ul><li>**データビューページ、データビューマネージャー**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**新しいデータビューを作成**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**データビューを編集**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88)／[新しいリンク](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**接続マネージャー**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**接続情報**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**接続を編集**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**新しい接続を作成**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## 関連リソース

* [2024年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2024.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
