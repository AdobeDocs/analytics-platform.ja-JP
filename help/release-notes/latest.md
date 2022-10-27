---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 07842c9f1e2f4708d0881dec75c067d93611626c
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 73%

---

# Customer Journey Analytics(CJA) リリースノート（2022 年 10 月/11 月）

**最終更新日**：2022年10月25日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 主な機能と更新

| 機能 | 説明 | [ロールアウトの開始](/help/release-notes/releases.md) | [一般公開](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL 主要指標の概要]ビジュアライゼーション** | [!UICONTROL 主要指標の概要]ビジュアライゼーションを使用すると、1 つの期間内で重要な指標のトレンドを確認できます。また、2 つの期間で指標のパフォーマンスを比較することもできます。[詳細情報](/help/analysis-workspace/visualizations/key-metric.md) | 2022年10月5日（PT） | 2022年10月19日（PT） |
| **複数値の変数で大文字と小文字が区別されない** | 大文字と小文字を区別しない複数値の変数の場合、`mvvar1` ～ `mvvar3` に格納されている値は、自動的に小文字に変換されなくなります。代わりに、Analytics Source Connector を通じて Adobe Experience Platform と CJA に渡されたデータは、ページから渡された元のケースを反映します。 | 該当なし | 2022年10月24日（PT） |
| **CJA 監査ログ** | Customer Journey Analytics(CJA) では、様々なサービスや機能に関するユーザーアクティビティを「監査ログ」の形式で監査できます。 これらのログは、問題のトラブルシューティングに役立つ監査証跡を形成し、HIPAA（Health Insurance Portability and Accountability Act）などの企業のデータ管理ポリシーや規制要件への準拠を効果的に行うのに役立ちます。以前は、これらのログは監査ログ API からのみ使用できました。 [詳細情報](/help/privacy/audit-log.md) | 該当なし | 2022年10月26日（PT） |
| **HIPAA 対応** | Adobeは、Healthcare Shield のお客様のみに対する、Customer Journey Analyticsおよびその他のExperience Platformベースのアプリケーションで、保護された医療情報の受信、使用、保守、送信をサポートするようになりました。 ヘルスケアシールドは、米国でのみカバーエンティティまたはビジネスアソシエイトとなる医療関連のお客様向けです。 [詳細情報](https://www.adobe.com/trust/compliance/hipaa-ready.html) | 該当なし | 2022 年 11 月 8 日 |
| **スケジュール済みプロジェクトのパスワード保護** | この機能は、HIPAA 対応の一部であり、Healthcare Shield のお客様にのみ適用されます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#password) | 該当なし/ | 2022 年 11 月 8 日. |

{style=&quot;table-layout:auto&quot;}

## 修正点

* 最新のMacOSバージョンの名前が正しく「Macintosh」にならない問題を修正しました。 この修正により、OS ディメンションでは、MacOS 11 から始まる「MacOS」バージョンの番号が使用され始めます。 (AN-301834)

### その他の  修正点

AN-302367;AN-302562;AN-304036

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **デフォルトのランディングページ** | 2023年9月29日（PT） | 今年初めに導入された[新規ランディングページ](/help/getting-started/landing.md)は、**2023年1月**&#x200B;にすべてのユーザーのデフォルトのエクスペリエンスとなる予定です。現在のページは廃止される予定で、すべてのユーザーは新しいエクスペリエンスを利用する必要があります。 |
| **IP からジオロケーションへのマッピングの改善** | 2022年9月29日（PT） | アドビの IP 検索ベンダーである Digital Element は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）へのアップグレードを行います。Adobe Analytics では、この新しいデータセットの導入を **2023年1月**&#x200B;まで延期しました。新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p> [!UICONTROL Analytics ソースコネクタ]を通じて提供される CJA データも、新しいマッピングを自動的に活用します。 |
| **[!UICONTROL 異常値検出]の自動実行条件** | 2022年9月29日（PT） | 現在、[!UICONTROL 異常値検出]は、時系列フリーフォームテーブルのすべての列で自動実行されます。分析のデータ確保やプロジェクトの読み込みの高速化を目的に、アドビでは[!UICONTROL 異常値検出]の自動実行方法を変更します。**2022年10月26日（PT）**&#x200B;より、異常値検出は、テーブルの最初の指標列でのみ自動実行されます。必要に応じて、他の列で[!UICONTROL 異常値検出]を実行するように列設定を設定できます。 |

{style=&quot;table-layout:auto&quot;}


## 関連リソース

* [2022年の以前の CJA リリースノート](/help/release-notes/2022.md)

* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)

* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)

* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)

* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
