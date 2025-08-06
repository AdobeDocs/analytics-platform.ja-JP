---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 379cf7af9bf6722fd483a9c0639fc6b294c398a4
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 81%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年7月）

**最終更新日**：2025年7月22日（PT）


このリリースノートは、2025年7月11日～2025年8月15日（PT）のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace プロジェクトでのコメントの追加と表示** | Analysis Workspace の新しい[コメント機能](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)を使用すると、Analysis Workspace プロジェクトのコンテキスト内でインサイトを共有し質問をすることができます。これにより、データに関する議論を効率化して、議論の対象となっているデータのコンテキスト内に会話を維持できます。次のことが可能です。 <ul><li>自身がアクセス権を持っている Analysis Workspace プロジェクトにコメントする</li><li>ビジュアライゼーション内の特定のポイントにコメントする、またはプロジェクトに関する一般的なコメントをする</li><li>他のユーザーにタグを付けて、コメントについて通知する</li><li>既存のコメントを管理する（編集、ピン留め、解決など）</li></ul>Customer Journey Analytics 管理者は[組織レベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)ことができます。プロジェクト所有者は[プロジェクトレベルでコメントを無効にする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)ことができます。 | 2025年6月25日（PT） | 2025年7月22日（PT） <p>（以前は2025年5月29日（PT））</p> |
| **PDF としてダウンロードしたプロジェクトは、ワークステーションにダウンロードされます** | プロジェクトを PDFとしてダウンロードすると、その PDF はワークステーションのダウンロードフォルダーにダウンロードされます。 以前は、プロジェクトを PDFとしてダウンロードすると、一意の URL を持つ PDF が新しいブラウザータブに表示されていました。 （ドキュメントへのリンクを添付） | | 2025年8月25日（PT） |
| **派生フィールド - 日付計算関数** | [ 日付計算 ](/help/data-views/derived-fields/derived-fields.md#date-math) 派生フィールド関数には、2 つの日付フィールドまたは日時フィールドの違いを返す機能があります。 | 2025年8月4日（PT） | 2025年8月8日（PT） |
| **派生フィールド - Depth 関数** | [Depth](/help/data-views/derived-fields/derived-fields.md#depth) 派生フィールド関数は、標準提供のイベント深度ディメンションで可能なものと同様に、フィールドの深度を返す機能を提供します。 | 2025年8月4日（PT） | 2025年8月8日（PT） |
| **派生フィールド - 型キャスト関数** | [Typecast](/help/data-views/derived-fields/derived-fields.md#typecast) 派生フィールド関数を使用すると、フィールド型をその場で変更し、Customer Journey Analytics内でそのフィールドを他の変換に使用できるようになります。 | 2025年8月4日（PT） | 2025年8月8日（PT） |

## Customer Journey Analytics の修正点

**Analysis Workspace**：AN-387014; AN-387500
**コンポーネント**：AN-387293
**コンテンツ分析**：AN-387595
**ガイド付き分析**：AN-382273
**Report Builder**：AN-382775
**レポート**：AN-382020、AN-387827
**セグメント化**：AN-382102
**共有指標およびディメンション**：AN-378451


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
