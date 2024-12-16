---
description: フィルタービルダーは、指標Dimension、フィルターおよびイベントをドラッグ&ドロップし、コンテナ階層ロジック、ルールおよび演算子に基づいてユーザーをフィルタリングするためのキャンバスです。 この統合開発ツールを使用すると、訪問やイベントをまたいでユーザーの属性とアクションを識別する、シンプルまたは複雑なフィルターを作成して保存できます。
title: フィルターの作成
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 8772f2dcd5f9c20ca9d366b8c172218f45e4713c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 7%

---

# フィルターの作成 {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_createaudience"
>title="オーディエンスの作成"
>abstract="オーディエンスは、フィルターから作成して、アクティブ化するために Adobe Experience Platform と共有できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filter_datapreview"
>title="データのプレビュー"
>abstract="このフィルターのデータをデータビューのデータと比較します。 プレビューの割合は、**過去 90 日間** のデータビューの合計数に基づきます。<br><br/> プレビューが読み込まれない場合、接続がまだバックフィル中の可能性があります。"

<!-- markdownlint-enable MD034 -->



**[!UICONTROL フィルタービルダー]** ダイアログでは、新しいフィルターの作成や、既存のフィルターの編集を行えます。 このダイアログには、「**[!UICONTROL フィルター]** マネージャーから作成または管理するフィルターのタイトルが **** 新しいフィルター [[!UICONTROL  または ] フィルターを編集 ](/help/components/filters/manage-filters.md) と表示されます。

>[!BEGINTABS]

>[!TAB  フィルタービルダー ]

![ 次の節で説明するフィールドとオプションを表示するフィルターの詳細ウィンドウ。](assets/filter-builder.png)

>[!TAB  フィルターの作成または編集 ]

![ 次の節で説明するフィールドとオプションを表示するフィルターの詳細ウィンドウ。](assets/create-edit-filter.png)

>[!ENDTABS]

1. 次の詳細を指定します（![必須](/help/assets/icons/Required.svg)は必須です）。

   | 要素 | 説明 |
   | --- | --- |
   | **[!UICONTROL データビュー]** | フィルターのデータ表示を選択できます。  定義したフィルターは、データビューの [ 設定 ](/help/data-views/create-dataview.md#settings-filters) タブでフィルターとして使用できます。 |
   | **[!UICONTROL プロジェクトのみのフィルター]** | フィルターが作成されたプロジェクトにのみ表示され、フィルターがコンポーネントリストに追加されないことを説明する情報ボックス。 **[!UICONTROL このフィルターをすべてのプロジェクトで使用できるようにして、コンポーネントリストに追加する]** を有効にして、その設定を変更します。 この情報ボックスは、[ クイックフィルター ](quick-filters.md) インターフェイスから **[!UICONTROL ビルダーを開く]** を使用して [!UICONTROL  クイックフィルター ] を作成し、クイックフィルター情報を標準フィルターに切り替えた場合にのみ表示されます。 |
   | **[!UICONTROL タイトル]** ![必須](/help/assets/icons/Required.svg) | フィルターに名前を付けます（例：`Last month mobile customers`）。 |
   | **[!UICONTROL 説明]** | フィルターの説明（例：`Filter to define the mobile customers for the last month`）を指定します。 |
   | **[!UICONTROL タグ]** | 1 つ以上のタグを作成または適用して、フィルターを整理します。 入力を開始して、選択可能な既存のタグを検索します。または、**[!UICONTROL Enter]** キーを押して新しいタグを追加します。 「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択して、タグを削除します。 |
   | **[!UICONTROL 定義]** ![ 必須 ](/help/assets/icons/Required.svg) | [ 定義ビルダー ](#definition-builder) を使用してフィルターを定義します。 |

   {style="table-layout:auto"}

1. フィルター定義が正しいかどうかを確認するには、右上のフィルターの結果の絶えず更新されるプレビューを使用します。
1. フィルターからオーディエンスを作成し、Experience Platformとオーディエンスを共有するには、「**[!UICONTROL フィルターからオーディエンスを作成]**」を選択します。 詳しくは、[ オーディエンスの作成と公開 ](/help/components/audiences/publish.md) を参照してください。
1. 選択：
   * **[!UICONTROL 保存]**：フィルターを保存します。
   * **[!UICONTROL 名前を付けて保存]**：フィルターのコピーを保存します。
   * **[!UICONTROL 削除]**：フィルターを削除します。
   * **[!UICONTROL キャンセル]**：フィルターに加えた変更をキャンセルしたり、新しいフィルターの作成をキャンセルしたりします。


## 定義ビルダー

定義ビルダーを使用して、フィルター定義を作成します。 この構成では、コンポーネント、コンテナ、演算子、ロジックを使用します。

定義のタイプと範囲を設定できます。

1. 定義のタイプを指定するには、ビルドにインクルード定義または除外定義を含めるかどうかを指定します。 ![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL オプション]** を選択し、ドロップダウンの切り替え **[!UICONTROL 含める]** または **[!UICONTROL 除外]** から選択します。
1. 定義の範囲を指定するには、「**[!UICONTROL 含める]**」または **[!UICONTROL 除外]** ドロップダウンから、定義の範囲を **[!UICONTROL イベント]**、**[!UICONTROL セッション]**、**[!UICONTROL 人物]** のいずれにするかを選択します。

これらの設定は、後でいつでも変更できます。

### コンポーネント

フィルター定義の構成の重要な部分は、ディメンション、指標、既存のフィルターおよび日付範囲を使用することです。 これらのすべてのコンポーネントは、フィルタービルダーのコンポーネントパネルから使用できます。

![ 定義の作成を開始 ](assets/start-building-filter.gif){width=100%}

コンポーネントを追加するには、次の手順に従います。

1. コンポーネントパネルからコンポーネントを **[!UICONTROL ここに指標、フィルター、Dimensionをドラッグ&amp;ドロップ]** にドラッグ&amp;ドロップします。 コンポーネントバーの ![ 検索 ](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。
1. コンポーネントの詳細を指定します 例えば、「値を選択 **[!UICONTROL から値を選択し]** す。 または値を入力します。 1 つ以上の値を指定する内容と方法は、コンポーネントと演算子によって異なります。
1. 必要に応じて、デフォルトの演算子を変更します。 例えば、から **[!UICONTROL equals]** へ **[!UICONTROL equals any of]** へ。 使用可能な演算子の詳細な概要については、[ 演算子 ](operators.md) を参照してください。

コンポーネントを編集するには：

* 「演算子」ドロップダウンメニューからコンポーネントの新しい演算子を選択します。
* 必要に応じて、演算子に別の値を選択または指定します。
* コンポーネントタイプがディメンションの場合、アトリビューションモデルを定義できます。 詳しくは、[ アトリビューションモデル ](#attribution-models) を参照してください。

コンポーネントを削除するには：

* コンポーネントで ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択します。

### コンテナ

複数のコンポーネントを 1 つ以上のコンテナにグループ化し、コンテナ内およびコンテナ間のロジックを定義できます。 コンテナを使用すると、フィルターの複雑な定義を作成できます。

![ コンテナを追加 ](assets/add-container.gif){Width=100%}

* コンテナを追加するには、**[!UICONTROL 設定]****[!UICONTROL オプション ![ から ](/help/assets/icons/Setting.svg) コンテナを追加]** を選択します。
* 既存のコンポーネントをコンテナに追加するには、コンポーネントをコンテナにドラッグ&amp;ドロップします。
* 別のコンポーネントをコンテナに追加するには、コンポーネントパネルからコンテナにコンポーネントをドラッグ&amp;ドロップします。 青い挿入ラインをガイドとして使用します。
* 別のコンポーネントをコンテナの外側に追加するには、コンポーネントパネルからコンテナの外側、メイン定義コンテナの内側にコンポーネントをドラッグ&amp;ドロップします。 青い挿入ラインをガイドとして使用します。
* コンテナ内のコンポーネント間、コンテナ間、コンテナとコンポーネント間のロジックを変更するには、適切な **[!UICONTROL And]**、**[!UICONTROL Or]**、**[!UICONTROL Then]** を選択します。 「次に」を選択すると、フィルターが順次フィルターに変わります。 詳しくは、[ 順次フィルターの作成 ](seg-sequential-build.md) を参照してください。
* コンテナレベルを切り替えるには、![WebPage](/help/assets/icons/WebPage.svg)**[!UICONTROL Event]**、![Visit](/help/assets/icons/Visit.svg)**[!UICONTROL Session]** または ![User](/help/assets/icons/User.svg)**[!UICONTROL Person]** を選択します。

以下の操作を行うために、コンテナで ![ 設定 ](/help/assets/icons/Setting.svg) を使用できます。

| コンテナアクション | 説明 |
|---|---|
| **[!UICONTROL コンテナを追加]** | コンテナにネストされたコンテナを追加します。 |
| **[!UICONTROL 除外]** | 結果をフィルター定義のコンテナから除外します。 薄い赤い左側のバーは、除外コンテナを示しています。 |
| **[!UICONTROL 含める]** | コンテナの結果をフィルター定義に含めます。 デフォルトは「含める」です。 薄いグレーの左バーは、インクルードコンテナを示します。 |
| **[!UICONTROL Name コンテナ]** | コンテナの名前をデフォルトの説明から変更します。 テキストフィールドに名前を入力します。 入力しない場合、デフォルトの説明が使用されます。 |
| **[!UICONTROL コンテナを削除]** | 定義からコンテナを削除します。 |


## 日付範囲

周期的な日付範囲を含むフィルターを作成できます。 そのため、実施中のキャンペーンやイベントに関する質問に答えることができます。 例えば、「過去 60 日間にオンライン購入を行った全員 *を含むフィルターを作成でき* す。

![ 相対日付範囲を使用したフィルター ](assets/filter-rolling-date-range.gif)

+++ 以下は、フィルターでの周期的な日付範囲の使用に関するビデオです

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

{{videoaa}}

+++

## フィルターを積み重ねる {#stack}

フィルターを使用してフィルターを作成できます。 フィルターでフィルターを使用すると、フィルターを最適化して複雑さを軽減できます。

デバイスタイプ（2）と米国状態（50）の組み合わせでフィルタリングするとします。 デバイスタイプ（携帯電話かタブレットか）と米国の州の独自の組み合わせに対して、それぞれ 100 個のフィルターを作成できます。 カリフォルニアのタブレットユーザーを取得するには、100 個のフィルターのいずれかを使用します。

![CA・タブレット用シンプルフィルター ](assets/filter-ca-tablet-single.png)

または、52 個のフィルターを定義できます。米国の州用に 50 個、携帯電話用に 1 個、タブレット用に 1 個のフィルターです。 次に、フィルターを積み重ねて、同じ結果を取得します。 カリフォルニアのタブレットユーザーを取得するには、次の 2 つのフィルターを積み重ねます。

![CA・タブレット用積層フィルター ](assets/filter-ca-tablet-stacked.png)


## アトリビューション {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_repeating"
>title="繰り返し"
>abstract="ディメンションのインスタンスと持続値を含みます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_instance"
>title="インスタンス"
>abstract="ディメンションのインスタンスと持続値を含みます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_nonrepeatinginstance"
>title="繰り返しなしインスタンス"
>abstract="ディメンション固有の（繰り返さない）インスタンスを含みます。"

<!-- markdownlint-enable MD034 -->



フィルタービルダーでディメンションを使用する場合、そのディメンションのアトリビューションモデルを指定するオプションがあります。 選択した属性モデルによって、データがディメンションコンポーネントに指定した条件に該当するかどうかが決まります。

ディメンションコンポーネント内で ![ 設定 ](/help/assets/icons/Setting.svg) を選択し、ポップアップからアトリビューションモデルの 1 つを選択します。

| モデル | 説明 |
|---|---|
| **[!UICONTROL 繰り返しモデル（デフォルト）]** | 検証を決定するために、ディメンションのインスタンスと持続値を含めます。 |
| **[!UICONTROL インスタンス]** | 検証を決定するために、ディメンションのインスタンス値のみを含めます。 |
| **[!UICONTROL 繰り返さないインスタンス]** | 選定を決定するために、ディメンションに一意のインスタンス（繰り返さない）値を含めます。 |


![ フィルター構築時のディメンションのアトリビューションモデル ](assets/filter-dimension-attribution.png)

### 例

フィルター定義の一部として、条件「ページ名が女性に等しい」を指定しました。 上記の例と同様です。 他の 2 つのアトリビューションモデルを使用して、このフィルター定義を繰り返します。 したがって、3 つのフィルターがあり、それぞれに独自のアトリビューションモデルが設定されています。

* 女性ページ – アトリビューション – 繰り返し（デフォルト）
* 女性ページ – アトリビューション – インスタンス
* 女性ページ – アトリビューション – 繰り返さないインスタンス


次の表に、アトリビューションモデルごとに、その条件で認定される受信イベント ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) を示します。


| 女性ページ – アトリビューション - <br/>*アトリビューションモデル* | イベント 1:<br/> ページ名 equals<br/>Women | イベント 2:<br/> ページ名 equals<br/>Men | イベント 3:<br/> ページ名 equals<br/>Women | イベント 4:<br/> ページ名が次と等しい <br/> 女性 <br/> （永続） | イベント 5:<br/> ページ名が等しい <br/> チェックアウト | イベント 6:<br/> ページ名 equals<br/>Women | イベント 7:<br/> ページ名が <br/> ホームと等しい |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 繰り返し（デフォルト） | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) |
| インスタンス | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) |
| 繰り返しなしインスタンス | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![削除](/help/assets/icons/Remove.svg) | ![削除](/help/assets/icons/Remove.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) |

3 つのフィルターを使用したイベントに関するレポートの例を次に示します。

![ 属性モデル結果のフィルタリング ](assets/filter-dimension-attribution-results.png)
