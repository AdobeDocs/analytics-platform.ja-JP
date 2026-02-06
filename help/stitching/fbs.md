---
title: フィールドベースのステッチ
description: フィールドベースのステッチの概念と作業について説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 4c5376171afe7ee830c52cc1066d0645a1adbc5d
workflow-type: tm+mt
source-wordcount: '1797'
ht-degree: 9%

---

# フィールドベースのステッチ

フィールドベースのステッチでは、イベントデータセットと、そのデータセットの永続 ID （cookie）および人物 ID を指定します。 フィールドベースのステッチは、特定の永続 ID を持つ匿名イベントに対して、人物 ID 情報をCustomer Journey Analytics データ分析で使用できるようにします。  その情報は、その特定の永続 ID の人物 ID を持つ行から取得されます。

イベントのユーザー ID 情報を取得できない場合は、その *未関連付け* イベントの代わりに永続 ID が使用されます。 その結果、ステッチが有効なデータセットを含む [&#x200B; 接続 &#x200B;](/help/data-views/data-views.md) に関連付けられた [&#x200B; データビュー &#x200B;](/help/connections/overview.md) では、人物 ID コンポーネントには、イベントレベルで人物 ID 値または永続 ID 値のいずれかが含まれます。

Customer Journey Analyticsをスタンドアロンソリューションとして使用する場合（Experience Platform ID サービスおよび関連する ID グラフへのアクセス権がない場合）、フィールドベースのステッチを使用できます。 または、使用可能な ID グラフを使用しない場合にも使用できます。

![フィールドベースのステッチ](/help/stitching/assets/fbs.svg)


## identityMap

フィールドベースのステッチでは、次のシナリオで [`identityMap` フィールドグループ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#identity) 使用できます。

- 名前空間でのプライマリ ID`identityMap` 使用して persistentID を定義します。
   - 異なる名前空間に複数のプライマリ ID が見つかった場合、名前空間の ID は辞書順に並べ替えられ、最初の ID が選択されます。
   - 単一の名前空間に複数のプライマリ ID が見つかった場合は、辞書学的に利用できる最初のプライマリ ID が選択されます。

  次の例では、名前空間と ID によりプライマリ ID リストが並べ替えられ、最終的に選択された ID が表示されます。

  <table style="table-layout:auto">
     <tr>
       <th>名前空間</th>
       <th>ID リスト</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>並べ替えられた ID リスト</th>
      <th>選択した ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>


- 名前空間 `identityMap` 使用して、永続 ID、人物 ID、またはその両方を定義します。
   - 永続 ID またはユーザー ID の複数の値が `identityMap` 名前空間で見つかった場合、最初の辞書編集可能な値が使用されます。
   - 永続 ID とユーザー ID の名前空間は、相互に排他的にする必要があります。

  以下の例では、使用する名前空間として ECID を選択しています。 その結果、ID リストが並べ替えられ、最後に選択された ID が表示されます。

  <table style="table-layout:auto">
     <tr>
       <th>名前空間</th>
       <th>ID リスト</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>並べ替えられた ID リスト</th>
      <th>選択した ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>

## フィールドベースのステッチの仕組み

ステッチでは、特定のデータセット内のデータに対して少なくとも 2 つのパスが作成されます。

- **ライブステッチ**：各ヒット（イベント）が発生するとそのヒットをステッチしようとします。 デバイスからデータセット *新規* 認証されたことのない）ヒットは、通常、このレベルでは結び付けられません。 既に認識済みのデバイスからのヒットは、直ちに結合されます。

- **ステッチを再生**:*再生* 一意の識別子（ユーザー ID）に基づいてデータを再生します。 このステージでは、以前は不明だったデバイス（永続的な ID）からのヒットが（人物 ID に）結び付けられます。 再生は、**frequency** と **lookback window** の 2 つのパラメーターで決まります。 Adobeでは、次のパラメーターの組み合わせを使用できます。
   - **毎日の頻度での毎日のルックバック**：データは毎日、24 時間のルックバックウィンドウで再生されます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、認証されていないプロファイルは、サイトを訪問した日に認証を行う必要があります。
   - **毎週の頻度での毎週のルックバック**：データは、毎週のルックバックウィンドウで週に 1 回再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 週間未満の未ステッチデータは、次の週次再生まで再処理されません。
   - **毎週の頻度での隔週ルックバック**：データは、毎週 1 回、隔週ルックバックウィンドウで再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、2 週間未満の未ステッチデータは、次の週別の再生まで再処理されません。
   - **毎週の頻度での毎月のルックバック**：データは、毎週、毎月のルックバックウィンドウで再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 か月未満の未ステッチデータは、次の週次再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合、リクエストされた ID を削除する以外に、認証されていないイベントに対するその ID の関連付けを取り消す必要があります。

  >[!IMPORTANT]
  >
  >ステッチ解除プロセスは、プライバシーリクエストの一環として、2025 年の初めに変更されます。 現在のステッチ解除プロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 イベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を修正するために、2025 年以降、新しいステッチプロセスにより、プライバシーリクエストの対象となるイベントが永続 ID で更新されます。
  > 


ルックバックウィンドウを超えたデータは再生されません。未認証の訪問と認証済みの訪問を一緒に識別するには、所定のルックバックウィンドウ内でプロファイルを認証する必要があります。 デバイスが認識されると、そのデバイスはその時点からライブステッチされます。

### 手順 1：ライブステッチ

ライブステッチは、コレクション時に既知のデバイスとチャネルに各イベントをステッチしようとします。

+++ 詳細

次の例について考えてみます。Bob がイベントデータセットの一部として様々なイベントを記録する場合を考えてみましょう。

*データが収集された日の状態：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | ユーザー ID | 結果の ID （ライブステッチの後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![&#x200B; 下矢印 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 デバイス** | | **4 人**:<br/>`246`、`Bob`、`3579`、`81911` |

新しいデバイスでの未認証イベントと認証イベントは、両方とも別のユーザーとして（一時的に）カウントされます。認識されたデバイス上の未認証のイベントは、ライブステッチされます。

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1、8、9、10 を除くすべてのイベントがライブステッチされます（すべてのイベントが `Bob` 識別子を使用します）。 ライブステッチは、イベント 4、6、12 の結果 ID を「解決」します。

遅延データ（タイムスタンプが 24 時間以上経過したデータ）は、「ベストエフォート」ベースで処理され、最高の品質を得るために現在のデータのステッチが優先されます。

+++ 

### 手順 2：再生のステッチ

一定の間隔（選択されたルックバックウィンドウに応じて週に 1 回または 1 日に 1 回）で、再生のステッチは、認識されたデバイスに基づいて履歴データを再計算します。 デバイスが未認証の状態で最初にデータを送信してからログインした場合、再生のステッチにより、未認証のイベントが適切なユーザーに結び付けられます。

+++ 詳細

次の表は、上記と同じデータを示していますが、データの再生に基づいて異なる数字が表示されています。

*再生後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | ユーザー ID | 結果の ID （ライブステッチの後） | 結果の ID （再生後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | ボブ |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 デバイス** | | **4 人**:<br/>`246`、`Bob`、`3579`、`81911` | **2 人**:<br/>`Bob`、`3579` |

{style="table-layout:auto"}

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1 と 10 が再生の結果としてステッチされ、イベント 8 と 9 のみがステッチされていない状態になります。 人物指標（累積）を 2 に減らします。

+++ 

### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、ステッチプロセスでユーザー ID の値に設定された識別情報が、すべてのレコードでプライバシーリクエストのユーザー主体の永続 ID の値に更新されます。

+++ 詳細

次の表は上記と同じデータですが、Bob に対するプライバシーリクエストが処理後のデータに与える影響を示しています。 Bob が認証された行は、他の行のユーザー ID として Bob が削除されると共に、削除されます（2、3、5、7、11）。

*Bob に対するプライバシーリクエスト後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | ユーザー ID | 結果の ID （ライブステッチの後） | 結果の ID （再生後） | ユーザー ID | 結果の ID （プライバシーリクエスト後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | ボブ ![&#x200B; 矢の右 &#x200B;](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![&#x200B; 上矢印 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | ボブ ![&#x200B; 矢の右 &#x200B;](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | ボブ ![&#x200B; 矢の右 &#x200B;](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 デバイス** | | **4 人**:<br/>246、`Bob`、`3579`、`81911` | **2 人**:<br/>Bob, `3579` |  | **3 人**:<br/>`246`、`3579`、`81911` |

+++ 

## 前提条件

次の前提条件は、特にフィールドベースのステッチに適用されます。

- ステッチを適用するAdobe Experience Platformのイベントデータセットには、プロファイルの識別に役立つ次の 2 つの列が必要です。

   - **永続 ID**：各行で使用できる識別子。 例えば、Adobe Analytics AppMeasurement ライブラリで生成された訪問者 ID や、Adobe Experience Platform ID サービスで生成された ECID などです。
   - **ユーザー ID**：一部の行でのみ使用できる識別子。 例えば、プロファイルが認証されると、ハッシュ化されたユーザー名またはメールアドレスなどです。 実質的に任意の識別子を使用できます。 ステッチでは、このフィールドを実際のユーザー ID 情報を保持すると見なされます。 最適なステッチの結果を得るには、データセットのイベント内で、永続 ID ごとに少なくとも 1 回、ユーザー ID を送信する必要があります。 Customer Journey Analytics接続内にこのデータセットを含める予定がある場合は、他のデータセットも同様の共通の ID を持っていることが推奨されます。

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 制限事項

次の制限は、特にフィールドベースのステッチに適用されます。

- 現在のキー再設定機能は、1 つの手順（永続 ID からユーザー ID へ）に制限されています。 複数の手順による再入力（例えば、永続 ID を人物 ID に割り当ててから別の人物 ID に割り当てる）はサポートされていません。
- 複数のユーザーが 1 つのデバイスを共有し、ユーザー間のトランジションの合計が 50,000 を超えると、Customer Journey Analyticsはそのデバイスに対するデータのステッチを停止します。
- 組織で使用されているカスタム ID マップはサポートされていません。
- ステッチでは大文字と小文字が区別されます。 Analytics ソースコネクタを通じて生成されたデータセットの場合、Adobeでは、ユーザー ID フィールドに適用される VISTA ルールまたは処理ルールをレビューすることをお勧めします。 これにより、これらのルールによって同じ ID の新しいフォームが導入されることがなくなります。 例えば、VISTA ルールまたは処理ルールにより、イベントの一部のみでユーザー ID フィールドが小文字になっていないか確認する必要があります。
- ステッチでフィールドの結合や連結は行われません。
- 人物 ID フィールドには、1 つのタイプの ID （1 つの名前空間からの ID）を含める必要があります。 例えば、人物 ID フィールドにログイン ID と電子メール ID の組み合わせを含めることはできません。
- 同じ永続 ID の同じタイムスタンプで複数のイベントが発生しても、人物 ID フィールドに異なる値がある場合、ステッチはアルファベット順に基づいて ID を選択します。 したがって、永続 ID A に同じタイムスタンプの 2 つのイベントがあり、1 つのイベントが Bob を指定し、もう 1 つが Ann を指定している場合、ステッチは Ann を選択します。
- 人物 ID にプレースホルダー値（例：`Undefined`）が含まれるシナリオには注意が必要です。 詳しくは、[FAQ](faq.md) を参照してください。
- 永続 ID とユーザー ID の両方に同じ名前空間を使用することはできません。名前空間は相互に排他的である必要があります。
