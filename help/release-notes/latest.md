---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新の Customer Journey Analytics リリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 20e99275a42312ed974ac4c1af28ede73180e748
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 92%

---

# 現在の Adobe Customer Journey Analytics リリースノート（2024年3月）

**最終更新日**：2024年3月20日（PT）

このリリースノートは、2024年3月13日（PT）～2024年4月のリリース期間を対象としています。Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **プロジェクトランディングページで新しい列を使用できます** | **[!UICONTROL 前回開いた日時]**&#x200B;列が、[Customer Journey Analytics ランディングページ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=ja)の「プロジェクト」タブを表示するときに利用できるようになりました。 <p>この情報は、プロジェクトが最後に開かれた日時を示し、組織内のユーザーにとってプロジェクトが有用かどうかを判断するのに役立ちます。以前は、**[!UICONTROL 前回の使用]**&#x200B;列は、計算指標マネージャー、セグメントマネージャー、アラートマネージャーでしか使用できませんでした。</p> |  | 2024年3月13日（PT） |
| **使用状況指標** | [使用状況指標インターフェイス](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ja)には、すべての接続で取り込まれた行とレポート可能な行の使用状況が表示されます。このインターフェイスを使用すると、Customer Journey Analytics の使用状況が契約上の合意事項に準拠しているかどうかを判断できます。 |  | 2024年3月13日（PT） |
| **Media Analytics レポート - 分平均オーディエンス（AMA）** | 分平均オーディエンスパネルが CJA で使用できるようになりました。Media Analytics のお客様は、分平均オーディエンスパネルを使用すると、コンテンツの平均消費量をより詳細に把握できます。 <p>分平均オーディエンスを使用すると、任意の長さやジャンルのプログラミングを比較できます。さらに、お客様はこのデジタル分平均オーディエンスを、線形 TV 分平均指標と比較したり追加したりできます。</p><p> このパネルでは、カスタム期間の平均オーディエンスをより柔軟に測定できるほか、期間の分類が事後に更新された場合にも測定できます。</p><p>詳しくは、[メディア分平均オーディエンスパネル](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)を参照してください。</p> |  | 2024年3月12日（PT） |
| **ユーザーからアカウントへの B2B スキーマ変換** | データセットを変換すると、Customer Journey Analytics B2B レポートシナリオにおけるユーザーベースのルックアップをより適切にサポートできます。この機能は、次のクラスに基づく B2B スキーマのデータセットで使用できます。<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul> | | 2024年3月26日（PT） |
| **Report Builder の使用状況が、計算指標マネージャーとフィルターマネージャーの「使用場所」列に含まれる** | 計算指標マネージャーまたはフィルターマネージャーで&#x200B;**使用場所**&#x200B;列を表示すると、Report Builder で使用状況データを使用できるようになりました。<p>以前は、フィルターマネージャーの使用状況データはアラート、プロジェクト、スケジュール済みプロジェクト、および計算指標に対してのみ、計算指標マネージャーの使用状況データはアラート、プロジェクト、およびスケジュール済みプロジェクトに対してのみ使用できました。</p> |  | 3 月下旬または 4 月上旬 |
| **Adobe Product Analytics：1 つのファネルステップ内のイベントを比較** | ファネル内：摩擦ビューでは、1 つのファネルステップ内のイベントを比較できるようになりました。ジャーニーにステップオプションがある場合や、A/B 実験が実行されるステップがある場合に特に便利です。 | 2024年3月29日（PT） | 2024年4月12日（PT） |
| **管理者は、組織内のすべての場所とアカウントを管理できます** | 管理者は、「ロケーション」タブ（コンポーネント/エクスポートページ）の新しいオプションを使用して、組織内のすべてのロケーションを表示および管理できます。 <p>管理者は、「ロケーションアカウント」タブ（コンポーネント/エクスポートページ）の新しいオプションを使用して、組織内のすべてのアカウントを表示および管理できます。</p><p>以前は、管理者は自分が作成した場所とアカウントのみを表示および管理できました。</p> | | 2024年4月 |
| **オーディエンスは Experience Platform の新しい「オーディエンス」セクションに公開される** | Customer Journey Analytics から公開されたオーディエンスが、Experience Platform の新しい「オーディエンス」セクションで使用できるようになりました。以前は、Customer Journey Analytics から公開されたオーディエンスは、プラットフォームの「セグメント」セクションで使用できました。この改善によるメリットは次のとおりです。<ul><li>オーディエンスが Platform に表示されるまでに 1 時間の遅延がなくなりました。公開されてから数秒後に使用できるようになります。</li><li>オーディエンスは、オーディエンスが最初に公開されたアプリケーションを表示する「接触チャネル」列を使用して、Platform で並べ替えることができます。</li><li>Platform のフィルターと並べ替えのオプションを使用すると、関連するオーディエンスをよりすばやく見つけることができます。</li></ul>詳しくは、[Experience Platform での Customer Journey Analytics オーディエンスの使用](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=ja#audiences-aep)の節を参照してください。 |  | 2024年4月 |
| **Experience Edge ボット検出** | [ボット検出](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ja)を使用すると、Web SDK、Mobile SDK、Server API で生成されたイベントが、既知のスパイダーやボットで生成されたものとして識別できます。 | | 2024年4月29日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-340429、AN-341544、AN-341974、AN-342176、AN-342391

## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **データビューと接続 UI のリンクを更新しました** | 2月15日 | 3 月初旬に、アドビは Customer Journey Analytics 製品のユーザーインターフェイスで、次のリンクを更新する予定です。ブックマークを必要に応じて更新してください。<ul><li>**データビューページ、データビューマネージャー**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**新しいデータビューを作成**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**データビューを編集**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88)／[新しいリンク](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**接続マネージャー**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**接続情報**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**接続を編集**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**新しい接続を作成**：[既存のリンク](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new)／[新しいリンク](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adobe API オブジェクトメンバーの追加 | 2024年1月17日（PT） | アドビでは、バージョン管理の通知や変更なしに、オプションのリクエストおよび応答メンバー（名前／値のペア）を既存の API オブジェクトに追加する場合があります。このような追加は、実装に対して重大な変更ではありません。アドビでは、理解できない場合は、このような追加が処理中に無視されるように、API と統合するサードパーティツールの API ドキュメントを参照することをお勧めします。アドビでは、最初にリリースノートを通じて標準通知を提供することなく、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |

{style="table-layout:auto"}

## 関連リソース

* [2023年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
