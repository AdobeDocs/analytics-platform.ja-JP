---
title: サブイベント分析
description: サブイベント分析を使用して、Customer Data Analyticsでイベント内の個々のジャーニーやその他のコンテナをフィルタリングし、商品レポートでアトリビューションの裁ち落としを排除する方法について説明します。
feature: Segmentation
hold: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: b4bec7c8e476bc2dbffce42bd52ff535b90dcb86
workflow-type: tm+mt
source-wordcount: 564
ht-degree: 0%

---

# サブイベント分析

{{release-limited-testing}}

サブイベント分析では、イベントレベルよりも詳細なレベルでイベントデータを分析できます。 イベント全体をフィルタリングするのではなく、イベント内の個々のコンテナでセグメント化できます。 例：

- 同じ順序で購入された他のすべての製品を含めずに、特定の製品カテゴリでセグメント化する
- Content Analytics データ内の特定のアセットカテゴリに関するセグメンテーションとは？
- メディア分析データ内の特定のメディアチャネルでのセグメンテーション。


Customer Journey Analyticsでは、サブイベント分析を使用するデータビュー内のコンテナを定義します。 サブイベント分析を使用しない場合、コンテナ項目属性でセグメント化すると、イベント内の任意の項目がコンテナ項目属性と一致するすべてのイベントが返されます。 その結果、アトリビューションが誤り、収益指標が高騰してしまいます。 サブイベント分析では、フィルターをイベント内の個々のアイテム行にスコープ付けし、これらの問題を解決します。

サブイベント分析では、除外ロジックは、コンテナに対する標準のイベントレベルの除外とは異なる動作をします。 コンテナ内で項目属性を除外すると、セグメントは、コンテナ内に&#x200B;**項目**&#x200B;を持つが、除外条件に一致しないイベントを返します。 セグメントは、項目がまったく含まれていないイベントを返しません。


## 例

Professional suites カテゴリの売上のみを測定する場合。 サブイベント分析を使用しない場合、プロフェッショナルスーツのセグメントを適用すると、プロフェッショナルスーツのカテゴリを持つ製品が少なくとも1つ含まれている注文（イベント）の各製品からの収益が含まれます。 サブイベント分析では、フィルターを製品レベルにスコーピングし、プロフェッショナルスーツ カテゴリの製品に対してのみ収益を返します。

また、「男性」カテゴリを除くすべてのカテゴリからオンラインの売上を測定することもできます。

>[!BEGINTABS]

>[!TAB  イベント分析]

セグメンテーションビルダーで、または&#x200B;**[!UICONTROL クイックセグメント]**&#x200B;の一部として、**[!UICONTROL イベント]** コンテナで&#x200B;**[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]**&#x200B;を&#x200B;**[!UICONTROL Include]**&#x200B;に指定します。

![製品カテゴリのプロフェッショナルスーツのイベントレベルに関するセグメンテーションを示すパネル &#x200B;](./assets/product-category-segmentation-events.png)

その結果、少なくとも1つの&#x200B;**[!UICONTROL Professional Suits]** **[!UICONTROL product_category]**&#x200B;を含むすべての注文が考慮され、これらの注文の他の製品からの収益は&#x200B;**[!UICONTROL 収益]**&#x200B;指標に含まれます。カテゴリについて報告すると、**[!UICONTROL 専門訴訟]** **[!UICONTROL product_category]**&#x200B;の製品を含む注文の一部である&#x200B;**[!UICONTROL product_category]**&#x200B;の他のすべての値が報告されます。

>[!TAB  サブイベント分析]

セグメンテーションビルダーで、または&#x200B;**[!UICONTROL クイックセグメント]**&#x200B;の一部として、**[!UICONTROL Products]** コンテナの&#x200B;**[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suites]**&#x200B;を&#x200B;**[!UICONTROL Include]**&#x200B;に指定します。

![製品カテゴリのプロフェッショナルスーツのサブイベントレベルに関するセグメンテーションを示すパネル &#x200B;](./assets/product-category-segmentation-subevents.png)

その結果、少なくとも&#x200B;**[!UICONTROL プロフェッショナルスーツ]** **[!UICONTROL product_category]**&#x200B;を含むすべての注文が考慮され、**[!UICONTROL 収益]**&#x200B;指標には&#x200B;**[!UICONTROL プロフェッショナルスーツ]** **[!UICONTROL product_categorey]**&#x200B;に属する製品の収益のみが含まれます。カテゴリについて報告する場合、**[!UICONTROL Professional Suits]** **[!UICONTROL Rproduct_category]**&#x200B;のみが報告されます。

>[!TAB  サブイベント分析（除外） ]

セグメンテーションビルダーで、または&#x200B;**[!UICONTROL クイックセグメント]**&#x200B;の一部として、**[!UICONTROL Products]** コンテナの&#x200B;**[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]**&#x200B;を&#x200B;**[!UICONTROL Exclude]**&#x200B;に指定します。

![製品カテゴリを除外するサブヒットレベルにセグメンテーションを表示するパネル Men](./assets/product-category-segmentation-subevents-exclude.png)

製品レベルで除外するには、少なくとも1つの製品を含むイベントが含まれ、そのスコープ内でサブイベントレベルの除外が適用されます。 この除外は、イベント全体を除外するイベントレベルの除外とは異なります。

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
