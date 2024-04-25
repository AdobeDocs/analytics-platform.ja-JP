---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: abaa747934ff2cdd0a3dab867165afb46fbc71db
workflow-type: ht
source-wordcount: '945'
ht-degree: 100%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年4月）

**最終更新日**：2024年4月17日（PT）

このリリースノートは、2024年4月10日（PT）～2024年5月のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **ストリーミングメディア：Adobe Experience Platform Edge への Roku データの送信** | [Experience Platform Edge を使用して Media Analytics をインストール](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)する際、Adobe Experience Platform Roku SDK を使用してストリーミングメディアデータを Adobe Experience Platform に送信できるようになりました。 |  | 2024年4月12日（PT） |
| **レポートアクティビティマネージャーで公開した月別レポート** | レポートアクティビティマネージャーですべての接続のレポートアクティビティを表示すると、今月と前月の両方で IMS 組織レベルで実行した[月別レポート／リクエスト](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites)を示すグラフが表示されるようになりました。<p>**メモ：** データは、2024年3月中旬から利用可能です。 | | 2024年4月15日（PT） |
| **モバイルスコアカードのインテリジェントキャプション** | [インテリジェントキャプション](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)は、アナリスト以外のユーザーがアナリストの助けを借りずにデータをより深く理解するのに役立ちます。これが Customer Journey Analytics スコアカードで使用できるようになりました。 |  | 2024年4月17日（PT） |
| **プロジェクト専用の[!UICONTROL ワークスペース]コンポーネントの権限の強化** | 以前は、あるユーザー（ユーザー A）が別のユーザー（ユーザー B）とプロジェクトを共有し、ユーザー B にプロジェクトへの編集アクセス権を付与した場合、ユーザー B はプロジェクトを編集できました。ただし、ユーザー B はプロジェクトに埋め込まれた[!UICONTROL クイックセグメント]を編集できませんでした。この制限は現在削除され、ユーザー B は共有プロジェクトに埋め込まれている[!UICONTROL クイックセグメント]や他のプロジェクト専用コンポーネントを編集できるようになりました。 |  | 2024年4月17日（PT） |
| **管理者は組織内のすべての場所を管理できます** | [場所ページ](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/locations-manager)の新しいオプションにより、管理者は組織内のすべての場所を表示および管理できます。以前は、管理者は作成した場所のみを表示および管理できました。 |  | 2024年4月17日（PT） |
| **Adobe Product Analytics：機能マトリックス** | お客様のコア機能、強力な機能、1 回限りの機能、疑わしい機能が何であるかを理解することで、投資に関する意思決定を促進します。[!UICONTROL 機能マトリックス]では、イベントを使用頻度とアクティブユーザーの割合で測定し、使用量の中央値と比較します。 | 2024年4月17日（PT） | 2024年4月30日（PT） |
| **Adobe Product Analytics：ファネルのインサイトの強化** | [フリクション](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/guided-analysis/funnel/friction)ビューでは、グラフとテーブルをさらに理解しやすくするために、カテゴリ、差分、説明を含めるようにドキュメント化されたインサイトが強化されました。 | 2024年4月17日（PT） | 2024年4月26日（PT） |
| **Adobe Product Analytics：リテンションビューの強化** | [リテンション](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/guided-analysis/retention/retention-rates)率ビューに次のいくつかの機能が追加され、より詳細にカスタマイズ可能なリテンションのインサイトが得らるようになりました。<ul><li>開始および再来訪イベントをリンク解除</li><li>1 つのビューで複数のリターンイベントを比較</li><li>設定時または設定後（無制限）、各設定（制限付き）およびブラケット設定で適用されるリテンションモデルをカスタマイズ</li><li>グラフ内の個々のコホート行を表示／非表示</li></ul> | 2024年4月24日（PT） | 2024年5月8日（PT） |
| **Adobe Product Analytics：1 つのファネルステップ内のイベントを比較** | [フリクション](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/guided-analysis/funnel/friction)ビューで、1 つのファネルステップ内のイベントを比較できるようになりました。ジャーニーにステップオプションがある場合や、A/B 実験が実行されるステップがある場合に特に便利です。 | 2024年4月23日（PT） | 2024年5月3日（PT） |
| **ユーザーからアカウントへの B2B スキーマ変換** | データセットを変換すると、Customer Journey Analytics B2B レポートシナリオにおけるユーザーベースのルックアップをより適切にサポートできます。この機能は、次のクラスに基づく B2B スキーマのデータセットで使用できます。<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul> | | 2024年5月1日（PT） |
| **Experience Edge ボット検出** | [ボット検出](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ja)を使用すると、Web SDK、Mobile SDK、Server API で生成されたイベントが、既知のスパイダーやボットで生成されたものとして識別できます。 | | 2024年5月1日（PT） |
| **派生フィールド：Next 関数または Previous 関数** | これらの新機能により、フィールドを入力として取得し、n 個前または n 個後の値を識別して、ユーザージャーニーをより詳細に把握できるようになります。また、この機能を、[!UICONTROL 派生フィールド]の他の関数（[!UICONTROL Concatenate] など）と組み合わせて、新しいディメンションを作成することもできます。 |  | 2024年5月1日（PT） |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをよりすばやく見つけることができます。</li></ul> |  | 2024年5月 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-319662、AN-337894、AN-338469、AN-340147、AN-340200、AN-340443、AN-341594、AN-342442、AN-342976、AN-343020、AN-343469、AN-343703、AN-343938、AN-344614、AN-344677、

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
