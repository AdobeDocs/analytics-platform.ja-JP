---
title: 最新のCustomer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示します。
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: b73d8eb73b0b65ca94f42d86b12cdfcc1ed99159
workflow-type: tm+mt
source-wordcount: 975
ht-degree: 28%

---

# 最新のCustomer Journey Analytics リリースノート（2026年8月）

**最終更新**: 2026年8月5日

これらのリリースノートは、2026年8月のリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ジャーニーキャンバスの機能強化**<br>&#x200B;次のジャーニーキャンバスの機能強化を利用できるようになりました。<ul><li>ジャーニーと過去の期間の比較。 現在のジャーニーを、4週間前、2四半期前、1年前、またはカスタム日付範囲と比較します。</li><li>選択したノードの場合、ジャーニーの任意のポイントで、選択したノードの後に来る最上位のディメンション項目を表示します。 選択したノードが分析の重要なイベントであり、その後のユーザーの行動を確認する場合に使用します。<p>以前は、選択したノードの前または後に表示できるのは、上位の即時ノードのみでした。 </p></li><li>ノード間の矢印の形状とスタイルを変更します。 ノード間で矢印をドラッグして矢印の形状（曲率）を変更し、矢印を右クリックして、スタイルをソリッド、破線、点線、点線、アニメーションのいずれかに変更します。</li></ul><p></p>詳しくは、[ジャーニーキャンバスビジュアライゼーションの設定](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)を参照してください。 |  | 2026年8月18日（PT） |
| **追加のデータ使用ラベルのサポート**<br> Customer Journey Analyticsでは、データセット内のエレメントに対する次の追加のデータ使用ラベルがサポートされるようになりました。<ul><li>C2 - サードパーティデータの書き出しを制限（現在利用可能）</li><li>C3 – 直接識別可能なデータの組み合わせを制限（現在利用可能）</li><li>C9 - データサイエンスの制限（8月または9月にリリース予定）</li></ul><p>詳しくは、[ ラベル、ポリシー、およびマーケティングアクション ](/help/data-views/data-governance.md)を参照してください。</p> | | 2026年8月または9月 |
| **同意ポリシーのフィルタリングとレポート**<br> Adobe Experience Platformの同意ポリシーに一致する訪問者をレポートできるようになりました。 （同意ポリシーのディメンションと指標は、接続のデータビューに追加されます）。<p>さらに、同意しない訪問者をデータがCustomer Journey Analyticsに取り込まれる前に除外することもできます。</p><p>詳しくは、同意レポートとフィルタリングの概要を参照してください。</p> | | 2026年8月 |
| **Content Analytics：有料メディアデータ** <br/>有料メディアは、Content Analyticsの3番目のチャネルとして利用できるようになりました。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年8月31日（PT） |
| **Migration Planner: Adobe AnalyticsからCustomer Journey Analyticsへの移行**<br> Migration Plannerは、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関連する最も複雑で時間のかかる作業（XDM スキーマの作成とAppMeasurementからの移行、またはAnalytics拡張機能（タグ）からExperience Platform Web SDKへの移行など）を自動化する移行ウィザードを提供します。 <p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年8月末または9月末 |
| **B2B：個人とアカウントの結合**<br> B2B アカウントの結合により、イベントデータセットがアカウント情報で強化され、Customer Journey Analyticsのカスタマージャーニー全体にわたって包括的な分析が可能になります。 <p>Customer Journey Analytics B2B editionで取り込む際に必要となるアカウント IDがイベントに欠けている場合、アカウントの結合は、ユーザーが提供した個人とアカウントのマッピングデータセットを使用して、その情報を自動的に導き出し、追加します。</p><p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年8月末または9月末 |
| **CJA レポート APIの最初の呼び出しガイド**<br> Adobe Customer Journey Analytics APIの最初の呼び出しガイドでは、基本的なレポートリクエストを設定するための手順と例を提供します。 | | 2026年8月10日（PT） |
| **CJA レポート APIの日付傾向ガイド**<br> Adobe Customer Journey Analytics APIの日付傾向ガイドでは、基本的なレポートリクエストを設定するための手順と例を提供します。 | | 2026年8月17日（PT） |

### Customer Journey Analytics の修正点

**Analysis Workspace**: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671 457760 443594, AN-, AN-
**コンポーネント**：
**接続**: AN-464934、AN-460768
**コンテンツ分析**：
**ガイド付き分析**：
**書き出し**: AN-451819、AN-448419、AN-456001
**データビュー**: AN-453201、AN-441965、AN-460967
**データ収集**: AN-462123、AN-451836、AN-453790、AN-459000、AN-456057、AN-461271、AN-459016、AN-460935
**実装**:
**Report Builder**: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**レポート**: AN-463576、AN-462400、AN-456394、AN-455619、AN-459530、AN-454103、AN-452866、AN-461181
**セグメント化**: AN-459002、AN-457730、AN-457146
**スケジュール済みレポート**: AN-455009、AN-460037、AN-462093
**共有指標と共有ディメンション**：
**オーディエンス分析**: AN-458292
**その他**: AN-466935、AN-462116、AN-454493、AN-457666、AN-457557、AN-456742、AN-437975、AN-460959

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールされたデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（広告付き無料テレビ）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、「[ ライブコンテンツを追跡するためのスケジュールデータのアップロード ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)」を参照してください。 | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |

>[!MORELIKETHIS]
>
>* [2026年の以前のCustomer Journey Analytics リリースノート ](/help/release-notes/2026.md)
>* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
>* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
>* [CX エンタープライズ リリース ノート ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
>* [Customer Journey Analytics ドキュメントの更新](/help/release-notes/doc-changes.md)

