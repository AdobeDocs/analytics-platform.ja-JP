---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 806bcaa72479c3e871e12fd1c4802bac97eda439
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 100%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2025年1月）

**最終更新日**：2025年1月22日（PT）

このリリースノートは、2024年10月23日～2025年1月30日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **接続の使用状況エクスペリエンスの更新** | 接続の「**[!UICONTROL 使用状況]**」タブでは、コアデータ、取り込まれたデータ、履歴データなどのレポート可能な行数のビジュアライゼーションが強化されました。また、接続別、データセット別、サンドボックス別、タグ別に使用状況データを表示して分類することもできます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | 2025年1月15日（PT） |
| **Adobe Analytics プロジェクトと含まれるコンポーネントを Customer Journey Analytics に移行する API** | Adobe Analytics プロジェクトと含まれるコンポーネントを Customer Journey Analytics に移行する API が使用できるようになりました。以前は、プロジェクトとコンポーネントの移行は、ユーザーインターフェイスを通じてのみ行うことができました。[詳細情報](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs)。ドロップダウンから「**CJA 移行 API**」を選択します。 |  | 2025年1月15日（PT） |
| **Journey Optimizer のレポートページでの Customer Journey Analytics のカスタムテンプレートの使用** | Customer Journey Analytics でテンプレートを作成または編集し、Journey Optimizer のレポートページで使用するテンプレートを保存して、Adobe Journey Optimizer の新しいレポートインターフェイスをカスタマイズできるようになりました。以前は、Adobe Journey Optimizer の新しいレポートインターフェイスをカスタマイズできませんでした。 <p>詳しくは、[テンプレートの作成と管理](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/templates/create-templates)の「テンプレートの作成」または「テンプレートの編集または削除」を参照してください。 |  | 2025年1月15日（PT） |
| **Analysis Workspace のテンプレート** | Customer Journey Analytics でテンプレートが使用できるようになりました。<ul><li>**事前定義済みテンプレート**：事前定義済みテンプレートを幅広く選択できます。これらのテンプレートを使用すると、最も一般的なレポートシナリオに対する簡易的なインサイトを得ることができます。事前定義済みテンプレートはそのまま使用できます。または、プロジェクトの開始点として使用し、特定の目的に合わせてカスタマイズすることもできます。[詳細情報](/help/analysis-workspace/templates/use-templates.md)</li><li>**会社テンプレート**：管理者は、組織に固有のユースケースのニーズを満たす会社テンプレートを作成できます。管理者が作成した会社テンプレートは、組織内のユーザーが使用できます。[詳細情報](/help/analysis-workspace/templates/create-templates.md)</li></ul> | 1月15日（PT） | 2025年1月30日（PT） |
| **製品の使用状況** | 組織が Customer Journey Analytics をどのように使用しているかを確認します。この機能を有効にすると、組織内のユーザーが Analysis Workspace を使用する際に、データを収集するデータセットが Adobe Experience Platform に作成されます。また、接続とデータビューも自動的に作成され、プロジェクトで使用される上位のプロジェクトタイプ、最もアクティブなユーザー、一番人気のコンポーネントなどのディメンションにアクセスできます。[詳細情報](/help/tools/product-usage/usage-overview.md) | 2024年10月23日（PT） | 2025年1月22日（PT） |
| **インテリジェントキャプション v2** | インテリジェントキャプションは、複数の折れ線グラフ、棒グラフ、横棒グラフ、ドーナツグラフ、面グラフ、フロー、フォールアウトなどのビジュアライゼーションでサポートされるようになりました。すべてのインテリジェントキャプションを一度に拡張ビューで表示することも、個々のインテリジェントキャプションを 1 つずつビューで表示することもできます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 2025年1月22日（PT） |
| **ガイド付き分析内からプロジェクトへのガイド付き分析の追加** | ガイド付き分析内から Workspace プロジェクトにガイド付き分析を追加できます。また、Analysis Workspace にガイド付き分析を直接追加することもできます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/guided-analysis/overview) |  | 2025年1月22日（PT） |
| **メディアコレクション：新しいメディアレポート XDM 用の Adobe ソースコネクタの更新** | Analytics ソースコネクタは、Adobe Analytics のストリーミングメディアデータを、Web SDK で使用される同じフィールドに自動的にマッピングします。現在、データは古い場所と新しい場所の両方にマッピングされていますが、今後は新しい場所のみが使用されます。（ドキュメントへのリンクを添付） |  | 2025年1月30日（PT） |

## Customer Journey Analytics の修正点

アラート：AN-363263、AN-364880、AN-365029、AN-365960
オーディエンス：AN-362564、AN-363254;
データ取り込み：AN-362359、AN-362751
データビュー：AN-362089、AN-365213、AN-365770、AN-366171、AN-366681
派生フィールド：AN-359711、AN-362496
書き出し場所：AN-363999
完全なテーブルの書き出し：AN-363055
Report Builder：AN-362937
Workspace：AN-359012、AN-359145、AN-359914、AN-361455、AN-361934、AN-362469、AN-363460、AN-364714、AN-364918、AN-366277、


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
