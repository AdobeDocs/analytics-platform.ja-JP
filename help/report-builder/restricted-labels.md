---
title: Report Builder の制限ラベルとは
description: Report Builder の制限ラベルについて説明します
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: ht
source-wordcount: '311'
ht-degree: 100%

---

# Report Builder の制限ラベル

一般に、Customer Journey Analytics のデータガバナンス関連の設定は、Adobe Experience Platform から継承されます。CJA と Adobe Experience Platform のデータガバナンスの統合により、機密性の高い CJA データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platform で使用されるデータセットに関して作成されたプライバシーラベルとポリシーは、 CJA データビューワークフローで表示できます。 これらのラベルにより、ユーザーが機密性の高いフィールドから指標やディメンションを作成しようとしても、それができなかったり警告が表示されたりします。データセットについて詳しくは、[データセットの概要](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja)を参照してください。

また、データが CJA から（レポート、書き出し、API などを介して）書き出されると、警告またはラベルが付加されて、特定の方法で処理する必要のある機密情報がレポートに含まれていることをユーザーに知らせます。

この統合により、コンプライアンスを管理しやすくなります。 組織のデータ管理人は、使用を制限するポリシーを設定できます。 その結果、CJA ユーザーは、データ管理人に定義されたポリシーにデータが準拠していることを認識したうえで、より自信を持ってデータを使用できます。

詳しくは、[Customer Journey Analytics とデータガバナンス](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=ja)を参照してください。

## Report Builder の制限付きデータの表示

CJA では、次の 2 つのアドビが定義するポリシーが表示され、レポート、ダウンロードおよび共有に影響します。

* Analytics の適用ポリシー
* ダウンロードの適用ポリシー

これらのポリシーの影響を受けるコンポーネントはグレー表示されます。 ポリシーが適用されているコンポーネントの上にマウスポインターを置くと、次の内容を示すメモが表示されます。**このデータの使用を禁止するポリシーがこのフィールドに適用されました。**&#x200B;詳しくは、[ラベルとポリシー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=ja)を参照してください。

![](assets/rb-restricted-label.png)

## 制限付きデータを含むレポートの更新

ユーザーが後で制限されるデータ要素を含む Report Builder レポートを作成した場合、レポートを更新すると、エラーメッセージが表示されます。

![](assets/error-restricted-data.png)
