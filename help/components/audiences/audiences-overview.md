---
title: Customer Journey Analytics オーディエンス公開の概要について学ぶ
description: Customer Journey Analytics でのオーディエンス公開の概念について説明します
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: e59bb52d5e9d79ba72036d5a00ed8abc69dcf735
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 79%

---

# オーディエンス公開の概要

>[!NOTE]
>
>オーディエンス分析とオーディエンス公開の違いを理解する：
>
>* **オーディエンス分析**:Experience Platform プロファイルデータセットからCustomer Journey Analytics接続にオーディエンスメンバーシップデータを取り込むことができます。 オーディエンス分析について詳しくは、[&#x200B; オーディエンス分析の概要 &#x200B;](/help/connections/audience-analysis/audience-analysis-overview.md) を参照してください。
>* **オーディエンスの公開**:Customer Journey Analyticsで検出されたオーディエンスを作成してAdobe Experience Platformに公開し、顧客のターゲティングやパーソナライゼーションに使用できます。

Customer Journey Analyticsで検出されたオーディエンスを作成してAdobe Experience Platformの [&#x200B; リアルタイム顧客プロファイル &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/home) に公開し、顧客のターゲティングやパーソナライゼーションに使用できます。 （Experience Platform プロファイルデータセットからCustomer Journey Analytics接続にオーディエンスメンバーシップデータを取り込む方法については、[Audience Analysis の概要 &#x200B;](/help/connections/audience-analysis/audience-analysis-overview.md) を参照してください。）

公開オーディエンスを使用すると、Customer Journey Analytics 内で見つかったインサイトを活用してアクションを行う明確な方法がわかります。アクションの例として、次のようなものがあります。

* Adobe Journey Optimizer でジャーニーにオーディエンスを使用する。
Experience Platform に公開されているオーディエンスの使用について詳しくは、Journey Optimizer ドキュメントの[オーディエンスの基本を学ぶ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences)を参照してください。
* Experience Platform の宛先を介してオーディエンスをサードパーティにエクスポートする。
* Customer Journey Analytics のイベントベースのデータから派生する有用な属性を使用して、リアルタイム顧客プロファイルを充実させる。
* オーディエンスの公開後に、最少の待ち時間でこれらをすべて行います。
詳しくは、[オーディエンスを作成および公開](/help/components/audiences/publish.md)の[待ち時間に関する考慮事項](/help/components/audiences/publish.md#latency-considerations)を参照してください。
* 1 回限りのオーディエンスまたは繰り返しオーディエンスの公開。

Customer Journey Analytics で作成するオーディエンスは、プロファイルで有効になっているデータセットに基づいている必要はありません。プロファイルに関連するデータセットやスキーマを有効にせずに、履歴データを Experience Platform に取り込むことができます。次に、これらのデータセットを使用して、Customer Journey Analytics で関連するオーディエンスを検出し、これらのオーディエンスを Experience Platform のリアルタイム顧客プロファイルに公開して、アクティベーションを行います。

## 主な用語

**オーディエンス**：名前空間と、その名前空間に関連する特定の ID の両方を持つ ID のセットまたはリスト。オーディエンスは、Adobe Experience Platform およびこれを基にしたアプリケーション（Customer Journey Analytics など）から転送できます。オーディエンスには、名前空間を混在させて含めることができます。

**セグメント**：一連のデータを一定期間評価した場合に、データのサブセットを生成する一連のルール。セグメントは、他のサポートサービスと組み合わせて、オーディエンスを作成するプロセスで使用できます。セグメントは Customer Journey Analytics で定義および管理されます。

## 権限

* 管理者には、Adobe Admin Console での&#x200B;**[!UICONTROL オーディエンス公開]**&#x200B;権限が自動的に付与されます。

* 管理者と製品プロファイル管理者は、個々のユーザーに&#x200B;**[!UICONTROL オーディエンスの作成]**&#x200B;および&#x200B;**[!UICONTROL オーディエンスの表示]**&#x200B;権限を付与できます。詳しくは、[ユーザーレベルのアクセス制御](/help/technotes/access-control.md#user-level-access)を参照してください。

* 管理者には Adobe Experience Platform での&#x200B;**[!UICONTROL プロファイル管理]**&#x200B;権限も必要です。

## データガバナンスと同意

Customer Journey Analytics でオーディエンスを公開すると、オーディエンスで使用されるフィールドに添付されたデータガバナンスラベルとポリシーが記録されます。任意の Adobe Experience アプリケーションでオーディエンスがアクティブ化されると、関連するすべてのデータガバナンスラベルおよびポリシーをそのオーディエンスで使用でき、適切に実施できるようになります。[同意の詳細情報](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#consent-policy)。

## 次の手順

* [オーディエンスの作成と公開](/help/components/audiences/publish.md)
* [オーディエンスの管理](/help/components/audiences/manage.md)
