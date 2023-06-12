---
title: CJA オーディエンス公開の概要
description: Customer Journey Analytics でのオーディエンス公開の概念について説明します
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 7b86650cd3475a203d597baeec2ec2152e082b10
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 83%

---

# CJA オーディエンス公開の概要

Customer Journey Analytics(CJA) で検出されたオーディエンスを作成し、に公開できるようになりました。 [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja) (RTCDP) をAdobe Experience Platformで利用し、お客様のターゲティングとパーソナライゼーションをおこなう。

公開オーディエンスを使用すると、CJA 内で見つかったインサイトを活用してアクションを行う明確な方法がわかります。アクションの例として、次のようなものがあります。

* Adobe Journey Optimizer でジャーニーにオーディエンスを使用する。
* Experience Platform の宛先を介してオーディエンスをサードパーティにエクスポートする。
* CJA のイベントベースのデータから派生する有用な属性を使用して、リアルタイム顧客プロファイルを充実させる。
* オーディエンスの公開後に、最小限の待ち時間でこれらをすべて行います。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=ja#latency)
* 1 回限りのオーディエンスまたは繰り返しオーディエンスの公開.

CJA で作成するオーディエンスは、プロファイルに対して有効になっているデータセットに基づいている必要はありません。 プロファイルに関連付けられたデータセットやExperience Platformを有効にすることなく、履歴データを取り込むことができます。 次に、これらのデータセットを使用して、CJA で関連するオーディエンスを検出し、アクティベーションのために、Experience Platform内の RTCDP に公開します。

## 主な用語

**オーディエンス**：名前空間と、その名前空間に関連する特定の ID の両方を持つ ID のセットまたはリスト。オーディエンスは、Adobe Experience Platform およびこれを基にしたアプリケーション（CJA など）から転送できます。オーディエンスには、名前空間を混在させて含めることができます。

**フィルター**：一連のデータを一定期間評価した場合に、データのサブセットを生成する一連のルール。フィルターは、他のサポートサービスと組み合わせて、オーディエンスを作成するプロセスで使用できます。フィルターは CJA で定義および管理されます。

**フィルター**&#x200B;と&#x200B;**セグメント**：CJA は、「セグメント」の概念を使用しません。代わりに、「フィルター」を使用します。いずれにも類似したロジックを含めることができる一連のルールですが、生成される出力は異なります。フィルターは、分析目的でデータセットを絞り込むために使用します。セグメントは、アクティベーションに使用できる ID のリストを生成するために使用されます。セグメントはリアルタイム顧客プロファイルでオーディエンスを生成しますが、フィルター（単独）では生成されません。CJA オーディエンスの公開は、CJA フィルターを使用して、リアルタイム顧客プロファイルで利用できるオーディエンスを作成するプロセスです。

## 権限

* 管理者には、Adobe Admin Console での&#x200B;**[!UICONTROL オーディエンス公開]**&#x200B;権限が自動的に付与されます。

* 管理者は、この権限を個々のユーザーに付与できます。

* 管理者には Adobe Experience Platform での&#x200B;**[!UICONTROL プロファイル管理]**&#x200B;権限も必要です。

## データガバナンスと同意

CJA でオーディエンスを公開すると、オーディエンスで使用されるフィールドに添付されたデータガバナンスラベルとポリシーが記録されます。任意の Adobe Experience アプリケーションでオーディエンスがアクティブ化されると、関連するすべてのデータガバナンスラベルおよびポリシーをそのオーディエンスで使用でき、適切に実施できるようになります。[同意の詳細情報](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ja#consent-policy)。

## 次の手順

* [オーディエンスの作成と公開](/help/components/audiences/publish.md)
* [オーディエンス管理](/help/components/audiences/manage.md)
