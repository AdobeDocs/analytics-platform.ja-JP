---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7a0e5a483e026d4e7997c8922f421b8ee92d673d
workflow-type: tm+mt
source-wordcount: '1638'
ht-degree: 19%

---

# 最新のCustomer Journey Analytics リリースノート（2026年3月）

**最終更新**: 2026年3月11日（PT）

これらのリリースノートは、2026年3月のリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ヘッダーの上書き** <br/>Content Analyticsでは、ヘッダー名とシークレットヘッダーの値を指定できます。 この[&#x200B; ヘッダーが設定を上書きします](/help/content-analytics/config/guided.md#header-overrides)。これにより、Content Analyticsはカスタム HTTP ヘッダーを送信して、実装したボット検出またはゲートトラフィックテクノロジを回避できます。 |  | 2026年2月2日（PT） |
| **複数のIMS組織のレポートスイートを結合**<br/> Analytics Source コネクタを使用して、複数のIMS組織のレポートスイートを結合できます。 この[IMS間データマッピング &#x200B;](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md)機能により、顧客データが複数のIMS組織に分散している場合でも、組織は顧客データを組み合わせて表示できます。 <p>**注：**&#x200B;この設定は、Adobe カスタマーケアにリクエストを送信する場合にのみ使用できます。</p> |  | 2026年2月12日（PT） |
| **フリーフォームテーブルに複数のディメンション列を含める**<br/> フリーフォームテーブルに最大5つのディメンション列を含めることができるようになり、複数のディメンション項目を並べて表示できるようになりました。 ディメンション項目の各行は、連結された単一のディメンション項目のように動作します。<p>複数のディメンション列を持つフリーフォームテーブルにフィルター、並べ替え、分類などを適用して、より詳細で詳細なカスタム分析を作成できます。</p><p>以前は、フリーフォームテーブルにディメンション列を1つだけ含めることができました。</p><p>詳しくは、[&#x200B; フリーフォームテーブルに複数のディメンション列を含める](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)を参照してください。</p> | 2026年1月28日（PT） | 2026年3月4日（PT） <p>（当初は2026年2月18日予定）</p> |
| **複数の列でテーブルを並べ替える**<br/>&#x200B;自由形式テーブルのデータを、ディメンションまたは指標のいずれであっても、Analysis Workspaceの複数の列で並べ替えることができるようになりました。<p>複数の列でデータを並べ替える際、各列に割り当てた優先度に従ってデータが並べ替えられます。優先度の番号は、並べ替えアイコンの横に表示されます。</p><p>詳しくは、[フリーフォームテーブルのフィルタリングと並べ替え](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)を参照してください。</p> | 2026年1月28日（PT） | 2026年3月4日（PT） <p>（当初は2026年2月18日予定）</p> |
| **Content Analytics:Content Analyticsの散布図ビジュアライゼーションのサムネールとプレビュー** <br/>[&#x200B; サムネールとプレビュー](/help/content-analytics/report/report.md)は、の散布図ビジュアライゼーションでアセットとエクスペリエンスに使用できます。 | 2026年2月17日（PT） | 2026年3月2日（PT） |
| **Content Analytics: Content Analyticsの棒グラフのビジュアライゼーションのサムネールとプレビュー** <br/>[&#x200B; サムネールとプレビュー](/help/content-analytics/report/report.md)は、棒グラフ（積み重ね）と横棒グラフ（積み重ね）のビジュアライゼーションでアセットとエクスペリエンスに使用できます。 | 2026年2月23日（PT） | 2026年3月9日（PT） |
| **接続でのデータセットのプレビューの再設計**<br/>&#x200B;個人ベースの接続で[追加](/help/connections/create-connection.md#add-datasets)または[編集](/help/connections/create-connection.md#edit-a-dataset)のデータセットを行うと、データをプレビューするエクスペリエンスが向上します。 有効なデータセットをステッチする場合、追加の[&#x200B; ステッチ指標](/help/stitching/use-stitching-ui.md#stitching-metrics)と[不正なID](/help/stitching/use-stitching-ui.md#bad-ids)に関する情報を利用できます。 | 2026年3月6日（PT） | 未定 |
| **Report Builder：すべてのスケジュール済みワークブックに対する管理者の表示**<br/> Report Builder Excel アドインには、管理者がスケジュール済みワークブックの担当者に関係なく、特定の組織のすべてのスケジュール済みワークブックを表示できる新しいフィルターオプションが含まれています。 このフィルターオプションは、Analytics管理者のみが使用できます。 スケジュールされたワークブックを表示する場合は、「ワークブック」タブと「レガシー」タブの両方で使用できます。<p>スケジュールされたすべてのワークブックを表示できる機能は、分散したチーム間でワークブックを移行する場合に特に便利です。この機能を使用すると、管理者は移行前にすべてのレガシーワークブックを簡単に見つけることができます。</p><p>以前は、管理者は自分がスケジュールしたワークブックのみを表示でき、他のユーザーがスケジュールしたワークブックは表示できませんでした。</br>詳細については、[&#x200B; スケジュールされたワークブックの管理](/help/report-builder/manage-schedules-reportbuilder.md)を参照してください。</p> | | 2026年3月10日（PT） |
| **近似区別関数の更新**<br/>&#x200B;近似区別関数で使用されているHLL確率論的アルゴリズムは、近日中に更新されます。 この関数を使用した数値の結果の出力は、次のように過去の数値からわずかに変化する場合があります。<ul><li>微量の一意の値をカウントする場合、推定値を使用するのではなく、正確なカウントを使用するように結果が改善されます。</li><li>より大きな値をカウントする場合、カウントの見積もりは、このアップデートの前と同じ精度を保持します（見積もりは、正確な数の5% （95%）以内に正確です）。</li></ul><p>個別関数の概算の詳細については、[詳細関数](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)の[個別関数の概算](/help/components/calc-metrics/cm-adv-functions.md)を参照してください</p> | | 2026年3月10日（PT） |
| **テーブルの書き出しの機能強化**<br/> テーブルの書き出しには、次の機能強化が含まれています。<p>書き出しの作成と設定の強化</p><ul><li>書き出しページから書き出しを作成します。 以前は、テーブルを右クリックしてAnalysis Workspaceから書き出しを作成することしかできませんでした。</li><li>書き出しの作成時に新しいアカウントまたは場所を追加します。</li><li>書き出したファイルのファイル名の作成とフォルダーの配置を自動化します。 これにより、ファイル名を予測可能にし、論理的な方法でフォルダーに整理できます。 以前は、ファイル名は予測不可能で、単一のフォルダーにグループ化されていました。</li><li>データウェアハウスの互換性を向上させるために、データをParquet ファイルとして書き出すサポートがあります。 以前は、CSVとJSONのみがサポートされていました。</li></ul><p>書き出し管理の強化</p><ul><li>書き出しページから1つ以上の書き出しを更新またはキャンセルします。</li><li>ログページから1つ以上の書き出しを再送信します。</li><li>書き出しが失敗するか、有効期限が近づいたときに、個々のユーザーまたはグループに電子メールを送信します。</li><li>失敗した書き出しについて、より正確なエラーメッセージを表示。</li></ul><p>計算指標、セグメント、ディメンションの機能強化</p><ul><li>より計算された指標関数のサポート。 以前は、単純な数学関数のみがサポートされていました。</li><li>書き出しの作成時にセグメントを適用します。</li><li>精度を向上させるダブルデータタイプディメンションのサポート。</li></ul><p>管理の強化</p><ul><li>管理者は、作成者に関係なく、すべての書き出しとログを表示できるようになりました。</li></ul><p>詳しくは、次のリソースを参照してください。<ul><li>[完全なテーブルをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)</li><li>[&#x200B; クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)</li><li>[&#x200B; クラウド書き出し場所の設定](/help/components/exports/cloud-export-locations.md)</li><li>[書き出しを管理](/help/components/exports/manage-exports.md)</li><li>[&#x200B; クラウド書き出しの場所とアカウントの管理](/help/components/exports/manage-export-locations.md)</li><li>[書き出しログの管理](/help/components/exports/manage-export-logs.md)</li></ul></p> | 2026年2月25日（PT） | 2026年3月11日（PT）<p>（当初は2026年3月4日に予定）</p> |
| **Analysis Workspaceの実践チュートリアル**<br/>&#x200B;新しい実践チュートリアルが利用可能になり、Analysis Workspaceでのパネル、ビジュアライゼーション、コンポーネントの基本的な使用方法を新しいユーザーにガイドできるようになりました。 <p>詳しくは、[Customer Journey Analytics ランディングページ &#x200B;](/help/getting-started/landing.md)を参照してください。</p> | | 2026年3月18日（PT） |
| **データミラーのサポート**<br/> Experience Platformの特定のソースコネクタに対するモデルベースのスキーマとchange data capture （CDC）機能のサポートにより、Customer Journey Analyticsは[、](/help/data-mirror/data-mirror.md)、および[!DNL Snowflake]のようなデータウェアハウスソリューションの[!DNL Azure Databricks] データミラー[!DNL Google BigQuery]機能をサポートできるようになります。<p>ベータ版にアクセスするには、アドビのアカウントチームにお問い合わせください。</p> | ベータ版リリース：2025年9月24日（PT） | 2026年3月25日（PT） |
| **Data Insights AgentとCopilotの統合** <br/> Data Insights AgentはMicrosoft Copilotと統合され、TeamsやPowerpointなどのMicrosoft ツール内で、自然言語プロンプトを使用してCustomer Journey Analytics データを直接操作できるようになりました。<p>詳しくは、[Adobe Marketing Agent for Microsoft 365 Copilot](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/ama-ms)を参照してください。</p> | | 2026年3月26日（PT） |
| **Adobe Engineering Agentでのデータ検証** <br/>新しいデータ検証スキルは、Data Engineering Agent内で利用できます。 Customer Journey Analyticsでデータを分析する前に、Adobe Experience Platformで直接データ品質を迅速に評価できます。 <p>データ検証スキルにより、オンデマンド、フィールドレベル、データセットレベルの検証が可能になり、統計的な要約と、無効な値や異常値のインテリジェントな検出を組み合わせることができます。 </p><p>データ検証スキルを活用することで、手作業のQA作業を削減し、データエンジニアリングワークフロー全体で信頼できるデータオンボーディングと変換を加速できます。</p><p>（ドキュメントへのリンクを添付）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年4月末 <p>（当初は 2026年3月31日（PT）にリリースされる予定でした）</p> |
| **パネルに分類を適用**<br/>&#x200B;分類をパネルに適用できるようになりました。 パネルレベルで分類を適用すると、分類はパネル内のすべてのフリーフォームテーブルのすべての列に適用されます。 | 2026年3月 | 2026年5月 |
| **ストリーミングメディアサービス：サポートスケジュールのデータ** <br/>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、視聴者をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |
| **イタリア語サポート**<br/> イタリア語ロケール（it-IT）がCustomer Journey AnalyticsのAnalysis Workspaceでサポートされるようになりました。 <p>Customer Journey Analyticsは、Experience Platform UIでサポートされているすべての言語をサポートしています。詳しくは、[Experience Platform UIのブラウザーと言語のサポート &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)を参照してください。</p><p>Experience Platformで[既定の言語](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)を変更できます。</p> | | 2026年4月8日（PT） |

## Customer Journey Analytics の修正点

**Analysis Workspace**: AN-440336, AN-440216, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**コンポーネント**:
**Content Analytics**:
**ガイド付き分析**:
**書き出し**: AN-432030
**データビュー**: AN-440004、AN-437154、AN-431165
**実装**:
**Report Builder**: AN-437895、AN-437083、AN-434288、AN-434209、AN-433224、AN-430622
**レポート**: AN-439482、AN-439545、AN-438708、AN-431206、AN-430079、AN-428302、AN-428257、AN-425779、AN-423330
**セグメント化**:
**スケジュール済みレポート**:
**共有の指標とディメンション**:
**その他**: AN-439795、AN-434783、AN-434233、AN-434005、AN-433368、AN-431322、AN-431165、AN-431012、AN-429983、AN-429067、AN-423285


## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| **TLS 1.2暗号スイートの削除** | 2026年2月11日（PT） | 管理者へのお知らせ：Adobeは、2026年5月27日に、Adobe データ収集サーバーから次のTLS 1.2暗号スイートのサポートを削除する予定です。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>ほとんどの実装では、顧客の操作は必要ありません。 この変更は、主に、古いTLS ライブラリを使用するレガシーネイティブアプリケーションから送信されるAnalytics データと、古いブラウザーまたはオペレーティングシステム上の少数のweb訪問者に影響します。 これらの暗号スイートのサポートを削除すると、セキュリティが強化され、Adobeが最新の暗号化標準に準拠します。 現在、これらの暗号スイートに依存するデータ収集トラフィックは、0.1%未満にとどまっています。</p> |

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
