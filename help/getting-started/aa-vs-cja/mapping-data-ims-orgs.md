---
title: 複数のIMS組織からの分析データのマッピング
description: 複数のソース IMS組織のレポートスイートから宛先IMS組織のレポートスイートと最終的なデータセットにデータをマッピングする方法について説明します。
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
TQID: https://experienceleague.adobe.com/6qERpivKabPPCynMGNKrLhhOMcROnlp7HKpbvXpzNSg
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: d682e1e729402bff7a3f6e3625402f57deee21ad
workflow-type: tm+mt
source-wordcount: 1127
ht-degree: 2%

---

# Cross-IMS データマッピング

この記事では、複数のIMS組織のレポートスイートから、1つのIMS組織のレポートスイート、つまり最終的にはデータセットにデータをマッピングする方法について説明します。

Analytics ソースコネクタは、デフォルトで1つの組織内のAdobe Analytics レポートスイートからデータを取り込みます。 *Cross-IMS データマッピング*&#x200B;は、複数のIMS組織からのAnalytics データをマッピングする機能であり、この制限に対する解決策を提供します。 この機能を有効にするプロセスについては、この記事を参照してください。


## シナリオ

複数のIMS組織がプロビジョニングされており、これらのIMS組織全体の複数のレポートスイートにAnalytics データが含まれています。 この設定は、次のような結果になります。

* 買収または合併
* 組織構造の要件
* 各地域の導入の制約

標準では、Customer Journey Analyticsの複数のIMS組織の複数のレポートスイートからのデータの組み合わせをレポートすることはできません。 この制限の理由は、Analytics ソースコネクタを介したAdobe AnalyticsからExperience Platformへのデータ取り込みは、単一のIMS組織が所有するデータの取り込みのみをサポートしているためです。 プロビジョニングを行い、Adobe Analytics、Experience PlatformおよびCustomer Journey Analyticsへのログインに使用するIMS組織。

*Cross-IMS データマッピング*&#x200B;機能を使用すると、Adobeにデータのマッピングを依頼できます。 この機能では、Analytics ソースコネクタを使用して、複数の&#x200B;*source* IMS組織に存在するレポートスイートからデータをマッピングし、1つの&#x200B;*destination* IMS組織に属するレポートスイート（および最終的にはデータセット）にマッピングします。 次に例を示します。

| イラスト | 説明 |
|---|---|
| ![複数のIMS組織をまたいでデータをマッピング ](/help/getting-started/assets/map-data-across-ims-orgs.png) | このマッピングを使用すると、IMS組織3内でプロビジョニングされたCustomer Journey Analyticsの1つの接続から、IMS組織1、IMS組織2およびIMS組織3に存在するレポートスイートについてレポートできます。 |

{style="table-layout:fixed"}

## 使用方法

*Cross-IMS データマッピング*&#x200B;機能を設定して有効にするには、Adobe アカウントマネージャーを通じてマッピングをリクエストする必要があります。 それには、次の手順を実行します。

1. 宛先IMS組織管理者として、レポートスイートをマッピングするすべてのソース IMS組織管理者から承認メールをリクエストします。 次のテキストをメールのテンプレートとして使用して、ソース IMS組織管理者に承認を依頼できます。

   | メールテンプレートの例 |
   | --- |
   | *会社名の担当者*&#x200B;は、選択した宛先組織に次のIMS組織（ソース IMS組織のリスト）へのアクセス権を付与するには、各IMS組織の管理者が自分のデータへのアクセスを許可する承認を送信することを確認する必要があります。 これにより、影響を受けるIMS組織からのデータアクセス権限を確実に尊重できます。 適切な承認を得るには、各管理者組織の登録済みAdobe管理者に、この名前とIMS組織を示す名前とIMS組織をこのメールに返信してもらいます。このIMS組織のデータを宛先組織[ リスト先IMS組織]に表示することを承認することを示す「承認済み」と言います。 この管理者は、そのIMS組織の管理者としてAdobe システムに登録されている管理者である必要があります。 |

1. 複数のソース IMS組織内のレポートスイートから宛先IMS組織へのマッピングをリクエストする宛先IMS組織管理者の代わりに、Adobe アカウントマネージャーにメールを送信します。 ソース IMS組織管理者から受信した承認メールを添付します。

Adobe アカウントマネージャーが、複数の組織からAnalytics データをマッピングするリクエストを含むメールを受信すると、そのリクエストはAdobe内でレビューされます。 Adobeのアカウントマネージャーから、その他の質問やオプションのトレーニングなどの情報を受け取ることができます。

承認されると、リクエストされたマッピングが作成され、通知されます。 ソース IMS組織名は、Experience PlatformのAnalytics レポートスイートの[ リスト ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data)のレポートスイートの名前に追加されます。


## 制限事項

*Cross-IMS データマッピング*&#x200B;機能には、次の制限が適用されます。

* レポートスイートを接続できるのは、組織全体で1回のみです。
* マッピングの削除をリクエストする前に、マッピングで宛先IMS組織として定義されているIMS組織のすべての接続を削除する必要があります。
* ECIDは、マッピングされたソース IMS組織間で互換性がなく、宛先IMS組織とも互換性がありません。


## 注意点

*Cross-IMS データマッピング*&#x200B;機能をリクエストする前に、次のトピックを検討することをお勧めします。

### プロファイル

*Cross-IMS データマッピング*&#x200B;機能が承認されたら、宛先IMS組織内の1つ以上のレポートスイートのデータをExperience Platformに追加できます。 これは、[Analytics ソースコネクタ ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)の設定を通じて行います。 ターゲットデータセットは、Experience Platformで作成されます。 この設定とプロセスの一環として、1つ以上のレポートスイートからプロファイルサービスにプロファイルデータを送信するオプションがあります。

上記のように、設定とプロセスの結果であるプロファイルの合計数を見積もります。 合計数が、宛先組織に対して契約上の権利を持つプロファイルの数以内であることを確認します。 [ フィルタールールと条件](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"}を適用して、プロファイルサービスへの取り込みにデータを選択的に含めたり除外したりします。 関連するレポートスイートのプロファイルサービスにプロファイルデータを送信するオプションを無効にします。


#### ステッチ

[ フィールドベース ](/help/stitching/fbs.md)と[ グラフベース ](/help/stitching/gbs.md)の両方をターゲットデータセットにステッチできます。 これらの1つ以上のターゲットデータセットでグラフベースのステッチを使用する場合は、[ プロファイル ](#profiles) セクションで説明しているように、プロファイル数の契約上の使用権限を維持してください。

リアルタイム顧客プロファイルのライセンスを取得していなくても、1つ以上のターゲットデータセットでグラフベースのステッチを使用する場合は、これらのターゲットデータセットに対してのみ[ID サービス ](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)を有効にしてください。


### 権限

宛先IMS組織でAnalytics ソースコネクタを設定するのに十分な権限を持つユーザーは、マッピングされたソース IMS組織からAnalytics データを取り込む機能を持ちます。 ソース IMS組織のいずれについても、そのユーザーに対する権限はチェックされません。

### データに関するレポート

*Cross-IMS データマッピング*&#x200B;機能は、Customer Journey Analytics [connection](/help/connections/overview.md)、1つ以上の[ データビュー](/help/data-views/data-views.md)、および[ ワークスペースプロジェクト ](/help/analysis-workspace/home.md)の一部としてデータを使用できるようにするための最初のステップに過ぎません。 1つのIMS組織で現在利用可能なデータを注意深く調べる必要があります。 また、データを適切にレポートするために、データ準備、派生フィールド、追加のルックアップテーブルなどの機能を検討します。

