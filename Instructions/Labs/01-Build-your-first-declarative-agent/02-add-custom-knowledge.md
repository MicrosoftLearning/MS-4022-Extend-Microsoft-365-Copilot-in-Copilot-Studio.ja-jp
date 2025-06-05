---
lab:
  title: '1.2: カスタム ナレッジを追加する'
---

# カスタム ナレッジを追加する

この演習では、前の演習で作成した宣言型エージェントを更新してカスタム指示とグラウンディング データを追加します。 この演習では、サンプル製品ファイルを格納した "Products" という名前のドキュメント ライブラリを含む SharePoint サイトがあることを前提としています。

この演習の所要時間は約 **20** 分です。

## 開始する前に

この演習を開始する前に、宣言型エージェントがグラウンディング データとして使用する製品関連ドキュメントを Microsoft 365 にアップロードする必要があります。 以下の手順を完了して、演習の準備をします。

> [!NOTE]
> ドキュメントを新しい SharePoint Online サイトにアップロードすると、ドキュメントのインデックスが作成され、Copilot で使用できるようになるまでに遅延が発生します。 エージェントをすぐにテストする場合は、ドキュメントを**既存**のサイトにアップロードします。 ドキュメントがインデックス付けされ、エージェントで遅延なく使用できるようになります。 新しい SharePoint Online サイトを使用することを選ぶ場合は、ドキュメントがインデックス付けされ Copilot で使用できるようになるまでの時間が長くなる可能性があります。
>
> **以下の手順では、ドキュメントを新しいサイトにアップロードする方法について説明します**。 既存のサイトを使用する場合は、**サンプル データのアップロード**というラベルの付いたセクションから始めて、**Products** ライブラリの代わりに既存のライブラリを使用します。

### サンプル データのダウンロード

1. Web ブラウザーで、コースの [GitHub リポジトリ](https://github.com/MicrosoftLearning/MS-4022-Extend-Microsoft-365-Copilot-in-Copilot-Studio/blob/master/Allfiles/Products.zip)に移動します。
1. **生ファイルのダウンロード** ボタンを選択して、**Products.zip** をダウンロードします。

    :::image type="content" source="../media/download-github.png" alt-text="GitHub の生ファイル ダウンロード ボタンが強調表示されている Microsoft Edge のスクリーンショット。":::

1. ダウンロードしたフォルダーを**開き**、後でアクセスできる `Products` という名前の、コンピューター上の新しいフォルダーに**すべてのコンテンツを展開**します。

### SharePoint サイトの作成

1. Web ブラウザーで、[https://www.microsoft365.com](https://www.microsoft365.com) に移動し、このラボに使用している Microsoft 365 アカウントで**サインイン**します。
1. 左側のメニューで **[アプリ]** (グリッド アイコン) を選択し、アプリのカタログから **SharePoint** を選びます。
1. 左側のメニューから **[作成]** (プラス アイコン) を選択し、**[サイト]** を選択します。
1. サイトの種類として **[チーム サイト]** を選択します。
1. **[テンプレートの選択]** ページで、**[Standard team]** を選択します。
1. **[プレビュー]** ページで **[テンプレートを使用]** を選択します。
1. **[サイトに名前を付ける]** ページで、「`Product support`」と入力したあと **[次へ]** を選択します。
1. 次の構成ページで、**[プライバシーの設定]** を **[パブリック]** に変更します。
1. **サイトの作成**を選択します。 **[完了]** ボタンがアクティブになるまでに、サイトの作成にしばらく時間がかかる場合があります。
1. **[完了]** を選びます。

### ドキュメント ライブラリを作成する

1. **Product support** SharePoint サイトで、ページの上部にある **[新規]** ボタンを選択し、**[ドキュメント ライブラリ]** を選択します。
1. **[新しいドキュメント ライブラリの作成]** ページで、**[空のライブラリ]** を選択します。
1. **[名前]** フィールドに「`Products`」と入力し、**[作成]** を選択します。

### サンプル データのアップロード

1. **Products** ライブラリから **[アップロード]** ボタンを選択し、**[ファイル]** を選択します。
1. 前の手順でサンプル ファイルを保存した、コンピューター上のフォルダーに移動します。
1. ローカルの Products フォルダー内のファイルを **[すべて選択]** し、**[開く]** を選択して SharePoint にアップロードします。
1. アップロードが完了するまで待ちます。 これで、ファイルが SharePoint の **Products** ライブラリに表示されます。

### SharePoint の URL をコピーする

次に、エージェントのナレッジを構成する際に使用する直接 URL をサイトにコピーします。

1. SharePoint の **[Products]** ライブラリ ページで、右上にある **[設定]** アイコンを選択し、**[ライブラリの設定]**、**[その他のライブラリ設定]** の順に選択します。

    :::image type="content" source="../media/sharepoint-library-settings.png" alt-text="[設定] メニューのライブラリ設定オプションを示す Microsoft Edge のスクリーンショット。":::

1. **[Web アドレス]** プロパティを見つけます。 **SharePoint サイトの URL** は、Web アドレスの `https://DOMAIN.sharepoint.com/sites/SITE_NAME/LIBRARY_NAME` 形式の部分です。 URL は `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products` となっている必要があります。
1. SharePoint サイトの URL を**コピー**し保存して、今後のラボの手順で使用できるようにします。

## エージェントにカスタム ナレッジを追加する

SharePoint URL を、典拠となるナレッジ ソースとしてエージェントに追加します。

### SharePoint URL を追加する

1. Copilot Studio の Product Support エージェントの概要ページで、**[ナレッジ]** セクションの **[ナレッジの追加]** を選択します。

    ![Microsoft Edge で開いた Copilot Studio のスクリーンショット。Product support エージェントの [ナレッジの追加] ボタンが強調表示されています。](../Media/product-support-add-knowledge.png)

2. 開いたウィザードの **[ナレッジの追加]** ページで、**[SharePoint]** を選択します。
3. テキスト ボックスに **Products** SharePoint ライブラリの URL を貼り付け、**[追加]** を選択します。 これは `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products` という形式になります。

4. **[SharePoint の追加]** ウィンドウで **[追加]** を選択し、ナレッジ ソースがエージェントに追加されるまで待ちます。 この処理には 1 ～ 2 分かかる可能性があります。
5. **Products** ライブラリがエージェントの概要情報の **[ナレッジ]** セクションに表示されていることに注目してください。

> **注**: Copilot Studio エージェントが、ユーザーの代わりにドキュメントにアクセスします。 エージェントは、エンド ユーザーがアクセスできるドキュメントからの回答とコンテンツのみを取得できます。

### カスタム指示を更新する

次に、エージェントの指示を更新して、エージェントがナレッジ ソースをどのように使用すべきかを説明します。

1. Copilot Studio のエージェントの概要ページで、**[詳細]** セクション内の **[編集]** を選択します。
1. **[指示]** テキスト ボックスの内容を次のように更新します。`You are an agent tasked with answering questions about Contoso Electronics products. Start every response by enthusiastically thanking the user for their question or comment, then respond to their question or comment. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.`
1. **[詳細]** セクションで **[保存]** を選択します。

## エージェントを Copilot Studio でテストする

最後に、カスタム ナレッジ ソースを使用するエージェントの機能をテストします。

1. Copilot Studio でエージェントの概要ページの **[エージェントのテスト]** ウィンドウから、**[更新]** ボタンを選択してテスト ウィンドウを最新の情報に更新し、エージェントの最新の変更点を読み込みます。
1. テスト会話のテキスト ボックスに「`Tell me about Eagle Air`」と入力し、メッセージを送信します。
1. 応答を待ちます。 応答に Eagle Air ドローンに関する情報が含まれていることに注目してください。 応答には、SharePoint に保存されている Eagle Air ドキュメントの引用と参照が含まれています。

いくつかのプロンプトを試してみましょう。

1. メッセージ ボックスに「`Recommend a product suitable for a farmer`」と入力し、メッセージを送信します。
1. 応答を待ちます。 応答には、Eagle Air に関する情報と、Eagle Air が推奨される理由に関する追加のコンテキストが含まれていることに注目してください。 応答には、OneDrive に保存されている Eagle Air ドキュメントの引用と参照が含まれています。
1. メッセージ ボックスに「`Explain why the Eagle Air is more suitable than Contoso Quad`」と入力し、メッセージを送信します。
1. 応答を待ちます。 応答では、 Contoso Quad よりも Eagle Air の方が農家による使用により適している理由が詳しく説明されていることに注目してください。

最後に、エージェントが回答できない質問をして、フォールバック応答をテストしましょう。

1. メッセージ ボックスに「`When was Mark8 released?`」と入力し、メッセージを送信します。
1. 応答を待ちます。 応答は、指示で定義されているとおりに、さらなる支援の提供を担当するチームにエージェントが連絡することを提案していることに注目してください。
