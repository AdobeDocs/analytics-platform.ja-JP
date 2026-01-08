---
title: 複数の IMS 組織からの Analytics データのマッピング
description: 複数のソース IMS 組織のレポートスイートから宛先 IMS 組織にデータをマッピングするようにリクエストする方法について説明します。
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# 複数の IMS 組織からの Analytics データのマッピング

Analytics ソースコネクタでのデータの取り込みは、Adobe Analyticsを使用する権限を持つ組織と同じ組織に属するCustomer Journey Analytics レポートスイートからのみ行えます。 複数の IMS 組織からの Analytics データをマッピングする機能は、この制限のソリューションとなります。 この機能を有効にするプロセスの概要を、この記事で説明します。


## シナリオ

複数の IMS 組織がプロビジョニングされており、これらの IMS 組織全体の複数のレポートスイートに Analytics データが含まれています。 この設定の結果は次のようになります。

* 買収または合併
* 組織構造の要件
* 地域のデプロイメントの制約

初期状態では、Customer Journey Analyticsの複数の IMS 組織をまたいだ複数のレポートスイートのデータの組み合わせに関してレポートすることはできません。 この制限がある理由は、Analytics ソースコネクタを介したAdobe AnalyticsからExperience Platformへのデータ取り込みは、1 つの IMS 組織が所有するデータの取り込みのみをサポートするからです。 プロビジョニングを行い、Adobe Analytics、Experience PlatformおよびCustomer Journey Analyticsへのログインに使用する IMS 組織。

*複数の IMS 組織からの Analytics データをマッピング* 機能を使用すると、データをマッピングするAdobeをリクエストできます。 この機能は、Analytics ソースコネクタを使用して、複数の *ソース* IMS 組織に存在するレポートスイートのデータを、1 つの *宛先* IMS 組織の一部であるデータセットにマッピングします。 例：

| イラスト | 説明 |
|---|---|
| ![&#x200B; 複数の IMS 組織間でのデータのマッピング &#x200B;](/help/getting-started/assets/map-data-across-ims-orgs.svg) | このマッピングを使用すると、IMS Organization 1、IMS Organization 2、および IMS Organization 3 に存在するレポートスイートについて、IMS Organization 3 内でプロビジョニングされたCustomer Journey Analytics内の 1 つの接続からレポートできます。 |

{style="table-layout:fixed"}

## 使用方法

*複数の IMS 組織からの Analytics データをマッピング* 機能を設定して有効にするには、Adobe アカウントマネージャーを通じてマッピングをリクエストする必要があります。 それには、次の手順を実行します。

1. 宛先 IMS 組織管理者として、レポートスイートをマッピングするすべてのソース IMS 組織管理者から承認メールをリクエストします。 次のテキストをメールのテンプレートとして使用し、ソース IMS 組織管理者の承認をリクエストできます。

   | サンプルメールテンプレート |
   | --- |
   | *会社名担当者*、選択した宛先組織に次の IMS 組織（ソース IMS 組織のリスト）へのアクセス権を付与するには、各 IMS 組織の管理者がデータへのアクセスを許可するために承認を送信する必要があります。 これにより、影響を受ける IMS 組織からデータアクセス権限を確実に付与できます。 適切な承認が得られるように、管理者の各組織の登録済みAdobe管理者に、名前と IMS 組織を表すこのメールに返信して、「承認します」と言って、この IMS 組織のデータが宛先組織 [ 宛先 IMS 組織をリスト ] に表示されることに対する承認を与えていることを示してください。 この管理者は、その IMS 組織の管理者としてAdobe システムに登録されている管理者である必要があることに注意してください。 |

1. 宛先 IMS 組織管理者として、複数のソース IMS 組織内のレポートスイートから宛先 IMS 組織へのマッピングをリクエストするメールをAdobe アカウント管理者に送信します。 ソース IMS 組織管理者から受信した承認メールを添付します。

アカウントマネージャーが、複数の組織から Analytics データをマッピングするリクエストが記載されたメールを受信すると、Adobe内でそのリクエストがレビューされます。 その他の質問、オプショントレーニング、その他の情報については、アカウントマネージャーから連絡があります。

承認されると、リクエストされたマッピングが作成され、通知が届きます。 ソース IMS 組織名は、Experience Platformの [Analytics レポートスイートのリスト &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) のレポートスイート名に追加されます。

## 制限とリスク

*複数の IMS 組織からの Analytics データをマッピング* 機能には、次の制限が適用されます。

* レポートスイートは、複数の組織をまたいで 1 回だけ接続できます。
* マッピングの削除をリクエストする前に、マッピングで宛先 IMS 組織として定義されている IMS 組織のすべての接続を削除する必要があります。
* ECID は、マッピングされたソース IMS 組織間で互換性がなく、宛先 IMS 組織とも互換性がありません。
* 宛先 IMS 組織で Analytics ソースコネクタを設定するのに十分な権限を持つユーザーは、マッピングされた任意のソース IMS 組織から Analytics データを取り込むことができます。 そのユーザーのソース IMS 組織に対する権限はチェックされません。
