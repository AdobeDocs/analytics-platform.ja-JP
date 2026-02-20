---
title: 永続性コンポーネントの設定
description: ディメンション値がイベント間で持続するかどうか、またはどのように持続するかを決定します。
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 75%

---


# [!UICONTROL 永続性] コンポーネントの設定 {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="永続性"
>abstract="ディメンションに適用されるデフォルトの配分モデルを設定します。配分は、レポートのセグメントの前に適用されます。"

<!-- markdownlint-enable MD034 -->



[!UICONTROL 永続性]とは、特定のディメンション値を、設定されたイベント以外の指標にも関連付けることのできる機能です。配分と有効期限の組み合わせを使用します。

![「永続性」オプションをハイライト表示するデータビューウィンドウ](../assets/persistence.png)

* **配分**&#x200B;では、1 つの列に同時に複数のディメンション項目を保持できる際、どの値が保持されるかを指定できます。

  >[!NOTE]
  >
  >レポートの指標に[デフォルト以外のアトリビューションモデル](/help/data-views/component-settings/attribution.md)を設定した場合、アトリビューションモデルでは、同じレポートのディメンションに設定した配分が無視されます。
  >
  >ただし、複数のディメンションを含む[完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md)を行う場合、アトリビューションでは各ディメンションに適用された配分モデルが保持されます。

* **有効期限** を使用すると、設定されたイベントを超えてディメンション項目が保持される期間を決定できます。

[!UICONTROL &#x200B; 永続性 &#x200B;] は、ディメンションでのみ使用でき、適用対象となるデータに遡って適用されます。 セグメント化や他の分析操作が適用される前に発生する即時のデータ変換です。

| 設定 | 説明 |
| --- | --- |
| [!UICONTROL 永続化を設定] | ディメンションの永続性を有効にします。永続性が有効になっていない場合、ディメンションは同じイベント内に存在する指標にのみ関連付けられます。この設定は、デフォルトで無効になっています。 |
| [!UICONTROL 配分] | 永続化のためにディメンションで使用される配分モデルを指定します。 オプションは次のとおりです。<ul><li>**[!UICONTROL 最新]**：ディメンション内の値は、後続の値で上書きされるまで保持されます</li><li> **[!UICONTROL オリジナル]**：このディメンションの最初の値は保持され、後続の値で上書きされません</li><li>**[!UICONTROL すべて]**：このディメンションのすべての値が同時に保持されます</li><li>**[!UICONTROL 最初の事例]**：このディメンションの最初の値が使用され、前後のすべてのイベントに適用されます。</li><li>**[!UICONTROL 最後の事例]**：このディメンションの最後の値が使用され、前後のすべてのイベントに適用されます。</li></ul> |
| [!UICONTROL 有効期限] | ディメンションの永続性ウィンドウを指定します。 オプションは次のとおりです。 <ul><li>**[!UICONTROL セッション]**（デフォルト）</li><li>**[!UICONTROL ユーザー]**</li><li>**[!UICONTROL カスタム時間]**</li><li>**[!UICONTROL 指標]**</li></ul>。場合によっては、購入時にディメンションの有効期限が切れるように設定できる必要があります（内部検索語や他のマーチャンダイジングの使用例など）。設定できる最大有効期限は 90 日です。 配分で「[!UICONTROL すべて]」を選択した場合は、「[!UICONTROL セッション]」または「[!UICONTROL 個人]」の有効期限のみ使用できます。 |

{style="table-layout:auto"}

## [!UICONTROL 配分] の設定

使用可能な配分設定は次のとおりです。

* **[!UICONTROL 最新]**：ディメンションに存在する最新の（タイムスタンプによる）値を保持します。ディメンションの有効期限内に発生した後続の値により、以前に保持されていた値が置き換えられます。このディメンションで「値なし」が [「値なし」オプション](no-value-options.md) で有効になっている場合、以前に保持された値は空の値で上書きされます。例えば、 [!UICONTROL 最新] の配分と [!UICONTROL セッション] の有効期限を含む次の表について考えてみましょう。

  | ディメンション | ヒット 1 | ヒット 2 | ヒット 3 | ヒット 4 | ヒット 5 |
  | --- | --- | --- | --- | --- | --- |
  | データセット値 |  | C | B |  | A |
  | 最新配分 |  | C | B | B | A |

* **[!UICONTROL オリジナル]**：有効期間中、ディメンション内に存在するタイムスタンプによってオリジナルの値を保持します。 このディメンションに値が含まれる場合、後続のイベントで別の値が表示されても、上書きされません。 例えば、 [!UICONTROL オリジナル] の配分と [!UICONTROL セッション] の有効期限を含む次の表について考えてみましょう。

  | ディメンション | ヒット 1 | ヒット 2 | ヒット 3 | ヒット 4 | ヒット 5 |
  | --- | --- | --- | --- | --- | --- |
  | データセット値 |  | C | B |  | A |
  | オリジナル配分 |  | C | C | C | C |

* **[!UICONTROL すべて]**：指標の [!UICONTROL パーティシペーション] アトリビューションモデルと似た動作をします。すべての値が等しく保持され、各値はレポート内の指標に対してフルクレジットを受け取ります。例えば、 [!UICONTROL すべて] の配分と [!UICONTROL セッション] の有効期限を含む次の表について考えてみましょう。

  | ディメンション | ヒット 1 | ヒット 2 | ヒット 3 | ヒット 4 | ヒット 5 |
  | --- | --- | --- | --- | --- | --- |
  | データセット値 | A | B | C |  | A |
  | 全配分 | A | A、B | A、B、C | A、B、C | A、B、C |

* **[!UICONTROL 最初の事例]**&#x200B;および&#x200B;**[!UICONTROL 最後の事例]**：（2022 年 1 月 19 日（PT））この 2 つの配分モデルは、「入口」および「出口」ディメンションのユースケースを満たします。指定された永続性スコープ (ルックバックでのセッション、ユーザー、またはルックバックを使用したカスタム期間) 内でディメンションの最初または最後の観測値を取得し、それを指定されたスコープ内のすべてのイベントに適用します。例：

  | ディメンション | ヒット 1 | ヒット 2 | ヒット 3 | ヒット 4 | ヒット 5 |
  | --- | --- | --- | --- | --- | --- |
  | タイムスタンプ（分） | 1 | 2 | 3 | 6 | 7 |
  | 元の値 |  | C | B |  | A |
  | 最初の事例 | C | C | C | C | C |
  | 最後の事例 | A | A | A | A | A |


## [!UICONTROL 有効期限] の設定

使用可能な有効期限設定は次のとおりです。

* **セッション**：特定のセッションの後に期限切れとなります。デフォルトの有効期限の期間。
* **ユーザーレポート期間**：レポート期間の最後に期限切れとなります。
* **グローバルアカウントレポート期間** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：レポート期間の最後に期限切れとなります。
* **アカウントレポート期間** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：レポート期間の最後に期限切れとなります。
* **商談レポート期間** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：レポート期間の最後に期限切れとなります。
* **購買グループレポート期間** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：レポート期間の最後に期限切れとなります。
* **カスタム時間**：指定された期間（最大 90 日）が過ぎると期限切れになります。この有効期限オプションは、オリジナル配分モデルと最新配分モデルでのみ使用できます。時間ベースの有効期限を使用する場合は、レポート期間の開始前（最大 90 日間）の値が考慮されます。
* **指標**：この指標がイベントで表示されると、ディメンションの永続化された値は直ちに期限切れになります。このディメンションの有効期限として任意の指標を使用できます。この有効期限オプションは、オリジナルの配分設定と最新の配分設定でのみ使用できます。


## [!UICONTROL バインディングディメンション]

ディメンション値の永続性を別のディメンション内のディメンション値にバインドできるドロップダウンメニュー。 有効なオプションには、データビュー内にある他のディメンションが含まれます。

バインディングディメンションの効果的な使用方法の例については、[Customer Journey Analyticsでのバインディングディメンションと指標の使用 &#x200B;](../../use-cases/data-views/binding-dimensions-metrics.md) を参照してください。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [バインディングディメンション](https://video.tv.adobe.com/v/3409294/?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## [!UICONTROL バインディング指標]

バインディングトリガーとして機能する指標を選択できるドロップダウンメニュー。 有効なオプションには、データビュー内にある指標が含まれます。

この設定は、オブジェクト配列のバインディングディメンションがコンポーネントよりも低い場合にのみ表示されます。 イベントにバインディング指標が存在する場合、ディメンション値はイベントレベルのディメンションからバインディングディメンションの下位のスキーマレベルにコピーされます。

バインディング指標の効果的な使用方法について詳しくは、[Customer Journey Analyticsでのバインディングディメンションと指標の使用 &#x200B;](../../use-cases/data-views/binding-dimensions-metrics.md) の 2 番目の例を参照してください。
