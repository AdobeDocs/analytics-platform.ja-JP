---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 61209c4f86052059ab2f1ef3a3d68e9c16f8e621
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 37%

---

# 最新のAdobe Customer Journey Analytics リリースノート（2024 年 6 月）

**最終更新日**：2024年6月12日（PT）

これらのリリースノートは、2024 年 6 月 6 日（PT）から 2024 年 7 月までのリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics 向けの AI アシスタント** | Customer Journey Analytics UI で自然言語の質問をし、Customer Journey Analytics ドキュメントに基づいて回答を得ることができます。[詳細情報](/help/ai-assistant.md) | | 2024年6月6日（PT） |
| **グラフベースのステッチ：UIS グラフの書き出しを使用したステッチ** | グラフベースのステッチを使用すると、ID グラフを使用して、次の方法でカスタマージャーニーをより詳細に把握できます。<ul><li>追加データを抽出、変換、読み込んで単一の識別子を反映することなく、異なる識別子を持つデータセットを結合する。</li><li>データセット間で ID を共有することで、単一のデータセットの優先 ID またはゴールデン ID のカバレッジを向上させます。</li><li>Real-time Customer Data PlatformおよびJourney Optimizerで作成されたプロファイルとCustomer Journey Analytics内のユーザーを一致させる。</li></ul>（ドキュメントへのリンクを添付） |  | 2024年6月28日（PT） |
| **ユーザーからアカウントへの B2B スキーマ変換** | B2B データ（アカウント、商談、マーケティングリスト、キャンペーンを含む）に対するユーザーベースの検索をサポートするために、B2B ルックアップデータセットを変換できます。 この変換は、次のクラスに基づく、B2B ルックアップスキーマのデータを含むデータセットに対してのみ使用できます。<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul>[詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024年6月5日（PT） |
| **派生フィールド - 数学関数** | データビュー内で簡単な数学演算子を実行して、ユーザーに関する質問に回答できます。例えば、製品、保証、発送による収益を組み合わせることができます。 <p>[詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 2024年6月5日（PT） |
| **派生フィールド – 派生フィールド - Next または Previous 関数** | 次または前の値を確認できます。 例えば、選択したマーケティングチャネルの前に操作した以前のマーケティングチャネルは何でしたか？ または、選択したページの前後でユーザーが操作したページは何でしたか？ 最も人気のあるチャネルユーザーは、店舗に出向く前にどのようなことを行いますか？ <p>[詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 2024年6月12日（PT） |
| **派生フィールド – 概要関数** | イベント、セッションおよびユーザーレベルで指標またはディメンションに集計タイプ関数を適用する機能を提供します。 （ドキュメントへのリンクを添付） | | 2024年6月26日（PT） |
| **派生フィールド – 重複排除機能** | 値が繰り返しカウントされるのを防ぐのに役立ちます。 ユーザーレベルまたはセッションレベルで適用することも、ディメンションの一意の値に基づいて適用することもできます。 （ドキュメントへのリンクを添付） |  | 2024年6月26日（PT） |
| **取り込みの優先順位と待ち時間** | イベントデータが 24 時間、48 時間、7 日前のいずれであっても、90 分以内（SLT）にCustomer Journey Analyticsでイベントデータを取り込めるようになりました。 この機能は、会社が購入した SKU パッケージによって異なることに注意してください。<ul><li>CJA 優先取り込み基本：90 分 SLT 処理中の 24 時間前のデータ（CJA 基盤および CJA セレクトで利用可能）</li><li>CJA 優先取り込み中級：90 分 SLT 処理中の 72 時間前のデータ（CJA プライムで使用可能）</li><li>CJA の優先取り込みの詳細設定：90 分 SLT 処理中の 1 週間の古いデータ（CJA Ultimate で利用可能）</li></ul> |  | 2024年6月12日（PT） |
| **書き出しと読み込みに使用されるアカウントと場所の共有** | ユーザーは、作成したアカウントと場所を組織内のすべてのユーザーに対して使用できるようになりました。アカウントと場所の所有者およびシステム管理者のみが、アカウントと場所を編集および削除できます。 以前は、アカウントと場所は、それらを作成したユーザーのみが使用できました。 これらの設定は、ユーザーが次の場合に使用できます [クラウド書き出しアカウントの設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) および [クラウドの書き出し場所の設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 2024年6月12日（PT） | 2024年6月18日（PT） |
| **フリーフォームテーブルのドロップダウンメニューで複数のフィルターを使用できる場合は、選択します** | 複数のフィルターがドロップダウンメニューとしてフリーフォームテーブルに追加された場合、フリーフォームテーブルのユーザーは一度に複数のフィルターを選択できるようになりました。 フリーフォームテーブルがフィルタリングされ、選択したフィルターのいずれかが含まれます。 <p>以前は、ユーザーはフィルタードロップダウンメニューで一度に 1 つのフィルターのみを選択できました。</p><p>（フォローするためのドキュメントリンク。）<!--For more information, see "Add filters to a project" in "Use components in Analysis Workspace."--> |  | 2024年6月19日（PT） |
| **ワークスペースプロジェクトの目次** | プロジェクトで新しい目次が使用できるようになりました。 目次には、プロジェクト内のパネルやビジュアライゼーションにすばやくジャンプできるリンクがあります。 <p>目次は、個々のプロジェクトに対して、または特定のユーザーのすべてのプロジェクトに対して有効にできます。</p><p>（フォローするためのドキュメントリンク。）<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | 2024年6月19日（PT） |
| **フリーフォームテーブルでのディメンション項目のハイパーリンクの作成** | 1 つ以上のディメンション項目にハイパーリンクを作成して、Analysis Workspaceのフリーフォームテーブル内でクリックできるようにします。 <p>URL 値を持つディメンション項目のハイパーリンクを作成したり、非 URL 値を持つディメンション項目のカスタム URL を作成したりできます。</p><p>変数を使用して、複数のディメンション項目の動的カスタム URL を作成できます。 変数は、ディメンション項目の値を参照することも、分類ディメンションを参照することもできます。</p><p>（フォローするためのドキュメントリンク。）<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | 2024年6月19日（PT） |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Adobe Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。<p>以前は、Customer Journey Analytics から公開されたオーディエンスは、Experience Platform の「セグメント」セクションで使用できました。</p><p>この改善によるメリットは次のとおりです。</p><ul><li>オーディエンスが Experience Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Experience Platform で並べ替えることができます。</li><li>Experience Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをよりすばやく見つけることができます。</li></ul> <p>（ドキュメントへのリンクを添付）</p> |  | 2024年7月14日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-345454; AN-349816; AN-349905; AN-350617

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

{style="table-layout:auto"}

## 関連リソース

* [2024年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2024.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
