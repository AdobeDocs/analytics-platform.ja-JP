---
description: 順次フィルターは、THEN 演算子を使用してフィルター条件のシーケンスを定義するフィルターです。
title: 順次フィルター
feature: Filters
exl-id: 64cb10b5-36f0-42c8-b687-ae5de5ced8b5
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '2460'
ht-degree: 3%

---

# 順次フィルター

順次フィルターは、コンポーネント、コンテナおよびコンポーネントまたはコンテナの間の [!UICONTROL Then] 論理演算子を使用して作成します。 [!UICONTROL Then] 論理演算子は、1 つのフィルター条件が発生し、その後に別のフィルター条件が発生することを意味します。



>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ 順次セグメント化 ](https://video.tv.adobe.com/v/25405/?quality=12&learn=on){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]

順次フィルターには、いくつかの [ 基本機能 ](#basics) と、順次フィルターをより複雑にするために設定できる追加オプションがあります。

![ 順次フィルター ](assets/sequential-filter.gif)

* シーケンスフィルター定義内の Then ロジックの [After and within](#after-and-within) 制約：

* フィルター定義のシーケンス全体の一部として [ 含める ](#include) データ。 コンテナの一部として定義されたシーケンスの場合は、または。 デフォルトでは、一致するすべてのデータが考慮されます。 そのデータは ![UserGroup](/help/assets/icons/UserGroup.svg)[!UICONTROL Everyone を含める ] で識別されます。

   * シーケンスの前のデータのみを考慮するには、「![SequenceBefore](/help/assets/icons/SequenceBefore.svg)**[!UICONTROL シーケンスの前のみ]**」を選択します。
   * シーケンスの後のデータのみを考慮するには、「![SequenceAfter](/help/assets/icons/SequenceAfter.svg)**[!UICONTROL Only After Sequence]**」を選択します。

* 順次フィルター定義の一部として [ 除外 ](#exclude) するデータ。

* 順次フィルター定義での条件の [ 論理グループ化 ](#logic-group) 方法。

## 基本



順次フィルターの作成の基本は、[ フィルタービルダー ](filter-builder.md) を使用して通常のフィルターを作成する場合と同じです。 [ 定義ビルダー ](filter-builder.md#definition-builder) を使用して、フィルター定義を作成できます。 この構成では、コンポーネント、コンテナ、演算子、ロジックを使用します。 通常フィルターは、メイン定義または [ 定義ビルダー ](filter-builder.md#definition-builder) 内で使用する任意のコンテナで **[!UICONTROL Then]** 演算子を選択するとすぐに、自動的に順次フィルターになります。

### 例

以下の例は、様々なユースケースで順次フィルターを使用する方法を示しています。

#### 単純なシーケンス

ページを表示してから別のページを表示した人物を特定します。 イベントレベルのデータは、このシーケンスを使用してフィルタリングされます。 前、過去、中間のユーザーのセッションや、セッション間で発生したページビューの時間や数には関係ありません。

![ 順次フィルター everyone を含める ](assets/sequence-include-everyone.png)

#### セッション間のシーケンス

あるセッションでページを表示した後に別のセッションで別のページを表示したユーザーを識別します。 セッションを区別するには、コンテナを使用してシーケンスを作成し、コンテナごとに ![ 訪問 ](/help/assets/icons/Visit.svg)**[!UICONTROL セッション]** レベルを定義します。

![ セッション間のシーケンスフィルター ](assets/sequence-filter-session.png)

#### 混合レベルシーケンス

特定されていないセッション数で 2 ページを閲覧したユーザーを特定してから、別のセッションで 3 ページ目を閲覧します。 この場合も、コンテナを使用してシーケンスを作成し、個別のセッションを定義するコンテナで ![ 訪問 ](/help/assets/icons/Visit.svg) **[!UICONTROL セッション]** レベルを定義します。

![ 個別の最終セッションを使用したシーケンスフィルター ](assets/sequence-filter-final-session.png)

#### 集計シーケンス

最初のセッションで特定のページにアクセスし、後で他のページにアクセスしたユーザーを特定します。 イベントのシーケンスを区別するには、コンテナを使用して ![WebPage](/help/assets/icons/WebPage.svg)**[!UICONTROL Session]** コンテナレベルでロジックを区切ります。

![ セッション集計コンテナ ](assets/session-aggregate-containers.png)


#### シーケンスをネスト

あるユーザーが別のページの前に訪問し、次に別の 2 ページを含むフォローアップセッションを行うすべてのセッションを特定します。 例えば、あるユーザーが最初にホームページを訪問したすべてのセッションを特定してから、カテゴリ 1 ページを訪問し、次に各セッションでカテゴリ 2 ページとカテゴリ 3 ページを訪問した他のセッションを識別します。

![ ネストされたシーケンス ](assets/sequence-nested.png)

## [!UICONTROL After] and [!UICONTROL Within]

**[!UICONTROL Then]** 演算子の ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]** と ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]** を使用して、さらに [time 制約 ](#time-constraints) または [Events、Sessions、またはDimensionの制約 ](#event-session-and-dimension-constraints) を定義できます。

### 時間制約

**[!UICONTROL Then]** 演算子に時間制約を適用するには：

1. ![Clock](/help/assets/icons/Clock.svg) を選択します。
1. コンテキストメニューから **[!UICONTROL Within]** または **[!UICONTROL After]** を選択します。
1. 期間（**[!UICONTROL 分]**、**[!UICONTROL 時間]** を **[!UICONTROL 年]**）まで指定します。
1. ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL *number *]**を選択すると、**[!UICONTROL -]**または**[!UICONTROL +]**を使用して数値を入力または指定できるポップアップが開きます。

時間制約を削除するには、![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用します。

時間制約演算子の詳細を次の表に示します。

| 演算子 | 説明 |
|--- |--- |
| **[!UICONTROL 後]** | [!UICONTROL After] 演算子は、2 つのチェックポイント間の時間の最小制限を指定するために使用されます。 「後」の値を設定すると、フィルターを適用した時点で制限時間が開始されます。 例えば、ページ A に訪問したユーザーを識別するコンテナに [!UICONTROL After] 演算子が設定されていて、1 日後までページ B に戻らない場合、訪問者がページ A を離れたところでその日が始まります。 訪問者をフィルターに含めるには、ページ A を離れてページ B を表示してから、少なくとも 1440 分（1 日）経つ必要があります。 |
| **[!UICONTROL 内部]** | [!UICONTROL Within] 演算子は、2 つのチェックポイントの間隔の最大値を指定するために使用します。例えば、ページ A にアクセスしたユーザーを識別するコンテナに [!UICONTROL Within] 演算子が設定され、その後 1 日以内にページ B に戻った場合、その日はページ A を離れたところから始まります。このフィルターに含めるには、ユーザーがページ B を開く前の最大時間を 1 日間とします。フィルターに含まれるユーザーの場合、ページ B を開くには、ページ A からページ B を表示してから最大 1440 分（1 日）以内にページ B を開く必要があります。 |
| **[!UICONTROL 後だが中]** | [!UICONTROL After] 演算子と [!UICONTROL Within] 演算子の両方を使用する場合、両方の演算子は順番ではなく、並行して開始および終了します。 <br/> 例えば、コンテナを `After = 1 Week(s) and Within = 2 Week(s)` に設定したフィルターを作成します。<br/> このフィルターで訪問者を識別するための条件が満たされるのは、1 ～ 2 週間のみです。 どちらの条件も、最初のページビューの時点から適用されます。 |


#### 例

時間制約の使用例をいくつか示します。

##### [!UICONTROL After] 演算子

2 週間後にのみ、あるページを訪問したユーザーと別のページを訪問したユーザーを特定します。 例えば、ホームページを訪問した人は、女性は |靴ページは 2 週間後のみ。

![ シーケンス後 ](assets/sequence-after.png)

ホームのページビューが 2024 年 6 月 1 日 00:01 に発生した場合、ページビューは Women に移動します | 2024 年 6 月 15 日（PT） 00:01 以降、ページビューが発生する限り、シューズは一致します。

##### [!UICONTROL Within] 演算子

5 分以内に、あるページを訪問したユーザーと別のページを訪問したユーザーを特定します。 例えば、ホームページにアクセスした訪問者が、次に女性ページにアクセスした訪問者です |5 分以内に靴ページ。

![ 内のシーケンス ](assets/sequence-within.png)

ホームのページビューが 2024 年 6 月 1 日 12:01 に発生した場合、ページビューは Women に移動します | 2024 年 6 月 15 日（PT） 12:16 より前にページビューが発生する限り、シューズは一致します。

##### [!UICONTROL After] but [!UICONTROL Within] 演算子

2 週間後から 1 か月以内に、あるページを訪問した後に別のページを訪問した人物を特定します。 例えば、ホームページにアクセスしてから 2 週間後、1 か月以内に女性を訪問した人物 |靴ページ。

![ シーケンスの後ろから内 ](assets/sequence-afterbutwithin.png)

2024 年 6 月 1 日にホームページにアクセスし、その女性を訪問するために戻っている人物 | 2019 年 6 月 15 日（PT）以降 00:01、ただし 2019 年 7 月 1 日（PT）より前のシューズページには該当するセグメントがあります。


### [!UICONTROL Event]、{Session] および [!UICONTROL 4}Dimension] の制約[!UICONTROL 

![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]** 制約および ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]** 制約を使用すると、時間制約だけでなく、イベント、セッション、ディメンションの制約も指定できます。 **[!UICONTROL イベント]**、**[!UICONTROL セッション]** または **[!UICONTROL その他のディメンション]** ![ 山形の権限 ](/help/assets/icons/ChevronRight.svg) **[!UICONTROL *Dimension名&#x200B;*]**を選択します。 「[!UICONTROL *検索*]」フィールドを使用して、ディメンションを検索できます。

#### 例

以下は、1 つの製品カテゴリページ（女性）にアクセスした人物を検索する順次フィルターの例です |靴）、チェックアウトページ（チェックアウト） |ありがとうございました）を 1 ページに収めました。

![ 内のシーケンスフィルター ](assets/sequence-filter-within.png)

次のシーケンス例は、一致するか一致しません。

| シーケンス | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|--- | :---: |
| ページ `Women \| Shoes` の後にページ `Checkout \| Thank You` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| ページ `Women \| Shoes`、ページ `Women \| Tops`、ページ `Checkout \| Thank You` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) |

## [!UICONTROL 含める]

順次フィルターまたは順次フィルターの一部である順次コンテナに含めるデータを指定できます。

### [!UICONTROL  全員 ] {#include_everyone}

全員を含む順次フィルターを作成するには、「![ ユーザーグループ ](/help/assets/icons/UserGroup.svg)**[!UICONTROL 全員を含める]** オプションを選択します。

順次フィルターは、指定したパターンに全体として一致するデータを識別します。  以下は、1 つの製品カテゴリページ（女性）にアクセスしたユーザーを検索する基本的なシーケンスフィルターの例です |靴）、チェックアウトページ（チェックアウト） |ありがとうございました）。 フィルターは ![ ユーザーグループ ](/help/assets/icons/UserGroup.svg)**[!UICONTROL 全員を含める]** に設定されています。

![ 順次フィルター everyone を含める ](assets/sequence-include-everyone.png)

次のシーケンス例は、一致するか一致しません。

| | シーケンス | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|---:|--- | --- |
| 1 | `Women \| Shoes` の後、同じセッションで `Checkout \| Thank You` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 2 | `Women \| Shoes` の後、`Men \| Shoes` の `Checkout \| Thank You` （異なるセッション間） | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 3 | `Checkout \| Thank You`、`Women \| Shoes` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) |

### [!UICONTROL  シーケンスの前のみ ] および [!UICONTROL  シーケンスの後のみ ]

オプション ![SequenceBefore](/help/assets/icons/SequenceBefore.svg)**[!UICONTROL Only Before Sequence]** および ![SequenceAfter](/help/assets/icons/SequenceAfter.svg)**[!UICONTROL Only After Sequence]** は、指定したシーケンスの前または後のサブセットにデータをフィルタリングします。

* ![SequenceBefore](/help/assets/icons/SequenceBefore.svg)**シーケンスの前のみ**：シーケンスの前のすべてのデータと、シーケンス自体の最初のデータを含みます。 シーケンスがデータの一部として複数回表示される場合、[!UICONTROL  シーケンスの前のみ ] には、シーケンスの最後の発生の最初のヒットとすべての前のヒットが含まれます。
* ![SequenceAfter](/help/assets/icons/SequenceAfter.svg)**Only After Sequence**：シーケンスとシーケンス自体の最後のデータの後のすべてのヒットを含みます。 シーケンスがデータの一部として複数回表示される場合、[!UICONTROL  シーケンスの後にのみ ] シーケンスの最初の発生の最後のヒットと、後続のすべてのヒットが含まれます。

B で識別される条件を持つコンポーネントのシーケンス、および D で識別される条件を持つコンポーネントの（Then）を指定する定義について考えてみます。3 つのオプションにより、データは次のように識別されます。


| B そして D | A | B | C | D | E | F |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| 全員を含む | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| シーケンスの前のみ | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |  |
| シーケンスの後のみ |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |



| B、D （複数回発生） | A | B | C | D | B | C | D | E |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 全員を含む | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| シーケンスの前のみ | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |
| シーケンスの後のみ |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |

#### 例

サイトセクション用の順次フィルターの 3 つのバージョンを定義しました。 オプション ![UserGroup](/help/assets/icons/UserGroup.svg)**[!UICONTROL Include Everyone]** を持つもの、オプション ![SequenceBefore](/help/assets/icons/SequenceBefore.svg)**[!UICONTROL Only Before Sequence]** を持つもの、オプション ![SequenceAfter](/help/assets/icons/SequenceAfter.svg)**[!UICONTROL Only After Sequence]** を持つもの。 3 つのフィルターに適切な名前を付けました。

![ シーケンスフィルター ](assets/site-section-filters.png)

これら 3 つのフィルターを使用してサイトセクションに関するレポートを作成する場合、フリーフォームテーブルの出力例は次のようになります。

![ 順次フィルターレポート ](assets/sequential-filter-freeform-table.png)

## [!UICONTROL 除外]

フィルター定義には、**[!UICONTROL 除外]** を使用して ![ ユーザー ](/help/assets/icons/User.svg) [!UICONTROL  ユーザー ]、![ 訪問 ](/help/assets/icons/Visit.svg) [!UICONTROL  セッション ] または ![web ページ ](/help/assets/icons/WebPage.svg) [!UICONTROL  イベント ] のデータを特別に除外しない限り、すべてのデータが含まれます。

[!UICONTROL  除外 ] を使用すると、一般的なデータを解除し、より焦点を絞ったフィルターを作成できます。 除外を使用すると、特定のユーザーグループを除外するフィルターを作成することもできます。 例えば、注文した人物を指定するフィルターを定義し、そのグループの人物を除外して *非購入者* を識別する場合などです。 ベストプラクティスは、特定の include 値に一致する特定のペルソナをターゲットに [!UICONTROL  除外 ] を使用しようとするのではなく、幅広い定義を使用するルールを作成することです。

除外定義の例を次に示します。

* **ページの除外**。フィルター定義を使用して、レポートから特定のページ （[ ホーム ページ *など*）を除外し、ページが `Home Page` に等しいイベント ルールを作成してから、ルールを除外します。 この定義には、「ホームページ *を除くすべてのページが自動的に含まれ* す。
* **参照ドメインの除外**。Google.comからの参照ドメインのみを含み、それ以外のドメインはすべて除外する定義を使用します。
* **非購入者の識別**。注文件数が 0 より大きい場合を識別し、[!UICONTROL  個人 ] を除外します。

[!UICONTROL  除外 ] を使用すると、ユーザーが特定のセッションに参加していない、または特定のイベントを実行していないシーケンスを識別できます。 [!UICONTROL  除外 ] は、[!UICONTROL  論理グループ ] に含めることもできます（以下を参照）。

コンテナは除外できますが、コンポーネントは除外できません。

### 例

[!UICONTROL  除外 ] の使用例については、以下を参照してください。

#### [!UICONTROL  除外 ] 内

あるページを訪問した人、別のページを訪問しなかった人、さらに別のページを訪問した人を特定します。 ![ 設定 ](/help/assets/icons/Setting.svg) 除外 ] を使用してコンテナを除外 [!UICONTROL  ます。 除外されたコンテナは、左側の薄い赤いバーで識別されます。

![ シーケンスを除外 ](assets/sequence-exclude.png)


#### 開始時の [!UICONTROL  除外 ]

別のページに移動せずに、あるページを訪問した人物を特定します。 例えば、これまでホームページを訪問したことがなく購入をチェックアウトした人などです。

![ シーケンス除外開始 ](assets/sequence-exclude-start.png)


#### 最後に [!UICONTROL  除外 ]

あるページを訪問したが、他のページを訪問しなかった人物を特定します。 例えば、ホームページを訪問したが、チェックアウトページにはアクセスしなかったユーザーです。

![ シーケンス除外の終了 ](assets/sequence-exclude-end.png)


## [!UICONTROL  論理グループ ]

>[!NOTE]
>
>[!UICONTROL  論理グループ ] は、順次フィルターでのみ定義できます。つまり、[!UICONTROL Then] 演算子がコンテナ内で使用されます。

論理グループを使用すると、条件を単一の順次フィルターチェックポイントにグループ化できます。 シーケンスの一部として、論理グループとして識別されるコンテナ内で定義されるロジックは、先行する順次チェックポイントの後、後続する順次チェックポイントの前に評価されます。

論理グループ内の条件は、どのような順序でも満たすことができます。 これに対して、非順次コンテナ（イベント、セッション、人物）では、シーケンス全体で条件を満たす必要がないので、Then 演算子で使用すると直感的でない結果が生じる可能性があります。

[!UICONTROL  論理グループ ] は、グループ化された条件の中で *複数の条件を、順序のないグループ* として扱うように設計されました。 それ以外の場合、論理グループ内の条件の順序は関係ありません。

論理グループを使用するためのベストプラクティスを次に示します。

* 順次チェックポイントをグループ化する。
* シーケンシャルフィルタの構成を簡単にする。

### 例

論理グループコンテナの使用例を以下に示します。

#### 任意の順序

あるページを訪問した人物を識別し、別のページのセットから各ページを任意の順序で表示しました。 例えば、ホームページを訪問した後、順序に関係なく、男性ページ、女性ページおよび子供ページを訪問したユーザーです。

このフィルターは [!UICONTROL  論理グループ ] を使用せずに構築できますが、構築は複雑で手間がかかります。 訪問者が表示できるページのシーケンスをすべて指定します。 わかりやすくするために、最初のコンテナのみ ![ChevronDown](/help/assets/icons/ChevronDown.svg) 開き、その他のコンテナは閉じます ![ChevronRight](/help/assets/icons/ChevronRight.svg)。 他のコンテナの内容は、タイトルから導き出すことができます。

![ 論理グループを使用しない例 ](assets/logicgroup-example-notusing.png)

次に示すように、[!UICONTROL  論理グループ ] を使用すると、このフィルターの作成を簡単に行うことができます。 コンテナには、必ず ![ グループ ](/help/assets/icons/Group.svg) **[!UICONTROL 論理グループ]** を選択します。

![ 論理グループを使用しない例 ](assets/logicgroup-example-using.png)

#### 最初の一致

あるページまたは別のページにアクセスしたユーザーを特定してから、さらに別のページにアクセスしたユーザーを特定します。 例えば、女性ページまたは男性ページにアクセスした後にチェックアウトにアクセスした人です |ありがとうページ。

![ 論理グループとの最初の一致を使用した例 ](assets/logicgroup-example-firstmatch.png)

#### [!UICONTROL Exclude][!UICONTROL And]

あるページを訪問したユーザーを識別し、他のページのセットには明示的に訪問しなかったが、さらに別のページには訪問したユーザーを識別します。 例えば、ホームページにアクセスしたユーザーは、男性ページや女性ページにはアクセスせず、子供ページにはアクセスしました。

![ 論理グループの除外および ](assets/logicgroup-exclude-and.png)

#### [!UICONTROL Exclude][!UICONTROL Or]

あるページを訪問したユーザーを識別し、一連のページのどのページにも明示的に訪問しなかったが、さらに別のページにも訪問したユーザーを識別します。 例えば、ホームページにアクセスしたユーザーは、男性および女性ページにはアクセスせず、子供ページにはアクセスしました。

![ 論理グループの除外および ](assets/logicgroup-exclude-or.png)


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->


## 最後の例

最後の例として、特定の製品ページについて学習したユーザーを特定します。このユーザーが「あなたの力を与える」キャンペーンに影響を受けることはありません。 そして、あなたのオンラインストアへの彼らの最初の訪問では、ホームページを見ましたが、男性カテゴリからのフィットネス（ギア）製品についてはこれ以上見ませんでした。 しかし、その直後の次のセッションでは、製品ページに移動し、最初にホームページを経由せずにオンライン注文を行いました。


![ 複雑な順次フィルターの例 ](assets/sequential-complex.png)
