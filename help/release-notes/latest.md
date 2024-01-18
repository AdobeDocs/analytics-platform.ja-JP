---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: efae6138159820414004a21de7c05b4373257876
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 31%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2024 年 1 月）

**最終更新日**：2024年1月12日

これらのリリースノートでは、2023 年 10 月末から 2024 年 1 月までのリリース期間を扱っています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **ガイド付き分析 — 定着率** | 目的の日付範囲内での最初のエンゲージメント後に再来訪するユーザーの割合を示す新しい表示タイプ。 [詳細情報](../guided-analysis/types/retention-rates.md) | 該当なし | 2024年1月8日（PT） |
| **時系列予測** | 予測は、標準指標または計算指標を、サポートされている任意の時間精度（時間単位、日単位、週単位、月単位、年単位）で予測する新しいAnalysis Workspace機能です。 | 該当なし | 2024年1月31日（PT） |
| **ガイド付き分析 — 近似曲線** | トレンドラインオーバーレイを [使用状況](/help/guided-analysis/types/usage.md) 表示を使用します。これは、データでより明確なパターンを表現するのに役立ちます。 | 該当なし | 2024年1月17日（PT） |
| **接続の詳細ページ — スキップされたレコード** | 接続の定義の一環としてレコードがスキップされた理由を調べることができるようになりました。 [詳細情報](../connections/manage-connections.md) | 該当なし | 2024年1月31日（PT） |
| **主要指標の概要ビジュアライゼーションの更新** | 主要指標の概要ビジュアライゼーションを使用する場合、選択した比較日付範囲オプションが主日付範囲に対するものか固定のものかに応じて、比較日付範囲が自動的に更新されるようになりました。 [詳細情報](/help/analysis-workspace/visualizations/key-metric.md)。 | 該当なし | 2024年1月17日（PT） |
| **ガイド付き分析 — ストリーム** | 個々のユーザーイベントストリームを参照できる新しいビュータイプ。 この分析により、エクスペリエンスのパターンを見つけ、より優れたユーザーストーリーを示すことができます。 | 該当なし | 2024年1月31日（PT） |
| **ガイド付き分析 — クエリレールの改善** | 一部のコンポーネント設定がクエリレールに含まれ、使いやすさが向上しました。 | 該当なし | 2024年1月31日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-310972; AN-332774; AN-332793; AN-332796; AN-333157; AN-334067; AN-334134; AN-334968; AN-335315; AN-335518; AN-335533; AN-335736;

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| AdobeAPI オブジェクトメンバーの追加 | 2024年1月17日（PT） | Adobeは、オプションの要求および応答メンバー（名前と値のペア）を既存の API オブジェクトに追加できますが、バージョン管理に関する通知や変更はありません。 このような追加は、実装に対する重大でない変更である必要があります。 Adobeでは、わからない場合に処理時に追加内容が無視されるように、API と統合するサードパーティツールの API ドキュメントを参照することをお勧めします。 Adobeは、リリースノートから標準通知を受け取らない限り、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |

{style="table-layout:auto"}

## 関連リソース

* [2023年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
