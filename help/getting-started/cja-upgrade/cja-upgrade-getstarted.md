---
title: Customer Journey Analytics へのアップグレードの基本を学ぶ
description: Adobe Analytics から Customer Journey Analytics へのアップグレードを計画します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: ht
source-wordcount: '721'
ht-degree: 100%

---

# 手順 1：Customer Journey Analytics へのアップグレードの基本を学ぶ

>[!AVAILABILITY]
>
>このページの情報は、次のより包括的なアップグレード情報に置き換えられます。 <ul><li>**推奨されるアップグレード手順**<p>詳しくは、[Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパス](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)を参照してください。</p></li><li>**Customer Journey Analytics アップグレードガイド**<p>組織と一意の状況に合わせて調整されたアップグレード手順を動的に生成する新しいアップグレードガイドが使用できます。</p><p>Customer Journey Analytics からガイドにアクセスするには、「**[!UICONTROL Workspace]**」タブを選択し、左側のパネルで「**[!UICONTROL Customer Journey Analytics にアップグレード]**」を選択します。画面の指示に従います。</p></li></ul>

Customer Journey Analytics は、次世代の分析です。強力なレポート時処理機能（データビューでのコンポーネントと派生フィールドの定義を通じて）と組み合わせて、マルチチャネルデータ収集（オンラインデータとオフラインデータの両方）を実現できます。

Adobe Analytics から Customer Journey Analytics へのアップグレードプロセスを開始する前に、Customer Journey Analytics のメリットと、正常にアップグレードするために必要な手順を理解する必要があります。

## Customer Journey Analytics のメリットについて

主なメリットには、次のようなものがあります（包括的なリストと、これらの主な機能のそれぞれについて詳しくは、[Customer Journey Analytics でのみ利用可能な機能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics)を参照してください）。

* [マルチチャネルレポート](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics は、あらゆる種類のデータスキーマとタイプを保持する Experience Platform の機能と組み合わされています。デジタル（Web）、POS（販売時点情報管理）システム、モバイル、CRM システムなどの複数のチャネルからデータを収集してレポートします。

* [データビューでのレポート時の変換](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Customer Journey Analytics のデータビューを使用すると、接続からのデータをさらに深く解釈できます。実装を変更せずにデータを変更または削除、部分文字列を使用してディメンションを操作、任意の値から指標を作成、サブイベントをセグメント化、または派生フィールドを使用できます。これらの変換はすべて非破壊的に行われます。

* [変換は履歴データと新規データに適用されます](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  データビューの操作は、履歴データにも新しいデータにも、非破壊で適用できます。

* [派生フィールド](/help/data-views/derived-fields/derived-fields.md)

  派生フィールドを使用すると、レポート時にデータを変換できます。データは、その場で結合、修正、作成し、すべてのレポートに対して遡って適用できます。

* [データビューは仮想レポートスイートを置き換えます](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  データビューは、現在存在する仮想レポートスイートの概念を取り入れ、これを拡張して、接続によって利用できるデータに対する追加の制御を有効にします。これらの変更により、タイムゾーンやセッションのタイムアウト間隔などの一般的な設定が設定可能になり、遡って適用できるようになります。

* [無制限の顧客ディメンションと指標](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  値には、数値、テキスト、オブジェクト、リスト、すべての組み合わせを使用できます。ディメンションはネストまたは階層化できます。

## アップグレードプロセスについて

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
このページの情報では、次の表でハイライト表示されているアップグレードプロセスの手順 1 について説明します。Adobe Analytics から Customer Journey Analytics にアップグレードするには、この表のすべての手順を完了します。

| アップグレードタスク | 詳細 |
|---------|----------|
| <span class="preview">**手順 1：アップグレードの基本を学ぶ**</span> | <span class="preview">Customer Journey Analytics へのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。</span> |
| **手順 2：[アップグレードパスの選択](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analytics へのアップグレードには様々な方法があります。組織の現在の Adobe Analytics 環境と長期的な目標に応じて、組織に最適な方法を選択してください。 |
| **手順 3：[データを Adobe Experience Platform に送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platform にデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| **手順 4：[履歴データの保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | ほとんどの組織では、Adobe Analytics の履歴データを一定期間保持する必要があります。これを実現するために様々なオプションが利用できます。 |
| **手順 5：[追加の実装タスクを実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics 環境が使用可能になる前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analytics からのアップグレードと新しい Customer Journey Analytics の実装に適用されます。</p><p>これらのタスクには次のものが含まれます。</p><ul><li>他のデータを Experience Platform に取り込む</li><li>手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとデータウェアハウスの考慮</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーオンボーディングの計画</li></ul> <p>詳しくは、[Customer Journey Analytics の概要](/help/getting-started/cja-getting-started.md)を参照してください。 |

{style="table-layout:auto"}

## まず、アップグレードパスを選択します

Customer Journey Analytics へのアップグレードには様々な方法があります。[組織に最適な方法を選択します](/help/getting-started/cja-upgrade/cja-upgrade-path.md)。

選択するアップグレードパスは、組織の現在の Adobe Analytics 環境と長期的な目標によって異なります。
