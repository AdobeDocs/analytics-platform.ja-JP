---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1534b628841a5b4588379b944822073f3288d710
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 79%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年6月）

**最終更新日**：2024年6月18日（PT）

このリリースノートは、2024年6月6日（PT）～2024年7月のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics 向けの AI アシスタント** | Customer Journey Analytics UI で自然言語の質問をし、Customer Journey Analytics ドキュメントに基づいて回答を得ることができます。[詳細情報](/help/ai-assistant.md) | | 2024年6月6日（PT） |
| **グラフベースのステッチ** | グラフベースのステッチを使用すると、Experience PlatformID サービスの ID グラフを使用して、次の方法でカスタマージャーニーをより詳細に把握できます。<ul><li>単一の識別子を反映するために追加のデータを抽出、変換、読み込みする必要なく、異なる識別子を持つデータセットを結合する。</li><li>データセット間で ID を共有して、単一のデータセットの優先 ID またはゴールデン ID の適用範囲を向上させる。</li><li>Real-Time Customer Data Platform と Journey Optimizer で作成したプロファイルを Customer Journey Analytics の人物と整合する。</li></ul>[詳細情報](/help/stitching/overview.md) |  | 2024年6月28日（PT） |
| **ユーザーからアカウントへの B2B スキーマ変換** | B2B データ（アカウント、商談、マーケティングリスト、キャンペーンなど）のユーザーベースのルックアップをサポートするために、B2B ルックアップデータセットを変換できます。この変換は、次のクラスに基づく B2B ルックアップスキーマのデータを含むデータセットでのみ使用できます。<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul>[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024年6月5日（PT） |
| **派生フィールド - 数学関数** | データビュー内で簡単な数学演算子を実行して、ユーザーに関する質問に回答できます。例えば、製品、保証、発送による収益を組み合わせることができます。[詳細情報](/help/data-views/derived-fields/derived-fields.md#math)</p> | | 2024年6月5日（PT） |
| **派生フィールド - Next 関数または Previous 関数** | 次の値または前の値を確認できます。例えば、選択したマーケティングチャネルの前に操作した以前のマーケティングチャネルは何でしたか？または、選択したページの前後でユーザーが操作したページは何でしたか？最も人気のあるチャネルユーザーは、店舗に出向く前にどのようなことを行いますか？ [詳細情報](/help/data-views/derived-fields/derived-fields.md#next-or-previous)</p> | | 2024年6月12日（PT） |
| **派生フィールド - Summarize 関数** | イベント、セッションおよびユーザーレベルで指標またはディメンションに集計タイプ関数を適用する機能を提供します。[詳細情報](/help/data-views/derived-fields/derived-fields.md#summarize) | | 2024年6月26日（PT） |
| **派生フィールド - 重複排除関数** | ある値が繰り返しカウントされるのを防ぐのに役立ちます。ユーザーレベルまたはセッションレベルで適用することも、ディメンションの一意の値に基づいて適用することもできます。（ドキュメントへのリンクを添付） |  | 2024年7月10日（PT） |
| **取り込みの優先順位と待ち時間** | イベントデータが 24 時間、48 時間、7 日前のいずれかに関係なく、90 分以内（SLT）に Customer Journey Analytics に取り込めるようになりました。この機能は、会社が購入した SKU パッケージによって異なります。<ul><li>CJA 優先取り込み基本：24 時間前のデータを 90 分以内に SLT 処理（CJA Foundation および CJA Select で使用可能）</li><li>CJA 優先取り込み中級：72 時間前のデータを 90 分以内に SLT 処理（CJA Prime で使用可能）</li><li>CJA 優先取り込み上級：1 週間前のデータを 90 分以内に SLT 処理（CJA Ultimate で使用可能）</li></ul> |  | 2024年6月12日（PT） |
| **書き出しと読み込みに使用されるアカウントと場所の共有** | ユーザーは、作成したアカウントと場所を組織内のすべてのユーザーに対して使用できるようになりました。アカウントと場所の所有者およびシステム管理者のみが、アカウントと場所を編集および削除できます。以前は、アカウントと場所を使用できるのは、それらを作成したユーザーのみでした。これらの設定は、ユーザーが[クラウドの書き出しアカウントを設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)し、[クラウドの書き出し場所を設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)する際に使用できます。 | 2024年6月12日（PT） | 2024 年 7 月中旬 |
| **ドロップダウンフィルターでの複数フィールドの選択** | ドロップダウンフィルターに複数のフィールドが追加されている場合、ユーザーは一度に複数のフィールドを選択できるようになりました。パネルがフィルタリングされ、選択したフィールドのいずれかが含まれます。 <p>以前は、ユーザーはドロップダウンフィルターで一度に 1 つのフィールドしか選択できませんでした。</p><p>ドロップダウンフィルターでの選択を必須にするオプションが、ドロップダウンフィルターを右クリックした際にメニューに移動されました。</p><p>以前は、ユーザーは、ドロップダウンメニューの「フィルターなし」オプションの横にある「x」をクリックできました。</p><p>詳しくは、を参照してください [静的ドロップダウンフィルター](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters) 。対象： [パネルの概要](/help/analysis-workspace/c-panels/panels.md).</p><p>[この機能のビデオデモをご覧ください](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | 2024年6月19日（PT） |
| **ワークスペースプロジェクトの目次** | プロジェクトで新しい目次を使用できるようになりました。目次には、ユーザーがプロジェクト内のパネルとビジュアライゼーション間をすばやく移動できるリンクが表示されます。 <p>目次は、すべてのプロジェクトの左側のパネルで使用できます。</p><p>詳しくは、[プロジェクトの目次](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)を参照してください。</p><p>[この機能のビデオデモをご覧ください](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | 2024年6月19日（PT） |
| **フリーフォームテーブルでのディメンション項目のハイパーリンクの作成** | 1 つ以上のディメンション項目にハイパーリンクを作成して、Analysis Workspace のフリーフォームテーブル内でクリックできるようにします。 <p>URL 値を持つディメンション項目のハイパーリンクを作成したり、URL 以外の値を持つディメンション項目のカスタム URL を作成したりできます。</p><p>変数を使用して、複数のディメンション項目の動的カスタム URL を作成できます。変数は、ディメンション項目の値や、分類ディメンションを参照できます。</p><p>詳しくは、[フリーフォームテーブルでディメンションのハイパーリンクを作成する](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)を参照してください。</p><p>[この機能のビデオデモをご覧ください](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | 2024年6月19日（PT） |
| **Adobe Journey OptimizerでのCustomer Journey Analyticsデータビューの使用** | Customer Journey Analyticsの新しい設定オプションを使用すると、手動の設定を行わなくても、Adobe Journey Optimizerで使用するCustomer Journey Analyticsデータビューを指定できます。 <p>この設定オプションを有効にする方法については、 [互換性](/help/data-views/create-dataview.md#compatibility) のセクション [データビューの作成または編集](/help/data-views/create-dataview.md).</p><p>以前は、Journey Optimizer データをCustomer Journey Analyticsで表示する際に、接続ビューとデータビューを手動で設定する必要がありました。</p> |  | 2024年6月19日（PT） |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをよりすばやく見つけることができます。</li></ul> <p>（ドキュメントへのリンクを添付）</p> |  | 2024年7月14日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-345454、AN-349816、AN-349905、AN-350617

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

{style="table-layout:auto"}

## 関連リソース

* [2024年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2024.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Streaming Media Collection アドオンのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
