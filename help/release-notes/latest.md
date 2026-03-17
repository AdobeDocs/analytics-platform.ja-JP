---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a8a09834818fafc0223d769c5371f829377860ff
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 19%

---

# 最新のCustomer Journey Analytics リリースノート（2026 年 3 月）

**最終更新日**:2026 年 3 月 11 日（PT）

これらのリリースノートは、2026 年 3 月のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ヘッダーオーバーライド**<br/>Content Analyticsでヘッダー名とシークレットヘッダー値を指定できます。 この [header overrides configuration](/help/content-analytics/config/guided.md#header-overrides) は、実装したボット検出やゲートトラフィックテクノロジーをバイパスするために、Content Analyticsがカスタム HTTP ヘッダーを送信することを保証します。 |  | 2026年2月2日（PT） |
| **複数の IMS 組織のレポートスイートを組み合わせる**<br/> Analytics Source コネクタを使用して、複数の IMS 組織のレポートスイートを組み合わせることができます。 この [&#x200B; クロス IMS データマッピング &#x200B;](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md) 機能を使用すると、顧客データが複数の IMS 組織に分散している場合でも、組織は顧客データの表示を組み合わせることができます。 <p>**注意：** この設定を使用できるのは、Adobe カスタマーケアにリクエストを送信した場合のみです。</p> |  | 2026年2月12日（PT） |
| **フリーフォームテーブルに複数のディメンション列を含める**<br/> フリーフォームテーブルに最大 5 つのディメンション列を含めることができ、複数のディメンション項目を並べて表示できるようになりました。 ディメンション項目の各行は、単一の連結されたディメンション項目のように動作します。<p>複数のディメンション列を持つフリーフォームテーブルにフィルター、並べ替え、分類などを適用して、より深く、よりカスタムな分析を作成できます。</p><p>以前は、フリーフォームテーブルには 1 つのディメンション列のみを含めることができました。</p><p>詳しくは、[&#x200B; フリーフォームテーブルに複数のディメンション列を含める &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md) を参照してください。</p> | 2026年1月28日（PT） | 2026年3月4日（PT） <p>（当初は 2026 年 2 月 18 日に予定）</p> |
| **複数の列でテーブルを並べ替え**<br/> Analysis Workspaceでは、ディメンションでも指標でも、フリーフォームテーブルのデータを複数の列で並べ替えることができるようになりました。<p>複数の列でデータを並べ替える際、各列に割り当てた優先度に従ってデータが並べ替えられます。優先度の番号は、並べ替えアイコンの横に表示されます。</p><p>詳しくは、[フリーフォームテーブルのフィルタリングと並べ替え](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)を参照してください。</p> | 2026年1月28日（PT） | 2026年3月4日（PT） <p>（当初は 2026 年 2 月 18 日に予定）</p> |
| **Content Analytics：散布図ビジュアライゼーションのサムネールとプレビュー**<br/>[&#x200B; サムネールとプレビュー &#x200B;](/help/content-analytics/report/report.md) は、Content Analyticsの散布図ビジュアライゼーションのアセットおよびエクスペリエンスで使用できます。 | 2026年2月17日（PT） | 2026年3月2日（PT） |
| **Content Analytics:Content Analyticsの棒グラフ（積み重ね）および横棒グラフ（積み重ね）のビジュアライゼーションのアセットおよびエクスペリエンスでは、棒グラフ**<br/>[&#x200B; ビジュアライゼーションのサムネールとプレビュー &#x200B;](/help/content-analytics/report/report.md) サムネールとプレビュー）を使用できます。 | 2026年2月23日（PT） | 2026年3月9日（PT） |
| **接続でのデータセットのプレビュー再設計**<br/> ユーザーベースの接続でデータセットを [&#x200B; 追加 &#x200B;](/help/connections/create-connection.md#add-datasets) または [&#x200B; 編集 &#x200B;](/help/connections/create-connection.md#edit-a-dataset) すると、データをプレビューするエクスペリエンスが向上します。 有効なデータセットをステッチする場合は、追加の [&#x200B; ステッチ指標 &#x200B;](/help/stitching/use-stitching-ui.md#stitching-metrics) および [&#x200B; 無効な ID に関する情報 &#x200B;](/help/stitching/use-stitching-ui.md#bad-ids) を使用できます。 | 2026年3月6日（PT） | 未定 |
| **Report Builder：管理者による、スケジュールされたすべてのワークブックの表示**<br/> Report Builder Excel アドインには、管理者がスケジュールしたユーザーに関係なく、特定の組織のすべてのスケジュールされたワークブックを表示できる新しいフィルタ オプションが含まれています。 このフィルターオプションは、Analytics 管理者のみが使用できます。 スケジュールされたワークブックを表示する際に、「ワークブック」タブと「従来」タブの両方で使用できます。<p>スケジュールされたすべてのワークブックを表示する機能は、管理者が移行前にすべてのレガシーワークブックを簡単に見つけることができるため、分散チーム間でワークブックを移行する場合に特に便利です。</p><p>以前は、管理者は、他のユーザーがスケジュールしたワークブックではなく、スケジュールしたワークブックのみを表示できました。</br> 詳しくは、[&#x200B; スケジュールされたワークブックの管理 &#x200B;](/help/report-builder/manage-schedules-reportbuilder.md) を参照してください。</p> | | 2026年3月10日（PT） |
| **個別概算カウント関数への更新**<br/> 個別概算カウント関数で使用される HLL 確率的アルゴリズムは、近日中に更新される予定です。 この関数を利用する数値の結果の出力は、次のように、過去の数値とは少し異なる場合があります。<ul><li>非常に少量の一意の値をカウントする場合、予測値を使用するのではなく、正確なカウントを使用するように結果が改善されます。</li><li>それより大きい数をカウントする場合、カウントの予測では、この更新の前と同じ精度が保持されます（予測は正確な数の 5% 以内、つまり 95% の確率で正確です）。</li></ul><p>個別概算カウント関数について詳しくは、「[&#x200B; 高度な関数 &#x200B;](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) の個別概算カウント [&#x200B; を参照してください &#x200B;](/help/components/calc-metrics/cm-adv-functions.md)</p> | | 2026年3月10日（PT） |
| **完全なテーブル書き出しの改善**<br/> 完全なテーブル書き出しには、次の機能強化が含まれています。<p>エクスポートの作成と設定の機能強化</p><ul><li>書き出しページで書き出しを作成します。 以前は、テーブルを右クリックしないと、Analysis Workspaceから書き出しを作成できませんでした。</li><li>書き出しを作成する際に、新しいアカウントまたは場所を追加します。</li><li>書き出したファイルのファイル名の作成とフォルダーの配置を自動化します。 これにより、ファイル名を予測可能にし、論理的にフォルダーに整理できます。 以前は、ファイル名は予測不可能で、1 つのフォルダーにグループ化されていました。</li><li>データウェアハウスの互換性を向上させるために、データを Parquet ファイルとしてエクスポートする機能がサポートされました。 以前は、CSV と JSON のみがサポートされていました。</li></ul><p>書き出し管理の機能強化</p><ul><li>書き出しページから 1 つ以上の書き出しを更新またはキャンセルします。</li><li>ログページから 1 つ以上の書き出しを再送信します。</li><li>書き出しが失敗した場合や有効期限が近づいた場合に、個々のユーザーまたはグループにメールを送信します。</li><li>失敗した書き出しのエラーメッセージをより正確に示します。</li></ul><p>計算指標、セグメント、ディメンションの機能強化</p><ul><li>より多くの計算指標関数のサポート。 以前は、単純な数学関数のみがサポートされていました。</li><li>書き出しを作成する際にセグメントを適用します。</li><li>精度を向上させるために、ダブルデータタイプのディメンションをサポート。</li></ul><p>管理機能の強化</p><ul><li>管理者は、作成者に関係なく、すべての書き出しとログを表示できるようになりました。</li></ul><p>詳しくは、次のリソースを参照してください。<ul><li>[完全なテーブルをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)</li><li>[&#x200B; クラウド書き出しアカウントの設定 &#x200B;](/help/components/exports/cloud-export-accounts.md)</li><li>[&#x200B; クラウドの書き出し場所の設定 &#x200B;](/help/components/exports/cloud-export-locations.md)</li><li>[&#x200B; 書き出しの管理 &#x200B;](/help/components/exports/manage-exports.md)</li><li>[&#x200B; クラウドの書き出し場所とアカウントの管理 &#x200B;](/help/components/exports/manage-export-locations.md)</li><li>[&#x200B; 書き出しログの管理 &#x200B;](/help/components/exports/manage-export-logs.md)</li></ul></p> | 2026年2月25日（PT） | 2026年3月11日（PT）<p>（当初は 2026 年 3 月 4 日に予定）</p> |
| **Analysis Workspaceの実践チュートリアル**<br/> Analysis Workspaceのパネル、ビジュアライゼーションおよびコンポーネントの使用に関する基本を初めて使用するユーザーをガイドする新しい実践チュートリアルが利用できるようになりました。 <p>詳しくは、[Customer Journey Analytics ランディングページ &#x200B;](/help/getting-started/landing.md) を参照してください。</p> | | 2026年3月18日（PT） |
| **データミラーのサポート**<br/> Experience Platformの特定のソースコネクタに対するモデルベースのスキーマおよび Change Data Capture （CDC）機能のサポートにより、Customer Journey Analyticsは、[、](/help/data-mirror/data-mirror.md)、[!DNL Snowflake] などの Data Warehouse ソリューションの [!DNL Azure Databricks] データミラー [!DNL Google BigQuery] 機能をサポートできるようになります。<p>ベータ版にアクセスするには、アドビのアカウントチームにお問い合わせください。</p> | ベータ版リリース：2025年9月24日（PT） | 2026年3月25日（PT） |
| **Data Insights Agentと Copilot の統合** <br/> Data Insights AgentがMicrosoft Copilot と統合され、自然言語プロンプトを使用して、Teams、Powerpoint などのCustomer Journey Analytics ツール内でMicrosoft データを直接操作できるようになりました。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年3月26日（PT） |
| **Adobe Engineering Agent でのデータ検証**<br/>Data Engineering Agent内で新しいデータ検証スキルを利用できます。 これらのスキルは、Customer Journey Analyticsでデータを分析する前に、Adobe Experience Platformで直接データの品質を迅速に評価するのに役立ちます。 <p>データ検証スキルは、統計的な要約と無効または異常な値のインテリジェントな検出を組み合わせて、オンデマンド、フィールドレベル、データセットレベルの検証を可能にします。 </p><p>データ検証スキルを使用することで、手動の QA 作業を減らし、データエンジニアリングワークフロー全体で信頼できるデータのオンボーディングと変換を加速します。</p><p>（ドキュメントへのリンクを添付）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年3月31日（PT） |
| **パネルへの分類の適用**<br/> 分類をパネルに適用できるようになりました。 パネルレベルで分類を適用すると、分類はパネル内のすべてのフリーフォームテーブルのすべての列に適用されます。 | 2026年3月 | 2026年5月 |
| **ストリーミングメディアサービス：スケジュールデータのサポート**<br/> 過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、視聴者をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |
| **イタリア語サポート**<br/> イタリア語ロケール（it-IT）がCustomer Journey AnalyticsのAnalysis Workspaceでサポートされるようになりました。 <p>[Experience Platform UI のブラウザーと言語のサポート &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support) で説明しているように、Customer Journey AnalyticsはExperience Platform UI でサポートされているすべての言語をサポートしています。</p><p>Experience Platformでは [&#x200B; デフォルト言語を変更 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) できます。</p> | | 2026年4月8日（PT） |

## Customer Journey Analytics の修正点

**Analysis Workspace**: AN-440336、AN-440216、AN-438445、AN-438216、AN-437856、AN-437776、AN-437765、AN-437365、AN-432793、AN-432094 431557、AN-431200、AN-429621、AN-429424、AN-427973、AN-426089、AN-425883、AN-424359
**コンポーネント**:
**Content Analytics**:
**ガイド付き分析**:
**書き出し**: AN-432030
**データビュー**: AN-440004、AN-437154、AN-431165
**実装**:
**Report Builder**: AN-437895、AN-437083、AN-434288、AN-434209、AN-433224、AN-430622
**レポート**:AN-439482、AN-439545、AN-438708、AN-431206、AN-430079、AN-428302、AN-428257、AN-425779、AN-423330
**セグメント化**:
**予定レポート**:
**共有指標およびディメンション**:
**その他**: AN-439795、AN-434783、AN-434233、AN-434005、AN-433368、AN-431322、AN-431165、AN-431012、AN-429983、AN-429067、AN-423285


## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **TLS 1.2 暗号スイートの削除** | 2026年2月11日（PT） | 管理者向けの注意：Adobeは、2026 年 5 月 27 日（PT）にAdobe データ収集サーバーから次の TLS 1.2 暗号スイートのサポートを削除する予定です。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>ほとんどの実装において、顧客側での対応は必要ありません。 この変更は、主に、古い TLS ライブラリを使用する従来のネイティブアプリケーションから送信される Analytics データと、古いブラウザーやオペレーティングシステムを使用する少数の web 訪問者に影響を与えます。 これらの暗号スイートのサポートを削除すると、セキュリティが強化され、Adobeが最新の暗号化標準に合わせて調整されます。 現在、これらの暗号スイートに依存しているデータ収集トラフィックは 0.1% 未満です。</p> |

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
