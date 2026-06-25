---
title: 現在の Customer Journey Analytics リリースノート
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
source-git-commit: 8cdfe0db0aabba05fbebe7d9215182e0fca31d66
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 44%

---

# 最新のCustomer Journey Analytics リリースノート（2026年6月）

**最終更新**: 2026年6月25日（PT）

これらのリリースノートは、2026年6月のリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **Data Mirror** <br/>[Data Mirror](/help/data-mirror/data-mirror.md)は、外部データウェアハウスソリューション（[!DNL Snowflake]、[!DNL Azure Databricks]、および[!DNL Google BigQuery]）からリレーショナルスキーマを使用してCustomer Journey Analyticsに行レベルの変更の取り込み（change data capture）を可能にするExperience Platform機能です。 データ関係を維持し、一意性を確保し、ETL （上流抽出、変換、格納）プロセスを必要とせずにバージョン管理をサポートします。 | 2026年3月25日（PT） | 2026年6月17日（PT） |
| **AI アシスタントでのデータの検証** <br/>AI アシスタントを使用して、[Adobe Experience Platform データセットのデータ品質を検証できます](https://experienceleague.adobe.com/ja/docs/experience-cloud-ai/experience-cloud-ai/agents/data-validation)。 Agent Orchestratorなら、データセットを統計的かつ意味的に検証し、データセットフィールドを分析して、データ品質の問題を特定できます。また、実用的なインサイトを得て自然言語による要約を返すことができます。 | | 2026年6月22日（PT） |

### Customer Journey Analytics の修正点

**Analysis Workspace**: AN-456858, AN-455865, AN-455706, AN-455592, AN-455484, AN-455180, AN-454999, AN-454170, AN-454145, AN-453793, AN-452921, AN-452009, AN-451958, AN-451643, AN-451600, AN-451525, AN-451477, AN-451262, AN-451161, AN-450772, AN-443594 434416, AN-
**コンポーネント**：
**接続**: AN-457065、AN-453705
**Content Analytics**:AN-451203、AN-447596
**ガイド付き分析**：
**書き出し**: AN-452006、AN-451989、AN-440567
**データビュー**: AN-451198
**実装**:
**Report Builder**: AN-440912, AN-457586, AN-457533, AN-455713, AN-455623, AN-455063, AN-454512, AN-454053, AN-453977, AN-453781, AN-453683, AN-451974, AN-451735, AN-451731, AN-451190, AN-449813, AN-447173, AN-447139, AN-446184, AN-445794, AN-445354 442819, AN-
**レポート**: AN-454589, AN-454517, AN-453982, AN-451822, AN-451497, AN-451463, AN-451259, AN-451215, AN-450661, AN-447699, AN-448375, AN-447692
**セグメント化**：
**スケジュール済みレポート**: AN-451980、AN-451882、AN-450715
**共有指標と共有ディメンション**：
**オーディエンス分析**:AN-449656、AN-450400
**その他**: AN-457063、AN-454140、AN-453937、AN-453825、AN-452959、AN-452934、AN-452296、AN-451781、AN-450974

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールされたデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。 | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |

>[!MORELIKETHIS]
>
>* [2026年の以前のCustomer Journey Analytics リリースノート &#x200B;](/help/release-notes/2026.md)
>* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
>* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
>* [CX エンタープライズ リリース ノート &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
>* [Customer Journey Analytics ドキュメントの更新](/help/release-notes/doc-changes.md)
