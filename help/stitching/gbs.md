---
title: グラフベースの合成
description: グラフベースのステッチングの概念と仕組みを説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
TQID: https://experienceleague.adobe.com/eeNrn3hVytufmz195UHNakznBoVRQ0A-qfOYucFF-X0
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
source-wordcount: 1899
ht-degree: 70%

---

# グラフベースのステッチ

グラフベースの合成では、イベントデータセット、そのデータセットの永続的ID （cookie）、およびID グラフから目的の人物ID名前空間を指定します。 グラフベースの合成では、任意のイベントでCustomer Journey Analytics data analysisで個人ID情報を使用できるようにします。 永続的IDは、Experience Platform ID サービスからID グラフをクエリして、指定された名前空間からユーザーIDを取得するために使用されます。

イベントの人物ID情報を取得できない場合は、その&#x200B;*ステッチ解除* イベントの代わりに永続的IDが使用されます。 その結果、結合が有効なデータセットを含む[接続](/help/connections/overview.md)に関連付けられた[&#x200B; データビュー](/help/data-views/data-views.md)で、人物ID データビューコンポーネントには、イベントレベルで人物ID値または永続的ID値が含まれます。


![グラフベースのステッチ](/help/stitching/assets/gbs.png)

## identityMap

グラフベースのステッチでは、次のシナリオで [`identityMap` フィールドグループ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#identity)の使用がサポートされます。

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

- `identityMap` 名前空間を使用して persistentID を定義します。
   - `identityMap` 名前空間に永続 ID の複数の値が見つかった場合、辞書順で最初に使用可能な ID が使用されます。

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


## グラフベースのステッチの仕組み

ステッチでは、特定のデータセット内のデータに対して少なくとも 2 つのパスが作成されます。

- **ライブステッチ**：永続 ID を使用し、ID グラフのクエリを実行して、選択した名前空間のユーザー ID を検索し、各ヒット（イベント）を受信すると、ステッチを試みます。 ルックアップからユーザー ID が使用できる場合、このユーザー ID はすぐにステッチされます。

- **再生のステッチ**：ID グラフから更新された ID に基づいてデータを&#x200B;*再生*&#x200B;します。 このステージでは、ID グラフが名前空間の ID を解決するので、以前は不明だったデバイス（永続 ID）からのヒットがステッチされます。 再生を決定する2つのパラメーター：**頻度**&#x200B;と&#x200B;**ルックバックウィンドウ**。 アドビでは、これらのパラメーターの次の組み合わせを提供しています。
   - **毎日の頻度での毎日のルックバック**：データは、24 時間のルックバックウィンドウで毎日再生されます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、未認証プロファイルは、サイトを訪問した日に認証を行う必要があります。
   - **毎週の頻度での毎週のルックバック**：データは、毎週のルックバックウィンドウで週に 1 回再生されます（[オプション](overview.md#options)を参照）。 このオプションには、未認証セッションの認証にかなり長い時間をかけられるという利点があります。 ただし、1 週間未満の未ステッチデータは、次の毎週の再生まで再処理されません。
   - **毎週の頻度での 2 週間ごとのルックバック**：データは、2 週間ごとのルックバックウィンドウで毎週 1 回再生されます（[オプション](overview.md#options)を参照）。 このオプションには、未認証セッションの認証にかなり長い時間をかけられるという利点があります。 ただし、2 週間未満の未ステッチデータは、次の毎週の再生まで再処理されません。
   - **毎週の頻度での毎月のルックバック**：データは、毎月のルックバックウィンドウで毎週再生されます（[オプション](overview.md#options)を参照）。 このオプションには、未認証セッションの認証にかなり長い時間をかけられるという利点があります。 ただし、1 か月未満の未ステッチデータは、次の毎週の再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合は、ソースデータセットからリクエストされた ID を削除する以外に、未認証のイベントに対するその ID のステッチも取り消す必要があります。 また、特定の ID に対する今後のグラフベースのステッチを防ぐために、その ID を ID グラフから削除する必要があります。

  >[!IMPORTANT]
  >
  >未ステッチプロセスは、プライバシーリクエストの一環として、2025年の初めに変更されます。 現在の未ステッチプロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 このイベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を解消するために、2025年以降、新しい未ステッチプロセスでは、プライバシーリクエストの対象となるイベントが永続 ID を使用して更新されます。
  > 

ルックバックウィンドウを超えたデータは再生されません。 プロファイルは、未認証の訪問と認証済みの訪問を同時に識別するために、特定のルックバックウィンドウ内で認証する必要があります。 デバイスが認識されると、その時点からライブステッチされます。

訪問者 A（永続 ID `246`）と訪問者 B（永続 ID `3579`）の次の 2 つの ID グラフの更新の推移と、これらの更新がグラフベースのステッチの手順に与える影響を考慮します。

![ID グラフ 3579](assets/identity-graphs.png)

[ID グラフビューア](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/identity-graph-viewer)を使用すると、特定のプロファイルの ID グラフの推移を表示できます。 また、ID をリンクする際に使用されるロジックをより深く理解するには、[ID サービスリンクロジック](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/identity-linking-logic)も参照してください。

### 手順 1：ライブステッチ

ライブステッチは、その時点の ID グラフからの既知の情報に対して、収集時に各イベントのステッチを試みます。

+++ 詳細

| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | 結果のID （ライブステッチ後） |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) *未定義* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Branch1](/help/assets/icons/Branch1.svg) *未定義* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Branch1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

各イベントについて、結果のIDがどのように解決されるかを確認できます。 指定したユーザーID名前空間の時間、永続的ID、およびID グラフの検索に基づきます。
ルックアップが複数の結果IDに解決する場合（イベント 7など）、ID グラフから返される字形の最初のIDが選択されます（例では`a.b@yahoo.co.uk`）。

+++

### 手順 2：再生のステッチ

再生のステッチは、一定の間隔（選択したルックバックウィンドウに応じて）で、間隔の時点での最新バージョンの ID グラフに基づいて履歴データを再計算します。

+++ 詳細

2023-05-13 16:30 に再生のステッチが行われ、24 時間のルックバックウィンドウが設定されているので、サンプルの一部のイベントが再ステッチされます（![再生](/help/assets/icons/Replay.svg) で示されます）。

| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | 結果のID <br/> （ライブステッチ後） | 結果のID <br/> （再生24時間後） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![再生](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![再生](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![再生](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


2023-05-13 16:30 に再生のステッチが行われ、7 日間のルックバックウィンドウが設定されているので、サンプルのすべてのイベントが再ステッチされます。


| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | 結果のID <br/> （ライブステッチ後） | 結果のID <br/> （再生7日後） |
|---|---|---|---|---|---|
| ![再生](/help/assets/icons/Replay.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) *未定義* | `246` | `a.b@yahoo.co.uk` |
| ![再生](/help/assets/icons/Replay.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](/help/assets/icons/Replay.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Branch1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![再生](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Branch1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![再生](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、結果のIDは、プライバシーリクエストのユーザー主体のすべてのレコードで削除されます。

+++ 詳細

次の表は上記と同じデータを表していますが、プライバシーリクエスト（例：2023-05-13 18:00）がサンプルイベントに与える影響を示しています。

| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | 結果のID （プライバシーリクエスト後） |
|--:|---|---|---|---|
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 2 | 2023-05-12 14:00 | `246` | `246`![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 3 | 2023-05-12 15:00 | `246` | `246`  ![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Branch1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Branch1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 前提条件

次の前提条件は、特にグラフベースのステッチに適用されます。

- ステッチを適用する Adobe Experience Platform のイベントデータセットには、行ごとにプロファイルを識別する 1 つの列（**永続 ID**）が必要です。 例えば、Adobe Analytics AppMeasurement ライブラリで生成された訪問者 ID や、Experience Platform ID サービスで生成された ECID などです。
- Experience Platform Identity ServiceのID グラフは、グラフベースのステッチを有効にする前に、サンドボックスレベルで設定する必要があります。
   - ID グラフには、人物IDを解決するためにステッチ中に使用する名前空間（例：`Email`または`Phone`）が必要です。
   - ID グラフには、関連するデータセット（*event*&#x200B;または&#x200B;*profile*&#x200B;のタイプで、ID値を持つ少なくとも2つの有用な名前空間を含む）のID情報を入力する必要があります。
   - 関連IDを保持するすべてのデータセットは、ID グラフデータの取り込みに[有効にする必要があります](faq.md#enable-a-dataset-for-the-identity-service)。 この有効化により、受信IDがすべての必要なソースから時間の経過とともにグラフに追加されます。
   - 既にReal-Time Customer Data ProfileやAdobe Journey Optimizerを使用している場合は、グラフを既にある程度設定しておく必要があります。<br/> グラフベースのステッチで有効になっているデータセットに過去のステッチ バックフィルも必要な場合、グラフには目的のステッチ結果を取得するために、ピリオド全体の過去のIDが既に含まれている必要があります。
- グラフベースのステッチを使用する場合、イベントデータセットがID グラフに貢献することを想定している場合は、[ID サービスのデータセットを有効にする](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)必要があります。
- 永続的IDとユーザーIDは、[identityMap](#identitymap)で使用できます。 または、永続的IDと人物IDは、XDM スキーマのフィールドにすることができます。この場合、フィールドはスキーマのID[&#128279;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity?lang=en)として定義する必要があります。

>[!NOTE]
>
>グラフベースのステッチには、Real-time Customer Data Platform ライセンスは必要あり&#x200B;**ません**。 Customer Journey Analytics の **Prime** パッケージ以上には、必要な Experience Platform ID サービスの使用権限が含まれています。


## 制限事項

次の制限事項は、特にグラフベースのステッチに適用されます。

- 指定された名前空間を使用してユーザー ID のクエリを実行する場合、タイムスタンプは考慮されません。 そのため、永続 ID が、以前のタイムスタンプを持つレコードのユーザー ID とステッチされる可能性があります。
- グラフ内の名前空間に複数の ID が含まれる共有デバイスのシナリオでは、辞書順で最初の ID が使用されます。 グラフリンクルールのリリースの一部として名前空間の制限と優先度が設定されている場合は、最後に認証されたユーザーの ID が使用されます。 詳しくは、[共有デバイス](/help/use-cases/stitching/shared-devices.md)を参照してください。
- ID グラフに ID をバックフィルできる期間は 3 か月までという厳密な制限があります。 Real-time Customer Data Platform などの Experience Platform アプリケーションを使用して ID グラフに入力していない場合は、バックフィル ID を使用します。
- [ID サービスのガードレール](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/guardrails)が適用されます。 例えば、次の[静的制限](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/guardrails#static-limits)を参照してください。
   - グラフ内の ID の最大数：50。
   - 1 回のバッチ取得での ID へのリンクの最大数：50。
   - グラフ取得での XDM レコード内の ID の最大数：20。
   - グラフ取得での XDM レコード内の ID の最小数：2。
