---
title: 現在の Customer Journey Analytics リリースノート
description: 最新のCustomer Journey Analyticsリリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: eff900722dc06d3bb272d1143c0e2344855e3c5c
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 29%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年1月）

**最終更新日**：2025年1月22日（PT）

これらのリリースノートは、2024 年 10 月 23 日（PT）から 2025 年 1 月 30 日（PT）までのリリース期間に対応しています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新された接続の使用状況エクスペリエンス** | 接続の **[!UICONTROL 使用状況]** タブに、次のレポート可能な行タイプの拡張ビジュアライゼーションが提供されるようになりました。コア、取り込んだデータ、履歴データです。 また、使用状況データを接続別、データセット別、サンドボックス別またはタグ別に表示して分類することもできます。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | 2025年1月15日（PT） |
| **Adobe Analytics プロジェクトと含まれているすべてのコンポーネントをCustomer Journey Analyticsに移行するための API** | Adobe Analytics プロジェクトと含まれるコンポーネントをCustomer Journey Analyticsに移行するための API が使用できるようになりました。 以前は、プロジェクトとコンポーネントの移行は、ユーザーインターフェイスからのみ行えます。 [詳細情報](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs). ドロップダウンから **CJA 移行 API** を選択します。 |  | 2025年1月15日（PT） |
| **Journey OptimizerのレポートページでCustomer Journey Analyticsのカスタムテンプレートを使用する** | Adobe Journey Optimizerのレポートページで使用するテンプレートをCustomer Journey Analyticsで作成または編集し、新しいレポートインターフェイスをカスタマイズできるようになりました。Journey Optimizer 以前は、Adobe Journey Optimizerの新しいレポートインターフェイスをカスタマイズできませんでした。 <p>詳しくは、「テンプレートの作成と管理 [ の「テンプレートの作成」または「テンプレートの編集または削除 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/create-templates) を参照してください。  |  | 2025年1月15日（PT） |
| **Analysis Workspaceのテンプレート** | テンプレートをCustomer Journey Analyticsで使用できるようになりました。<ul><li>**事前定義済みテンプレート**：様々な事前定義済みテンプレートを使用できます。 これらのテンプレートを使用すると、最も一般的なレポートシナリオに関する迅速なインサイトを得ることができます。 事前定義済みのテンプレートをそのまま使用できます。 または、プロジェクトの出発点として使用し、特定の目的に合わせてカスタマイズすることもできます。 [詳細情報](/help/analysis-workspace/templates/use-templates.md)</li><li>**会社テンプレート**：管理者は、組織に固有のユースケースのニーズを満たす会社テンプレートを作成できます。 管理者が作成する会社テンプレートは、組織内のユーザーが使用できます。 [詳細情報](/help/analysis-workspace/templates/create-templates.md)</li></ul> | 15年1月 | 2025年1月30日（PT） |
| **製品の使用状況** | 組織が Customer Journey Analytics をどのように使用しているかを確認します。この機能を有効にすると、組織内のユーザーが Analysis Workspace を使用する際に、データを収集するデータセットが Adobe Experience Platform に作成されます。また、接続とデータビューも自動的に作成され、プロジェクトで使用される上位のプロジェクトタイプ、最もアクティブなユーザー、一番人気のコンポーネントなどのディメンションにアクセスできます。[詳細情報](/help/tools/product-usage/usage-overview.md) | 2024年10月23日（PT） | 2025年1月22日（PT） |
| **インテリジェントキャプション v2** | 複数行、棒グラフ、横棒グラフ、ドーナツ、領域、フロー、フォールアウトのビジュアライゼーションでインテリジェントキャプションがサポートされるようになりました。 拡張ビューで、すべてのインテリジェントキャプションを一度に表示するか、個々のインテリジェントキャプションを 1 つずつ表示するかを選択できます。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 2025年1月22日（PT） |
| **ガイド付き分析内からプロジェクトにガイド付き分析を追加する** | ガイド付き分析内からWorkspace プロジェクトにガイド付き分析を追加できます。 また、ガイド付き分析をAnalysis Workspaceに直接追加することもできます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/guided-analysis/overview) |  | 2025年1月22日（PT） |
| **Media Collection：新しい Media レポート XDM 用のAdobeSource コネクタの更新** | Analytics Source コネクタは、Adobe Analyticsのストリーミングメディアデータを、Web SDKで使用されるフィールドと同じフィールドに自動的にマッピングします。 現在、データは古い場所と新しい場所の両方にマッピングされていますが、今後は新しい場所のみが使用されます。 （ドキュメントへのリンクを添付） |  | 2025年1月30日（PT） |

## Customer Journey Analytics の修正点

アラート：AN-363263、AN-364880、AN-365029、AN-365960
オーディエンス：AN-362564; AN-363254;
データ取り込み：AN-362359; AN-362751
データビュー：AN-362089; AN-365213; AN-365770; AN-366171
派生フィールド：AN-359711; AN-362496
書き出し場所：AN-363999
テーブル全体の書き出し：AN-363055
Report Builder: AN-362937
Workspace: AN-359012; AN-359145; AN-359914; AN-361455; AN-361934; AN-362469; AN-363460; AN-364714; AN-364918; AN-366277;


## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | | |

## 関連リソース

* [2024年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2024.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
