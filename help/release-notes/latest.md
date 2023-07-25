---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e6b2df9ae90ef5663206e768b985749de38e263c
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 100%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2023年7月）

**最終更新日**：2023年7月25日（PT）

Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics は、Customer Journey Analytics でクロスチャネルのデータやインサイトを操作する新しい方法です。これらの新機能により、製品チームは、ガイド付き分析ワークフローを通じて、製品エクスペリエンスに関するデータとインサイトをセルフサービスで提供できるようになります。チームで実行できる操作：<ul><li>時間の経過に伴うユーザーエンゲージメントのパターンを理解する</li><li>製品のユーザーベースの成長と保持を追跡する</li><li>製品の摩擦の領域を特定する</li><li>機能リリースと最初の使用の影響を測定する</li><li>製品のジャーニー全体を通したエンゲージメントと育成に役立つ、意味のあるユーザーセグメントを見つける</li><li>Analysis Workspace に接続して、より詳細な分析やアナリストとの共同作業を行う</li></ul>Adobe Product Analytics は、Customer Journey Analytics の有料アドオンです。この機能を使用できるように組織をプロビジョニングする場合は、アドビのアカウントチームにお問い合わせください。[詳細情報](/help/guided-analysis/overview.md) | 該当なし | 2023年7月17日（PT） |
| **派生フィールド** | これは、派生フィールドの最初のリリースを表します。派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。さらに、派生フィールドをデータビューのコンポーネント（指標またはディメンション）として定義し、その派生フィールドを Workspace のコンポーネントとして使用することができます。<p>このリリースでは、マーケティングチャネルテンプレートと次の機能がサポートされています。</p><ul><li>連結</li><li>Case When</li><li>検索と置換</li><li>ルックアップ</li><li>URL の解析</li></ul> <p>[詳細情報](/help/data-views/derived-fields/derived-fields.md)</p> | 2023年5月10日（PT） | 2023年8月2日（PT） |
| **プロファイルデータやルックアップデータへのルックアップサポートの拡張** | プロファイルデータセットまたはルックアップデータセット内のフィールドのルックアップとしてデータセットを追加できるようになります。これまでは、イベントデータセットのみがサポートされていました。[詳細情報](/help/connections/create-connection.md) | 2023年6月21日（PT） | 2023年7月12日（PT） |
| **Report Builder の機能強化** | <ul><li>セルからの複数データブロックのフィルタリング。複数のデータブロックに対するフィルターを 1 つのセルから変更できます。定義済みのセルを使用し、それを複数のデータブロックに割り当てて、セルに定義されたフィルターに基づいてデータを更新します。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=ja)</li><li>行ヘッダーと列ヘッダーの表示／非表示の切り替え。データブロックのテーブルヘッダーや、行ヘッダーと列ヘッダーの表示／非表示を切り替えて、テーブルの書式設定を変更したり、レポートでデータブロックを整列させたりすることができます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=ja#build-the-data-block)</li></ul> | 該当なし | 2023年7月19日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-317971、AN-319234、AN-320439、AN-320519、AN-321740、AN-322444、AN-323116

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **Customer Journey Analytics によるデータの処理方法の変更** | 2023年6月22日（PT） | 最近、Customer Journey Analytics でのデータの処理方法が変更されました。<ul><li>発生後の経過時間が 24 時間未満のイベントデータは、すべてストリーミングで取り込まれます。</li><li>経過時間が 24 時間以上のイベントデータは、（より新しいデータと同じバッチにある場合でも）バックフィルと見なされ、低い優先度で取り込まれます。</li></ul> |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API、Customer Journey Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。2024年5月1日（PT）以降、Adobe I/O では新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 関連リソース

* [2023年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
