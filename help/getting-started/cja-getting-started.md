---
title: Customer Journey Analytics クイックスタートガイド
description: Customer Journey Analytics を実装するのに必要な前提条件およびワークフローについて把握します。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/qYz2G6gugkSMH-BITMExxjkheGHrYFvDTZbR66c-Rr0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 837
ht-degree: 85%

---

# クイックスタートガイド

Customer Journey Analytics を実装するには、次のワークフローに従う必要があります。 初期タスクの中には、Adobe Experience Platform で実行されるものと、Customer Journey Analytics で実行されるものがあります。

## 前提条件

Customer Journey Analytics を利用できる人物は次のとおりです。

* [Adobe Experience Platform](https://www.adobe.com/jp/experience-platform.html) 用にプロビジョニングされている
* Customer Journey Analytics SKU を購入している。

## ワークフロー

| タスク | 詳細 |
| --- | --- |
| **手順 1：Adobe Analytics から Customer Journey Analytics にアップグレードする場合：アップグレードパスを選択し、データを Adobe Experience Platform に送信します** | Adobe Analytics から Customer Journey Analytics にアップグレードする場合、様々なパスが使用可能です。 考えられるアップグレードパスにはそれぞれ独自のメリットとデメリットがあり、ある組織にとって適切なパスでも別の組織にとって適切ではない場合があります。 <p>Adobe Analytics から Customer Journey Analytics へのアップグレードを開始するには、次のいずれかの操作を行います。</p><ul><li>Adobe が推奨するアップグレードパスに従う。 詳しくは、[Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパス](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)を参照してください。</li><li>使用可能なすべてのアップグレードパスについて理解し、組織にとって最適なパスを選択する。 詳しくは、[Customer Journey Analytics へのアップグレードの概要](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)を参照してください。</li></ul> |
| **手順 2：他のデータを Adobe Experience Platform に取り込む** | この手順は、Adobe Experience Platform で実行され、いくつかのサブ手順が必要となります。<ul><li>**手順 2a：データスキーマの準備**：[Adobe Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用して顧客体験データを標準化し、顧客体験管理の[スキーマを定義](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja)します。</li><li>**手順2b: スキーマに基づいてデータセットを作成する**: Platformのデータは、電子メールデータセット、CRM データセット、POS データセット、Adobe Analytics データセットなどのデータセットで構成されます。各データセットは、スキーマとデータのバッチで構成されます。 [Experience Platform でデータセットを作成](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ja)できます。</li><li>**手順 2c：Experience Platform へのデータの取り込み**：いくつかのオプションがあります。</li></ul> |
| **手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続の作成** | 接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。 Experience Platform データセットについてレポートを作成するには、まずExperience PlatformとWorkspaceのデータセット間のコネクションを確立する必要があります。<br>詳しくは、[ コネクションの作成または編集](/help/connections/create-connection.md)を参照してください。 |
| **手順 4：データビューの作成** | データ表示は、データの「フィルタリングされた」表示です。 同じ接続に対して、訪問タイムアウトやアトリビューションなどの設定を異なるデータビューを作成できます。単一のデータセットに対して複数のデータビューを作成できます。<br>[データビューの作成](/help/data-views/create-dataview.md)を参照してください。 |
| **手順 5：レポート API の使用状況の移植**</br> Adobe Analytics から移行する場合にのみ適用されます。 | Customer Journey Analytics レポート API は同じ形式ですが、異なるエンドポイントを使用します。 レポート API の使用状況を Adobe Analytics レポート API から Customer Journey Analytics レポート API に移植します。 |
| **手順 6：データフィードとデータウェアハウスのユースケースの考慮**</br> Adobe Analytics から移行する場合にのみ適用されます。 | Adobe Analytics で使用していたデータフィードとデータウェアハウスの機能を最適にレプリケートするには、Customer Journey Analytics で使用可能な書き出しオプションの使用方法を決定します。<!-- link to docs Rob is creating --> |
| **手順 7：プロジェクトとコンポーネントの移行**</br> Adobe Analytics から移行する場合にのみ適用されます。 | Adobe Analytics のコンポーネント移行領域では、Adobe Analytics から Customer Journey Analytics にプロジェクトとその関連コンポーネントを移行できます。<p>移行プロセスには、次が含まれます。</p><ul><li>Customer Journey Analytics で Adobe Analytics プロジェクトを再作成する。</li><li>Adobe Analytics レポートスイートのディメンションと指標を、Customer Journey Analytics データビューのディメンションと指標へマッピングする。</li></ul><p>移行を開始する前に、まず[コンポーネントとプロジェクトを Adobe Analytics から Customer Journey Analytics に移行する準備をします](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=ja)。</p><p>必要な準備をすべて整えたら、[コンポーネントとプロジェクトを Adobe Analytics から Customer Journey Analytics に移行](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=ja)できます。</p> |
| **手順 8：ユーザーのオンボーディングの計画** | Adobe Analytics と同様、Analysis Workspace は Customer Journey Analytics の主なユーザー向けツールです。 ただし、Customer Journey Analytics で Analysis Workspace を使用する際は、ユーザーが認識しておく必要がある主な違いがいくつかあります。<p>Customer Journey Analytics の Analysis Workspace の主な違いを理解できるよう、十分な時間（3～6 か月）をユーザーに与える必要があります。</p><p>Adobe Analytics と Customer Journey Analytics の主な違いについて詳しくは、[Adobe Analytics ユーザー向けユーザーガイド](/help/getting-started/aa-to-cja-user.md)を参照してください。</p> |
| **手順 9：ワークスペースでのクロスチャネルデータのレポート** | 接続とデータビューを作成したら、Analysis Workspaceの機能と柔軟性を使用して、取り込んだデータを分析します。<br>詳しくは、[基本分析](/help/analysis-workspace/perform-basic-analysis.md)および[高度な分析](/help/analysis-workspace/perform-adv-analysis.md)を実行するを参照してください。 |

## クイックスタートガイド

[データ取り込み](../data-ingestion/data-ingestion.md)の節では、上記のワークフローに関するクイックスタートガイドを提供しています。 これらのクイックスタートガイドでは、Adobe Experience Platform で様々なソース（Adobe Analytics など）のデータを取り込んで Customer Journey Analytics で使用する方法について説明しています。
