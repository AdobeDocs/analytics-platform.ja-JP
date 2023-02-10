---
title: Customer Journey Analytics ガイド
description: Customer Journey Analytics のランディングページ。
exl-id: c2d9b758-42a4-4b58-9bab-095518efb86d
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 6e90688d72ddf7791ad8c4c12d5293070d987e39
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 82%

---

# Customer Journey Analytics ガイド

このテクニカルドキュメントガイドでは、Customer Journey Analytics のセルフサポートを提供します。Customer Journey Analytics を使用すれば、お好きなチャネルから、オンラインとオフラインの両方ですべての顧客データを Adobe Experience Platform に取り込むことができます。その後、現在 Analysis Workspace を使用して、既存のデジタルデータを分析しているのと同じようにこのデータを分析できます。

Customer Journey Analytics を使用すると、共通の顧客 ID に基づいて Analysis Workspace のオンラインデータとオフラインデータを接続する方法を制御でき、最終的に、アトリビューション、フィルター、フロー、フォールアウトなどを実行できます。その対象は Customer Journey Analytics の顧客データセット全体にわたります。

Analytics Select、Prime および Ultimate のお客様は、このアドオン製品を購入できます。詳しくは、アドビのアカウントチームにお問い合わせください。

<table frame="none"> 
 <tbody> 
  <tr> 
   <td colname="col1" colsep="0" rowsep="0" valign="top"> <p class="head"> <b>新しいトピックまたは注目トピック</b> </p> <p> 
     <ul>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cca/overview.html?lang=ja#cja-connections"> Cross-Channel Analytics（Customer Journey Analytics での ID のステッチ）</a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en">Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=ja"> レポートスイートを様々なスキーマと組み合わせる </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=en"> 処理ルール、VISTA および分類とデータ準備の比較 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=en"> Adobe Analytics と CJA にまたがるレポート機能のデータ処理の比較 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=en"> 仮想レポートスイート、データビュー、AEP サンドボックスおよび Analytics ソースコネクタ </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html"> Adobe Analytics から Customer Journey Analytics への進化 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja-user.html"> Adobe Analytics ユーザー向け CJA ユーザーガイド </a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ja#connection-detail"> 強化された接続管理機能の使用 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja#cja-dataviews"> 強化されたデータビュー機能の使用 </a> </li>
   <td colname="col2" valign="top"><p class="head"> <b>はじめに</b> </p> 
      <ul> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja">Customer Journey Analytics を使い始める</a> </li> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja">よくある質問</a> </li> 
   </ul> <p class="head"><b>リリースノート</b> </p> 
     <li>新機能と修正点については、最新の <a href="https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja" format="https" scope="external">Customer Journey Analytics リリースノート</a>を参照してください。 </li>
    <td colname="col3" valign="top"> <p class="head"><b>CJA API</b> </p> 
    <ul> 
     <li>すべての <a href="https://developer.adobe.com/cja-apis/docs/" format="https" scope="external">Customer Journey Analytics API</a> を参照してください。 </li>
      <li>最新の <a href="https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API" format="https" scope="external">Customer Journey Analytics Reporting API</a> を参照してください。 </li>
    </ul> <p class="head"> <b>Adobe Experience Platform リソース</b> </p> 
    <ul> 
     <li><a href="https://www.adobe.com/jp/experience-platform.html" format="http" scope="external">Adobe Experience Platform</a> </li> 
     <li> <a href="https://experienceleague.adobe.com/docs/platform-learn/tutorials/overview.html?lang=ja" format="https" scope="external">Adobe Experience Platform チュートリアル</a> </li> 
     <li><a href="https://www.adobe.io/apis/experienceplatform/home/api-reference.html" format="https" scope="external">API リファレンス</a> </li> 
     <li><a href="https://www.adobe.com/jp/experience-platform/documentation-and-developer-resources.html" format="https" scope="external">ドキュメントと開発者向けリソース</a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html" format="https" scope="external"> 従来のAdobe Analyticsからデータを取り込んで使用する方法に関するクイックスタートガイド
     <li><a href="https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja" format="https" scope="external">レポートスイートデータ用の Adobe Analytics ソースコネクタ</a> </li>
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
