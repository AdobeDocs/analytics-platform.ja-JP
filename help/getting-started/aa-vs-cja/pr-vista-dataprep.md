---
source-git-commit: 8943af2bc81de5ece238dc7647ff3f66b14b9776
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 4%

---
# Adobe Analytics処理ルール、VISTA および分類と、Analytics Source Connector 用の Data Prep の比較

[処理ルールと VISTA ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) Adobe Analytics [データ収集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). これらの変換は、Adobeのデータ処理の一環として発生します。この変換は、Adobe Analyticsでのレポートおよび分析のためにデータが保存される前におこなわれます。


[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) は、 [AEP](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en) CJA などの AEP アプリケーションでデータが利用できるようになる前に。 データ準備は、多くの AEP と統合されています [ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) また、 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)：レポートスイートデータをAdobe Analyticsから AEP に取り込む方法を提供します。

Adobe Analyticsで収集され、格納されたデータは、処理ルール、VISTA ルール、またはその両方で変換できます。 ただし、その後、Analytics ソースコネクタを介して AEP に転送されるレポートスイートは、Data Prep を使用して別の時間に変換される可能性があります。 これは、様々な目的に適しています。

* **CJA や RTCDP で使用するレポートスイート間のスキーマの違いの解決**. 例えば、レポートスイート A でeVar1 を検索語句として定義し、レポートスイート B でeVar2 を検索語句として定義している場合、data prep を使用して、2 つの異なる eVar を、両方の eVar のデータを含む共通のフィールドにマッピングできます。 これにより、 [異なるスキーマでレポートスイートを組み合わせる](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) （CJA 接続内、または RTCDP で使用）。
* **eVar フィールドと意味的に意味のある名前のマッピング**. Analytics ソースコネクタからの eVar および prop は、次のようなフィールドにマッピングされます。 _\_experience.analytics.customDimensions.eVars.eVar1_.  eVar準備は、ユーザーにとってより意味のある名前を持つ新しいフィールドや、他のデータソースからの名前と一致する名前に、データと prop フィールドをマッピングするために使用できます。 （ただし、これは、CJA データビューでフィールドの名前を変更するなど、他の方法でも実行できます）。
* **データの一般的な変換**. データ準備には、ADC を介して受信するデータに基づいて新しいフィールドを計算し、計算するのに使用できる数百のマッピング関数があります。 区切りフィールドは別々のフィールドに分割できます。 フィールドを組み合わせることができます。 文字列を操作できます。 正規表現などに基づいて、フィールドから情報を抽出できます。


また、Data Prep がとのクロスオーバーを持っていることにも気付くかもしれません。 [分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=ja) 場合によっては たとえば、区切りフィールドがある場合、Data Prep を使用して、分類を使用せずに、そのフィールドを複数の個々のフィールドに分割できます。 ただし、通常、分類は、受信する Analytics ヒットのストリーム外で提供される参照ファイルをアップロードすることで、フィールドにメタデータを追加する方法です。 例えば、SKU を「サイズ」、「ブランド」、「色」などにグループ化する分類ファイルをアップロードできます。 分類と Data Prep のもう 1 つの違いは、分類が過去のデータにも今後もデータにも適用される点です。 一方、Data Prep マッピングは、マッピングが先に作成された時点からデータに適用されます。