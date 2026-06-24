---
description: 管理者は、データ辞書の正常性を監視する責任があります。 これには、コンポーネントがデータを収集しているか、承認されているか、説明が含まれているか、重複がないかが含まれます。
title: データ辞書の正常性の監視
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
TQID: https://experienceleague.adobe.com/RKh01bcmVkoZ2wkHDvBM-oX9rRagVaOqK4fn2A-IpaI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df28738e-9c71-4aa8-929e-edde22340cc6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: b7493ad9283b5830c36b8e3ac942bf9295b693f8
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 88%

---

# データ辞書の正常性の監視 {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="データディクショナリ"
>abstract="このオプションを選択すると、プライマリコンポーネントは、複製コンポーネントにアクセスできるすべてのユーザー（所有者と、コンポーネントが共有されているすべてのユーザー）と共有されます。 その後、これらのユーザーは、今後のプロジェクトのコンポーネントリストからプライマリコンポーネントを選択できます。 ただし、統合された重複コンポーネントの所有者であっても、コンポーネントを編集できません。 <br/>このオプションは、プライマリコンポーネントがセグメント、計算指標または日付範囲である場合にのみ使用できます。 指標とディメンションは、すべてのユーザーが常に使用できます。
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_share_primary"
>title="プライマリコンポーネントを共有"
>abstract="このオプションを選択すると、プライマリコンポーネントは、複製コンポーネントにアクセスできるすべてのユーザー（所有者と、コンポーネントが共有されているすべてのユーザー）と共有されます。 その後、これらのユーザーは、今後のプロジェクトのコンポーネントリストからプライマリコンポーネントを選択できます。 ただし、統合された重複コンポーネントの所有者であっても、コンポーネントを編集できません。 <br/>このオプションは、プライマリコンポーネントがセグメント、計算指標または日付範囲である場合にのみ使用できます。 指標とディメンションは、すべてのユーザーが常に使用できます。
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_delete_duplicates"
>title="置き換えられた重複を削除"
>abstract="このオプションを選択すると、統合された重複は使用できなくなります。 重複を引き続き使用する場合は、このオプションの選択を解除します。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics管理者は、健全なデータ要素を管理する責任があります。

## 正常なデータ辞書の特徴

正常なデータ辞書とは、すべてのコンポーネントが次のとおりであることです。

* 使用され、データを収集している

* ユーザーが最適な使用方法を把握できるように役立つ説明が含まれている

* 不要な重複が発生しない

* 管理者によって承認されている

## データ辞書の正常性の確認

データ辞書で正常性の問題を特定するには：

1. Analysis Workspace プロジェクトを開きます。

1. Analysis Workspace の左側にある「データ辞書」アイコンを選択します （データ辞書にアクセスする別の方法については、[データ辞書の概要](/help/components/data-dictionary/data-dictionary-overview.md)の「データ辞書へのアクセス」を参照してください）。

   データ辞書ウィンドウが表示されます。

   ![辞書の正常性を示すデータ辞書の管理者ビュー](assets/data-dictionary-admin.png)

1. ドロップダウンメニューで正しいデータビューが選択されていることを確認します。

1. 「[!UICONTROL **要素の正常性**]」タブで、次のいずれかのオプションの横にある「[!UICONTROL **表示**]」を選択します。

   * [!UICONTROL **コンポーネントの説明がありません**]

   * [!UICONTROL **コンポーネントに重複があります**]

   * [!UICONTROL **コンポーネントにデータが接続されていません**]

   選択した内容に応じて、適切なセグメントがデータ要素に適用され、関連するコンポーネントのみが表示されます。

1. 任意のコンポーネントを編集して、データ辞書の正常性を改善します。 データ辞書でコンポーネントを編集する方法については、[データ辞書でのコンポーネントエントリの編集](/help/components/data-dictionary/edit-entries-data-dictionary.md)を参照してください。
