---
description: Analysis Workspaceでプロジェクトにコメントする方法を学ぶ
title: プロジェクトへのコメントの追加と管理
feature: Workspace Basics
role: User
exl-id: 05f69a1c-31c2-40d8-ae8b-a084169897b1
source-git-commit: 518bebc18611136873fce5c23dd7041afafe1220
workflow-type: tm+mt
source-wordcount: '1857'
ht-degree: 1%

---

# プロジェクトへのコメントの追加と管理 {#comment-on-projects}

Analysis Workspaceのコメントを使用すると、Analysis Workspace プロジェクトのコンテキスト内でインサイトを共有し、質問することができます。 これにより、データに関する議論を効率化して、議論の対象となっているデータのコンテキスト内に会話を維持できます。

>[!NOTE]
>
>プロジェクトのコメントを追加および管理する機能は、プロジェクトレベルまたは組織レベルで無効にすることができます。 この節で説明するように、コメントを追加および管理できない場合、Customer Journey Analytics管理者またはプロジェクト所有者がこの機能を無効にしています。
>
>* **プロジェクト：** プロジェクト所有者は、「プロジェクトの作成 [&#x200B; で説明しているように、プロジェクトのこの機能を無効にすることができ &#x200B;](/help/analysis-workspace/build-workspace-project/create-projects.md) す。
>* **組織：** Customer Journey Analytics管理者は、[&#x200B; 環境設定 &#x200B;](/help/analysis-workspace/user-preferences.md) に記載されているように、組織に対してこの機能を無効にすることができます。

## コメントを表示

コメントは、右側のパネルのコメント領域、またはコメントバッジ（存在する場合）から表示できます。

>[!NOTE]
>
>右側のパネルにコメント領域が表示される前に、プロジェクトを保存する必要があります。 プロジェクトがまだ保存されていない場合は、コメントを追加する前に [&#x200B; プロジェクトを保存 &#x200B;](/help/analysis-workspace/build-workspace-project/save-projects.md) する必要があります。


![Analysis Workspaceでのコメントの表示 &#x200B;](assets/workspace-comments-view.png)

### コメント領域でコメントを表示する

Analysis Workspace プロジェクトで作成されたすべてのコメントは、右側のパネルのコメント領域に表示されます。 既存のコメントの合計数は、コメントアイコンに表示されます。

1. デフォルトでは、プロジェクトを初めて開いたときに、Analysis Workspaceのプロジェクトごとにコメント領域が展開されます。

   プロジェクトの右側のパネルにあるコメント領域アイコンを選択して、コメント領域を開いたり閉じたりします。

   ![&#x200B; コメント領域が閉じられました &#x200B;](assets/comments-area-closed.png)

   各コメントには、コメントが投稿された日のタイムスタンプが表示されます。 コメントが当日に投稿された場合は、時間帯が表示されます。 コメントが投稿された日時の全体を表示するために、その日または時間にマウスを移動します。

1. （オプション）コメント領域を検索するには、検索アイコン ![&#x200B; 検索アイコン &#x200B;](assets/comments-search-icon.png) を選択し、単語または語句を入力します。 コメント エリアは、その単語または語句を含むコメントのみを含むようにフィルタリングされます。

### プロジェクト内のコメントバッジの表示

[&#x200B; プロジェクトの特定の領域で &#x200B;](#comment-on-a-specific-area-of-the-project) 行われたコメントには、コメントが関連するプロジェクトの領域に **コメントバッジ** ![&#x200B; コメントバッジ &#x200B;](assets/comment-indicator.svg) が表示されます。 バッジを選択してコメントを表示します。 バッジを選択したら、コメント自体を選択して、右側のパネルのコメント領域でコメントをハイライト表示できます。

数値は、プロジェクトの各バッジに表示され、作成順に並べられます。 プロジェクトの同じエリアに複数のコメントが配置されている場合、バッジに 3 つのドットが表示されます ![&#x200B; コメントバッジが複数 &#x200B;](assets/comment-indicator-multiple.svg)。 3 ドットバッジを選択すると、その領域のすべてのコメントが表示されます。

<!-- Insert screeshot-->

プロジェクトのすべてのコメントバッジを非表示にするには：

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。

1. コメントエリアの下部で、「**[!UICONTROL 配置されたバッジを非表示にする]** オプションを有効にします。

## コメントを追加

プロジェクトの特定の領域を参照するコメントを追加するか、一般的なコメントを追加できます。

### プロジェクトの特定の領域に関するコメント

プロジェクトの特定の領域（フリーフォームテーブルの指標値など）にコメントするには：

1. プロジェクトをAnalysis Workspaceで開いた状態で、コメントを挿入するプロジェクトの領域を右クリックします。

   すべてのビジュアライゼーションで、ビジュアライゼーションヘッダーのコメントバッジをサポートしていますが、ビジュアライゼーション内の特定のデータポイントのコメントバッジをサポートしているのは、次のビジュアライゼーションのみです。

   * フリーフォームテーブル
   * コホートテーブル
   * 行

   <!--add screenshot-->

1. **[!UICONTROL コメントを追加]** を選択します。

1. 「**[!UICONTROL 新しいコメント]**」フィールドにコメントを指定します。

   コメントは最大 15,000 文字で、基本的なマークアップ、ハイパーリンク、箇条書きと番号付きのリスト、絵文字を含めることができます。

1. （オプション） @記号の後に名前を入力して、コメントについて他のユーザーに通知します。 @記号を使用して他のユーザーに通知する方法については、[&#x200B; コメントに他のユーザーを含める &#x200B;](#include-others-in-a-comment) を参照してください。

1. 「**[!UICONTROL 送信]**」を選択します。

   **コメントバッジ**![&#x200B; コメントバッジ &#x200B;](assets/comment-indicator.png) は、[&#x200B; プロジェクト内のコメントバッジを表示 &#x200B;](#view-comment-badges-in-a-project) で説明されているように、コメントを追加したWorkspace プロジェクトの領域に配置されます。 コメントは、右側のパネルのコメント領域の上部にも表示されます。

### プロジェクトに関する一般的なコメントを追加します

Analysis Workspaceでプロジェクトにコメントを追加するには：

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。<!-- add screen shot -->

1. 「**[!UICONTROL 新しいコメント]**」フィールドにコメントを指定します。

   コメントは最大 15,000 文字で、基本的なマークアップ、ハイパーリンク、箇条書きと番号付きのリスト、絵文字を含めることができます。

1. （オプション） @記号の後に名前を入力して、コメントについて他のユーザーに通知します。 @記号を使用して他のユーザーに通知する方法については、[&#x200B; コメントに他のユーザーを含める &#x200B;](#include-others-in-a-comment) を参照してください。

1. 「**[!UICONTROL 送信]**」を選択します。

   コメントがコメント領域の上部に表示されます。詳細は [&#x200B; コメント領域のコメントの表示 &#x200B;](#view-comments-in-the-comments-area) を参照してください。

## コメントに他者を含める

Analysis Workspaceのコメント機能を使用すると、他のユーザーとの共同作業が容易になります。

@記号を使用してコメントに人物を含める場合は、次の点に注意してください。

* 含めるユーザーには、Adobe Experience Cloudの通知設定に基づく通知が届きます。

  詳しくは、「[&#x200B; コメントに関する通知を受信 &#x200B;](#receive-notifications-about-comments)」を参照してください。

* 組織内の任意のユーザーをコメントに含めることができますが、Customer Journey Analyticsへのアクセス権は自動的には付与されません。

コメントに他のユーザーを含めるには：

1. @記号を入力し、含める人の名、姓またはメールアドレスの入力を開始します。

   ![&#x200B; ユーザーをタグ付け &#x200B;](assets/comments-tag-user.png)

1. ドロップダウンメニューに表示されたら、人物の名前を選択します。

## コメントに返信する

1. Analysis Workspaceで、コメントを追加するプロジェクトを開きます。

1. Analysis Workspaceの右側のパネルにあるコメント領域アイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択し、返信するコメントの横にある **[!UICONTROL 返信]** を選択します。

   返信するコメントのテキストを含め、元のテキストを引用タグで囲むには、返信する特定のコメントまたは返信の横にある 3 ドットアイコンを選択し、「**[!UICONTROL 引用返信]**」を選択します。 引用返信は、コメントまたは返信が参照しているコメントを示すのに適した方法です。

   または

   コメントが作成されたパネルまたはビジュアライゼーションのコメントアイコンを選択し、「**[!UICONTROL 返信]**」を選択します。

1. 「**[!UICONTROL 新しいコメント]**」フィールドにコメントを指定します。

   コメントは最大 15,000 文字で、基本的なマークアップ、ハイパーリンク、箇条書きと番号付きのリスト、絵文字を含めることができます。

1. （オプション） @記号の後に名前を入力して、コメントについて他のユーザーに通知します。 @記号を使用して他のユーザーに通知する方法については、[&#x200B; コメントに他のユーザーを含める &#x200B;](#include-others-in-a-comment) を参照してください。

1. 「**[!UICONTROL 送信]**」を選択します。

## コメントに関する通知を受信

プロジェクト所有者および [&#x200B; メンションした特定のユーザー &#x200B;](#include-others-in-a-comment) は、Adobe Experience Cloud通知の設定に基づいて通知を受け取ります。 デフォルトでは、アプリ内通知が届き、Customer Journey Analyticsの [Experience Cloud通知 &#x200B;](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#view-notifications) アイコン ![Experience Cloud通知アイコンから確認 &#x200B;](assets/experience-cloud-notification.svg) きます。

さらに、ユーザーは [&#x200B; メール通知を購読 &#x200B;](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#subscribe-to-in-app-and-email-notifications) および [Experience Cloud通知を購読 &#x200B;](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#slack) して、メール通知およびSlack通知を受け取るようにSlack通知を設定できます。

## 既存のコメントにバッジを配置する

右側のパネルのコメント領域にコメントがあるが、プロジェクトにまだバッジがない場合、そのバッジを追加できます。

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。

1. バッジを配置するコメントの横にある詳細アイコン ![&#x200B; 詳細アイコン &#x200B;](/help/assets/icons/MoreSmallList.svg) を選択してから、「バッジを配置 **[!UICONTROL を選択します]**。

1. 既存のコメントのバッジを配置するプロジェクトの領域を選択します。

   **コメントバッジ**![&#x200B; コメントバッジ &#x200B;](assets/comment-indicator.png) は、選択したWorkspace プロジェクトの領域に配置されます。 コメントは、右側のパネルのコメント領域の上部にも表示されます。

   詳しくは、[&#x200B; プロジェクト内のコメントバッジを表示 &#x200B;](#view-comment-badges-in-a-project) を参照してください。

バッジを削除するには：

1. 削除するバッジを選択し、「**[!UICONTROL バッジを削除]**」を選択します。

   バッジは削除されますが、右側のパネルのコメント領域にはコメントを引き続き使用できます。

## 既存のコメントのバッジの移動

既存のコメントに既に配置されているコメントバッジを移動できます。

1. プロジェクトをAnalysis Workspaceで開いた状態で、移動するコメントのバッジを見つけます。

1. バッジを右クリックし、「**[!UICONTROL プレースメントを移動]**」を選択します。

1. バッジを配置するプロジェクトの領域を選択します。

<!-- add section about adding images to comments. will be available at GA. Include that "you can have a maximum of 5 images per comment, and each image can be up to 2 MB." -->

## コメントへのリンクのコピー

コメントへのリンクをコピーして、他のユーザーとリンクを共有できます。 プロジェクトへのアクセス権を既に持つユーザーのみが、リンクを使用してプロジェクトにアクセスできます。

コメントへのリンクをコピーするには：

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。

1. リンクをコピーするコメントの横にある詳細アイコン ![&#x200B; 詳細アイコン &#x200B;](/help/assets/icons/MoreSmallList.svg) を選択してから、「**[!UICONTROL リンクをコピー]** を選択します。

   リンクがシステムクリップボードにコピーされます。 メールやその他のタイプのメッセージにリンクを貼り付けることができます。

## コメントのテキストのコピー

コメントの本文をコピーして、他のユーザーと共有できます。

コメントの本文をコピーするには：

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。

1. コピーするテキストを含んだコメントの横にある詳細アイコン ![&#x200B; 詳細アイコン &#x200B;](/help/assets/icons/MoreSmallList.svg) を選択してから、「**[!UICONTROL 本文をコピー]** を選択します。

   コメントの本文がシステムのクリップボードにコピーされます。

## コメントに高評価を付ける

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。

1. 推奨するコメントの下の **[!UICONTROL いいね]** を選択します。

## コメントの削除

コメントを削除すると、元のコメントと返信または添付ファイルも削除されます。

削除されたコメントは復元できません。

コメントを削除するには：

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。

1. 削除するコメントの横にある「その他 ![&#x200B; アイコン &#x200B;](/help/assets/icons/MoreSmallList.svg) を選択してから、「**[!UICONTROL 削除]** を選択します。

1. もう一度 **[!UICONTROL 削除]** を選択して、削除を確認します。

## コメントの解決

コメントを解決すると、コメントは解決済みとしてマークされ、コメント領域には表示されません。 コメントにバッジが関連付けられている場合、そのバッジはプロジェクトから削除されます。

コメントを解決するには：

1. プロジェクトをAnalysis Workspaceで開いた状態で、Analysis Workspaceの右側のパネルにあるコメントエリアのアイコン ![&#x200B; コメント領域のアイコン &#x200B;](/help/assets/icons/Comment.svg) コメント領域のアイコン）を選択します。

1. 解決するコメントの横にある「その他 ![&#x200B; アイコン &#x200B;](/help/assets/icons/MoreSmallList.svg) を選択したあと、「**[!UICONTROL 解決]**」を選択します。

1. もう一度 **[!UICONTROL 解決]** を選択して確認します。

既定では、解決済みのコメントはコメント領域に表示されません。 解決済みコメントを表示するには、次の手順に従います。

1. コメント領域でフィルターアイコンを選択し、「**[!UICONTROL 解決済みのコメントを非表示にする]** オプションの選択を解除します。
