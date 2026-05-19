---
title: Quantum Metric Friction イベントをCustomer Journey Analyticsに追加する
description: Quantum Metricで収集したフリクションイベントをCustomer Journey Analyticsの行動データに追加し、CJAのインサイトに深みを加えます。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
autotag-review: '2026-05-19T09:50:19.249Z'
TQID: 'https://experienceleague.adobe.com/ez4GO2CJ0g-nOGI4GlYrZQhuGKxQRvWoXPe4vcHGznU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 685
ht-degree: 1%

---

# Quantum Metric Friction イベントをCustomer Journey Analyticsに追加する

Quantum Metricは、ページ読み込みの遅さ、ページ読み込みエラー、レイジクリックなどのフリクションイベントを収集します。 これらのイベントは、ユーザージャーニーの補完的なイベントとしてCustomer Journey Analyticsに渡すことができます。 この結合データを使用すると、下流の指標に対する摩擦の影響をより深く理解できます。

## 前提条件：

このユースケースには、次の2つの要件があります。

* Quantum Metricの&#x200B;**開発Ops** パッケージの使用権限が必要です。
* Adobe Experience Platform Data Collectionでタグを使用する必要があります。

## 手順1：量子指標摩擦イベントに対応するスキーマフィールドを作成する

このユースケースでは、データを送信するための専用のスキーマフィールドが必要です。 このフィールドをスキーマ内の任意の場所に作成し、好きな名前を付けることができます。 組織で名前または場所に関する環境設定がない場合は、値の例が提供されます。

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. **[!UICONTROL データ収集]** > **[!UICONTROL スキーマ]**&#x200B;に移動します。
1. リストから目的のスキーマを選択します。
1. 目的のオブジェクトの横にある「![&#x200B; フィールドを追加」アイコン &#x200B;](/help/assets/icons/AddCircle.svg)を選択します。 例えば、`Implementation Details`の横です。
1. 右側に、必要な[!UICONTROL 名前]を入力します。 例：`qmErrorName`。
1. 目的の[!UICONTROL 表示名]を入力します。 例：`Quantum Metric error name`。
1. [!UICONTROL Type]を&#x200B;**[!UICONTROL String]**&#x200B;として選択します。
1. 「**[!UICONTROL 保存]**」を選択します。

## ステップ 2：量子指標タグ拡張機能を使用してフリクションイベントをキャプチャする

量子指標データを含めるようにタグを設定する方法については、Adobe Experience Platform Destinations ガイドの[量子指標の拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/analytics/quantum-metric)を参照してください。 この拡張機能を使用すると、既存のデータセットにさらに行が渡されます。

Adobe Experience Platform Data Collectionのタグを使用して、摩擦イベントの名前を手動で設定し、XDM オブジェクトに含めて分析できるようにします。 これを行う方法の1つは、ルールのカスタムコードにあります。

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

次に、動的に設定されたデータ要素をXDM オブジェクトに追加します。

![量子指標エラー名のスクリーンショット &#x200B;](assets/error-name.png)

## 手順3:Customer Journey Analyticsのデータビューに1つ以上のディメンションと指標を追加する

既存のデータビューを編集して、セッション IDをCustomer Journey Analyticsで使用可能なディメンションとして追加します。

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. Customer Journey Analyticsに移動し、上部メニューの&#x200B;**[!UICONTROL Data management]**&#x200B;から&#x200B;**[!UICONTROL Data views]**&#x200B;を選択します（オプション）。
1. 目的の既存のデータビューを選択します。
1. 左側のQuantum Metric friction event フィールドのリストを見つけて、中央の指標エリアにドラッグします。
1. 右側のペインで、[値を含める/除外](/help/data-views/component-settings/include-exclude-values.md)設定を、追跡する目的のフリクションイベントに設定します。 同じ指標に複数のフリクションイベントを追加して、組み合わせることができます。 また、フリクションイベントフィールドの別のコピーを指標エリアにドラッグして、他のフリクションイベントを別の指標として追跡することもできます。
1. 必要なすべてのディメンションと指標を作成したら、**[!UICONTROL 保存]**&#x200B;をクリックします。
1. エラーイベントの完全なリストについては、量子指標のドキュメントを参照してください。 さらに質問がある場合は、Quantum Metric カスタマーサポート担当者にお問い合わせいただくか、[Quantum Metric カスタマーリクエストポータル &#x200B;](https://community.quantummetric.com/s/public-support-page)からリクエストを送信してください。

## ステップ 4:Analysis Workspaceの残りのデータでディメンションと指標を使用する

収集した量子指標のフリクションイベントデータと他の訪問者データを組み合わせることで、Customer Journey Analyticsの他のディメンションや指標と同じように使用できます。

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. Customer Journey Analyticsに移動し、上部メニューの&#x200B;**[!UICONTROL Workspace]**&#x200B;を選択します。
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. [&#x200B; フリーフォームテーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)を作成します。
1. 目的のディメンションと指標をWorkspaceキャンバスにドラッグして分析します。

![&#x200B; フリクショングラフ &#x200B;](assets/friction-graph.png)

考えられる分析のアイデアは次のとおりです。

* トレンド摩擦イベントデータの推移
* フォールアウトまたはfunnel ビジュアライゼーションでは、Customer Journey Analytics イベントをステップとして追加し、量子指標フリクション イベントをステップとして追加します。 このレポートでは、訪問者が最も頻繁に問題に遭遇する場所を確認できます。
* 顧客がつまずきやすい出来事を経験した訪問者に対して、セグメントを作成し適用することで、より詳細な分析を実現します
