---
title: Report Builderの制限ラベル
description: Report Builderの制限ラベルについて説明します。
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 40%

---

# Report Builder の制限ラベル

通常、Customer Journey Analyticsのデータガバナンス関連の設定は、Experience Platformから継承されます。 Customer Journey AnalyticsとExperience Platform Data Governance の統合により、Customer Journey Analyticsの機密データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platformで使用されるデータセットに関して作成されたプライバシーラベルとポリシーは、Customer Journey Analytics データビューワークフローで表示できます。 これらのラベルにより、ユーザーが機密性の高いフィールドから指標やディメンションを作成しようとしても、それができなかったり警告が表示されたりします。 データセットについて詳しくは、[データセットの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview)を参照してください。

また、データが Adobe Customer Journey Analytics から（レポート、書き出し、API などを介して）書き出されると、特定の方法で処理する必要がある機密情報がレポートに含まれていることをユーザーに知らる警告またはラベルが付加されます。

この統合により、コンプライアンスを管理できるようになります。 組織のデータ管理人は、使用を制限するポリシーを設定できます。その結果、Adobe Customer Journey Analytics ユーザーは、データ管理人により定義されたポリシーにデータが準拠していることを認識したうえで、より自信を持ってデータを使用できます。

詳しくは、[Customer Journey Analytics とデータガバナンス](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-privacy/privacy-overview)を参照してください。

## 制限付きデータの表示

Customer Journey Analyticsでは、次の 2 つのAdobeで定義されるポリシーが表示され、レポート、ダウンロードおよび共有に影響します。

* Analytics の適用ポリシー
* ダウンロードの適用ポリシー

これらのポリシーの対象となるコンポーネントはグレー表示され、「![InfoOutline](/help/assets/icons/InfoOutline.svg)」アイコンが表示されます。 情報アイコンにポインタを合わせると、次の内容を示すメモが表示されます。**[!UICONTROL このデータの使用を禁止するポリシーがこのフィールドに適用されました]**。

詳しくは、[&#x200B; ラベルとポリシー &#x200B;](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance) を参照してください。


![&#x200B; データの使用禁止を示すポリシーノート &#x200B;](assets/restricted-label.png){zoomable="yes"}


## 制限付きデータを含むレポートの更新

ユーザーが後で制限されるデータ要素を含む Report Builder レポートを作成した場合、レポートを更新すると、エラーメッセージが表示されます。

![&#x200B; データ要素が後で制限された後に表示されるエラーメッセージ。](assets/error-restricted-data.png){width="100%" zoomable="yes"}
