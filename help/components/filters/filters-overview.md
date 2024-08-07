---
title: フィルターの概要
description: フィルターの用途と、単純なフィルターの作成方法を理解します。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 23%

---


# フィルターの概要 {#overview}

Customer Journey Analytics を使用すると、強力で重要なオーディエンスフィルターを作成、管理、共有し、レポートに適用できます。フィルターを使用すると、特性やインタラクションに基づいて人物のサブセットを識別できます。 フィルターは、特定のニーズに合わせて作成し、他のチームメンバーと検証、編集、および共有できる、体系化されたオーディエンスインサイトとして作られています。

フィルターは以下に基づくことができます

- 属性（ブラウザータイプ、デバイス、訪問回数、国、性別）
- インタラクション（キャンペーン、キーワード検索、検索エンジン）、
- 出口およびエントリ（Facebookのユーザー、定義されたランディングページ、参照ドメイン、ジオフェンスイベント）
- カスタム変数（フォームフィールド、定義されたカテゴリ、顧客 ID）、
- とその他の条件。

フィルタービルダーでフィルターを作成して保存したり、（ワークスペースで）フォールアウトビジュアライゼーションからフィルターを生成したりできます。また、複数のフィルターをまとめて、積み重ねフィルターとして使用することもできます。

フィルタリングには、フィルターを作成して事前テストを実行する [ フィルタービルダー ](/help/components/filters/filter-builder.md) や、組織全体でフィルターを収集し、タグ付けし、承認し、セキュリティ設定し、共有する [ フィルターマネージャー ](/help/components/filters/manage-filters.md) が含まれます。

IMS 組織ごとに作成できるフィルターの最大数は 50,000 個です。

## フィルターのタイプ {#types}

使用可能なフィルターのタイプと作成方法について詳しくは、[ フィルターの作成 ](/help/components/filters/create-filters.md) を参照してください。

## 順次フィルター {#sequential}

順次フィルターを使用すると、ナビゲーション（サイト全体のページビュー、モバイルアプリのシーンとのインタラクション、セットトップボックスのメニューの使用）に基づいてユーザーを識別できます。 順次フィルターは、定義されたアクションとインタラクションのフィルターを提供し、ユーザーが好きなものと避けているものを識別するのに役立ちます。 順次フィルターを作成する場合、THEN 演算子を使用してユーザーナビゲーションの定義と順序を指定します。

>[!IMPORTANT]
>
>クロスチャネルの順次フィルターを作成するには、**選択** パッケージが必要です。 使用しているCustomer Journey Analyticsパッケージが不明な場合は、管理者にお問い合わせください。

次に例を示します。

| セッション 1 | セッション 2 | セッション 3 |
| --- | --- | --- |
| メインランディングページ A に移動し、キャンペーンページ B を除外してから、製品ページ C を表示した。 | その後、再びメインランディングページ A に移動し、キャンペーンページ B を除外して、製品ページ C に移動した後、新しいページ D に移動します。 | その人物は 1 回目と 2 回目の訪問と同じパスに入ってフォローし、ページ F を除外して、ターゲットの製品ページ G に直接移動します。 |

## フィルターコンテナ {#containers}

フィルターは、ネストされたコンテナモデルを使用した、ユーザーレベル、セッションレベル、イベントレベルの階層に基づいています。 ネストされたコンテナを使用することで、コンテナ間およびコンテナ内のルールに基づいて、ユーザーの属性とアクションを定義できます。


<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> ユーザー</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> セッション</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> イベント</td>
</tr>
</table>

>[!NOTE]
>ユーザーコンテナは、以前は訪問者コンテナと呼ばれていました。セッションコンテナは訪問コンテナ、イベントコンテナはヒットコンテナでした。

フィルターは、ユーザーの属性や、サイト、モバイルアプリ、またはデータを収集したその他のデバイスタイプとのインタラクションに基づいてユーザーをフィルタリングする条件を設定します。 フィルターに条件を設定するには、ユーザー特性やナビゲーション特性に基づいてユーザーをフィルターするルールを設定します。 ユーザーデータをさらに分類するには、特定の訪問数や、ページビューのヒット数、画面のタップ数、メニューの選択肢に基づいて、各ユーザーをフィルターできます。 ただし、CRM またはロイヤルティシステムから取り込んだ属性に基づいてフィルタリングすることもできます。 フィルタービルダーは、これらのサブセットを作成するためのシンプルなアーキテクチャで、訪問者／訪問／ヒットコンテナの順にネストされた階層的なコンテナとしてルールを適用します。

フィルタービルダーで使用されるコンテナアーキテクチャでは、人物が最も外側のコンテナとして定義されます。 コンテナには、セットトップボックスの訪問およびページビュー、モバイルアプリケーション画面、メニュー画面など、ユーザーに固有の包括的なデータが含まれています。 ネストされたセッションコンテナを使用すると、ユーザーのデータをセッションに基づいて分類するルールを設定でき、ネストされたイベントコンテナを使用すると、ユーザーの情報を個々のインタラクションに基づいて分類できます。 各コンテナを使用すると、個人の履歴、セッション別に分類されたインタラクション、または個々のエクスペリエンスイベントの分類についてレポートできます。

### ユーザーコンテナ {#person}

ユーザーコンテナには、指定した期間内のユーザーに対するすべての訪問とページビュー、モバイルアプリ画面、セットトップボックス、またはコンソールゲーム操作が含まれます。 基本的に、Customer Journey Analytics接続内で定義したデータセットに含まれる、すべてのエクスペリエンスイベントです。 ユーザーレベルのフィルターは、条件を満たすページビュー数、モバイルアプリまたはセットトップボックス画面を返します。 さらに、オンラインチャネルとオフラインチャネルをまたいで、その同じ人物による他のすべてのインタラクション（定義された日付範囲によってのみ制限される）も含まれます。 最も広く定義されたコンテナとして、人物コンテナレベルで生成されたレポートは、すべての訪問をまたいでページビューやモバイルアプリ画面などを返し、複数訪問のクロスチャネル分析を生成できます。 したがって、個人コンテナは、定義された日付範囲に基づいて最も変更されやすくなっています。
人物コンテナには、人物の全体的な履歴に基づく値を含めることができます。

- 初回購入までの日数
- オリジナルの入口ページまたはモバイルアプリのホーム画面
- オリジナルの参照ドメイン

### セッションコンテナ {#session}

セッションコンテナでは、特定のセッションのページインタラクション、モバイルアプリインタラクション、キャンペーンまたはコンバージョンを識別できます。 セッションコンテナは、ルールに合致すると訪問セッション全体での動作をキャプチャするので、最も一般的に使用されるコンテナです。 セッション コンテナでは、フィルターの作成と適用に含める、または除外するセッションを定義することもできます。 次の質問に答えるのに役立ちます。

- Web とコールセンターの両方のデータソースと関与したセッションの数
- 購入へのコンバージョンにつながったページが何ページありましたか？

セッションコンテナには、1 回のセッションあたりの発生件数に基づく値が含まれます。

- セッションタイプ
- 入口ページ
- 再来訪頻度
- パーティシペーション指標
- 線形的に割り当てられた指標

Customer Journey Analyticsのデータビューを使用すると、セッションの持続時間だけでなく、新しいセッションを作成するタイミングも決定できます。 例えば、ユーザーがモバイルアプリを起動するたびに基づいて、新しいモバイルアプリセッションを定義できます。 詳しくは、[ セッション設定 ](/help/data-views/session-settings.md) を参照してください。

### イベントコンテナ {#event}

イベントコンテナは、フィルターに含めたりフィルターから除外したりするページ、モバイルアプリケーションまたはその他のタイプのイベントを定義します。 これは、条件が true のモバイルアプリで特定のクリック数、ページビュー数、ボタンのタップ数を識別するために使用できる最も狭いコンテナです。 イベントコンテナを使用すると、単一のトラッキングコードを表示したり、モバイルアプリの特定の領域内の動作を分離したりできます。 また、アクションが発生したときの特定の値（注文が発生したときのマーケティングチャネルなど）を把握することもできます。

イベントコンテナには、値ベースの、次の項目に対する単一ページの分類が含まれます。

- 製品
- リスト prop
- リストディメンション
- マーチャンダイジングディメンション （イベントのコンテキスト内）

## 標準提供のフィルターテンプレート {#template}

従来の Analytics には、多数の標準テンプレートと計算指標が用意されています。 その多くは、Customer Journey Analyticsに当てはまらないか、名前を変更するか、再作成する必要があります。 その他は、Customer Journey Analytics内のコンテキスト対応変数のソリューションに依存します。

| フィルター名 | 説明 |
| --- | --- |
| すべてのデータ | すべてのデータは、フリーフォームテーブルの行に指標を追加したときにレポートに動的に追加される必須フィルターです。 |
