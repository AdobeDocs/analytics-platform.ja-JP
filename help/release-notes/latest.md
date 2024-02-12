---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9f60d83673591aebeffeb6442bf9f8b897ab2f20
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 95%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年1月）

**最終更新日**：2024年1月30日（PT）

このリリースノートは、2024年1月8日～2024年2月13日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **スキップされたレコードの詳細** | 接続の設定時にレコードがスキップされた理由の詳細を取得できます。 詳しくは、 [接続の詳細](../connections/manage-connections.md#connection-details) を参照してください。 | 2024年2月5日（PT） | 2024年2月5日（PT） |
| **時系列予測** | [予測](../analysis-workspace/c-forecast/forecasting.md)は、標準指標または計算指標を、フリーフォームテーブルと折れ線グラフに対してサポートされている任意の時間精度（時間単位、日単位、週単位、月単位、年単位）で予測する新しい Analysis Workspace 機能です。 | 2024年1月31日（PT） | 2024年2月21日（PT） |
| **主要指標の概要ビジュアライゼーションの更新** | 主要指標の概要ビジュアライゼーションを使用する際、選択した比較日付範囲オプションが主な日付範囲に対して相対的であるか固定であるかに応じて、比較日付範囲が自動的に更新されるようになりました。[詳細情報](/help/analysis-workspace/visualizations/key-metric.md)。 | 該当なし | 2024年1月17日（PT） |
| **Adobe Product Analytics - リテンション率分析** | リテンション率は、ユーザーの継続的な再来訪習慣を測定できる新しいガイド付き分析です。[詳細情報](../guided-analysis/types/retention-rates.md) | 該当なし | 2024年1月8日（PT） |
| **Adobe Product Analytics - トレンドラインオーバーレイ** | トレンドラインは、[使用状況トレンド](/help/guided-analysis/types/usage.md)ビューで使用できる新しいオーバーレイ設定で、データのより明確なパターンを示すのに役立ちます。 | 該当なし | 2024年1月17日（PT） |
| **Adobe Product Analytics - クエリパネルの機能強化** | ガイド付き分析では、左側のクエリパネルに、以前はビジュアライゼーション設定で使用できた、ビュータイプとカウント方法設定が含まれるようになりました。 | 該当なし | 2024年1月31日（PT） |
| **Adobe Product Analytics - ユーザーストリーム分析** | ユーザーストリームは、個々のユーザーイベントストリームを探索できる新しいガイド付き分析で、エクスペリエンスパターンを検索し、より良いユーザーストーリーを伝えるのに役立ちます。 | 該当なし | 2024年2月7日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-310972、AN-332774、AN-332793、AN-332796、AN-333157、AN-334067、AN-334134、AN-334968、AN-335315、AN-335518、AN-335533、AN-335736、

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| Adobe API オブジェクトメンバーの追加 | 2024年1月17日（PT） | アドビでは、バージョン管理の通知や変更なしに、オプションのリクエストおよび応答メンバー（名前／値のペア）を既存の API オブジェクトに追加する場合があります。このような追加は、実装に対して重大な変更ではありません。アドビでは、理解できない場合は、このような追加が処理中に無視されるように、API と統合するサードパーティツールの API ドキュメントを参照することをお勧めします。アドビでは、最初にリリースノートを通じて標準通知を提供することなく、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |

{style="table-layout:auto"}

## 関連リソース

* [2023年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
