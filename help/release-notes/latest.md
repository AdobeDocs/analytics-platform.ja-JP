---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b8f70f38471e216c52a6c19b05fa259b9d2426ef
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 80%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年2月）

**最終更新日**：2024年2月20日（PT）

このリリースノートは、2024年2月14日～2024年3月11日（PT）のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **時系列予測** | [予測](../analysis-workspace/c-forecast/forecasting.md)は、標準指標または計算指標を、フリーフォームテーブルと折れ線グラフに対してサポートされている任意の時間精度（時間単位、日単位、週単位、月単位、年単位）で予測するために使用される新しい Analysis Workspace 機能です。 | 2024年1月31日（PT） | 2024年2月21日（PT） |
| **Media Analytics レポート - 分平均オーディエンス（AMA）** | 分平均オーディエンスパネルが CJA で使用できるようになりました。Media Analytics のお客様は、分平均オーディエンスパネルを使用すると、コンテンツの平均消費量をより詳細に把握できます。分平均オーディエンスを使用すると、任意の長さやジャンルのプログラミングを比較できます。さらに、お客様はこのデジタル分平均オーディエンスを線形 TV 分平均指標と比較または線形 TV 分平均指標に追加できます。このパネルでは、カスタム期間の平均オーディエンスをより柔軟に測定できるほか、期間の分類が事後に更新された場合にも測定できます。 |  | 2024年2月 |
| **ルックアップおよびプロファイルデータの行数指標** | 接続の一部として設定されたデータセットの行数指標に、プロファイルおよび参照データセットに追加、スキップ、削除されたレコードが含まれるようになりました。 |  | 2024年2月14日（PT） |
| **Experience Edge ボット検出** | [ボット検出](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ja)を使用すると、Web SDK、Mobile SDK、Server API で生成されたイベントが、既知のスパイダーやボットで生成されたものとして識別できます。 | | 2024年4月29日（PT） |
| **使用状況指標** | 使用状況指標インターフェイスには、すべての接続で取り込まれた行とレポート可能な行の使用状況が表示されます。このインターフェイスを使用すると、Customer Journey Analytics の使用状況が契約上の合意事項に準拠しているかどうかを判断できます。 | 2024年2月20日（PT） | 2024年3月上旬 |
| **Adobe Product Analytics：任意のユーザーと共有** | Product Analytics へのアクセス権を持たないユーザーと、Adobe Product Analytics プロジェクトへの読み取り専用リンクを共有できます。 |  | 2024年2月21日（PT） |
| **Adobe Product Analytics：計算指標の適用** | Analysis Workspace またはトレンド：使用状況ビューの計算指標ビルダーで作成された計算指標にアクセスできるようになり、時間の経過に伴う指標のトレンドと比較が可能になりました。 |  | 2024年2月16日（PT） |
| **データビューと接続 UI のリンクを更新しました** | 3 月初めに、Adobeは製品ユーザーインターフェイスで、次のリンクをCustomer Journey Analyticsに更新する予定です。 ブックマークを更新してください。<ul><li>**データ・ビュー・ページ、データ・ビュー・マネージャ**: [既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**新しいデータビューを作成**: [既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**データビューを編集**: [既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [新しいリンク](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**接続マネージャ**: [既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**接続情報**: [既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**接続を編集**: [既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**新しい接続を作成**: [既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |  | 2024年3月 |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-333172、AN-336887、AN-337402、AN-337593、AN-338482、AN-338684、AN-339883、AN-340200

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
