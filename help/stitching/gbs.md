---
title: グラフベースのステッチ
description: グラフベースのステッチの概念と動作について説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 5%

---

# グラフベースのステッチ

グラフベースのステッチでは、イベントデータセットを指定します。 そのイベントデータセットには、永続 ID （cookie）と、人物 ID 値を保持する ID グラフから目的のステッチ名前空間を指定します。 グラフベースのステッチでは、ステッチ ID の新しい列がイベントデータセットに追加されます。 永続 ID は、指定されたステッチ名前空間を使用してExperience Platform ID サービスから ID グラフをクエリし、ステッチされた ID を更新するために使用されます。


![&#x200B; グラフベースのステッチ &#x200B;](/help/stitching/assets/gbs.png)

## identityMap

グラフベースのステッチでは、次のシナリオで [`identityMap` フィールドグループ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#identity) 使用できます。

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

- 名前空間 `identityMap` 使用して persistentID を定義します。
   - persistentID の複数の値が `identityMap` 名前空間で見つかった場合、最初の辞書的に利用可能な ID が使用されます。

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


## グラフベースのステッチの仕組み

ステッチでは、特定のデータセット内のデータに対して少なくとも 2 つのパスが作成されます。

- **ライブステッチ**：は、永続 ID を使用して、ID グラフにクエリを実行し、選択した名前空間のユーザー ID を検索し、発生した各ヒット（イベント）をステッチしようとします。 人物 ID をルックアップから使用できる場合、この人物 ID は直ちに関連付けられます。

- **ステッチを再生**:*再生* ID グラフから更新された ID に基づいてデータを再生します。 このステージでは、ID グラフが名前空間の ID を解決したので、以前は不明だったデバイス（永続的な ID）からのヒットがステッチされます。 再生は、**frequency** と **lookback window** の 2 つのパラメーターで決まります。 Adobeでは、次のパラメーターの組み合わせを使用できます。
   - **毎日の頻度での毎日のルックバック**：データは毎日、24 時間のルックバックウィンドウで再生されます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、認証されていないプロファイルは、サイトを訪問した日に認証を行う必要があります。
   - **毎週の頻度での毎週のルックバック**：データは、毎週のルックバックウィンドウで週に 1 回再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 週間未満の未ステッチデータは、次の週次再生まで再処理されません。
   - **毎週の頻度での隔週ルックバック**：データは、毎週 1 回、隔週ルックバックウィンドウで再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、2 週間未満の未ステッチデータは、次の週別の再生まで再処理されません。
   - **毎週の頻度での毎月のルックバック**：データは、毎週、毎月のルックバックウィンドウで再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 か月未満の未ステッチデータは、次の週次再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合、ソースデータセットからリクエストされた ID を削除する以外に、認証されていないイベントに対するその ID のステッチも取り消す必要があります。 また、その特定の ID に対してグラフベースのステッチが今後行われないようにするために、ID を ID グラフから削除する必要があります。

  >[!IMPORTANT]
  >
  >ステッチ解除プロセスは、プライバシーリクエストの一環として、2025 年の初めに変更されます。 現在のステッチ解除プロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 イベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を修正するために、2025 年以降、新しいステッチプロセスにより、プライバシーリクエストの対象となるイベントが永続 ID で更新されます。
  > 

ルックバックウィンドウを超えたデータは再生されません。未認証の訪問と認証済みの訪問を一緒に識別するには、所定のルックバックウィンドウ内でプロファイルを認証する必要があります。 デバイスが認識されると、その時点からライブステッチされます。

次の 2 つの ID グラフの経時的な更新、訪問者 A （永続 ID `246`）および訪問者 B （永続 ID `3579`）の場合の更新状況、およびこれらの更新がグラフベースのステッチの手順に与える影響を検討します。

![ID グラフ 3579](assets/identity-graphs.svg)

[ID グラフビューア &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer) を使用して、特定のプロファイルの ID グラフを経時的に表示できます。 ID のリンク時に使用されるロジックの理解を深めるには、[ID サービスリンクロジック &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) も参照してください。

### 手順 1：ライブステッチ

ライブステッチは、コレクション時に、各イベントを ID グラフからその時点での既知の情報にステッチしようと試みます。

+++ 詳細

| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email`![DataMapping](/help/assets/icons/DataMapping.svg) | ステッチ ID （ライブステッチ後） |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) *undefined* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Branch1](/help/assets/icons/Branch1.svg) *undefined* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

ステッチされた ID がイベントごとにどのように解決されるかを確認できます。 時刻、永続 ID、指定された名前空間の ID グラフのルックアップに基づきます（同時）。
参照が複数のステッチ ID に解決される場合（イベント 7 の場合など）、ID グラフによって返される辞書的な最初の ID が選択されます（この例では `a.b@yahoo.co.uk`）。

+++

### 手順 2：再生のステッチ

一定の間隔（選択したルックバックウィンドウに応じて）で、再生のステッチを行うと、その間隔の時点での ID グラフの最新バージョンに基づいて、履歴データが再計算されます。

+++ 詳細

2023-05-13 16:30 に再生のステッチが行われ、24 時間のルックバックウィンドウ設定では、サンプルの一部のイベントが再ステッチされます（![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) で示されます）。

| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email`![DataMapping](/help/assets/icons/DataMapping.svg) | ステッチ ID<br/> （ライブステッチ後） | ステッチ ID<br/> （再生 24 時間後） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


2023-05-13 16:30 に再生のステッチが行われ、7 日間のルックバックウィンドウ設定では、サンプルのすべてのイベントが再ステッチされます。


| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email`![DataMapping](/help/assets/icons/DataMapping.svg) | ステッチ ID<br/> （ライブステッチ後） | ステッチ ID<br/> （再生 7 日後） |
|---|---|---|---|---|---|
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg) *undefined* | `246` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、ステッチされた ID は、プライバシーリクエストのユーザー主体に対するすべてのレコードで削除されます。

+++ 詳細

次の表は上記と同じデータですが、サンプルイベントに対するプライバシーリクエスト（例：2023-05-13 18:00）の効果を示しています。

| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email`![DataMapping](/help/assets/icons/DataMapping.svg) | ステッチ ID （プライバシーリクエスト後） |
|--:|---|---|---|---|
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 2 | 2023-05-12 14:00 | `246` | `246`![&#x200B; ブランチ 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![&#x200B; 分岐 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 前提条件

次の前提条件は、特にグラフベースのステッチに適用されます。

- ステッチを適用するAdobe Experience Platformのイベントデータセットには、各行でプロファイルを識別する 1 つの列（**永続 ID** が必要です。 例えば、Adobe Analytics AppMeasurement ライブラリで生成された訪問者 ID や、Experience Platform ID サービスで生成された ECID などです。
- Experience Platform ID サービスの ID グラフは、グラフベースのステッチを有効にする前に、サンドボックスレベルで設定する必要があります。
   - ID グラフには、人物 ID を解決するためにステッチ中に使用する名前空間（例：`Email` または `Phone`）が必要です。
   - ID グラフには、任意の関連するデータセット（タイプ *イベント* または *プロファイル* からの ID 情報を入力する必要があります。このデータセットには、ID 値を持つ便利な名前空間が少なくとも 2 つ含まれています。
   - そのような関連する ID を保持するすべてのデータセットは、[ID グラフデータ取り込みに対して有効にする &#x200B;](faq.md#enable-a-dataset-for-the-identity-service) 必要があります。 このイネーブルメントにより、必要なすべてのソースから、受信 ID が時間の経過と共にグラフに追加されるようになります。
   - リアルタイム顧客データプロファイルまたはAdobe Journey Optimizerをしばらく使用している場合は、ある程度グラフを設定しておく必要があります。<br/> グラフベースのステッチが有効なデータセットで履歴のステッチバックフィルも必要な場合、必要なステッチ結果を取得するには、期間全体の履歴 ID がグラフに既に含まれている必要があります。
- グラフベースのステッチを使用する場合で、ID グラフに貢献するイベントデータセットが予想される場合は、[ID サービスのデータセットを有効にする &#x200B;](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) 必要があります。
- 永続 ID と人物 ID は、[identityMap](#identitymap) で使用できます。 または、永続 ID と人物 ID は、XDM スキーマのフィールドにすることもできます。この場合、フィールドは、スキーマで [ID として定義 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity?lang=en) されている必要があります。

>[!NOTE]
>
>グラフベースのステッチに Real-time Customer Data Platform ライセンスは必要ありません **要ありません**。 Customer Journey Analyticsの **Prime** パッケージ以降には、必要なExperience Platform ID サービス使用権限が含まれています。


## 制限事項

次の制限は、特にグラフベースのステッチに適用されます。

- 指定された名前空間を使用してユーザー ID のクエリを実行する際に、タイムスタンプは考慮されません。 そのため、永続的な ID が、以前のタイムスタンプを持つレコードの人物 ID に結び付けられる可能性があります。
- グラフ内の名前空間に複数の ID が含まれる共有デバイスシナリオでは、最初の辞書作成 ID が使用されます。 名前空間の制限と優先度がグラフリンクルールのリリースの一部として設定されている場合は、最後に認証されたユーザーの ID が使用されます。 詳しくは、[&#x200B; 共有デバイス &#x200B;](/help/use-cases/stitching/shared-devices.md) を参照してください。
- ID グラフへの ID のバックフィルには、3 か月というハードリミットがあります。 Real-time Customer Data Platform などのExperience Platform アプリケーションを使用していない場合は、ID グラフへの入力にバックフィル ID を使用します。
- [ID サービスガードレール &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) が適用されます。 例えば、次の [&#x200B; 静的制限 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits) を参照してください。
   - グラフ内の ID の最大数：50。
   - 単一のバッチ取得での ID へのリンクの最大数：50。
   - グラフ取り込み用の XDM レコードの ID の最大数：20。
   - グラフ取り込み用の XDM レコードの最小 ID 数：2.
