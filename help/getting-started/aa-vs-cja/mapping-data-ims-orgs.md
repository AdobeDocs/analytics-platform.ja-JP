---
title: クロス IMS データマッピング
description: 複数のソース IMS 組織のレポートスイートから宛先 IMS 組織にデータをマッピングするようにリクエストする方法について説明します。
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
source-git-commit: 7260c9cadbd5b6e5e85f778547635330b8bfc49a
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 1%

---

# クロス IMS データマッピング

Analytics ソースコネクタでのデータの取り込みは、Adobe Analyticsを使用する権限を持つ組織と同じ組織に属するCustomer Journey Analytics レポートスイートからのみ行えます。 *クロス IMS データマッピング* 機能は、複数の IMS 組織からの Analytics データをマッピングする機能で、この制限に対するソリューションを提供します。 この機能を有効にするプロセスの概要を、この記事で説明します。


## シナリオ

複数の IMS 組織がプロビジョニングされており、これらの IMS 組織全体の複数のレポートスイートに Analytics データが含まれています。 この設定の結果は次のようになります。

* 買収または合併
* 組織構造の要件
* 地域のデプロイメントの制約

初期状態では、Customer Journey Analyticsの複数の IMS 組織をまたいだ複数のレポートスイートのデータの組み合わせに関してレポートすることはできません。 この制限がある理由は、Analytics ソースコネクタを介したAdobe AnalyticsからExperience Platformへのデータ取り込みは、1 つの IMS 組織が所有するデータの取り込みのみをサポートするからです。 プロビジョニングを行い、Adobe Analytics、Experience PlatformおよびCustomer Journey Analyticsへのログインに使用する IMS 組織。

*クロス IMS データマッピング* 機能を使用すると、データをマッピングするようにAdobeをリクエストできます。 この機能は、Analytics ソースコネクタを使用して、複数の *ソース* IMS 組織に存在するレポートスイートのデータを、1 つの *宛先* IMS 組織の一部であるレポートスイート（および最終的なデータセット）にマッピングします。 次に例を示します。

| イラスト | 説明 |
|---|---|
| ![ 複数の IMS 組織間でのデータのマッピング ](/help/getting-started/assets/map-data-across-ims-orgs.svg) | このマッピングを使用すると、IMS Organization 1、IMS Organization 2、および IMS Organization 3 に存在するレポートスイートについて、IMS Organization 3 内でプロビジョニングされたCustomer Journey Analytics内の 1 つの接続からレポートできます。 |

{style="table-layout:fixed"}

## 使用方法

*クロス IMS データマッピング* 機能を設定して有効にするには、Adobe アカウント管理者を通じてマッピングをリクエストする必要があります。 それには、次の手順を実行します。

1. 宛先 IMS 組織管理者として、レポートスイートをマッピングするすべてのソース IMS 組織管理者から承認メールをリクエストします。 次のテキストをメールのテンプレートとして使用し、ソース IMS 組織管理者の承認をリクエストできます。

   | サンプルメールテンプレート |
   | --- |
   | *会社名担当者*、選択した宛先組織に次の IMS 組織（ソース IMS 組織のリスト）へのアクセス権を付与するには、各 IMS 組織の管理者がデータへのアクセスを許可するために承認を送信する必要があります。 これにより、影響を受ける IMS 組織からデータアクセス権限を確実に付与できます。 適切な承認が得られるように、管理者の各組織の登録済みAdobe管理者に、名前と IMS 組織を表すこのメールに返信して、「承認します」と言って、この IMS 組織のデータが宛先組織 [ 宛先 IMS 組織をリスト ] に表示されることに対する承認を与えていることを示してください。 この管理者は、その IMS 組織の管理者としてAdobe システムに登録されている管理者である必要があることに注意してください。 |

1. 宛先 IMS 組織管理者の代わりに、複数のソース IMS 組織内のレポートスイートから宛先 IMS 組織へのマッピングをリクエストするメールをAdobe アカウントマネージャーに送信します。 ソース IMS 組織管理者から受信した承認メールを添付します。

Adobe アカウントマネージャーが、複数の組織から Analytics データをマッピングするリクエストを含むメールを受信すると、Adobe内でそのリクエストがレビューされます。 その他の質問、オプションのトレーニング、その他の情報については、Adobe アカウントマネージャーから連絡があります。

承認されると、リクエストされたマッピングが作成され、通知が届きます。 ソース IMS 組織名は、Experience Platformの [Analytics レポートスイートのリスト ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) のレポートスイート名に追加されます。


## 制限事項

*クロス IMS データマッピング* 機能には、次の制限が適用されます。

* レポートスイートは、複数の組織をまたいで 1 回だけ接続できます。
* マッピングの削除をリクエストする前に、マッピングで宛先 IMS 組織として定義されている IMS 組織のすべての接続を削除する必要があります。
* ECID は、マッピングされたソース IMS 組織間で互換性がなく、宛先 IMS 組織とも互換性がありません。


## 注意点

*クロス IMS データマッピング* 機能をリクエストする前に、次のトピックを検討してください。

### プロファイル

*クロス IMS データマッピング* 機能が承認されると、宛先 IMS 組織内の 1 つ以上のレポートスイートのデータをExperience Platformに追加できます。 これを行うには、[Analytics ソースコネクタ ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) を設定します。 次に、ターゲットデータセットがExperience Platformで作成されます。 この設定とプロセスの一環として、1 つ以上のレポートスイートからプロファイルサービスにプロファイルデータを送信するオプションがあります。

前述のように、設定とプロセスの結果として生じるプロファイルの合計数を推定します。 合計数が、宛先組織に対して契約で権利を付与されるプロファイルの数に含まれていることを確認します。 プロファイルサービスへの取り込みに対してデータを選択的に含めるか除外する [ フィルタリングルールと条件 ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"} を適用します。 または、プロファイルデータを関連するレポートスイートのプロファイルサービスに送信するオプションを無効にします。


### ステッチ

*クロス IMS データマッピング* 機能が承認されると、宛先 IMS 組織内の 1 つ以上のレポートスイートのデータをExperience Platformに追加できます。 これを行うには、[Analytics ソースコネクタ ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) を設定します。 Analytics ソースコネクタで設定したレポートスイートのターゲットデータセットは、Experience Platformで作成します。 この設定とプロセスの一環として、1 つ以上のレポートスイートからプロファイルサービスにプロファイルデータを送信するオプションがあります。

ターゲットデータセットに対して、[ フィールドベース ](/help/stitching/fbs.md) と [ グラフベース ](/help/stitching/gbs.md) の両方のステッチを使用できます。 これらのターゲットデータセットの 1 つ以上でグラフベースのステッチを使用する場合は、[ プロファイル ](#profiles) の節で説明しているように、プロファイル数の契約上の使用権限の範囲内に収まるようにします。

リアルタイム顧客プロファイルのライセンスを持っていないが、1 つ以上のターゲットデータセットでグラフベースのステッチを使用する必要がある場合は、これらのターゲットデータセットで [ID サービス ](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) のみを有効にしてください。


### 権限

宛先 IMS 組織で Analytics ソースコネクタを設定するのに十分な権限を持つユーザーは、マッピングされた任意のソース IMS 組織から Analytics データを取り込むことができます。 そのユーザーのソース IMS 組織に対する権限はチェックされません。

### データのレポート

*クロス IMS データマッピング* 機能は、データをCustomer Journey Analytics [connection](/help/connections/overview.md)、1 つ以上の [ データビュー ](/help/data-views/data-views.md) および [workspace プロジェクト ](/help/analysis-workspace/home.md) の一部として使用できるようにする最初の手順にすぎません。 1 つの IMS 組織で使用可能になったデータを慎重に検査する必要があります。 また、このデータを正しくレポートするには、データ準備、派生フィールド、追加のルックアップテーブルなどの機能を考慮する必要があります。
