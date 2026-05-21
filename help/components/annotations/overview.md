---
title: 注釈の概要
description: Analysis Workspace で注釈を使用する方法について説明します。
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
role: User
TQID: https://experienceleague.adobe.com/GTQ6Q0saYtBvHM4Iva-lL3ifA9ERbONI9JQkOyaqSRA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 320
ht-degree: 86%

---

# 注釈の概要

注釈を使用すると、コンテキストデータのニュアンスとインサイトを組織内の他の関係者に効果的に伝えることができます。 注釈を使用すると、カレンダーイベントを特定のディメンションや指標に関連付けることができます。 既知のデータの問題、祝日、キャンペーンの開始などを含む日付または日付範囲に注釈を付けることができます。次に、イベントを視覚的に表示し、キャンペーンやその他のイベントが、サイトトラフィック、モバイルアプリの利用状況、売上などの指標に影響を与えたかどうかを確認できます。

例えば、プロジェクトを組織と共有しているとします。 受け入れられるオファーが大幅に減少した場合は、**良くないオファー**&#x200B;注釈を作成して、その注釈の範囲をデータビュー全体に設定できます。 その日付を含んだデータセットをユーザーが表示すると、データと共に、プロジェクト内の注釈が表示されます。

![注釈がハイライト表示された折れ線グラフ。](assets/annotation-example.png)

注釈は次の場所に適用できます。

* 単一の日付または日付範囲。

* データセット全体、または特定の指標、ディメンション、セグメント。

* 注釈が作成されるプロジェクト（デフォルト）またはすべてのプロジェクト。

* 注釈が作成されるデータビュー（デフォルト）、またはすべてのデータビュー。

注釈の作成に使用できる様々なオプションについて詳しくは、[注釈の作成](/help/components/annotations/create-annotations.md)を参照してください。 その後、[注釈ビルダー](create-annotations.md#annotation-builder)で注釈を作成、変更および保存します。

注釈を管理するには、[注釈マネージャー](manage-annotations.md)を使用します。

## 注釈のオンまたはオフ

注釈は、複数のレベルでオンまたはオフにできます。

| レベル | 方法 |
|---|---|
| **ビジュアライゼーション** | ![設定](/help/assets/icons/Setting.svg)／**[!UICONTROL 設定]**／**[!UICONTROL 注釈を表示]**&#x200B;を有効または無効にします。<br/>![ビジュアライゼーションの注釈の有効化または無効化](/help/components/annotations/assets/annotations-visualization.png) |
| **プロジェクト** | Workspace プロジェクトメニューから、**[!UICONTROL プロジェクト]**／**[!UICONTROL プロジェクト情報および設定]**&#x200B;を選択し、「**[!UICONTROL 注釈を表示]**」を有効または無効にします。<br/>![プロジェクトの注釈の有効化または無効化](/help/components/annotations/assets/annotations-project.png) |
| **ユーザー** | 「**[!UICONTROL コンポーネント]**」タブから「**[!UICONTROL 環境設定]**」を選択するか、Workspace プロジェクトメニューから&#x200B;**[!UICONTROL プロジェクト]**／**[!UICONTROL ユーザー環境設定]**&#x200B;を選択します。 <br/>**[!UICONTROL 環境設定]**&#x200B;で、「**[!UICONTROL プロジェクトと分析]**」を選択します。 左側のタブバーから、「**[!UICONTROL データ]**」を選択します。 下部で、**[!UICONTROL フリーフォームテーブル]**&#x200B;見出しの下にある「**[!UICONTROL 注釈を表示]**」を有効または無効にします。<br/>![ユーザーの注釈の有効化または無効化](/help/components/annotations/assets/annotations-user.png) |
