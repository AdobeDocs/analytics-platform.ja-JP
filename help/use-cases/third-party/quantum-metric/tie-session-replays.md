---
title: Quantum Metric session replays to data in Customer Journey Analytics
description: Link Quantum Metric セッションでは、CJAデータを使用して再生し、「何」の背後にある「理由」をより深く理解します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: a03505aeb56f99b28f50819765a496705876b89c
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 2%

---

# Quantum Metric session replays to data in Customer Journey Analytics

Quantum Metric セッションの再生をCJAのデータとリンクさせることで、お客様は「何」の背後にある「理由」をより深く理解できます。  Workspaceを使用してフリクションのあるセッションを検出し、ハイパーリンクされたセッション ID をクリックして、Quantum Metric でのセッションの再生を調べることができます。  このデータにより、セッション内の動作を確認し、消費者の摩擦を引き起こす要因をより深く理解できます。  CJAと連動したセッションリプレイを通じて、お客様の行動に関する重要なコンテキストをエクスペリエンスに取り込むことができます。

## 前提条件

以下の手順では、Adobe Experience Platform Data Collection でタグを使用していることを前提としています。 組織でタグを使用しない場合は、これらのデータ収集方法を手動の web SDK実装に適応させることができます。

詳しくは、[Quantum Metric タグ拡張機能 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) のドキュメントを参照してください。

## 手順 1:Quantum Metric セッション ID に対応するスキーマフィールドの作成

このユースケースでは、データの送信先となる専用のスキーマフィールドが必要です。 このフィールドは、スキーマ内の任意の場所に作成し、好きな名前を付けることができます。 組織が名前や場所を好まない場合は、値の例を指定します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. **[!UICONTROL データ収集]**/**[!UICONTROL スキーマ]** に移動します。
1. リストから目的のスキーマを選択します。
1. 目的のオブジェクトの横にある ![ フィールドを追加 ](/help/assets/icons/AddCircle.svg) アイコンを選択します。 例えば、`Implementation Details` の隣です。
1. 右側で、目的の [!UICONTROL  名前 ] を入力します。 例：`qmSessionId`。
1. 目的の [!UICONTROL  表示名 ] を入力します。 例：`Quantum Metric session ID`。
1. [!UICONTROL  タイプ ] を **[!UICONTROL 文字列]** として選択します。
1. 「**[!UICONTROL 保存]**」を選択します。

## 手順 2:Quantum Metric タグ拡張機能を使用して Quantum Metric セッション ID を取得する

Adobe Experience Platformに送信するデータに Quantum Metric セッション ID を追加するには、次の手順に従います。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. **[!UICONTROL データ収集]**/**[!UICONTROL タグ]** に移動します。
1. 目的のタグプロパティを選択します。
1. 「**[!UICONTROL データ要素]**」を選択してから、「**[!UICONTROL データ要素の追加]**」を選択します。
1. 次の設定を行います。
   * **[!UICONTROL 名前]**: `Quantum Metric session ID`
   * **[!UICONTROL 拡張機能]**: [!UICONTROL Core]
   * **[!UICONTROL データ要素タイプ]**:[!UICONTROL  カスタムコード ]
1. 「**[!UICONTROL エディターを開く]**」ボタンを選択して、次のコードを貼り付けます。

   ```js
   // Check for the presence of the Quantum Metric session ID cookie
   const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
   if(qmCookie != null) return qmCookie;
   // If a cookie is not set, check local storage
   const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
   if (qmLocalStorage?.s != null) return qmLocalStorage.s;
   ```

1. 「**[!UICONTROL 保存]**」を選択します。

## 手順 3：データ要素を目的の XDM スキーマフィールドにマッピングする

データ要素に目的の値を取得するロジックが含まれたので、データ要素を XDM オブジェクトにマッピングします。

1. タグプロパティ内で、「**[!UICONTROL データ要素]**」を選択し、XDM オブジェクトを格納するデータ要素を選択します。
1. このデータ要素の右列で、スキーマフィールドの作成時に確立されたパスに移動します。
1. パーセント記号で囲まれたデータ要素の名前に値を設定します。 例：`%Quantum Metric session ID%`。
1. 「**[!UICONTROL 保存]**」を選択します。
1. ライブラリを追加し、変更を実稼動環境に公開します。

XDM オブジェクトが送信イベントアクション設定に既に含まれている場合は、変更が公開されるとデータが表示されます。

>[!NOTE]
>
>Web SDKは、Quantum Metric コードよりも高速に実行される場合があります。 この場合、セッション ID は後続のヒットで送信されます。 訪問者がバウンスした場合、これらのインスタンスではセッション ID は収集されません。

## 手順 3：使用可能なディメンションとしての Quantum Metric セッション ID の追加

実装で上記の変更が公開されたら、既存のデータビューを編集して、セッション ID をCustomer Journey Analyticsで使用可能なディメンションとして追加します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、トップメニューで **[!UICONTROL データビュー]** を選択します。
1. 目的の既存のデータビューを選択します。
1. 左側の「Quantum Metric session ID」フィールドを見つけて、中央の「ディメンション」領域にドラッグします。
1. 右側のウィンドウで、「[ 永続性 ](/help/data-views/component-settings/persistence.md) 設定を `Session` に設定します。
1. 「**[!UICONTROL 保存]**」を選択します。

## 手順 4：セッション ID ディメンションに対応するようにAnalysis Workspaceを設定する

Workspaceでフリーフォームテーブルを作成し、セッション ID 値が Quantum Metric に直接リンクするように設定します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、上部のメニューで ]**0}Workspace} を選択します。**[!UICONTROL 
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) を作成します。
1. セッション ID ディメンションをWorkspace キャンバスにドラッグします。
1. ディメンション列ヘッダーを右クリックし、「**[!UICONTROL すべてのディメンション項目のハイパーリンクを作成]**」を選択します。
1. **[!UICONTROL カスタム URL の作成]** を選択します。
1. 次の URL 構造を貼り付けます。

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. 「**[!UICONTROL 作成]**」をクリックします。

各セッション ID は、クリック可能なリンクになりました。 Analysis Workspace ディメンション項目にハイパーリンクを追加する方法について詳しくは、[ フリーフォームテーブルでのハイパーリンクの作成 ](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) を参照してください。

## 手順 5:Customer Journey Analyticsからのセッションの表示

セッションの再生を調べる興味深いセグメントが見つかったら、そのセグメントを、セッション ID のリンクを含むパネルに適用できます。 この表は、そのセグメント内のすべてのセッションを返します。いずれかのセッションをクリックすると、Quantum Metric で詳細を確認できます。

詳しくは、Quantum Metric の [ セッション再生のエンタープライズガイド ](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) を参照してください。 また、Quantum Metric のカスタマーサポート担当者に連絡するか、[Quantum Metric 顧客リクエストポータル ](https://community.quantummetric.com/s/public-support-page) を通じてリクエストを送信することもできます。
