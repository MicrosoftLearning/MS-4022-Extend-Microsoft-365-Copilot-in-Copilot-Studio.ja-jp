---
lab:
  title: 1.1 宣言型エージェントを作成する
  description: この演習では、生成 AI を使用して宣言型エージェントを作成し、指示を改善し、エージェントを Microsoft 365 に公開し、Microsoft 365 Copilot でエージェントをテストします。
  duration: 20 minutes
  level: 200
  islab: true
  primarytopics:
    - Microsoft 365
    - Microsoft 365 Copilot
---

# 宣言型エージェントを作成する

この演習では、生成 AI を使用して宣言型エージェントを作成し、指示を改善し、エージェントを Microsoft 365 に公開し、Microsoft 365 Copilot でエージェントをテストします。

この演習の所要時間は約 **20** 分です。

## 生成 AI を使用して宣言型エージェントを作成する

まず、Copilot Studio で新しい宣言型エージェントを作成します。 生成 AI を使用して、エージェントの指示とプロパティを下書きします。

1. Web ブラウザーで、[Microsoft Copilot Studio](https://copilotstudio.microsoft.com/) (`https://copilotstudio.microsoft.com`) に移動します。
1. Copilot Studio で作成するアクセス許可がある職場または学校アカウントを使用して、サインインします。
1. **[Microsoft Copilot Studio へようこそ]** ページにメッセージが表示されたら、国/地域を選択してから **[使用開始]** を選択します。
1. **[Copilot Studio へようこそ]** ポップアップが表示された場合は、 **[スキップ]** を選択します。
1. Copilot Studio にアクセスすると、新しいエージェントを作成するためのホーム ページから始めることが多くなります。

    ![カスタム エージェントを作成するための対話的インターフェイスのスクリーンショット。](../Media/copilot-start-screen.png)

1. 左側のナビゲーション パネルで **[エージェント]** に移動します。
1. エージェント ページから **[Microsoft 365 Copilot]** を選択します。
1. **[Microsoft 365 Copilot エージェント]** ページで、[エージェント] セクション内の **[追加]** を選択します。

    ![Copilot Studio の [Microsoft 365 Copilot エージェント] ページのスクリーンショット。](../Media/add-copilot-agent.png)

    エージェントの作成ページに移動します。ここで、ビルドするエージェントの詳細を定義できます。


## エージェントを構成し指示を定義する

次に、エージェントのプロパティとメタデータを手動で構成して、この演習で一貫性のある結果が得られるようにします。

1. **[名前]** フィールドに「`Product support`」と入力します。
1. **description** プロパティに「`A product support agent that can answer queries about Contoso Electronics products`」と入力します。
1. **[指示]** テキスト ボックスに、次のように入力します。
  
    ```md
        - You are an agent tasked with answering questions about Contoso Electronics products.
        - Start every response to the user with "Thanks for using a Copilot agent!\n\n" and then answer the questions and help the user.
        - Do not answer questions unrelated to Contoso Electronics products.
        - Maintain a helpful and approachable tone throughout interactions.
    ```

1. 提案されたプロンプトが、生成 AI を使用して生成されていることに注意してください。 これらのプロンプトは、今後の演習で更新します。
1. ページの上部にある **[作成]** を選択して、エージェントを作成します。  しばらくすると、エージェントの概要ページが表示されます。

## Copilot Studio でエージェントをテストする

次に、Microsoft 365 Copilot に公開する前に、Copilot Studio 内のテスト ウィンドウでエージェントの動作をテストします。

1. **Product support** エージェントの概要ページの **[公開の詳細]** セクションで、エージェントがまだ公開されていないことに注意してください。

    ![公開前の Product support エージェント ページのスクリーンショット。](../Media/product-support-publish-details.png)

1. エージェントの概要情報の右側に **[エージェントのテスト]** ウィンドウが表示されない場合は、[公開] ボタンの横にある **[テスト]** ボタンを選択して、テスト ウィンドウを開きます。
1. テスト ペイン内のテキスト ボックスに「`What can you do?`」と入力し、メッセージを送信します。
1. 応答を待ちます。 応答が "Copilot エージェントをご利用いただき、ありがとうございます。" というテキストで始まることに注目してください。 これは、前に定義したエージェントへの指示どおりです。

    ![テスト ウィンドウでの Product support エージェントとの会話のスクリーンショット。](../Media/product-support-test-pane-1.png)

    また、現在、エージェントには指示はありますが、カスタム ナレッジ ソースやアクションはまだないことに注意してください。 Contoso 製品に関する質問に正確に回答できるようにエージェントをまだ構成していません。 これは次の演習で行います。

> [!NOTE]
> エージェントを編集する必要がある場合は、エージェントの概要ページの **[詳細]** セクションで **[編集]** を選択します。 変更を保存。 もう一度テストする前に、テスト ペイン内の **[新しいテスト セッションの開始]** ボタンを選択します。

## エージェントを Microsoft 365 Copilot に公開する

次に、エージェントを Microsoft 365 Copilot に公開します。 **Product support** エージェントの概要ページから、以下を行います。

1. **[発行]** ボタンを選びます。 Microsoft 365 Copilot および Microsoft Teams のユーザーに表示されるエージェントの情報を入力するように求められます。

> [!NOTE]
> このフォームの情報は、組織の Office および Teams カタログのカタログ エントリと Microsoft 管理センターの統合アプリ一覧に入力するために使用されます。 エージェントを呼び出すために Microsoft 365 Copilot の言語モデルで使用されるわけではありません。

1. **[短い説明]** テキスト ボックスに「`Answers questions about Contoso Electronics products`」と入力し、自動生成されたコンテンツを置き換えます。
1. 残りのフィールドには、既定の提案をそのまま使用します。
1. **公開**を選択します。
    ![[公開] ボタンを選択する前の [エージェントの公開] ウィンドウのスクリーンショット。](../Media/publish-window.png)
1. エージェントが公開されるまで待ちます。  公開中にモーダル ウィンドウを閉じないでください。 これには数分かかることがあります。

> [!NOTE]
> [公開] を選択すると、エージェントに対応するボット リソースがテナントの Microsoft Entra ID 環境にプロビジョニングされます。 このリソースを使用すると、Microsoft Teams でエージェントとやり取りできます。

1. エージェントが公開されると、**[可用性オプション]** ウィンドウが表示されます。
1. **[共有リンク]** で **[コピー]** を選択してエージェントの共有リンクをコピーしたあと、**[完了]** を選択します。
    ![[コピー] ボタンが強調表示されている [可用性オプション] ウィンドウのスクリーンショット。](../Media/share-link-copy.png)
1. エージェントが公開されたことがエージェントの概要ページの **[公開の詳細]** セクションに表示されていることに注目してください。

    ![Copilot Studio での Product support エージェントの [公開の詳細] セクションのスクリーンショット。](../Media/publish-details.png)

    共有リンクをもう一度コピーする必要がある場合は、**[公開の詳細]** セクションで **[可用性オプション]** を選択します。

1. Web ブラウザーで新しいタブを開き、共有リンクを URL バーに貼り付けて、**Enter** キーを押します。 モーダル ウィンドウが開いて、エージェントの概要が表示されます。 ここには、公開時に提供した、エージェントに関するユーザー向けの情報と、エージェントに必要なアクセス許可が表示されます。

    ![Microsoft 365 Copilot に追加される前に Product support エージェントの概要情報を提供するモーダル ウィンドウのスクリーンショット。](../Media/product-support-add-agent.png)

1. **[追加]** を選択して、エージェントを Microsoft 365 Copilot に追加します。
1. エージェントが追加されるまで待ちます。 エージェントは Microsoft 365 Copilot で起動されます。

## エージェントを Microsoft 365 Copilot でテストする

次に、エージェントを Microsoft 365 Copilot でテストし、その機能を**イマーシブ** エクスペリエンスと**コンテキスト内**エクスペリエンスの両方で検証しましょう。

前の手順に従って、現在、**イマーシブ** エージェント エクスペリエンスを使用しています。 チャット インターフェイスの横にある **[エージェント]** セクションで、現在直接チャットしているエージェントとして **Product Support** が選択されていることに注意してください。

![Microsoft 365 Copilot での Product support エージェントとのイマーシブ エクスペリエンスのスクリーンショット。](../Media/product-support-immersive.png)

1. テキスト ボックスに「`What can you do?`」と入力し、メッセージを送信します。
1. メッセージを送信し、応答を待ちます。 応答が "Copilot エージェントをご利用いただき、ありがとうございます。" というテキストで始まることに注目してください。 これは、エージェントへの指示で指定したガイダンスに従っています。

ブラウザーで続けて、**コンテキスト内**エクスペリエンスをテストしてみましょう。

1. サイド バーの **[エージェント]** ペインの上にある **[新しいチャット]** を選択し、**Product Support** エージェントとのイマーシブ チャットを終了し、Microsoft 365 Copilot との新しい会話を開始します。

    ![Microsoft 365 Copilot のサイドバーにある [Copilot] ボタンのスクリーンショット。](../Media/select-copilot.png)

1. メッセージ ボックスに、<kbd>@</kbd> 記号を入力します。 使用可能なエージェントの一覧を示すポップアップが表示されます。

    ![Microsoft 365 Copilot のエージェント ポップアップを示す Microsoft Edge のスクリーンショット。](../Media/copilot-agents-flyout.png)

1. ポップアップで **[Product Support]** を選択します。 メッセージ ボックスの上にあるステータス メッセージに注目してください。 **[Product Support とチャット中]** と表示されます。 これで、Copilot との会話内で Product Support エージェントと**コンテキストを踏まえて**チャットしています。つまり、エージェントは Copilot との会話のコンテキストを考慮できます。

    ![Microsoft 365 Copilot を示す Microsoft Edge のスクリーンショット。 ステータス メッセージ 'Chatting with Product support' が強調表示されています。](../Media/product-support-in-context.png)

1. テキスト ボックスに「`What can you do?`」と入力し、メッセージを送信します。

1. 応答を待ちます。 応答が "質問をありがとうございます。" というテキストで始まることに注目してください。 これは、エージェントへの指示で指定したガイダンスに従っています。

1. コンテキスト内エクスペリエンスを終了するには、ステータス メッセージでバツ印 (X) を選択します。 ステータス メッセージが削除され、Product Support エージェントとのチャットが終了したことを示すメッセージがチャット ウィンドウに表示されていることに注意してください。 Copilot と直接会話を続けられます。

    ![Microsoft 365 Copilot を示す Microsoft Edge のスクリーンショット。 エージェント ステータスメッセージのクロス アイコンが強調表示されています。](../Media/exit-in-context-experience.png)

これで、Microsoft 365 Copilot のイマーシブ エクスペリエンスとコンテキスト内エクスペリエンスの両方でエージェントをテストしました。
