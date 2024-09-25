---
title: Customer Journey Analyticsオーディエンス公開の概要について説明します
description: Customer Journey Analytics でのオーディエンス公開の概念について説明します
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 4d71aaaaa0ac0162588dd6767e6c6209676dfc18
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 50%

---

# Customer Journey Analyticsオーディエンス公開の概要

Customer Journey Analyticsで検出されたオーディエンスを作成してAdobe Experience Platformの [ リアルタイム顧客プロファイル ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja) に公開し、顧客のターゲティングやパーソナライゼーションに使用できるようになりました。

オーディエンスを公開すると、Customer Journey Analytics内で見つかったインサイトを活用してアクションを実行する明確な方法がわかります。 アクションの例として、次のようなものがあります。

* Adobe Journey Optimizer でジャーニーにオーディエンスを使用する。
* Experience Platform の宛先を介してオーディエンスをサードパーティにエクスポートする。
* Customer Journey Analyticsのイベントベースのデータから派生する有用な属性を使用して、リアルタイム顧客プロファイルを充実させる。
* オーディエンスの公開後に、最小限の待ち時間でこれらをすべて行います。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* 1 回限りのオーディエンスまたは繰り返しオーディエンスを公開する。

Customer Journey Analyticsで作成するオーディエンスは、プロファイルで有効になっているデータセットに基づいている必要はありません。 プロファイルに関連するデータセットやスキーマを有効にすることなく、履歴データをExperience Platformに取り込むことができます。 次に、これらのデータセットを使用して、関連するオーディエンスをCustomer Journey Analyticsで検出し、アクティベーション目的で、これらのオーディエンスをExperience Platformでリアルタイム顧客プロファイルに公開します。

## 主な用語

**オーディエンス**：名前空間と、その名前空間に関連する特定の ID の両方を持つ ID のセットまたはリスト。オーディエンスは、Adobe Experience Platformとその上に配置されたアプリケーション（Customer Journey Analyticsなど）から転送できます。 オーディエンスには、名前空間を混在させて含めることができます。

**フィルター**：一連のデータを一定期間評価した場合に、データのサブセットを生成する一連のルール。フィルターは、他のサポートサービスと組み合わせて、オーディエンスを作成するプロセスで使用できます。フィルターはCustomer Journey Analyticsで定義および管理されます。

**フィルター** と **セグメント**:Customer Journey Analyticsは、「セグメント」の概念を使用しません。代わりに、「フィルター」を使用します。 いずれにも類似したロジックを含めることができる一連のルールですが、生成される出力は異なります。フィルターは、分析目的でデータセットを絞り込むために使用します。セグメントは、アクティベーションに使用できる ID のリストを生成するために使用されます。セグメントはリアルタイム顧客プロファイルでオーディエンスを生成しますが、フィルター（単独）では生成されません。Customer Journey Analyticsオーディエンスの公開は、Customer Journey Analyticsフィルターを使用して、リアルタイム顧客プロファイルで利用できるオーディエンスを作成するプロセスです。

## 権限

* 管理者には、Adobe Admin Console での&#x200B;**[!UICONTROL オーディエンス公開]**&#x200B;権限が自動的に付与されます。

* 管理者は、この権限を個々のユーザーに付与できます。

* 管理者には Adobe Experience Platform での&#x200B;**[!UICONTROL プロファイル管理]**&#x200B;権限も必要です。

## データガバナンスと同意

Customer Journey Analyticsでオーディエンスを公開すると、オーディエンスで使用されるフィールドに添付されたデータガバナンスラベルとポリシーが記録されます。  任意の Adobe Experience アプリケーションでオーディエンスがアクティブ化されると、関連するすべてのデータガバナンスラベルおよびポリシーをそのオーディエンスで使用でき、適切に実施できるようになります。[同意の詳細情報](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#consent-policy)。

## 次の手順

* [オーディエンスの作成と公開](/help/components/audiences/publish.md)
* [オーディエンス管理](/help/components/audiences/manage.md)
