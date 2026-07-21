---
title: 最新のCustomer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 3fcb9c403ace295c1a7e62c21d8bb444a4f9c011
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 39%

---

# 最新のCustomer Journey Analytics リリースノート（2026年7月）

**最終更新**: 2026年7月8日

これらのリリースノートは、2026年7月のリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **サブイベント分析** <br/>[&#x200B; サブイベント分析](/help/components/segments/sub-event.md)を使用すると、イベントレベルよりも詳細なレベルでデータを分析できます。 イベント全体をフィルタリングするのではなく、イベント内の個々のコンテナでセグメント化できます。 <p>例えば、同じ注文で購入された他の商品をすべて含めずに、特定の商品カテゴリーでセグメンテーションできます。 イベントデータの一部であるオブジェクトまたは配列を、データビュー内で個別の[&#x200B; カスタムコンテナ &#x200B;](/help/data-views/create-dataview.md#custom-containers)として定義することもできます。 | 2026年7月21日（PT） | 2026年7月末 |
| **B2B edition：アドホックおよびリレーショナルデータセットのサポート** <br/> アドホックおよびリレーショナルデータセットも、Customer Journey Analytics B2B editionのアカウントベースの接続でサポートされるようになりました。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年7月20日（PT） |
| **Content Analytics：有料メディアデータ** <br/>有料メディアは、Content Analyticsの3番目のチャネルとして利用できるようになりました。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年7月31日（PT） |
| **Connections使用インターフェイスの更新** <br/>接続を管理する際の使用インターフェイスで、Customer Journey AnalyticsやCustomer Journey Analytics B2B editionなどの各モジュールの使用状況の詳細を確認できるようになりました。 <p>さらに、各モジュールの利用状況レポートを月別に分類できるようになりました。</p><p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年7月31日（PT） |
| **CX Enterprise Coworker: Adobe AnalyticsからAdobe Analyticsに移行する際のデータの検証** <br/>CX Enterprise Coworkerの新しいスキルを使用すると、既存のCustomer Journey Analytics実装のデータとCustomer Journey Analytics実装のデータを検証できます。 <p>このスキルは、必要に応じて各ディメンション、指標、トレンドを個別に自動的に比較します。 また、すべてのAdobe Analytics レポートスイートをすべてのCustomer Journey Analytics データビューと比較することもできます。 そして、AIを活用してインサイトとレコメンデーションを生成し、Customer Journey Analyticsへの移行を促進します。</p><p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年7月末 |
| **インライン分類**<br/>[&#x200B; インライン分類](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md#inline-classifications)を使用すると、フリーフォームテーブル内の行の名前を変更したり、行を結合したりできます。 テーブル内の変更された行から派生フィールドを作成します。 | 2026年7月20日（PT） | 2026年7月25日（PT） |

### Customer Journey Analytics の修正点

**Analysis Workspace**: AN-457527、AN-451161、AN-459034、AN-458071、AN-458398
**コンポーネント**：
**接続**: AN-457065
**コンテンツ分析**：
**ガイド付き分析**：
**書き出し**：
**データビュー**: AN-453201
**データ収集**:
**実装**:
**Report Builder**:AN-457533、AN-453683
**レポート**: AN-457607、AN-447692、AN-451259、AN-455713
**セグメント化**：
**スケジュール済みレポート**: AN-450715
**共有指標と共有ディメンション**：
**オーディエンス分析**:
**その他**: AN-457063

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールされたデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、「[&#x200B; ライブコンテンツを追跡するためのスケジュールデータのアップロード &#x200B;](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)」を参照してください。 | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |

>[!MORELIKETHIS]
>
>* [2026年の以前のCustomer Journey Analytics リリースノート &#x200B;](/help/release-notes/2026.md)
>* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
>* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
>* [CX エンタープライズ リリース ノート &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
>* [Customer Journey Analytics ドキュメントの更新](/help/release-notes/doc-changes.md)

