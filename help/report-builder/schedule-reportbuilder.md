---
title: Customer Journey Analytics での Report Builder を使用したワークブックのスケジュール設定方法
description: Report Builderのスケジュール機能の使用方法を学ぶ
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: 9505f21748b3d94b2398f898e5399d095ccec260
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 15%

---

# メールでの共有によるワークブックのスケジュール設定

ワークブックを保存して分析を完了したら、スケジュール機能を使用してチームの他のユーザーとワークブックを共有できます。 スケジュール機能を使用すると、ワークブック内のデータを自動更新するスケジュールを作成できます。 さらに、指定した日時、指定したオーディエンスに添付ファイルとして Excel ワークブックファイルをメールで送信します。 スケジュールを設定すると、受信者には、自動的かつ定期的に最新情報が送られます。 また、スケジュール機能を使用して、自動更新のスケジュールを設定せずに、ワークブックを 1 回送信することもできます。

1 つのワークブックに対して複数のスケジュールを作成できます。例えば、毎日チームにワークブックを送信するスケジュールと、週に 1 回マネージャーにワークブックを送信するスケジュールを 2 つ作成するとします。

また、スケジュール機能を使用すると、ワークブックのパスワード保護を設定したり、以前にスケジュールされたワークブックを編集したりできます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [&#x200B; ワークブックのスケジュール &#x200B;](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## ワークブックのスケジュール設定

ワークブックをスケジュールするには：

1. Report Builderハブで「**[!UICONTROL スケジュール]**」を選択してスケジュールを作成し、Excel ファイル（.xlsx）を個人またはグループに自動的に配布できるようにします。

   ![&#x200B; 「スケジュール」ボタンを選択して、スケジュールを作成します。](./assets/schedule.png){zoomable="yes"}

1. **[!UICONTROL ワークブックのスケジュール]** または ![&#x200B; 追加 &#x200B;](/help/assets/icons/Add.svg) を選択して、新しいスケジュールワークブックを作成します。

   ![&#x200B; ワークブックスケジュールウィンドウ。](./assets/schedule-workbook.png){zoomable="yes"}

   スケジュールウィンドウには、ブック名やブックの最終変更日など、ブックに関する事前定義済みの情報が表示されます。

### ファイル

「**[!UICONTROL ファイル]**」セクションでは、ファイルの種類、名前、およびファイルを保護するためのパスワードの詳細を指定します。

![&#x200B; スケジュールペイン。](./assets/schedule-pane.png){zoomable="yes"}

1. 現在のブックがまだ選択されていない場合は、![TableSelect](/help/assets/icons/TableSelect.svg) を使用して選択します。

1. （任意） **[!UICONTROL ファイル名]** を入力します。

   ワークブックのファイル名のデフォルト値はワークブックの名前ですが、必要に応じてファイル名を変更できます。

1. **[!UICONTROL ファイルタイプ]** を選択します。

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   **[!UICONTROL CSV]** を選択する場合、スケジュールされたワークブックは zip 添付ファイルとして送信されることに注意してください。 一部の企業のメール管理では、zip 添付ファイルを含んだメールがブロックされる場合があります。 それに応じて警告が表示されます。

1. （オプション）「**[!UICONTROL ファイル名にタイムスタンプを追加する]**」を選択します。

   ファイル名にタイムスタンプを付加して、ワークブックの更新日を識別できます。タイムスタンプは、特定の日付に送信されたワークブックのバージョンを確認するのに役立ちます。 選択すると、次のいずれかを選択できます。

   * **[!UICONTROL ISO 日付形式]**：ファイル名に `YYYY-MM-DD` が追加されます。
   * **[!UICONTROL ISO 日付形式+ タイムスタンプ]**：ファイル名に `YYYY-MM-DD_HH-MM-SS` が追加されます。

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. **[!UICONTROL ワークブックをパスワードで保護]** にパスワードを入力します。 有効なパスワードには、少なくとも 8 文字、数字、特殊文字が必要です。 ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) を選択してパスワードを表示し、![Visibility](/help/assets/icons/Visibility.svg) を選択してパスワードを非表示にします（デフォルト）。


### 電子メール

「**[!UICONTROL メール]**」セクションで、メールの受信者、件名、説明を指定します。

![&#x200B; スケジュールのメール設定 &#x200B;](assets/schedule-email.png){zoomable="yes"}

1. **受信者**&#x200B;を入力します。組織で認識されるユーザーの名前を入力できます。 または、組織外の人物のメールアドレスを入力できます。

1. 受信者向けに、メールの&#x200B;**件名**&#x200B;と説明を入力します。件名はデフォルトでワークブックファイル名に設定されますが、必要に応じて変更できます。説明セクションに詳細を追加できます。

1. 必要に応じて、「説明 **[!UICONTROL テキスト領域に説明を入力]** きます。


### スケジュール

「**[!UICONTROL スケジュール]**」セクションでは、ワークブックと共にメールを受信者に送信するスケジュールを定義できます。

![&#x200B; スケジュールの定義 &#x200B;](assets/schedule-enable.png){zoomable="yes"}

1. **[!UICONTROL スケジュールオプションを表示]** を選択して、スケジュールを定義します。

1. 開始日を **[!UICONTROL 開始日]** に入力します。 または、「![&#x200B; カレンダー &#x200B;](/help/assets/icons/Calendar.svg)」を選択して、カレンダーから開始日を選択します。

1. 終了日を **[!UICONTROL 終了日]** に入力します。 または、「![&#x200B; カレンダー &#x200B;](/help/assets/icons/Calendar.svg)」を選択して、カレンダーから終了日を選択します。

1. **[!UICONTROL 頻度]** を選択します。 選択した頻度に応じて、追加のオプションがあります。 次の表を参照してください。

   | 頻度 | オプション |
   |---|---|
   | **[!UICONTROL 1 時間ごとに送信]** | **[!UICONTROL 時間数ごとに送信]** の値を入力します。 |
   | **[!UICONTROL 毎日送信]** | **[!UICONTROL 1 日の頻度]**:**[!UICONTROL 毎日送信]**、**[!UICONTROL 平日ごとに送信]**、または **[!UICONTROL カスタム頻度]** を選択します。<br/> 「カスタム頻度 **[!UICONTROL を選択した場合は、]** 日数ごとに送信 **[!UICONTROL の値を入力し]** す。 |
   | **[!UICONTROL 毎週送信]** | **[!UICONTROL 週数ごとに送信]** の値を入力します。 **[!UICONTROL 曜日]** を選択します。 |
   | **[!UICONTROL 毎月曜日に送信]** | **[!UICONTROL 曜日]** と **[!UICONTROL 週]** を選択します。 |
   | **[!UICONTROL 毎月日ごとに送信]** | **[!UICONTROL その月のこの日に送信]** から値を選択します。 |
   | **[!UICONTROL 毎年、その月の日ごとに送信]** | 「**[!UICONTROL 曜日]**」を選択し、「**[!UICONTROL 週]**」を選択して、「**[!UICONTROL 月]**」を選択します。 |
   | **[!UICONTROL 特定の日付で毎年送信]** | **[!UICONTROL 月]** を選択し、**[!UICONTROL その月のこの日に送信]** から値を選択します。 |

### 送信

ワークブックを送信するには：

* **[!UICONTROL スケジュールオプションを表示]** を使用してスケジュールを定義していない場合は、「**[!UICONTROL 今すぐ送信]**」を選択して、ワークブックを直ちにメールで送信します。
* **[!UICONTROL スケジュールオプションを表示]** を使用してスケジュールを定義した場合は、「**[!UICONTROL スケジュールに従って送信]**」を選択して、定義したスケジュールを使用してメールでワークブックを送信します。

どちらの場合も、Report Builder ハブの下部に確認トーストが表示されます。

ワークブックの送信をキャンセルするには、「**[!UICONTROL キャンセル]**」を選択します。

## スケジュールされたワークブックの管理

既にスケジュールされたワークブックの管理について詳しくは、「[&#x200B; スケジュールされたワークブックの管理 &#x200B;](/help/report-builder/manage-schedules-reportbuilder.md)」を参照してください。

