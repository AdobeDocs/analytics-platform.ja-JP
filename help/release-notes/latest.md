---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: aa7f4361b1353a86b87c36c3d08e99ddb8ffd049
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 53%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2023 年 9 月）

**最終更新日**：2023年9月13日（PT）

これらのリリースノートでは、2023 年 9 月 13 日から 2023 年 10 月 3 日までのリリース期間を扱っています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics ソースコネクタでの A4T 分類のサポート** | `_experience.decisioning.propositions.scopeDetails.correlationID` フィールドが Adobe Analytics ソースコネクタスキーマで使用できるようになりました。このフィールドは、A4T 分類のサポートに使用され、2023 年 9 月以降に入力されます。 | | 該当なし | 2023年9月12日（PT） |
| **派生フィールドの更新** | 派生フィールドの機能に対して、次の更新がおこなわれました。<ul><li>The [!UICONTROL 参照] 関数の名前がに変更されました。 [!UICONTROL 分類]に含まれ、CSV データを読み込むための追加のオプションが含まれます。 **（リリース 2023 年 9 月 28 日）**</li><li>派生フィールドを定義する際に使用できる追加の関数は次のとおりです。 [!UICONTROL トリミング], [!UICONTROL 小文字] および [!UICONTROL 参照].</li><li>派生フィールドの定義で、次のフィールドもサポートされるようになりました。 [!UICONTROL 参照] および [!UICONTROL プロファイル] データセット。</li></ul>[詳細情報](/help/data-views/derived-fields/derived-fields.md) | 該当なし | 2023年9月13日（PT） |
| **Adobe Product Analyticsの新機能** | <ul><li>**異常値検出**：イベントを、過去のトレンドから派生した期待される値と比較します。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**トレンド使用頻度ビュー**：使用頻度別に機能の採用状況を測定します。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**ユーザーの環境設定**：カラーパレットや数値形式など、多数のユーザー環境設定を指定します。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=ja)</li></ul> | 該当なし | 2023年9月18日（PT） |
| **Experience Edge デバイスの参照** | Device Edge ネットワークを介して、自動デバイスタイプのExperience Platform収集を有効にします。 この Experience Edge サービスは、他のCustomer Journey Analyticsアプリと共にExperience Platformに役立ちます。 （後に続くドキュメントリンク） | 該当なし | 2023年9月27日（PT） |
| **コンポーネントを管理する際に使用できる新しい列** | 次の新しい列が [計算指標マネージャー](/help/components/calc-metrics/cm-workflow/cm-manager.md) そして [フィルターマネージャー](/help/components/filters/manage-filters.md) コンポーネントを管理する場合：<ul><li>使用場所</li><li>前回の使用</li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、および削除または変更する必要があるかどうかを判断するのに役立ちます。 この情報と共にデータディクショナリを使用すると、組織でのコンポーネントの使用方法を追跡し、より深く理解することができます。</p> | 2023年9月20日（PT） | 2023年10月4日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | 該当なし | 該当なし |

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
