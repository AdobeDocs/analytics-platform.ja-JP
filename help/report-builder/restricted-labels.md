---
title: Report Builderの制限ラベル
description: Report Builderの制限付きラベルについて説明します。
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: f2ef16dc-055a-4bb7-baa5-7039653f3966id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 39%

---

# Report Builder の制限ラベル

通常、Customer Journey Analyticsのデータガバナンス関連の設定は、Experience Platformから継承されます。 Customer Journey AnalyticsとExperience Platform Data Governanceの統合により、機密性の高いCustomer Journey Analytics データへのラベル付けとプライバシーポリシーの適用が可能になります。

Experience Platformで使用されるデータセットに作成されたプライバシーラベルとポリシーは、Customer Journey Analytics データビューのワークフローで表示できます。 これらのラベルは、機密フィールドから指標やディメンションを作成するユーザーを停止または警告します。 データセットについて詳しくは、[データセットの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview)を参照してください。

また、データが Adobe Customer Journey Analytics から（レポート、書き出し、API などを介して）書き出されると、特定の方法で処理する必要がある機密情報がレポートに含まれていることをユーザーに知らる警告またはラベルが付加されます。

この統合により、コンプライアンスを管理できます。 組織のデータ管理人は、使用を制限するポリシーを設定できます。 その結果、Adobe Customer Journey Analytics ユーザーは、データ管理人により定義されたポリシーにデータが準拠していることを認識したうえで、より自信を持ってデータを使用できます。

詳しくは、[Customer Journey Analytics とデータガバナンス](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-privacy/privacy-overview)を参照してください。

## 制限付きデータの表示

Customer Journey Analyticsでは、レポート、ダウンロード、共有に影響する、Adobeで定義された2つのポリシーが表示されます。

* Analytics の適用ポリシー
* ダウンロードの適用ポリシー

これらのポリシーの対象となるコンポーネントはグレー表示され、![InfoOutline](/help/assets/icons/InfoOutline.svg) アイコンがあります。 情報アイコンにカーソルを合わせると、次の情報を示すメモが表示されます。**[!UICONTROL このデータの使用を禁止するポリシーがこのフィールドに適用されました]**。

詳しくは、[ ラベルとポリシー](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance)を参照してください。


![ データの使用禁止を示すポリシーノート。](assets/restricted-label.png){zoomable="yes"}


## 制限付きデータを含むレポートを更新する

ユーザーが後で制限されるデータ要素を含む Report Builder レポートを作成した場合、レポートを更新すると、エラーメッセージが表示されます。

![ データ要素が後で制限された後に表示されるエラーメッセージ。](assets/error-restricted-data.png){width="100%" zoomable="yes"}
