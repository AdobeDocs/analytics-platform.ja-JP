---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 94dffc915f624309bca4709ba9140b64b3e3aa41
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 46%

---

# 最新のCustomer Journey Analytics リリースノート（2026 年 1 月）

**最終更新日**：2026年1月14日（PT）

これらのリリースノートは、2026 年 1 月のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey AnalyticsのExperience Platform プロファイルデータセットからのオーディエンスの分析** | Experience Platform プロファイルデータセットからCustomer Journey Analytics接続にオーディエンスメンバーシップデータを取り込めるようになりました。 オーディエンスは、Analysis Workspaceで使用する新しいディメンションとして使用できるようになります。<p>これは、Customer Journey Analyticsの新しい機能で XDM オブジェクトマップを取り込むことで可能になりました。これにより、プロファイルオーディエンス ID を取り込むことができます。</p><p>以前は、単純な XDM マップのみをCustomer Journey Analyticsに取り込むことができました。</p><p>オーディエンスデータをディメンションとしてAnalysis Workspaceの任意のプロジェクトに追加できるだけでなく、次の新しいWorkspace テンプレートも使用できます。</p><ul><li>Audience Analyticsの概要</li><li>同意ポリシーの概要</li></ul><p>詳しくは、[&#x200B; オーディエンス分析の概要 &#x200B;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html?lang=ja) を参照してください。</p> | 2025年10月22日（PT） | 2026年1月27日（PT） <p> （当初は 2026 年 1 月 22 日に予定）</p> |
| **データストーリーテリング：Workspace レポートからスライドプレゼンテーションを生成する** | Analysis Workspace レポートに基づくスライドプレゼンテーション（.pptx 形式）を自動生成できるようになりました。 Workspace は、レポート内で主要なインサイトを検出し、関係者が利用できるスライドに変換します。<p>この機能により、結果を明らかにし、エグゼクティブ向けの説明文を作成し、ビジネスへの影響を伝えるために必要な時間と労力が削減されます。</p><p>詳しくは、[データストーリーテリング：Workspace レポートからスライドプレゼンテーションを生成する](/help/analysis-workspace/curate-share/generate-slides.md)を参照してください。</p> | 2025年10月22日（PT） | 2026年1月28日（PT） |
| **フリーフォームテーブルに複数のディメンション列を含める** | フリーフォームテーブルに最大 5 つのディメンション列を含めることができ、複数のディメンション項目を並べて表示できます。 ディメンション項目の各行は、単一の連結されたディメンション項目のように動作します。<p>複数のディメンション列を持つフリーフォームテーブルにフィルター、並べ替え、分類などを適用して、より深く、よりカスタムな分析を作成できます。</p><p>以前は、フリーフォームテーブルには 1 つのディメンション列のみを含めることができました。</p><p>詳しくは、[&#x200B; フリーフォームテーブルに複数のディメンション列を含める &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md) を参照してください。</p> | 2026年1月28日（PT） | 2026年2月18日（PT） |
| **複数の列でテーブルを並べ替える** | ディメンションか指標かに関わらず、Analysis Workspaceで複数の列でフリーフォームテーブルのデータを並べ替えることができるようになりました。<p>複数の列のデータを並べ替える場合、各列に割り当てた優先度に従ってデータが並べ替えられます。 優先度番号は、並べ替えアイコンの横に表示されます。</p><p>詳しくは、[&#x200B; フリーフォームテーブルのフィルタリングと並べ替え &#x200B;](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables-by-multiple-columns-advanced-sorting) の [&#x200B; 複数の列でテーブルを並べ替える &#x200B;](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) を参照してください。</p> | 2026年1月28日（PT） | 2026年2月18日（PT） |
| **複数の IMS 組織のデータソースの結合** | Analytics Source コネクタを使用して、複数の IMS 組織から複数のデータソースを組み合わせることができるようになりました。 これにより、顧客データが複数の IMS 組織に分散している場合でも、組織は顧客データを組み合わせて表示できます。 <p>**注意：** この設定を使用できるのは、Adobe カスタマーケアにリクエストを送信した場合のみです。</p>  <p>（ドキュメントのリンクは以下を参照。）</p> |  | 2026年1月30日（PT） |
| **接続におけるステッチ** | Customer Journey Analyticsのステッチプロセスが、より簡単になりました。 データセットを複製し、その複製されたデータセットにステッチを適用する代わりに、Customer Journey Analytics へのデータ取り込み時にステッチが行われるようになりました。これにより、複製されたデータセットとスキーマの必要性がなくなります。 <p>さらに、Adobe カスタマーケアを通じてステッチをリクエストする代わりに、更新された Connections インターフェイスを通じて自分でステッチを開始 [&#x200B; できるようになりました &#x200B;](/help/stitching/use-stitching-ui.md)。</p><p> *以前お知らせしたリリース日は、追加の作業が必要であったこととホリデーシーズンが原因で延期されました。 現在は、安定性を確保し、ホリデー期間中の中断を最小限に抑えるのに、段階的なロールアウトが予定されています。*</p> | 2025年10月28日（PT） | 2026年1月30日（PT） |
| **データミラーのサポート** | Experience Platform の特定のソースコネクタに対するモデルベースのスキーマと変更データキャプチャ（CDC）機能のサポートにより、Customer Journey Analytics では、[!DNL Snowflake]、[!DNL Azure Databricks]、[!DNL Google BigQuery] のデータウェアハウスソリューションの[データミラー](/help/data-mirror/data-mirror.md)機能をサポートできます。<p>ベータ版にアクセスするには、アドビのアカウントチームにお問い合わせください。</p> | ベータ版リリース：2025年9月24日（PT） | 未定 |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |

## Customer Journey Analytics の修正点

**Analysis Workspace**: AN-423389、AN-423316、AN-422636、AN-422482、AN-422121、AN-422116、AN-422027、AN-421134、AN-420187、AN-406271 406188、AN-405997、AN-405983、AN-405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713 404502 404353 404352 404048 403241 402523 400795 396149 390990 390646 383484 376980 371729 347570 404835、AN-COUNTERN、AN-COUNTERN、AN-COUNTERN、AN-AN-AN AN – から AN – へ、AN – から AN – へ、AN – から AN – へ、AN – から AN – へ、AN – から AN – へ、AN – から AN – へ、AN – から AN – へ、AN – から AN – へ
**コンポーネント**:
**Content Analytics**:
**ガイド付き分析**: AN-421274
**エクスポート**:
**データビュー**: AN-421891, AN-404627
**実装**:
**Report Builder**: AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**レポート**:
**セグメント化**:
**予定レポート**:AN-423087、AN-422686
**共有指標およびディメンション**:
**その他**: AN-422946、AN-422775、AN-422273、AN-422100、AN-420045、AN-404891、AN-390912


## Customer Journey Analytics 管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし |  |  |

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
