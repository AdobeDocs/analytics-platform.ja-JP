---
title: Content Analytics有料メディア自動設定
description: データセット、接続、データビューなどの自動設定について説明します。
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: e9274ad7899537837723e2eb9cd842c5449530ff
workflow-type: tm+mt
source-wordcount: '2309'
ht-degree: 2%
---
# ペイドメディアの自動設定

Content Analyticsで有料メディアチャネルを有効にして設定を保存すると、Adobeは、有料メディアデータセットのレポート設定を使用して、選択した接続とデータビューを更新します。 デフォルトのディメンション、指標、ルックアップロジック、またはサマリーデータグループを自分で再作成する必要はありません。

オブジェクトの3つのレイヤーが作成されます。

| オブジェクト | 次を含む | 目的 |
| --- | --- | --- |
| 概要データセット | 広告、エクスペリエンスのプレースメント、アセットレベルでのAdvertisingネットワークのパフォーマンスデータと、サポートされている場合はデモグラフィックまたは地理的な分類。 | 配信、クリック、支出、広告ネットワークで報告された結果を測定できます |
| メタデータと属性検索データセット | アカウント、キャンペーン、広告グループ、広告、エクスペリエンス、アセットの詳細。Content Analyticsのクリエイティブ属性。 | 識別子を使用するのではなく、認識可能な名前、クリエイティブの詳細、サムネール、コンテンツ属性を使用してレポートを作成できます。 |
| データビューコンポーネントと設定 | ディメンション、指標、計算指標、派生フィールド、概要データグループ。 | 手動でデータセット間の関係を再構築することなく、Workspace分析を構築できます。 |

ペイドメディアを有効にしても、ペイドメディアデータがサイトの注文、予約、収益に自動的に接続されるわけではありません。 エクスペリエンスイベントデータと有料メディアデータの相関関係は、顧客固有のトラッキングキーマッピングとレポート設定が必要です。

## 概要データセット

下の図は、Content Analyticsで1つ以上の広告ネットワークに対して有料メディアチャネルを有効にした場合に、サマリーデータセットがどのように生成されるかを示しています。 利用可能な広告ネットワークの関連APIを使用して、エクスペリエンス、アセット、広告データをダウンロードし、6つのサマリーデータセットに変換できます。

![概要データセットの有料メディア生成](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

特定の広告ネットワークによって、作成されるサマリーデータセットが決まります。 ソースコネクタを設定したすべての広告ネットワークが、6つの可能なサマリーデータセットをすべて生成するわけではありません。 次の情報を含むサマリーデータセットの概要については、次の表を参照してください。

* 概要データセット名、イベントタイプ、およびコンポーネントサフィックス
* エンティティ
* 分類
* 次のネットワークの![&#x200B; チェックマーク &#x200B;](/help/assets/icons2/Checkmark.svg)に入力されるデータセット：
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest、Snapchat、およびTikTokは、リリースの限定的なテスト段階にあり、お使いの環境ではまだ利用できない場合があります。 機能が一般提供されると、この注記は削除されます。 Customer Journey Analytics リリースプロセスについて詳しくは、[Customer Journey Analytics機能リリース &#x200B;](/help/release-notes/releases.md)を参照してください
    >


* サマリーデータセットの各行が何を表しているかを確認できます。

| 概要データセット <br/> イベントタイプ <br/> コンポーネントサフィックス | エンティティ <br/>分類 | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | 各行は、次を表します |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Ad<br/>none | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | デモグラフィック情報や地理的な内訳を使用しない、広告の日々のパフォーマンス。 |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | 広告<br/>年齢、性別 | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | 広告の日々のパフォーマンス <br/>を年齢と性別ごとに示します。 |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad<br/>国、地域 | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | 広告の1日のパフォーマンス <br/>を国と地域ごとに分類します。 |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience<br>Platform, position | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | 広告のクリエイティブ体験に関連付けられた日々のパフォーマンス <br/>は、プラットフォームとポジションごとに分類されます<br/>。 |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | アセット <br/>なし | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | | | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | 広告/キャンペーンのコンテキストで<br/> アセットレベルの日々のパフォーマンス <br/>を示します。デモグラフィックや地理的な内訳はありません。 |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | アセット <br/>年齢、性別 | ![チェックマーク](/help/assets/icons2/Checkmark.svg) | | | | | 広告/キャンペーンのコンテキスト <br/>で、アセットレベルの日々のパフォーマンス <br/>を年齢と性別ごとに分類しました。 |


この表では、データセットのカバレッジについて説明しますが、特定のネットワークがすべての指標またはメタデータフィールドに入力されることを保証するものではありません。 分析に必要なフィールドを確認します。 使用できないフィールドまたはサポートされていない分類は、フィールドの測定されたゼロ値と同じではありません。

別々のルックアップデータセットには、アカウント、キャンペーン、広告グループ、広告、エクスペリエンス、アセットなどが記述されます。 エンティティ GUIDを使用して、名前とメタデータを提供します。 サマリーデータセットと6つのルックアップデータセットの間に1対1のペアリングはありません。

概要データのグループ化は、同等のディメンションをまとめます。グループ化は、6つのパフォーマンス指標の合計を合計しません。

## コンポーネント

Content Analyticsの有料メディアチャネルは、有効にすると、いくつかのデータビューコンポーネントも生成されます。 これらのコンポーネントには、類似の名前付きコンポーネントを区別するためのコンポーネントサフィックスが用意されています。

### 指標

広告ネットワークによって、パフォーマンスの内訳は異なります。 Content Analyticsでは、指標のあらゆるバージョンを交換可能として扱う代わりに、これらの区別を維持しています。

次に例を示します。

| コンポーネント | 意味 | 適切な開始分析 |
| --- | --- | --- |
| 広告の概要をクリック | 広告の内訳なしレベルで報告されたクリック数 | キャンペーンや広告のパフォーマンス |
| アセットの概要をクリック | アセットレベルで報告されたクリック数 | Creative-asset-performance |
| 広告の地域をクリック | 「広告地域」レポートのクリック数 | 各国・地域別のパフォーマンス |
| エクスペリエンスの配置をクリック | エクスペリエンス配置レポートからのクリック数 | プレースメント別のCreative パフォーマンス |

各クリック指標コンポーネントは、異なるレポートコンテキストを提供します。 これらの指標コンポーネントを総計に合計することはできません。 同じ基本広告アクティビティを、複数のサマリーデータセットで表すことができます。

### ディメンション

各概要データセットには、IDとGUIDが含まれています。 IDは、広告ネットワークが提供するID （アカウント、キャンペーン、広告グループ、広告、エクスペリエンス、アセットなど）で、広告ネットワークデータ内で&#x200B;**一意です。** GUIDは、Adobeが提供するID （アカウント、キャンペーン、広告グループ、広告、エクスペリエンス、アセットなど）で、**個の広告ネットワークで一意です。** IDとGUIDは、対応する名前とメタデータを検索するために使用されます。

### 派生フィールド

派生フィールドは、自動レポート設定の一部です。 派生フィールドは、識別子を名前やメタデータに変換し、クリエイティブ属性を公開し、レポートソース全体で使用される同等のディメンションをサポートします。 追加の広告活動を行ったり、web サイトのコンバージョンを自動的に特定したりすることはありません。

分析の指標にも同じ内訳を使用し、その内訳でサポートされるディメンションを使用します。 デモグラフィックおよび地理的な合計は、必ずしも広告ネットワークの内訳なし合計と等しくなく、取り込み失敗を意味しないことに注意してください。

## レポートと分析

Content Analyticsの有料メディアの設定と取り込みが完了したら、レポートと分析から始めることができます。 いくつかの例については、以下の表を参照してください。 使用可能な場合は、規範的なグループ化されたディメンションを使用し、一致するレポートレベルから指標を選択します。

| ビジネス上の疑問 | 開始レベル | 行と分類 | 開始指標 | 重要な境界 |
| --- | --- | --- | --- | --- |
| キャンペーンや広告のパフォーマンス？ | 広告の概要 | キャンペーン名、広告グループ名、広告名。オプションで広告ネットワークとアカウント名 | インプレッション広告の概要、クリック広告の概要、費用の広告の概要、CTRとCPCの一致 | 配信/支出合計に1つのレベルを使用します。アカウントを結合する前に通貨を検証します |
| どのクリエイティブアセットが最も強い反応を得るか？ | アセットの概要 | アセット名（有料メディア）、アセット ID （オプションで広告ネットワーク） | インプレッション数アセットの概要、クリック数アセットの概要、クリックスルー率アセットの概要 | これは、ネットワークによって報告されるアセットパフォーマンスであり、後でオンサイトのコンバージョンが発生したことを示すものではありません |
| パフォーマンスに関連する画像特性は何か？ | アセットの概要 | アセットタグ、アセットオブジェクト、アセット人物カテゴリ、アセットシーン、またはその他の使用可能なアセット属性 | アセットの概要、インプレッション数、クリック数、CTR | 属性抽出は使用可能である必要があります。複数値の属性カテゴリは重複する可能性があります |
| 有料パフォーマンスに関連するメッセージの特徴は何ですか？ | 体験の配置 | エクスペリエンスのキーワード、エクスペリエンスのトーン、エクスペリエンスの説得戦略、またはその他の使用可能なエクスペリエンス属性（オプションでプラットフォームと配置） | インプレッション / エクスペリエンスの配置、クリック / エクスペリエンスの配置、一致するCTR | 入力されたエクスペリエンス属性が必要です。結果は配置に固有で、関連付けを説明するもので、因果関係は示されません |
| どのプレースメントが最も効果的か？ | 体験の配置 | エクスペリエンス名、プラットフォーム、配置 | インプレッション / エクスペリエンスの配置、クリック / エクスペリエンスの配置、一致するCTR | 配置の定義と使用可能な値は、広告ネットワークによって異なります |
| MetaとGoogleの広告/アセット/エクスペリエンスはどのように比較されますか？ | 質問に対して選択された広告サマリー、アセットサマリー、またはエクスペリエンス配置 | 適切なキャンペーン、アセット、エクスペリエンスディメンションを使用した広告ネットワーク | 両方のネットワークで同じレベルと指標の定義 | 両方のネットワークで入力されたフィールドのみを比較します。Googleでは、このモデルの3つのデモグラフィック/地理的概要は入力されません |

これらのレポートでは、クリエイティブ属性とパフォーマンスの関連付けを明らかにできますが、属性が結果を引き起こしたことを証明することはできません。

互換性のない組み合わせを避ける：アセット名（有料メディア）と広告概要の指標は、アセットレポートの代わりにはなりません。 アセット分析にアセットサマリー指標を使用し、地域分析にAd Geography指標を使用します。 互換性のないペアリングからの空またはゼロのセルは、アクティビティがないことを示すものとして解釈しないでください。

### 例

ここでは、有料メディアのパフォーマンスに関するレポートを作成および分析する方法の例と、Content Analyticsのエクスペリエンスおよびアセットのデータを有料メディアのデータと組み合わせる方法を示します。

#### 広告キャンペーンのパフォーマンス

広告レベルでキャンペーンのパフォーマンスをレポートしたり、 Analysis Workspaceでは、Campaign Nameをディメンション（行）として使用し、次の表に示す指標を使用します。 各指標には同じコンポーネントサフィックスがあります。

| 指標 | レポートレベル |
| --- | --- |
| インプレッション数 | 広告の概要 |
| クリック数 | 広告の概要 |
| 費用 | 広告の概要 |
| クリックスルー率 | 広告の概要 |
| クリック単価 | 広告の概要 |

オプションで、キャンペーン名を広告名で分類しますが、5つの列すべてを広告概要レベルに保ちます。

個々のアセットを調査するには、アセット名（有料メディア）と一致するアセットの概要の列を含む別のテーブルを使用します。 2つのテーブルの合計を一緒に追加しないでください。

#### 最もパフォーマンスの高い広告の特定

Metaの広告が最も効果を発揮している場所を把握する必要があります。

まず、地理とデモグラフィックの内訳を追加して調査します。 ディメンションとしてキャンペーン名または広告名を使用し、次の表に示す指標を使用します。 各指標には同じコンポーネントサフィックスがあります。

| 指標 | レポートレベル |
| --- | --- |
| インプレッション数 | 広告地域 |
| クリック数 | 広告地域 |
| 費用 | 広告の概要 |
| クリックスルー率 | 広告地域 |
| クリック単価 | 広告の概要 |


#### ペイドメディアデータとエクスペリエンスイベントのデータを結合

ペイドメディアのパフォーマンスとオンサイトの行動データを結合して、キャンペーンや広告が、web サイトのエンゲージメント、コンバージョン、収益とどのように関連しているかを把握できます。 例えば、広告ネットワークのクリック数と支出数を、同じキャンペーンの訪問に起因する注文と比較します。

このレポートを設定するには、有料メディアの概要データセットとオンサイトイベントデータセットを同じCustomer Journey Analytics接続に含めます。 ランディングページのURL パラメーターや既存のイベントフィールドから、安定したキャンペーン、広告、サポートされているアセットの識別子を取得できます。 必要に応じて派生フィールドを使用し、これらの値を解析して、対応する有料メディア識別子にマッピングすることで、必要なネットワークとアカウントのコンテキストを維持します。 識別子を文字列として保持します。 一致するイベントと概要ディメンションを関連付けるには、データビューで概要データグループを設定します。 有料メディアチャネルを有効にしても、この実装固有のURL トラッキングとマッピングは自動的に設定されません。


| トラッキングオプション | 注意点 |
|---|---|
| Meta Ads | サポートされている`campaign.id`、`adset.id`、`ad.id`などの動的識別子を使用して、宛先URL パラメーターを設定します。 Web サイトで解決された値をキャプチャします。 コネクタを有効にしても、これらのパラメーターが自動的に広告URLに追加されるわけではありません。 |
| Google 広告 | |
| 個別アセット | 下流プロセスの結果をアセットレベルでレポートするには、クリックに関連する特定のアセットにマッピングする、キャプチャされたIDが必要です。 カスタム URL パラメーターは、広告フォーマットがアセット固有のトラッキングを許可する場合に、これをサポートできます。 広告識別子だけでは、1つの広告内の複数のアセットを区別することはできず、複数のアセット全体に適用された1つの静的アセットパラメーターでは、クリックに関連付けられたアセットを識別できません。 |

Analysis Workspaceでは、キャンペーンまたは広告の比較に&#x200B;**[!UICONTROL Ad Summary]**&#x200B;指標を、サポートされているアセットの比較に&#x200B;**[!UICONTROL Asset Summary]**&#x200B;指標を使用します。 アトリビューションモデルとルックバックウィンドウを、レポートの質問を反映するオンサイトのコンバージョン指標に適用します。

次の点に注意してください。

* ペイドメディアデータは、個人IDを持たない要約データです。 オンサイトでの行動は、イベントデータです。
* 一致するディメンションをグループ化すると、これらのソースでのレポートがサポートされますが、個々の広告ネットワークのコンバージョンとweb サイトのコンバージョンが一致したり、個人レベルのステッチが実行されたりすることはありません。
* この比較は、因果関係ではなく関連性を示しています。
* コンバージョンの定義、アトリビューションウィンドウ、ビューションスルーまたはモデル化されたコンバージョン、同意、レポート日またはタイムゾーンにより、結果は異なる場合があります。
* トラッキングパラメーターがチャネルをまたいで再利用される場合、キャンペーンのタグが付けられた訪問のソースを検証します。


#### キャンペーンのパフォーマンスとオンサイト注文の比較

ランディングページ URLには、複数のトラッキングパラメーターを含めることができます。 この例では、`utm_id`のキャンペーン IDを使用して、キャンペーンの支出とweb サイトの注文を比較しています。

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

この比較に使用されるパラメーター：`utm_id=120218706543980215`。 他のパラメーターは、ソース、メディア、キャンペーンのラベルを表しますが、この例で使用する一致するフィールドとしては使用されません。

URLがweb サイトイベントデータでキャプチャされ、web サイトイベントデータセットと有料メディアデータセットの両方が同じCustomer Journey Analytics接続に含まれている場合：

1. キャンペーンの特定： 派生フィールドを使用して、URLから`utm_id`を読み取り、その値を有料メディアデータ内の対応するキャンペーン識別子にマッピングします。
1. 一致するディメンションをグループ化します。 データビューで、web サイトキャンペーンディメンションを有料キャンペーンディメンションの`Summary Data Group`に追加し、既存のメンバーを保持します。
1. 予算と注文の比較。 Analysis Workspaceでは、グループ化されたキャンペーンディメンションをフリーフォームテーブルの行として使用します。 `Ad Summary`の支出とweb サイト `Orders`を列として追加します。 `Orders`のアトリビューションモデルとルックバックウィンドウを設定します。


フリーフォームの表には、各キャンペーンに起因するweb サイトの注文と、広告ネットワークの支出が表示されています。 広告費が類似したふたつのキャンペーンでは、web サイトの下流におけるアクションの貢献度が異なります。 広告の指標だけでパフォーマンスを評価するのではなく、キャンペーンとランディングページの体験を特定し、より詳細な調査やテストを実施できます。

この例ではキャンペーン IDを使用しますが、一致する値を取得できる場合は、同じアプローチで広告グループ、広告、またはアセットの識別子を使用できます。 **[!UICONTROL Asset Foreground Colors]**&#x200B;などのContent Analytics属性を使用すると、クリエイティブの特徴と有料メディアのパフォーマンスを比較できます。 アセットに特化したトラッキングと一致する属性のディメンションを両方のソースで設定することで、その比較をweb サイトへの属性付き注文に拡張し、その結果をクリエイティブテストの指針として活用できます。

#### アセットのパフォーマンスとweb データの組み合わせ

有料メディアへの投資に関連するアセットのパフォーマンスについてレポートおよび分析する場合は、広告ネットワークの有料メディア設定に特定のアセット UTM パラメーターを追加することを検討してください。 例えば、s`ite_source_name`、`campaign.id`、`adset.id`、`placement`などの標準の動的パラメーターの他に、`aca_asset_id=999999`などの静的カスタムパラメーターを追加します。

このカスタムパラメーターは、ランディングページのURLに追加されます。 例：https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&aca_id_2=8888888&utm_medium=paid&utm_source=fb&utm_id=120241705099830539&utm_term=120241705099840539&utm_campaign=120241705099830539

ページ上のアセットと有料メディアデータとの関係が構築されました。 Analysis Workspaceでこのリレーションを使用して、Content Analytics アセットのメタデータ（**[!UICONTROL Asset Foreground Colors]**&#x200B;など）が有料メディアキャンペーンの成功にどのように貢献しているかを確認します。


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
