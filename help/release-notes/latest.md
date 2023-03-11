---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の CJA リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f3233f0be1fb455535af4532fe32b5db8560fb62
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 30%

---

# 最新のCustomer Journey Analytics(CJA) リリースノート（2023 年 3 月）

**最終更新日**：2023年3月10日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 主な機能と更新

| 機能 | 説明 | [ロールアウトの開始](/help/release-notes/releases.md) | [一般公開](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Analysis Workspaceのデータ辞書** | データディクショナリは、ユーザーと管理者の両方が、CJA 環境のコンポーネント（ディメンション、指標）を追跡し、より深く理解するのに役立ちます。 [詳細情報](/help/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 9 日 | 2023 年 3 月 23 日 |
| **モバイルダッシュボードのデータストーリー** | データストーリーを使用すると、カスタマイズ可能な複数の詳細ビューをモバイルスコアカードプロジェクトのタイルに追加できます。 データストーリーを使用して、カスタマージャーニーにおける主な推進要因、関連指標、様々な手順を詳しく調べます。 これらのビューを簡単にスワイプして、主要指標の背後にある全体像を把握できます。 [詳細情報](/help/mobile-app/create-scorecard.md#create-data-story) | 該当なし | 2023 年 3 月 9 日 |
| **スケジュール済みプロジェクトの有効期限** | スケジュールの頻度に関係なく、スケジュールされたプロジェクトの最大有効期限日は最大 1 年に設定できます。 [詳細情報](/help/analysis-workspace/curate-share/t-schedule-report.md) | 該当なし | 2023 年 3 月 9 日 |
| **プロジェクトのリンク共有（ログインは不要） — プライベートベータアクセスのみ** | CJA へのアクセス権を持たないユーザーと、Analysis Workspaceプロジェクトへの読み取り専用リンクを共有できるようになりました。 プロジェクトリンクは、組織外の人や、組織内で CJA 用にプロビジョニングされていない人と共有できます。 [詳細情報](/help/analysis-workspace/curate-share/share-projects.md)<p>プライベートベータ版に参加するには、Adobeアカウントチームにお問い合わせください。 | 2023 年 3 月 16 日（プライベートベータ版） | 2023 年 4 月 |
| **パネルの日付範囲の更新** | ワークスペースに、次の機能強化が追加されました。<ul><li>2 月のリリース以降、ディメンション項目とデータプレビューは、過去 90 日間ではなく、パネルの日付範囲に基づいておこなわれます。 </li><li>表示されるすべてのディメンション項目は、パネルの日付範囲内のデータに基づきます。 ディメンション項目に日付範囲外のデータが含まれる場合は、リストの下部に、日付範囲外の追加データを表示できます。</li><li>Dimensionにデータがないデータは、左側のパネルに表示できます。 「その他のオプションを表示」をクリックすると、パネルの日付範囲外のデータを含むディメンション項目が表示されます。</li><li>セグメントおよび計算指標ビルダーでのデータプレビューは、関連するパネルがなく、過去 90 日間の期間を使用しているコンポーネントマネージャーからアクセスしない限り、パネルの日付範囲に基づきます。</li><li>データプレビューは、パネルの日付範囲に基づいて、データやコンポーネントを表示します。</li></ul> | 該当なし | 2023年2月8日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-309729;AN-309975;AN-311779;AN-313095

## CJA 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| Analytics Source Connector の可用性 | 2023年2月15日（PT） | 2023 年 2 月 28 日に、カナダにある新しいAdobe Experience Platformデータセンターで Analytics ソースコネクタの利用が可能になりました。 |

{style="table-layout:auto"}

## 関連リソース

* [2023年の以前の CJA リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
