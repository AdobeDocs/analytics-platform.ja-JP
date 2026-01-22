---
title: オーディエンス分析の設定
description: オーディエンス分析の設定方法を学ぶ
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: d780233ca6c8988637881a4f65ed16169bb0385b
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 12%

---

# オーディエンス分析の設定 {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="結合ポリシー"
>abstract="結合ポリシーは、複数のデータセットのプロファイルデータを、オーディエンスの作成に使用される統合された顧客プロファイルに組み合わせます。 複数の結合ポリシーが表示されていて、どちらを選択すればよいかわからない場合は、「デフォルトの時間ベース」を選択します。 または、データチームに問い合わせて、各結合ポリシーに関連付けられているオーディエンスを確認します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="サンドボックス"
>abstract="正しいExperience Platform プロファイルデータセットを含んだサンドボックスを選択します。 これらのデータセットには、Analysis Workspaceでレポートするオーディエンスデータを含める必要があります。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="ユーザー ID"
>abstract="ユーザー ID を表すフィールドをスキーマから選択します。 選択できるのは、スキーマ内で ID としてマークされ、ID 名前空間を持つフィールドのリストに限られます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="プライマリ ID 名前空間を使用"
>abstract="Customer Journey Analyticsで primary=true 属性でマークされた ID を ID マップで検索し、その ID をその行のユーザー ID として使用する場合は、このオプションを有効にします。 この ID は、Experience Platform でパーティション分割に使用するプライマリキーです。 <br/> このオプションを無効のままにする場合は、以下の ID 名前空間フィールドから名前空間を選択します。 Customer Journey Analyticsは、各行の ID マップでこの名前空間キーを検索し、その名前空間の ID を行のユーザー ID として使用します。"

<!-- markdownlint-enable MD034 -->

Audience analysis では、オーディエンスメンバーシップデータをExperience Platform プロファイルデータセットからCustomer Journey Analytics接続に取り込むことができます。 オーディエンスは、Analysis Workspaceで使用する新しいディメンションとして使用できるようになります。 オーディエンス分析の概要について詳しくは、[&#x200B; オーディエンス分析の概要 &#x200B;](/help/connections/audience-analysis/audience-analysis-overview.md) を参照してください。

>[!IMPORTANT]
>
>オーディエンスデータは毎日再処理および生成されるので、前日（昨日）の分析に対してのみオーディエンスデータが正確になります。
>
>オーディエンスは、オーディエンス分析設定を作成した翌日に、Customer Journey Analytics データビューで使用できます。

## オーディエンス分析設定の作成

Audience analysis configuration を作成する際は、分析するExperience Platform オーディエンスに関連付けられたサンドボックスと結合ポリシーを選択します。 Customer Journey Analyticsは、新しいルックアップデータセットを作成してから、ルックアップデータセットとプロファイルデータセットを選択した接続に自動的に追加します。

システム管理者のみが、オーディエンス分析設定を作成できます。

オーディエンス分析設定を作成するには：

1. Customer Journey Analyticsで、**[!UICONTROL Data Management]**/**[!UICONTROL Audience Analysis configuration]** を選択します。

   ![&#x200B; オーディエンス分析のメインページ &#x200B;](assets/audience-analysis-empty.png)

1. **[!UICONTROL 設定を作成]** を選択します。

   ![&#x200B; オーディエンス分析設定の作成 &#x200B;](assets/audience-analysis-create.png)

1. 「**[!UICONTROL 詳細]**」セクションで、次の情報を指定します。

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL 名前]** | 設定の名前を指定します。 |
   | **[!UICONTROL サンドボックス]** | 接続に追加するプロファイルデータセットを含んだExperience Platform サンドボックスを選択します。 1 つのサンドボックスで、最大 100 個のオーディエンス分析設定をサポートできます。 <p>Adobe Experience Platform は、単一の Platform インスタンスを別々の仮想環境に分割して、デジタルエクスペリエンスアプリケーションの開発と発展を支援する仮想[サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)を提供します。 サンドボックスは、データセットを含む「データサイロ」と考えることができます。 サンドボックスは、データセットへのアクセスを制御するために使用します。</p> |

1. 「**[!UICONTROL プロファイルデータセット]**」セクションで、次の情報を指定します。

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL 結合ポリシー]** | オーディエンス分析に使用するプロファイルデータセットに対応する、結合ポリシーを選択します。 <p>結合ポリシーは、Adobe Experience Platformが複数のデータセットのプロファイルデータを、オーディエンスの作成に使用される統合された顧客プロファイルに組み合わせる方法を決定します。 選択する結合ポリシーは、オーディエンスに含まれるプロファイルの属性に影響します。 毎日、このデータのスナップショットがExperience Platformで生成されます。 このスナップショットは、特定の時点でのデータの静的ビューを提供し、イベントデータを含みません。</p><p>複数の結合ポリシーが表示されていて、どちらを選択するか不明な場合は、結合ポリシー **[!UICONTROL デフォルトの時間ベース]** を選択します。 また、データチームに問い合わせて、各結合ポリシーに関連付けられているオーディエンスをより深く理解することもできます。</p> |
   | **[!UICONTROL プロファイルデータセット]** | 選択した結合ポリシーに関連付けられているプロファイルデータセット。 このプロファイルデータセットには、分析するExperience Platform オーディエンスデータが含まれています。 このプロファイルデータセットは、選択した接続に追加されます。<p>結合ポリシーを選択すると、プロファイルスナップショットの書き出しが表示されます。 例：`Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`。</p><p>詳しくは、『Experience Platform ダッシュボードガイド』の [&#x200B; プロファイル属性データセット &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets) を参照してください。</p> |

1. 「**[!UICONTROL 接続]**」セクションで、「**[!UICONTROL 接続を選択]**」をクリックします。

1. 接続ダイアログで、プロファイルデータセットを追加する接続の横にあるチェックボックスをオンにし、「**[!UICONTROL 接続を使用]**」を選択します。

   1 つの接続は、1 つのオーディエンス分析設定にのみ関連付けることができます。

1. 接続を設定するには、次の情報を指定します。

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL ユーザー ID]** | ユーザー ID を表すフィールドをスキーマから選択します。<p>選択は、スキーマ内の ID としてマークされ、ID 名前空間を持つフィールドのリストに限定されます。 **[!UICONTROL IdentityMap]** はデフォルトで選択されており、ほとんどの設定に適しています。 </p><p>選択するユーザー ID がない場合は、スキーマで 1 つ以上のユーザー ID が定義されていないことを意味します。 詳しくは、[UI で ID フィールドを定義](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity)を参照してください。</p> |
   | **[!UICONTROL プライマリ ID 名前空間を使用]** | このオプションは、ユーザー ID に **[!UICONTROL ID マップ]** を選択した場合に表示されます。 <p>Customer Journey Analyticsで primary=true 属性でマークされた ID を ID マップで検索し、その ID をその行のユーザー ID として使用する場合は、このオプションを有効にします。 この ID は、Experience Platform でパーティション分割に使用するプライマリキーです。 また、この ID は、（Customer Journey Analytics接続でのデータセットの設定方法に応じて）Customer Journey Analytics人物 ID として使用する際の主な候補でもあります。</p> |
   | **[!UICONTROL ID 名前空間]** | このオプションは、ユーザー ID に **[!UICONTROL ID マップ]** を選択した場合に表示されます。 プライマリ ID 名前空間を使用する場合、このオプションは無効になります。 <p>ID 名前空間は、[Experience Platform ID サービス](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)のコンポーネントです。 名前空間は、ID が関連付けられているコンテキストを示します。 名前空間を指定すると、Customer Journey Analyticsは各行の ID マップでこの名前空間キーを検索し、その名前空間の ID を行のユーザー ID として使用します。 Customer Journey Analyticsでは、すべての行の完全なデータセットスキャンを実行して、どの名前空間が存在するかを判断することはできないので、使用可能なすべての名前空間がドロップダウンメニューに表示されます。 データ内で指定されている名前空間を把握しておく必要があります。これらの名前空間は自動検出されません。</p> |

   <!-- Add this when B2B releases for AuA **[!UICONTROL Account ID]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}|  (only displayed for account-based connections) The Account ID that is used to support account-based reporting for the dataset. -->

1. 「**[!UICONTROL データビュー]**」セクションで、「**[!UICONTROL データビューを選択]**」をクリックします。

1. データビューダイアログで、Analysis Workspace内のExperience Platform オーディエンスデータを分析する際に使用する 1 つ以上のデータビューの横にあるチェックボックスをオンにします。 これらのデータビューは、レポート用にExperience Platform オーディエンスデータで自動的に設定されます。

1. **[!UICONTROL データビューを使用]** を選択します。

1. 「**[!UICONTROL 作成]**」を選択して、設定を作成します。

   >[!IMPORTANT]
   >
   >プロファイルデータセットは 1 日に 1 回更新されるので、オーディエンス分析を設定した翌日に、Customer Journey Analytics データビューでオーディエンスを使用できます。


1. 24 時間後、[&#x200B; データビューでオーディエンスディメンションを表示 &#x200B;](#view-audience-dimensions-in-the-data-view) して、選択したデータビューでオーディエンスディメンションが使用できることを確認します。

## データビューでのオーディエンスディメンションの表示

[&#x200B; オーディエンス分析設定の作成 &#x200B;](#create-an-audience-analysis-configuration) を完了すると、設定時に選択したデータビューにオーディエンスディメンションが追加されたことを確認できます。

データビューでオーディエンスディメンションを表示するには、データビューが割り当てられている製品プロファイルの製品プロファイル管理者である必要があります。 詳しくは、[&#x200B; アクセス制御 &#x200B;](/help/technotes/access-control.md) を参照してください。

データビューでオーディエンス分析ディメンションを表示するには：

1. Customer Journey Analytics で、**[!UICONTROL データ管理]**／**[!UICONTROL データビュー]**&#x200B;を選択します。

1. **[!UICONTROL ディメンション]** セクションで、次のディメンションが使用可能になります。

   * **[!UICONTROL オーディエンス名]**

   * **[!UICONTROL オーディエンスオリジン]**

   * **[!UICONTROL 終了したオーディエンスオリジン]**

   * **[!UICONTROL 退出したオーディエンス名]**

   これらの各ディメンションは、オーディエンス分析設定時に選択した結合ポリシーに関連付けられたプロファイルデータセットに追加され、作成した新しいルックアップデータセットに追加されました。

   ![&#x200B; データビューで使用できるオーディエンスディメンション &#x200B;](assets/audience-analysis-dataview-dataset.png)

1. Analysis Workspaceでオーディエンス分析ディメンションを使用します。

   Analysis Workspaceのデータビューを使用するアクセス権を持つユーザーは、新しいディメンションを表示して、分析で使用できるようになりました。 Customer Journey Analyticsでのオーディエンス分析ディメンションの使用方法について詳しくは、[Analysis WorkspaceでのExperience Platform オーディエンスの分析 &#x200B;](/help/connections/audience-analysis/analyze-audiences.md) を参照してください。


