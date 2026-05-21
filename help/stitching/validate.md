---
title: Customer Journey AnalyticsでのId照合の検証
description: Customer Journey AnalyticsでID ステッチを検証する方法について説明します。 ステッチの前後で認証率とIDを測定します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: b9b73926-6502-4a48-ba73-c784f80950d3
TQID: https://experienceleague.adobe.com/Ognl-DJP3hlQmBPGQE5J4c2fw6jjBsO-g-NjSenmafQ
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 1757
ht-degree: 1%

---

# ステッチの検証

[ID ステッチ ](/help/stitching/overview.md) （または単にステッチ）の目標は、クロスチャネル分析に対するイベントデータセットの適合性を高めることです。 この昇格は、データセット内のすべてのデータ行に、使用可能な目的の最上位IDが含まれている場合に達成されます。 この昇格により、次のことが可能になります。

* 匿名のユーザーを除外することなく、ユーザー中心のレポートを作成できます。
* 複数のデバイスを1人のユーザーに接続します。
* チャネルをまたいで顧客とつながる。

この記事では、1つ以上の新しく作成されたステッチされたデータセットの高度を測定し、ステッチがこれらのメリットをもたらしているという確信を提供するための分析方法の概要を説明します。

分析方法には、管理者が通常アクセスできる[ データビューコンポーネント設定](/help/data-views/component-settings/overview.md)が含まれます。 また、このモデルでは、Analysis Workspaceプロジェクトの担当者が、計算指標とビジュアライゼーションを作成する必要があります。

これらの分析方法は、フィールドベースのステッチングとグラフベースのステッチングの両方に使用できますが、一部の要素は、特にグラフベースのステッチシナリオでは、データセットに存在しない場合があります。 このような欠落している要素があると、Analysis Workspaceで直接リフトを計算することが難しくなります。

>[!NOTE]
>
>1つ以上のデータセットをつなぎ合わせて（検証）することで、最終的により優れた分析とインサイトが得られます。 ただし、この記事では、Experience Platformのすべてのデータセットが同じID名前空間に揃えられたCustomer Journey Analytics設定の全体的な値については説明しません。 また、これらのデータセットはすべてつながっており、カスタマージャーニー全体にわたって分析を実行できます。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Stitching enablement and validation](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/visitor-id/stitching-enablement-and-validation){target="_blank"}を参照してください。

>[!ENDSHADEBOX]



## 接続の検証での結合

この節では、接続インターフェイスで有効にしたステッチを検証する方法について詳しく説明します。

### 接続の推奨事項

接続インターフェイスで有効にしたステッチを検証するには、**[!UICONTROL データセットのバックフィル]**&#x200B;の短い期間と代表的な期間を選択します。 例えば、1週間です。

次の例では、イベントデータセットをつなぎ合わせます。 イベントデータセットを追加するテスト接続を設定しました。 このデータセットでは、**[!UICONTROL ECID]** **[!UICONTROL 名前空間]**&#x200B;を&#x200B;**[!UICONTROL 永続的ID]**&#x200B;として、**[!UICONTROL 訪問者のハッシュ化された電子メールアドレス（directMarketing.hashedEmail）]**&#x200B;を&#x200B;**[!UICONTROL 人物ID]**&#x200B;として定義します。 このステッチを検証するには、短い期間（2026年1月24日 – 2026年2月10日）の&#x200B;**[!UICONTROL データセットのバックフィル]**&#x200B;を定義します。 この小さなウィンドウを使用して、ステッチが意図したとおりに機能するかどうかを検証します。

![ ステッチ設定](/help/stitching/assets/stitching-config.png)

### データビューの前提条件

ステッチ検証を行うには、ステッチされたデータセットに必要なすべてのディメンションと指標がデータビューで定義されていることを確認する必要があります。 先ほど定義した接続に基づいて、データビューを作成します。 データビュー設定の&#x200B;**[!UICONTROL コンポーネント]**&#x200B;手順では、次のことが必要です。

* **[!UICONTROL 指標とディメンション]**&#x200B;から&#x200B;**[!UICONTROL ID名前空間]**&#x200B;をディメンションとして&#x200B;**[!UICONTROL ディメンション]** リストに追加します。

  ![ID 名前空間](/help/stitching/assets/identity-namespace.png)


* **[!UICONTROL スキーマフィールド]**&#x200B;から、イベントのユーザーIDとして定義した&#x200B;**[!UICONTROL 訪問者ハッシュ化された電子メールアドレス識別子]**&#x200B;を選択します。 フィールドをディメンションとして&#x200B;**[!UICONTROL ディメンション]** リストに追加し、指標として&#x200B;**[!UICONTROL 指標]** リストに追加します。 指標の&#x200B;**[!UICONTROL コンポーネント名]**&#x200B;を`Email set`に変更します。

  ![電子メール ID](/help/stitching/assets/email-identifier.png)

データビューが保存されていることを確認します。

### Workspace プロジェクトの作成

Workspaceで、新しいプロジェクトを作成し、フリーフォームテーブルを使用して、ステッチ設定をテストするために定義した日付範囲の&#x200B;**[!UICONTROL 電子メールセット]**&#x200B;指標を表示します。 このフリーフォームテーブルには、メール アドレスを持つイベントがステッチ前に表示されます。

![概要フリーフォームテーブルの結合 – メールセット ](/help/stitching/assets/workspace-emailset.png)

メール アドレスがステッチ プロセスの後に設定されているイベントを確認するには、計算指標`Email stitched namespace`を定義します。 この計算指標は、**[!UICONTROL ID名前空間]**&#x200B;がハッシュ化されたメール名前空間`email_lc_sha256`と等しい&#x200B;**[!UICONTROL イベント]**&#x200B;を見ています。

![ ステッチの概要 – メール ステッチ済み名前空間の計算指標](/help/stitching/assets/cm-email-stitched-namespace.png)

新しい計算指標&#x200B;**[!UICONTROL Email stitched namespace]**&#x200B;をフリーフォームテーブルに追加すると、ステッチプロセスの後にメールアドレスを持つイベントの数が増加します。

![概要フリーフォームテーブルの結合 – メールセットと結合](/help/stitching/assets/workspace-emailset-stitched.png)

さらに2つの計算指標を定義することで、さらにインサイトを得ることができます。

* **[!UICONTROL メール認証率]**。 この計算指標は、ステッチプロセスの前の認証率を決定します。

  ![電子メール認証率の計算指標の定義](/help/stitching/assets/cm-email-authentication-rate.png)

* **[!UICONTROL ステッチ認証率]**。 この計算指標は、ステッチプロセス後の認証率を決定します。

  ![ ステッチされた認証率の計算指標の定義](/help/stitching/assets/cm-stitched-authentication-rate.png)

これら2つの計算指標をフリーフォームテーブルに追加すると、ステッチされたイベントの増加を確認できます。

![概要フリーフォームテーブルの結合 – 認証済み](/help/stitching/assets/workspace-authenticated.png)

より多くのインサイトを得るには、さらに2つの計算指標（**[!UICONTROL パーセント増加]**&#x200B;および&#x200B;**[!UICONTROL 上昇率]**）をフリーフォームテーブルに追加して、ステッチ設定の影響を確認できます。

![概要フリーフォームテーブルのステッチ – 認証済み上昇率](/help/stitching/assets/workspace-authenticated-lift.png)



## ステッチの検証をリクエスト

この節では、Adobeから要求したステッチを検証する方法について詳しく説明します。 このメソッドは非推奨（廃止予定）ですが、このメソッドを使用して結合されたデータセットが残っている可能性があります。

### データビューの前提条件

ステッチ検証測定プランの場合は、ステッチされたデータセットから必要なすべてのディメンションと指標がデータビューで定義されていることを確認する必要があります。 `stitchedID.id`と`stitchedID.namespace.code`の両方のフィールドがディメンションとして追加されていることを確認します。 結合されたデータセットは、元のデータセットの正確なコピーですが、結合プロセスでは、次の2つの新しい列がデータセットに追加されます。

* `stitchedID.namespace.code`を使用して、**[!UICONTROL ステッチされた名前空間]** ディメンションを定義します。 このディメンションには、行が昇格されたIDの名前空間（例：`Email`または`Phone`）が含まれます。 または、ステッチプロセスがフォールバックする名前空間（`ECID`など）。
  ![ ステッチされた名前空間ディメンション ](/help/stitching/assets/stitchednamespace-dimension.png)

* `stitchedID.id`を使用して、**[!UICONTROL ステッチ ID値]** ディメンションを定義します。 このディメンションには、IDの生の値が含まれます。 例：ハッシュ化されたメール、ハッシュ化された電話、ECID。 この値は、**[!UICONTROL ステッチされた名前空間]**で使用されます。
  ![ ステッチ ID ディメンション ](/help/stitching/assets/stitchedid-dimension.png)


さらに、ディメンション内の値の存在に基づく2つのステッチ指標を追加する必要があります。

1. ステッチされたデータセットの人物IDを含むフィールドを使用して、人物IDが設定されているかどうかを定義する指標を設定します。 人物IDがベースラインの確立に役立つため、グラフベースのステッチングを使用している場合でも、この人物IDを追加します。 個人IDがデータセット内に含まれていない場合、ベースラインは0%になります。

   次の例では、`personalEmail.address`がIDとして機能し、**[!UICONTROL _Email set]**指標の作成に使用されています。
   ![電子メールセット指標](/help/stitching/assets/emailset-metric.png)

1. `stitchedID.namespace.code` フィールドを使用して、**[!UICONTROL メールのステッチ済み名前空間]**&#x200B;指標を作成します。 コンポーネント設定](/help/data-views/component-settings/include-exclude-values.md)に[除外の値を含めるように指定してください。そのため、データ行をに昇格しようとしている名前空間の値のみを考慮してください。
   1. **[!UICONTROL 値を含める/除外する]**&#x200B;を選択します。
   1. すべての条件が&#x200B;]**を**[!UICONTROL &#x200B;一致&#x200B;]**として満たしている場合は、**[!UICONTROL &#x200B;を選択します。
   1. **[!UICONTROL Equals]** `email`を&#x200B;**[!UICONTROL Criteria]**&#x200B;として指定し、メール名前空間に昇格されたイベントを選択します。

   ![ メールのステッチ済み名前空間指標](/help/stitching/assets/emailstitchednamespace-metric.png)

### ステッチされた寸法

これらのディメンションの両方がデータビューに追加された状態で、Analysis Workspaceの[ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)を使用して、各ディメンションに含まれるデータを確認します。

**[!UICONTROL ステッチされた名前空間]** ディメンション テーブルでは、通常、各データセットに2行が表示されます。 1つの行は、ステッチプロセスでフォールバックメソッド（ECID）を使用する必要があった場合を表します。 他の行には、目的のID名前空間（電子メール）に関連付けられたイベントが表示されます。

**[!UICONTROL ステッチ ID値]** ディメンション テーブルに、イベントから取得された生の値が表示されます。 この表では、永続的IDと目的の人物IDの間で値が振動していることがわかります。

![ ステッチされたディメンションを確認](/help/stitching/assets/check-data-on-stitching.png)


### デバイス中心または人物中心のレポート

接続を作成する際は、ユーザーIDに使用するフィールドまたはIDを定義する必要があります。 例えば、web データセットでデバイス IDを個人IDとして選択すると、デバイス中心のレポートを作成し、このデータを他のオフラインチャネルと結合する機能が失われます。 クロスチャネルのフィールドやID （電子メールなど）を選択すると、未認証のイベントが失われます。 この影響を把握するには、未認証のトラフィックの量と認証済みのトラフィックの量を把握する必要があります。

1. 合計&#x200B;]**の計算指標**[!UICONTROL 未認証イベントを作成します。 次に示すように、ルールビルダーでルールを定義します。
   合計![未認証イベント ](/help/stitching/assets/calcmetric-unauthenticatedeventsovertotal.png)

1. 以前に定義した&#x200B;**[!UICONTROL _Email set]**&#x200B;指標に基づいて、計算指標&#x200B;**[!UICONTROL Email認証率]**を作成します。 次に示すように、ルールビルダーでルールを定義します。
   ![電子メール認証率](/help/stitching/assets/calcmetric-emailauthenticationrate.png)

1. 合計&#x200B;]**の計算指標に対する**[!UICONTROL &#x200B;未認証イベントと&#x200B;**[!UICONTROL 電子メール認証率]**&#x200B;計算指標を使用して、[ ドーナツ ](/help/analysis-workspace/visualizations/donut.md)のビジュアライゼーションを作成します。 このビジュアライゼーションには、未認証および認証済みのデータセット内のイベントの数が表示されます。

   ![IDの詳細](/help/stitching/assets/identification-details.png)



### 識別率の接続

ステッチの前と後の識別パフォーマンスを測定します。 それには、さらに3つの計算指標を作成します。

1. ステッチされた名前空間がイベントの合計数に対して目的のIDに設定されているイベントの数を計算する&#x200B;**[!UICONTROL ステッチ認証率]**&#x200B;の計算指標。 データビューを設定する際に、イベントの名前空間がemailに設定されている場合にのみカウントするフィルターを含む&#x200B;**[!UICONTROL Email ステッチ名前空間]**&#x200B;指標を作成しました。 計算指標は、この&#x200B;**[!UICONTROL メールのステッチ名前空間]**指標を使用して、データの何パーセントが目的のIDを持っているかを示します。
   ![ ステッチ済み認証率の計算指標](/help/stitching/assets/calcmetric-stitchedauthenticationrate.png)

1. 現在の識別率とステッチされた識別率の間の生のパーセント変化を計算する&#x200B;**[!UICONTROL パーセント増加]**計算指標。
   ![増加率の計算指標](/help/stitching/assets/calcmetric-percentincrease.png)

1. 現在の識別率とステッチされた識別率の間の上昇率を計算する&#x200B;**[!UICONTROL 上昇率]**計算指標。
   ![上昇分の計算指標](/help/stitching/assets/calcmetric-lift.png)


### まとめ

Analysis Workspace フリーフォームテーブル内のすべてのデータを組み合わせると、次のようなステッチが提供する影響と値を確認できます。

* 現在の認証率：イベントの合計数に対して、既に正しいユーザーIDを持つイベントの数のベースライン。
* ステッチされた認証率：イベントの合計数に対して正しいユーザーIDを持つイベントの新しい数。
* パーセント増加：ステッチされた認証率からベースラインの現在の認証率を引いた未加工の増加率。
* 上昇率：ベースラインの現在の認証率に対する変化率の割合。

![識別パフォーマンス ](/help/stitching/assets/identification-performance.png)


## 重要な留意点

この記事の重要なポイントは、ステッチの検証と分析が次のことに役立つことです。

* 現在のレートとステッチされたレートを比較することで、認証効果の包括的なカスタムビューを提供します。
* パーセンテージの向上とリフト指標を通じて、改善を明確に測定。
* ステッチングをユーザー認証に導入した場合の真の影響を特定するのに役立ちます。
* チーム間で認証のパフォーマンスを伝えるための標準化された方法を構築する。
* 認証戦略と最適化に関するデータ主導の意思決定が可能になります。

これらの指標を組み合わせることで、関係者は、Customer Journey Analyticsの合成が認証の成功率や全体的な人物識別のパフォーマンスにどのような影響を与えるかを包括的に把握できます。
