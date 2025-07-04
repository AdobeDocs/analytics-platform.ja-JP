---
description: セグメントビルダーは、コンテナ階層ロジック、ルールおよび演算子に基づいて、指標ディメンション、セグメントおよびイベントをセグメント担当者にドラッグ&ドロップするキャンバスです。 この統合開発ツールを使用すると、訪問やイベントをまたいで人物の属性とアクションを識別する、シンプルまたは複雑なセグメントを作成および保存できます。
title: セグメントの構築
feature: Filters, Segments
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: ec2fc88372814b01a04d4cc824181222ee55a83d
workflow-type: tm+mt
source-wordcount: '1569'
ht-degree: 51%

---

# セグメントの構築 {#build-segments}

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="オーディエンスの作成"
>abstract="セグメントからオーディエンスを作成し、Adobe Experience Platform と共有してアクティブ化することができます。"

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="データのプレビュー"
>abstract="このセグメントのデータとデータビューのデータを比較します。プレビューの割合は、**過去 90 日間**&#x200B;のデータビューの合計数に基づきます。<br><br/>プレビューが読み込まれない場合、接続でバックフィル中の可能性があります。"

**[!UICONTROL セグメントビルダー]** ダイアログでは、新しいセグメントの作成や既存のセグメントの編集を行うことができます。 ダイアログのタイトルは、**[!UICONTROL セグメント]** マネージャーから作成または管理するセグメントの場合、**&#x200B;** 新規セグメント [[!UICONTROL &#x200B; または &#x200B;] セグメントを編集 ](/help/components/segments/seg-manage.md) になります。

>[!BEGINTABS]

>[!TAB  セグメントビルダー ]

![ 次の節で説明するフィールドとオプションを表示するセグメントの詳細ウィンドウ。](assets/filter-builder.png)

>[!TAB  セグメントの作成または編集 ]

![ 次の節で説明するフィールドとオプションを表示するセグメントの詳細ウィンドウ。](assets/create-edit-filter.png)

>[!ENDTABS]

1. 次の詳細を指定します（![必須](/help/assets/icons/Required.svg)は必須です）。

   | 要素 | 説明 |
   | --- | --- |
   | **[!UICONTROL データビュー]** | セグメントのデータ表示を選択できます。  定義したセグメントは、データビューの [ 設定 ](/help/data-views/create-dataview.md#settings-filters) タブでセグメントとして使用できます。 |
   | **[!UICONTROL プロジェクトのみのセグメント]** | セグメントが作成されたプロジェクトでのみ表示され、セグメントがコンポーネントリストに追加されないことを説明する情報ボックス。 **[!UICONTROL このセグメントをすべてのプロジェクトで使用できるようにして、コンポーネントリストに追加する]** を有効にして、その設定を変更します。 この情報ボックスは、[ クイックセグメント ](seg-quick.md) インターフェイスから **[!UICONTROL ビルダーを開く]** を使用して [!UICONTROL &#x200B; クイックセグメント &#x200B;] を作成し、クイックセグメント情報を通常のセグメントに切り替えた場合にのみ表示されます。 |
   | **[!UICONTROL タイトル]** ![必須](/help/assets/icons/Required.svg) | セグメントに名前を付けます（例：`Last month mobile customers`）。 |
   | **[!UICONTROL 説明]** | セグメントの説明（例：`Segment to define the mobile customers for the last month`）を指定します。 |
   | **[!UICONTROL タグ]** | 1 つ以上のタグを作成または適用して、セグメントを整理します。 入力を開始すると、選択できる既存のタグが見つかります。または、**[!UICONTROL Enter]** キーを押して新しいタグを追加します。「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択して、タグを削除します。 |
   | **[!UICONTROL 定義]** ![必須](/help/assets/icons/Required.svg) | [定義ビルダー](#definition-builder)を使用して、セグメントを定義します。 |

   {style="table-layout:auto"}

1. セグメント定義が正しいかどうかを確認するには、右上にあるセグメントの結果の絶えず更新されるプレビューを使用します。
1. セグメントからオーディエンスを作成し、Experience Platformとオーディエンスを共有するには、「**[!UICONTROL セグメントからオーディエンスを作成]**」を選択します。 詳しくは、[オーディエンスの作成と公開](/help/components/audiences/publish.md)を参照してください。
1. 次のいずれかを選択します。
   * **[!UICONTROL 保存]**：セグメントを保存します。
   * **[!UICONTROL 名前を付けて保存]**：セグメントのコピーを保存します。
   * **[!UICONTROL 削除]**：セグメントを削除します。
   * **[!UICONTROL キャンセル]**：セグメントに加えた変更をキャンセルするか、新しいセグメントの作成をキャンセルします。


## 定義ビルダー

セグメント定義を作成するには、定義ビルダーを使用します。 この作成では、コンポーネント、コンテナ、演算子およびロジックを使用します。

定義のタイプと範囲を設定できます。

1. 定義のタイプを指定するには、この作成にインクルード定義または除外定義を含めるかどうかを指定します。![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL オプション]** を選択し、ドロップダウンメニューから **[!UICONTROL 含める]** または **[!UICONTROL 除外]** を選択します。
1. 定義の範囲を指定するには、**[!UICONTROL 含める]** または **[!UICONTROL 除外]** ドロップダウンメニューから、定義の範囲を **[!UICONTROL イベント]**、**[!UICONTROL セッション]**、**[!UICONTROL 人物]**、**[!UICONTROL グローバルアカウント]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL アカウント]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL オポチュニティ]** [!BADGE B2B editionB2B edition &#x200B;]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 購入グループ]**&rbrack;{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} のいずれにするかを選択します

これらの設定は、後で常に変更できます。

### コンポーネント

セグメント定義の構成の重要な部分は、ディメンション、指標、既存のセグメントおよび日付範囲を使用することです。 これらのすべてのコンポーネントは、セグメントビルダーのコンポーネントパネルから使用できます。

![定義の作成を開始](assets/start-building-filter.gif){width=100%}

コンポーネントを追加するには、次の手順に従います。

1. コンポーネントパネルからコンポーネントを **[!UICONTROL ここに指標、セグメント、ディメンションをドラッグ&amp;ドロップ]** にドラッグ&amp;ドロップします。 コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。
1. コンポーネントの詳細を指定します。例えば、「**[!UICONTROL 値を選択]**」から値を選択します。または値を入力します。1 つ以上の値を指定できる内容と方法は、コンポーネントと演算子によって異なります。
1. オプションで、デフォルトの演算子を変更します。例えば、**[!UICONTROL 等しい]**&#x200B;から&#x200B;**[!UICONTROL 次のいずれかと等しい]**&#x200B;に変更します。使用可能な演算子の概要について詳しくは、[演算子](seg-operators.md)を参照してください。

コンポーネントを編集するには：

* 「演算子」ドロップダウンメニューからコンポーネントの新しい演算子を選択します。
* 必要に応じて、演算子に別の値を選択または指定します。
* コンポーネントタイプがディメンションの場合は、アトリビューションモデルを定義できます。 詳しくは、[アトリビューションモデル](#attribution)を参照してください。

コンポーネントを削除するには：

* コンポーネントで「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択します。

### コンテナ

複数のコンポーネントを 1 つ以上のコンテナにグループ化し、コンテナ内およびコンテナ間でロジックを定義できます。コンテナを使用すると、セグメントの複雑な定義を作成できます。

![コンテナを追加](assets/add-container.gif){Width=100%}

* コンテナを追加するには、![設定](/help/assets/icons/Setting.svg) **[!UICONTROL オプション]** から「**[!UICONTROL コンテナを追加]**」を選択します。
* 既存のコンポーネントをコンテナに追加するには、コンテナにコンポーネントをドラッグ＆ドロップします。
* 別のコンポーネントをコンテナに追加するには、コンポーネントパネルからコンテナにコンポーネントをドラッグ＆ドロップします。青色の挿入線をガイドとして使用します。
* 別のコンポーネントをコンテナの外側に追加するには、コンテナの外側、メイン定義コンテナの内側にあるコンポーネントパネルからコンポーネントをドラッグ＆ドロップします。青色の挿入線をガイドとして使用します。
* コンテナ内のコンポーネント間、コンテナ間またはコンテナとコンポーネント間のロジックを変更するには、適切な「**[!UICONTROL および]**」、「**[!UICONTROL または]**」、「**[!UICONTROL 次に]**」を選択します。「次に」を選択すると、セグメントが順次セグメントに変換されます。 詳しくは、[ 順次セグメントの作成 ](seg-sequential-build.md) を参照してください。
* コンテナレベルを切り替えるには、![グローバル](/help/assets/icons/Globe.svg)「**[!UICONTROL グローバルアカウント]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、![アカウント](/help/assets/icons/Account.svg)「**[!UICONTROL アカウント]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、![商談](/help/assets/icons/Opportunity.svg)「**[!UICONTROL 商談]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、![購買グループ](/help/assets/icons/BuyingGroup.svg)「**[!UICONTROL 購買グループ]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、![Web ページ](/help/assets/icons/WebPage.svg)「**[!UICONTROL イベント]**」、![訪問](/help/assets/icons/Visit.svg)「**[!UICONTROL セッション]**」または![ユーザー](/help/assets/icons/User.svg)「**[!UICONTROL ユーザー]**」を選択します。

コンテナ内の ![設定](/help/assets/icons/Setting.svg) は、次のアクションに使用できます。

| コンテナアクション | 説明 |
|---|---|
| **[!UICONTROL コンテナを追加]** | ネストされたコンテナをコンテナに追加します。 |
| **[!UICONTROL 除外]** | 結果をセグメント定義のコンテナから除外します。 薄い赤色の左側のバーは、除外コンテナを示します。 |
| **[!UICONTROL 含める]** | コンテナからの結果をセグメント定義に含めます。 「含める」がデフォルトです。薄いグレーの左側のバーは、インクルードコンテナを示します。 |
| **[!UICONTROL コンテナに名前を付ける]** | コンテナの名前をデフォルトの説明から変更します。テキストフィールドに名前を入力します。入力しない場合、デフォルトの説明が使用されます。 |
| **[!UICONTROL コンテナを削除]** | 定義からコンテナを削除します。 |


## 日付範囲

周期的な日付範囲を含むセグメントを作成できます。 これにより、進行中のキャンペーンやイベントに関する質問に答えることができます。 例えば、*過去 60 日間にオンライン購入を行った全員* を含むセグメントを作成できます。

![ 相対日付範囲を使用したセグメント ](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [セグメントでの周期的な日付範囲](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## セグメントの積み重ね {#stack}

セグメントは、セグメントを使用して作成できます。 セグメントでセグメントを使用する場合、セグメントを最適化して複雑さを軽減できます。

デバイスタイプ（2）と米国の状態（50）の組み合わせでセグメント化するとします。 デバイスタイプ（携帯電話かタブレットか）と米国の州の一意の組み合わせごとに、100 個のセグメントを作成できます。 カリフォルニア州のタブレットユーザーを取得するには、100 個のセグメントのいずれかを使用します。

![ カリフォルニアとタブレットのシンプルセグメント ](assets/filter-ca-tablet-single.png)

または、52 のセグメントを定義できます。米国の州に 50 のセグメント、携帯電話用に 1 つ、タブレット用に 1 つずつです。 次に、セグメントを積み重ねて同じ結果を取得します。 カリフォルニア州のタブレットユーザーを取得するには、次の 2 つのセグメントを積み重ねます。

![CA とタブレット向けの積み重ねセグメント ](assets/filter-ca-tablet-stacked.png)


## アトリビューション {#attribution}

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="繰り返し"
>abstract="ディメンションのインスタンスと持続値を含みます。"


>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="インスタンス"
>abstract="ディメンションのインスタンスを含みます。"


>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="繰り返さないインスタンス"
>abstract="ディメンション固有の（繰り返さない）インスタンスを含みます。"




セグメントビルダーでディメンションを使用する場合、そのディメンションのアトリビューションモデルを指定するオプションがあります。 選択したアトリビューションモデルによって、ディメンションコンポーネントに指定した条件に対して選定されるデータが決まります。

ディメンションコンポーネント内で ![設定](/help/assets/icons/Setting.svg) を選択し、ポップアップからアトリビューションモデルのいずれかを選択します。

| モデル | 説明 |
|---|---|
| **[!UICONTROL 繰り返しモデル（デフォルト）]** | ディメンションにインスタンスと永続化された値を含めると、選定が決まります。 |
| **[!UICONTROL インスタンス]** | ディメンションにインスタンス値のみを含めると、選定が決まります。 |
| **[!UICONTROL 繰り返さないインスタンス]** | ディメンションに一意のインスタンス（繰り返さない）値を含めると、選定が決まります。 |


![ セグメント構築時のディメンションのアトリビューションモデル ](assets/filter-dimension-attribution.png)

### 例

セグメント定義の一部として、条件「ページ名が女性に等しい」を指定しました。 上記の例と同様です。 他の 2 つのアトリビューションモデルを使用して、このセグメント定義を繰り返します。 したがって、3 つのセグメントそれぞれに独自のアトリビューションモデルがあります。

* 女性ページ - アトリビューション - 繰り返し（デフォルト）
* 女性ページ - アトリビューション - インスタンス
* 女性ページ - アトリビューション - 繰り返さないインスタンス


次の表に、各アトリビューションモデルについて、この条件で選定 ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) される受信イベントを示します。


| 女性ページ - アトリビューション - <br/>*アトリビューションモデル* | イベント 1：<br/>ページ名が<br/>女性と等しい | イベント 2：<br/>ページ名が<br/>男性と等しい | イベント 3：<br/>ページ名が<br/>女性と等しい | イベント 4：<br/>ページ名が<br/>女性と等しい<br/>（永続化） | イベント 5：<br/>ページ名が<br/>チェックアウトと等しい | イベント 6：<br/>ページ名が<br/>女性と等しい | イベント 7：<br/>ページ名が<br/>ホームと等しい |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 繰り返し（デフォルト） | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) |
| インスタンス | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) |
| 繰り返さないインスタンス | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) | ![削除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![削除](/help/assets/icons/Remove.svg) |

3 つのセグメントを使用したイベントに関するレポートの例は次のとおりです。

![ セグメント属性モデルの結果 ](assets/filter-dimension-attribution-results.png)
