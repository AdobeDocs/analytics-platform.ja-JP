---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b313600ff215dea5a869e5a6125120a64f50235b
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 27%

---

# 最新の Customer Journey Analytics（CJA）リリースノート（2023年5月）

**最終更新日**：2023年5月8日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 主な機能と更新

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非実稼動用サンドボックスのバックフィル** | 非実稼働用サンドボックスで Analytics ソースコネクタのデータフローを作成する場合、非実稼働用サンドボックスでのバックフィルは 3 か月に制限されます。 実稼働用サンドボックスの場合、13 か月間の状態が保たれます。 | 該当なし | 2023年4月26日（PT） |
| **プロジェクトのリンク共有（ログインは不要）** | Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。 これには、組織外のユーザーや、組織内でAdobe Analytics用にプロビジョニングされていないユーザーとの共有が含まれます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>この機能はデフォルトで有効になっており、システム管理者が無効にできます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023 年 5 月 4 日 | 2023年6月 |
| **Analytics ダッシュボードアプリ（モバイルアプリ）のホーム画面を更新しました** | 新しく更新されたホーム画面では、1 つの統合スコアカードリストにすべてのスコアカードを表示できます。  1 回のログインで複数の組織にアクセスできる場合、組織のすべてのスコアカードを 1 つのリストで使用できます。 | 該当なし | 2023 年 5 月 11 日 |
| **派生フィールド** | これは、派生フィールドの最初のリリースを表します。 派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。 さらに、派生フィールドをデータビューのコンポーネント（指標またはディメンション）として定義し、その派生フィールドを Workspace のコンポーネントとして使用することができます。<p>このリリースでは、マーケティングチャネルテンプレートと次の機能がサポートされています。</p><ul><li>連結</li><li>Case When</li><li>検索と置換</li><li>ルックアップ</li><li>URL の解析</li></ul> <p>[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023 年 5 月 11 日 | 未定 |
| **CJA のReport Builder — セルからのデータビューの選択** | この機能を使用すると、ユーザーはセルからデータブロックのデータビューを選択できます。 これは、ブックを作成し、同様のデータ構造を持つ複数のデータビューがあり、異なるデータビューで複数回ブックを再利用する場合に便利です。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 該当なし | 2023 年 5 月 24 日 |
| **Analysis Workspaceでのコンポーネントの並べ替え** | <p>左側のパネルまたはAnalysis Workspaceのデータディクショナリでコンポーネントを表示する際に、新しい「並べ替え」オプションを使用できるようになりました。 コンポーネントは、「推奨」（最も一般的に使用されるコンポーネント）、「アルファベット順」（アルファベット順）または「分類」（タイプ）で並べ替えることができます。</p><p>以前は、コンポーネントの検索またはフィルタリングのみおこなえました。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | 該当なし | 2023 年 5 月 11 日 |
| **フリーフォームテーブルからの動的ディメンションを含む行の削除** | Analysis Workspaceのフリーフォームテーブルで、x アイコンを使用して、動的ディメンションを含む特定の行をすばやく削除できるようになりました。 その際、「等しくない」フィルタールールが自動的に適用されます。<p>以前は、動的ディメンションを含む行を削除する唯一の方法は、フィルターダイアログでルールを手動で作成することでした。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | 該当なし | 2023 年 5 月 11 日 |
| **パネル内にビジュアライゼーションを追加する新しいボタン** | Analysis Workspaceの各パネルの下部に新しいボタンが表示され、ビジュアライゼーションをすばやく追加できるようになりました。 <p>以前は、パネルにビジュアライゼーションを追加する唯一の方法は、左側のパネルからビジュアライゼーションをドラッグしたり、既存のビジュアライゼーションを複製またはコピーしたり、空のパネルを作成したりすることでした。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#quick-viz)</p> | 該当なし | 2023 年 5 月 18 日 |
| **ディープリンク（モバイルアプリ）** | ユーザーがスコアカードへのリンクを送信して、そのリンクをアプリのスコアカードプロジェクトに直接導くことを許可します。 これにより、プロジェクトを共有し、技術的でないオーディエンスからのエンゲージメントを促進する作業がさらに簡単になります。 | 該当なし | 2023 年 5 月 18 日 |
| **インテリジェントキャプション** | Line ビジュアライゼーションの自然言語の概要を使用して、ユーザー向けのストーリーテリングを強化します。 | 2023 年 5 月 18 日 | 2023 年 6 月 2 日 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-316412;AN-317105;AN-318122;AN-317353

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | 該当なし | 該当なし |

{style="table-layout:auto"}

## 関連リソース

* [2023年の以前の CJA リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
