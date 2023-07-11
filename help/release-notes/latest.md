---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新のCustomer Journey Analyticsリリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: daf41a2aefeebe6339b4f86cc04c071b57887ce3
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 40%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2023 年 7 月）

**最終更新日**：2023年7月10日

Adobe Customer Journey Analyticsのリリースは [連続配信モデル](releases.md) これにより、機能のデプロイメントに向けて、よりスケーラブルで段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analyticsは、Customer Journey Analyticsでクロスチャネルのデータとインサイトを操作する新しい方法です。 これらの新機能により、製品チームは、ガイド付き分析ワークフローを通じて、製品エクスペリエンスに関するデータとインサイトをセルフサービスで提供できるようになります。チームで実行できる操作：<ul><li>時間の経過に伴うユーザーエンゲージメントのパターンを理解する</li><li>製品のユーザーベースの増加と保持を追跡す&#x200B;る</li><li>製品の摩擦領域を特定する</li><li>機能リリースの影響を測定し&#x200B;、最初に使用</li><li>製品に関する生涯のジャーニーを通じて、ユーザーの意味のあるセグメントを発見し、育成し&#x200B;ます</li><li>Analysis Workspaceと連携して、より深い分析とアナリストとの共同作業を実現</li></ul>Adobe Product Analyticsは、Customer Journey Analyticsへの有料アドオンです。 この機能を使用するように組織をプロビジョニングする場合は、Adobeアカウントチームにお問い合わせください。 [詳細情報](/help/guided-analysis/overview.md) | 該当なし | 2023年7月17日（PT） |
| **派生フィールド** | これは、派生フィールドの最初のリリースを表します。派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。さらに、派生フィールドをデータビューのコンポーネント（指標またはディメンション）として定義し、その派生フィールドを Workspace のコンポーネントとして使用することもできます。<p>このリリースでは、マーケティングチャネルテンプレートと次の機能がサポートされています。</p><ul><li>連結</li><li>Case When</li><li>検索と置換</li><li>ルックアップ</li><li>URL の解析</li></ul> <p>[詳細情報](/help/data-views/derived-fields/derived-fields.md)</p> | 2023年5月10日（PT） | 2023年8月2日（PT） |
| **プロファイルおよび参照データの参照のサポートが拡張されました。** | プロファイルまたは参照データセット内のフィールドの参照としてデータセットを追加する機能を提供します。 以前は、イベントデータセットのみがサポートされていました。 [詳細情報] | 2023年6月21日（PT） | 2023年7月12日（PT） |
| **Report Builderの強化** | <ul><li>複数のデータブロックのセルからフィルターします。 1 つのセルの複数のデータブロックに対するフィルターを変更できます。 定義済みのセルを使用し、複数のデータブロックに割り当て、セルで定義されたフィルターに基づいてデータを更新します。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>行ヘッダーと列ヘッダーの表示/非表示を切り替えます。 データ・ブロック・テーブル・ヘッダーの表示/非表示を切り替えたり、行と列のヘッダーを使用して、テーブルの書式を変更したり、レポート内のデータ・ブロックを整列させたりできます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | 該当なし | 2023年7月19日（PT） |
| **Experience Edge 位置情報検索** | Adobe Experience Edge では、すべての Experience Edge ユーザー (Adobe Analytics、Customer Journey Analytics、Adobe Target、Adobe Medium分析、Adobe Experience Platformなど ) に統合された地理データを提供する地域ルックアップサービスを追加しています。 | 該当なし | 2023年7月26日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-317971;AN-319234;AN-320439;AN-320519;AN-321740;AN-322444;AN-323116

## Customer Journey Analytics管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **データの処理方法の変更Customer Journey Analytics** | 2023年6月22日（PT） | 最近、Customer Journey Analyticsでのデータの処理方法を変更しました。<ul><li>タイムスタンプが 24 時間未満のイベントデータは、でストリーミングされます。</li><li>タイムスタンプが 24 時間以上のイベントデータ（新しいデータと同じバッチにある場合でも）はバックフィルと見なされ、より低い優先度で取り込まれます。</li></ul> |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **AdobeIO OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | AdobeIO JWT 資格情報を使用しているAdobe Analytics API、Customer Journey AnalyticsAPI、Livestream のお客様は、次の手順で AdobeIO OAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. AdobeIO では、2024年5月1日（PT）以降、新しい JWT 資格情報の作成を許可しません。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 関連リソース

* [2023 年の以前のCustomer Journey Analyticsリリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
