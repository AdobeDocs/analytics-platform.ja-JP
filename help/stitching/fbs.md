---
title: フィールドベースの接続
description: フィールドベースのステッチングの概念と仕組みを説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
TQID: https://experienceleague.adobe.com/xqNEj5V-fQTo-8j5S9Ad-5ZezRjjr8kdt2Xmx0U8xDI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d682e1e729402bff7a3f6e3625402f57deee21ad
workflow-type: tm+mt
source-wordcount: 1902
ht-degree: 82%

---

# フィールドベースのステッチ

フィールドベースの合成では、イベントデータセットと、そのデータセットの永続的ID （cookie）および人物IDを指定します。 フィールドベースの合成では、特定の永続IDを持つ匿名イベントに対して、Customer Journey Analytics data analysisで個人ID情報を使用できるようにします。  その情報は、その特定の永続的IDの個人IDを持つ行から取得されます。

イベントの人物ID情報を取得できない場合は、その&#x200B;*ステッチ解除* イベントの代わりに永続的IDが使用されます。 その結果、結合が有効なデータセットを含む[接続](/help/connections/overview.md)に関連付けられた[&#x200B; データビュー](/help/data-views/data-views.md)で、人物ID コンポーネントには、イベントレベルで人物ID値または永続的ID値が含まれます。

Customer Journey Analyticsをスタンドアロンソリューションとして使用する場合（Experience Platform ID サービスおよび関連するID グラフにアクセスできない場合）は、フィールドベースのステッチを使用できます。 または、使用可能な ID グラフを使用しない場合は、フィールドベースのステッチを使用できます。

![フィールドベースのステッチ](/help/stitching/assets/fbs.png)


## identityMap

フィールドベースのステッチでは、次のシナリオで [`identityMap` フィールドグループ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#identity)の使用がサポートされます。

- `identityMap` 名前空間のプライマリ ID を使用して persistentID を定義します。
   - 異なる名前空間に複数のプライマリ IDが見つかった場合、名前空間内のIDは辞書的に並べ替えられ、最初のIDが選択されます。
   - 単一の名前空間に複数のプライマリ ID が見つかった場合、辞書順で最初に使用可能なプライマリ ID が選択されます。

  次の例では、名前空間と ID により、並べ替えられたプライマリ ID リストが生成され、最後に選択された ID が表示されます。

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
      <th>選択された ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>


- `identityMap` 名前空間を使用して、永続 ID 、ユーザー ID、またはその両方を定義します。
   - `identityMap` 名前空間に永続 ID またはユーザー ID の複数の値が見つかった場合、辞書順で最初に使用可能な値が使用されます。
   - 永続 ID とユーザー ID の名前空間は、相互に排他的である必要があります。

  次の例では、使用する名前空間として ECID を選択しています。 その選択により、並べ替えられた ID リストが生成され、最後に選択された ID が表示されます。

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
      <th>選択された ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>

## フィールドベースのステッチの仕組み

ステッチでは、特定のデータセット内のデータに対して少なくとも 2 つのパスが作成されます。

- **ライブステッチ**： ヒット（イベント）が検出されるたびにステッチを試みます。 データセットに対する&#x200B;*新規*&#x200B;の（認証されたことがない）デバイスからのヒットは通常、このレベルではステッチされません。 既に認識されているデバイスからのヒットは、即座にステッチされます。

- **再生のステッチ**：一意の識別子（ユーザー ID）に基づいてデータを&#x200B;*再生*&#x200B;します。 このステージでは、以前は不明だったデバイス（永続 ID）からのヒットが（ユーザー ID に）ステッチされます。 再生を決定する2つのパラメーター：**頻度**&#x200B;と&#x200B;**ルックバックウィンドウ**。 アドビでは、これらのパラメーターの次の組み合わせを提供しています。
   - **毎日の頻度での毎日のルックバック**：データは、24 時間のルックバックウィンドウで毎日再生されます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、未認証プロファイルは、サイトを訪問した日に認証を行う必要があります。
   - **毎週の頻度での毎週のルックバック**：データは、毎週のルックバックウィンドウで週に 1 回再生されます（[オプション](overview.md#options)を参照）。 このオプションには、未認証セッションの認証にかなり長い時間をかけられるという利点があります。 ただし、1 週間未満の未ステッチデータは、次の毎週の再生まで再処理されません。
   - **毎週の頻度での 2 週間ごとのルックバック**：データは、2 週間ごとのルックバックウィンドウで毎週 1 回再生されます（[オプション](overview.md#)を参照）。 このオプションには、未認証セッションの認証にかなり長い時間をかけられるという利点があります。 ただし、2 週間未満の未ステッチデータは、次の毎週の再生まで再処理されません。
   - **毎週の頻度での毎月のルックバック**：データは、毎月のルックバックウィンドウで毎週再生されます（[オプション](overview.md#options)を参照）。 このオプションには、未認証セッションの認証にかなり長い時間をかけられるという利点があります。 ただし、1 か月未満の未ステッチデータは、次の毎週の再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合は、リクエストされた ID を削除する以外に、未認証のイベントに対するその ID のステッチも取り消す必要があります。

  >[!IMPORTANT]
  >
  >未ステッチプロセスは、プライバシーリクエストの一環として、2025年の初めに変更されます。 現在の未ステッチプロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 このイベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を解消するために、2025年以降、新しい未ステッチプロセスでは、プライバシーリクエストの対象となるイベントが永続 ID を使用して更新されます。
  > 


ルックバックウィンドウを超えたデータは再生されません。 プロファイルは、未認証の訪問と認証済みの訪問を同時に識別するために、特定のルックバックウィンドウ内で認証する必要があります。 デバイスが認識されると、その時点からライブステッチされます。

### 手順 1：ライブステッチ

ライブステッチは、既知のデバイスとチャネルに対して、収集時に各イベントのステッチを試みます。

+++ 詳細

Bob が様々なイベントをイベントデータセットの一部として記録する次の例を考えてみましょう。

*収集された日に表示されるデータ：*

| イベント | タイムスタンプ | 永続 ID（cookie ID） | ユーザー ID | 結果のID （ライブステッチ後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 デバイス** | | **4 人**：<br/>`246`、`Bob`、`3579`、`81911` |

新しいデバイスでの未認証イベントと認証イベントは、両方とも別のユーザーとして（一時的に）カウントされます。 既知のデバイスでの未認証イベントは、ライブステッチされます。

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1、8、9  と 10 を除くすべてのイベントがライブステッチされます（すべて `Bob` 識別子を使用します）。 ライブステッチは、イベント 4、6、および12の結果として得られるIDを「解決」します。

遅延データ（タイムスタンプが 24 時間以上経過したデータ）は、「最大限の労力」で処理され、最高品質を得るために現在のデータのステッチが優先されます。

+++ 

### 手順 2：再生のステッチ

再生のステッチは、一定の間隔（選択したルックバックウィンドウに応じて週に 1 回、または日に 1 回）で、認識されたデバイスに基づいて履歴データを再計算します。 認証されていない状態でデバイスが最初にデータを送信し、その後ログインした場合、再生のステッチは、未認証のイベントを正しいユーザーに結び付けます。

+++ 詳細

次の表は、上記と同じデータを示していますが、データの再生に基づいて異なる数字が表示されています。

*再生後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID（cookie ID） | ユーザー ID | 結果のID （ライブステッチ後） | 結果のID （リプレイ後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 デバイス** | | **4 人**：<br/>`246`、`Bob`、`3579`、`81911` | **2 人**：<br/>`Bob`、`3579` |

{style="table-layout:auto"}

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1 と 10 が再生の結果としてステッチされ、イベント 8 と 9 のみがステッチされていない状態になります。 また、人物指標（累積）は 2 に減少しています。

+++ 

### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、ステッチプロセスによって個人ID値に設定されたID情報は、プライバシーリクエストのユーザー主体の永続的なID値にすべてのレコードで更新されます。

+++ 詳細

次の表は上記と同じデータを表していますが、Bob に対するプライバシーリクエストが処理後のデータに与える影響を示しています。 Bob が認証されている行（2、3、5、7、11）が削除され、他の行のユーザー ID としての Bob も削除されます。

*Bob に対するプライバシーリクエスト後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID（cookie ID） | ユーザー ID | 結果のID （ライブステッチ後） | 結果のID （リプレイ後） | ユーザー ID | 結果のID （プライバシーリクエスト後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![上矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 デバイス** | | **4 人**：<br/>246、`Bob`、`3579`、`81911` | **2 人**：<br/>Bob、`3579` |  | **3 人**：<br/>`246`、`3579`、`81911` |

+++ 

## 前提条件

次の前提条件は、特にフィールドベースのステッチに適用されます。

- ステッチを適用する Adobe Experience Platform のイベントデータセットには、プロファイルの識別に役立つ次の 2 つの列が必要です。

   - **永続 ID** - 各行で使用できる識別子。 例えば、Adobe Analytics AppMeasurement ライブラリで生成された訪問者 ID や、Adobe Experience Platform ID サービスで生成された ECID などです。
   - **ユーザー ID** - 一部の行で使用できる識別子。 例えば、プロファイルの認証後にハッシュ化されたユーザー名やメールアドレスなどがあります。 事実上任意の識別子を使用できます。 ステッチでは、このフィールドを実際のユーザー ID 情報を保持すると見なされます。 最適なステッチの結果を得るには、データセットのイベント内で、永続 ID ごとに少なくとも 1 回、ユーザー ID を送信する必要があります。 Customer Journey Analytics 接続内にこのデータセットを含める予定がある場合は、他のデータセットも同様の共通の識別子を持っていることが推奨されます。

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 制限事項

次の制限事項は、特にフィールドベースのステッチに適用されます。

- 現在のキー変更機能は、1 つの手順（永続 ID からユーザー ID への変更）に制限されます。 複数手順でのキーの変更（例えば、永続 ID をユーザー ID に、その後別のユーザー IDに変更）はサポートされません。
- 複数のユーザーが1つのデバイスを共有し、ユーザー間のトランジションの合計数が50,000を超えた場合、Customer Journey Analyticsはそのデバイスのデータの結合を停止します。
- 組織で使用されているカスタム ID マップはサポートされていません。
- ステッチでは、大文字と小文字が区別されます。 Analytics ソースコネクタを通じて生成される Analytics データセットの場合、アドビでは、ユーザー ID フィールドに適用される VISTA ルールや処理ルールのレビューを行うことを確認することをお勧めします。 このレビューにより、これらのルールによって同じ ID の新規フォームが生成されないことが確認されます。 例えば、VISTA ルールまたは処理ルールにより、イベントの一部のみでユーザー ID フィールドが小文字になっていないか確認する必要があります。
- ステッチでは、フィールドの組み合わせや連結は行われません。
- ユーザー ID フィールドには、1 つのタイプの ID（1 つの名前空間からの ID など）を含める必要があります。 例えば、ユーザー ID フィールドにログイン ID とメール ID の組み合わせを含めることはできません。
- 同じ永続的 ID に対して同じタイムスタンプを持つ複数のイベントが発生し、ユーザー ID フィールドの値が異なる場合、ステッチでは、アルファベット順に ID が選択されます。 したがって、永続的な ID A にタイムスタンプが同じイベントが 2 つあり、一方のイベントが「Bob」を、もう一方のイベントが「Ann」を指定した場合、ステッチは「Ann」を選択します。
- ユーザー ID にプレースホルダー値（例：`Undefined`）が含まれるシナリオに注意してください。 詳しくは、[FAQ](faq.md) を参照してください。
- 永続的IDとユーザーIDの両方に同じ名前空間を使用することはできません。名前空間は相互排他的である必要があります。
