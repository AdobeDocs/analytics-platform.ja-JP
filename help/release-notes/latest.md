---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 29c124da55842bcb9085059a9008f7a7d6baf44e
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 47%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2024 年 2 月）

**最終更新日**：2024年2月14日（PT）

このリリースノートは、2024年2月14日～2024年3月11日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **時系列予測** | [予測](../analysis-workspace/c-forecast/forecasting.md) は、フリーフォームテーブルや折れ線グラフでサポートされている任意の時間精度（時間単位、日単位、週単位、月単位、年単位）を使用して標準指標や計算指標を予測するために使用される新しいAnalysis Workspace機能です。 | 2024年1月31日（PT） | 2024年2月21日（PT） |
| **Media Analytics レポート — 分平均オーディエンス (AMA)** | 分平均オーディエンスパネルが CJA で使用できるようになりました。 Media Analytics のお客様は、分平均オーディエンスパネルを使用して、コンテンツの平均消費量をより深く理解できます。 分平均オーディエンスを使用すると、任意の長さやジャンルのプログラミングを比較できます。さらに、お客様はこのデジタル分平均オーディエンスを線形 TV 分平均指標と比較または線形 TV 分平均指標に追加できます。このパネルでは、カスタム期間の平均オーディエンスをより柔軟に測定できるほか、期間の分類が事後に更新された場合にも測定できます。 |  | 2024年2月16日（PT） |
| **ルックアップおよびプロファイルデータの行数指標** | 接続の一部として設定されたデータセットの行数指標に、プロファイルおよび参照データセットに追加、スキップ、削除されたレコードが含まれるようになりました。 |  | 2024年2月14日（PT） |
| **Experience Edge ボット検出** | [ボット検出](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) を使用すると、Web SDK、Mobile SDK、Server API で生成されたイベントが、既知のスパイダーやボットで生成されたものとして識別できます。 | | 2024年2月21日（PT） |
| **使用状況指標** | 使用状況指標インターフェイスには、すべての接続で取り込まれた行とレポート可能な行の使用状況が表示されます。 このインターフェイスを使用すると、Customer Journey Analyticsの使用が契約上の合意事項に準拠しているかどうかを判断できます。 | 2024年2月20日（PT） | 2024 年 3 月上旬 |
| **Adobe Product Analytics：他のユーザーと共有** | Product Analyticsへのアクセス権を持たないユーザーと、Adobe Product Analyticsプロジェクトへの読み取り専用リンクを共有できます。 |  | 2024年2月21日（PT） |
| **Adobe Product Analytics：計算指標の適用** | Analysis Workspaceまたはトレンド：使用状況ビューの計算指標ビルダーで作成した計算指標にアクセスできるようになり、経時的に指標のトレンドを表示し比較できるようになりました。 |  | 2024年2月16日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-339883; AN-340200

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
