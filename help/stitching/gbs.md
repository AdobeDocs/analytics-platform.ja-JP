---
title: グラフベースのステッチ
description: グラフベースのステッチの説明
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '1553'
ht-degree: 7%

---

# グラフベースのステッチ


グラフベースのステッチでは、イベントデータセットと、そのデータセットの一時的な ID （ユーザー ID）の永続 ID （cookie）および名前空間を指定します。 グラフベースのステッチでは、新しいステッチされたデータセットのステッチ ID に新しい列が作成されます。 次に、永続 ID を使用して、指定された名前空間を使用してExperience Platform ID サービスから ID グラフをクエリし、ステッチされた ID を更新します。

>[!NOTE]
>
>データセットが [ID サービスに対して有効 &#x200B;](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) になっていることを確認する必要があります。
>


![&#x200B; グラフベースのステッチ &#x200B;](/help/stitching/assets/gbs.png)

## identityMap

グラフベースのステッチでは、次のシナリオで [`identityMap` フィールドグループ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#identity) 使用できます。

- 名前空間でのプライマリ ID`identityMap` 使用して persistentID を定義します。
   - 異なる名前空間に複数のプライマリ ID が見つかった場合、名前空間の ID は辞書的に並べ替えられ、最初の ID が選択されます。
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

- **ライブステッチ**：は、永続 ID を使用して、ID グラフにクエリを実行し、選択した名前空間の一時的な ID を検索し、発生した各ヒット（イベント）をステッチしようとします。 ルックアップから一時的な ID を使用できる場合、この一時的な ID は直ちにステッチされます。

- **ステッチを再生**:*再生* ID グラフから更新された ID に基づいてデータを再生します。 このステージでは、ID グラフが名前空間の ID を解決したので、以前は不明だったデバイス（永続的な ID）からのヒットがステッチされます。 再生は、**頻度** および **ルックバックウィンドウ** の 2 つのパラメーターによって決定されます。 Adobeでは、次のパラメーターの組み合わせを使用できます。
   - **毎日の頻度での毎日のルックバック**：データは毎日、24 時間のルックバックウィンドウで再生されます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、認証されていない訪問者は、サイトを訪問した日に認証を行う必要があります。
   - **毎週の頻度での毎週のルックバック**：データは、毎週のルックバックウィンドウで週に 1 回再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 週間未満の未ステッチデータは、次の週次再生まで再処理されません。
   - **毎週の頻度での隔週ルックバック**：データは、毎週 1 回、隔週ルックバックウィンドウで再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、2 週間未満の未ステッチデータは、次の週別の再生まで再処理されません。
   - **毎週の頻度での毎月のルックバック**：データは、毎週、毎月のルックバックウィンドウで再生されます（[&#x200B; オプション &#x200B;](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 か月未満の未ステッチデータは、次の週次再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合、ソースデータセットからリクエストされた ID を削除する以外に、認証されていないイベントに対するその ID のステッチも取り消す必要があります。 また、その特定の ID に対してグラフベースのステッチが今後行われないようにするために、ID を ID グラフから削除する必要があります。

  >[!IMPORTANT]
  >
  >ステッチ解除プロセスは、プライバシーリクエストの一環として、2025 年の初めに変更されます。 現在のステッチ解除プロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 イベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を修正するために、2025 年以降、新しいステッチプロセスにより、プライバシーリクエストの対象となるイベントが永続 ID で更新されます。
  > 

ルックバックウィンドウを超えたデータは再生されません。未認証の訪問と認証された訪問を一緒に識別するには、訪問者は、所定のルックバックウィンドウ内で認証する必要があります。 デバイスが認識されると、その時点からライブステッチされます。

永続 ID `246` および `3579` の次の 2 つの ID グラフ、これらの ID グラフが時間の経過と共にどのように更新されるか、およびこれらの更新がグラフベースのステッチの手順にどのように影響するかを考えてみましょう。

![ID グラフ 246](assets/identity-graph-246.svg)
![ID グラフ 3579](assets/identity-graph-3579.svg)

[ID グラフビューア &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/identity-graph-viewer) を使用して、特定のプロファイルの ID グラフを経時的に表示できます。 ID のリンク時に使用されるロジックの理解を深めるには、[ID サービスリンクロジック &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/identity-linking-logic) も参照してください。

### 手順 1：ライブステッチ

ライブステッチは、コレクション時に、各イベントを ID グラフからその時点での既知の情報にステッチしようと試みます。

+++ 詳細

| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID （ライブステッチ後） |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

ステッチされた ID がイベントごとにどのように解決されるかを確認できます。 時刻、永続 ID、指定された名前空間の ID グラフのルックアップに基づきます（同時）。
参照が複数のステッチ ID に解決される場合（イベント 7 の場合など）、ID グラフによって返される辞書的な最初の ID が選択されます（この例では `a.b@yahoo.co.uk`）。

+++

### 手順 2：再生のステッチ

一定の間隔（選択したルックバックウィンドウに応じて）で、再生のステッチを行うと、その間隔の時点での ID グラフの最新バージョンに基づいて、履歴データが再計算されます。

+++ 詳細

2023-05-13 16:30 に再生のステッチが行われ、24 時間のルックバックウィンドウ設定では、サンプルの一部のイベントが再ステッチされます（![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) で示されます）。

| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID<br/> （ライブステッチ後） | ステッチ ID<br/> （再生 24 時間後） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


2023-05-13 16:30 に再生のステッチが行われ、7 日間のルックバックウィンドウ設定では、サンプルのすべてのイベントが再ステッチされます。


| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID<br/> （ライブステッチ後） | ステッチ ID<br/> （再生 7 日後） |
|---|---|---|---|---|---|
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![&#x200B; 再生 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、ステッチされた ID は、プライバシーリクエストのユーザー主体に対するすべてのレコードで削除されます。

+++ 詳細

次の表は上記と同じデータですが、サンプルイベントに対するプライバシーリクエスト（例：2023-05-13 18:00）の効果を示しています。

| | 時間 | 永続 ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID （プライバシーリクエスト後） |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![&#x200B; リンク &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 前提条件

次の前提条件は、特にグラフベースのステッチに適用されます。

- ステッチを適用するAdobe Experience Platformのイベントデータセットには、各行で訪問者を特定する 1 つの列（**永続 ID** が必要です。 例えば、Adobe Analytics AppMeasurement ライブラリで生成された訪問者 ID や、Experience Platform ID サービスで生成された ECID などです。
- 永続 ID も、スキーマで [ID として定義 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity) する必要があります。
- Experience Platform ID サービスの ID グラフには、ステッチ中に `Email` 一時的な ID`Phone` を解決するために使用する名前空間（**や** など）が必要です。 詳しくは、[Experience Platform ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home) を参照してください。

>[!NOTE]
>
>グラフベースのステッチに Real-time Customer Data Platform ライセンスは必要ありません **要ありません**。 Customer Journey Analyticsの **Prime** パッケージ以降には、必要なExperience Platform ID サービス使用権限が含まれています。


## 制限事項

次の制限は、特にグラフベースのステッチに適用されます。

- 指定された名前空間を使用して一時的な ID をクエリする場合、タイムスタンプは考慮されません。 そのため、永続的 ID が、以前のタイムスタンプを持つレコードからの一時的な ID でステッチされる可能性があります。
- グラフ内の名前空間に複数の ID が含まれる共有デバイスシナリオでは、最初の辞書作成 ID が使用されます。 名前空間の制限と優先度がグラフリンクルールのリリースの一部として設定されている場合は、最後に認証されたユーザーの ID が使用されます。 詳しくは、[&#x200B; 共有デバイス &#x200B;](/help/use-cases/stitching/shared-devices.md) を参照してください。
- ID グラフへの ID のバックフィルには、3 か月というハードリミットがあります。 Real-time Customer Data Platform などのExperience Platform アプリケーションを使用していない場合は、ID グラフへの入力にバックフィル ID を使用します。
- [ID サービスガードレール &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/guardrails) が適用されます。 例えば、次の [&#x200B; 静的制限 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/guardrails#static-limits) を参照してください。
   - グラフ内の ID の最大数：50。
   - 単一のバッチ取得での ID へのリンクの最大数：50。
   - グラフ取り込み用の XDM レコードの ID の最大数：20。
   - グラフ取り込み用の XDM レコードの最小 ID 数：2.
