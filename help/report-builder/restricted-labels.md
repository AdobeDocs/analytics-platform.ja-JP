---
title: Report Builder内の制限付きラベルとは
description: Report Builderの制限付きラベルを記述します
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# Report Builderの制限付きラベル

通常、データガバナンス関連のCustomer Journey Analyticsは、Adobe Experience Platformから継承されます。 CJA とAdobe Experience Platform Data Governance の統合により、機密の CJA データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platformが使用するデータセットで作成されたプライバシーラベルとポリシーは、 CJA データビューワークフローで表示できます。 これらのラベルは、機密性の高いフィールドから指標やディメンションを作成するユーザーに対して、停止または警告を出します。 データセットについて詳しくは、 [データセットの概要](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja)

また、データが CJA から（レポート、書き出し、API などを介して）書き出されると、警告またはラベルが追加され、特定の方法で処理する必要のある機密情報がレポートに含まれていることをユーザーに通知します。

この統合により、コンプライアンスをより簡単に管理できます。 組織のデータ管理人は、使用を制限するポリシーを設定できます。 その結果、CJA ユーザーは、データ管理人が定義したポリシーに準拠していることを知り、より自信を持ってデータを使用できます。

詳しくは、 [Customer Journey Analyticsとデータガバナンス](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## 制限されたデータをReport Builder

CJA では、次の 2 つのAdobe定義のポリシーが表示され、レポート、ダウンロードおよび共有に影響します。

* Analytics ポリシーの適用
* ダウンロードポリシーの適用

これらのポリシーの影響を受けるコンポーネントはグレー表示されます。 ポリシーが適用されているコンポーネントの上にマウスポインターを置くと、次の内容を示すメモが表示されます。 **このデータの使用を禁止するポリシーがこのフィールドに適用されました。** 詳しくは、 [ラベルとポリシー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## 制限されたデータを含むレポートを更新

ユーザーが後で制限されるデータ要素を含むReport Builderレポートを作成した場合、レポートが更新されると、エラーメッセージが表示されます。

![](assets/error-restricted-data.png)
