---
lab:
  title: '2.1: プロンプト アクションを作成する'
---

# プロンプト アクションを作成する

この演習では、プロンプト アクションを作成し、Copilot Studio でプロンプトをテストし、Copilot エージェント内でプロンプトをテストします。 ユーザーが生のアイデアを、特定の形式とガイドラインに従う整理されたマーケティング ピッチに変えるのに役立つプロンプト アクションを作成します。

この演習の所要時間は約 **15** 分です。

## Copilot Studio でカスタム プロンプトを作成する

1. Web ブラウザーで [Copilot Studio](https://copilotstudio.microsoft.com) (`https://copilotstudio.microsoft.com`) に移動して、Copilot Studio を開きます。
1. 左側のナビゲーションから **[ツール]** を選択します。
1. **[+ 新しいツール]** を選択します。
1. [新しいツール] ポップアップ ウィンドウで、**[プロンプト]** を選択します。 プロンプト ビルダー UI に移動します。 Copilot はこのウィンドウ内で使用できますが、この演習ではプロンプトを手動で定義します。
1. ウィンドウの上部にあるテキスト ボックスで、自動生成された名前を選択し、名前 **Marketing Pitch Prompt** に置き換えます。
1. **[指示]** テキスト ボックスに「`Create a marketing pitch for a product based on a `」と入力します。
1. 入力した文の末尾にカーソルを置いて、**[コンテンツの追加]** を選択します。
1. **[テキスト]** を選択します。
1. **[名前]** フィールドに「`Draft`」と入力します。
1.  **[サンプル データ]** フィールドに「`The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.`」と入力して、**[閉じる]** を選択します。

    !["Draft" という名前で構成されている入力変数を示す、Copilot Studio のプロンプト ビルダー UI のスクリーンショット。](../Media/prompt-content-sample-data.png)

## プロンプトをテストし改善する

1. 指示ボックスの上にある **[テスト]** を選択して、指定したサンプル データでプロンプトをテストします。
1. **[モデル応答]** セクションでテストの実行の出力を表示します。

より構造化された一貫性のある出力を作成するようにプロンプトを改善しましょう。

1. **[指示]** テキストボックスで、既存の指示に以下を追加してプロンプトを変更します。

    ```The pitch should follow the following Contoso guidelines:
       - Start with a brief hook
       - Describe unique value proposition
       - End with a call-to-action
       - Use an exciting and influential tone
    ```

1. もう一度 **[テスト]** を選択して、プロンプトを再テストします。
1. 応答の違いに注目してください。
    ![洗練されたプロンプトをテストした後のカスタム プロンプト UI のスクリーンショット。](../Media/test-prompt-refined.png)
1. **[保存]** を選択してプロンプトを保存します。

## (省略可能) エージェントにプロンプト アクションを追加する

前のラボを完了し、宣言型エージェントを作成した場合は、このアクションをエージェントに追加し、アクションを参照するようにエージェントの指示を更新することができます。

### プロンプト ツールを追加する

1. Copilot Studio のサイドバーから **[エージェント]** を選択します。
1. **[Microsoft 365 Copilot]** を選択します。
1. **[エージェント]** の下にある、アクションを追加する **Product Support** エージェントを選択します。
1. ページの **[ツール]** セクションから **[ツールの追加]** を選択します。
1. **[プロンプト]** フィルターを選択します。
1. **マーケティング ピッチ プロンプト** ツールを選択します。
    ![マーケティング ピッチ プロンプト ツールが一覧表示されている [ツールの追加] ウィンドウのスクリーンショット。](../Media/add-marketing-pitch-tool.png)
1. **[アプリの追加および構成]** を選択し、ツールが追加されるまで待ちます。 このツールは、Product Support エージェントの **[ツール]** に表示されるようになります。
    ![Product Support エージェントの [ツール] セクションのスクリーンショット。マーケティング ピッチ プロンプト ツールが一覧表示されています。](../Media/agent-updated-tools.png)

### エージェントの指示とスターター プロンプトを更新する

エージェントの指示を更新して、プロンプトの使用に関するガイダンスを指定します。

1. **[指示]** テキスト ボックスで、既存の指示テキストに以下を追加し、変更を**保存**します: `Use the Marketing Pitch Prompt tool to craft pitches for products that follow Contoso guidelines based on users' draft ideas.`。
1. **[おすすめプロンプト]** セクションで、Eagle Air のおすすめプロンプトを次のおすすめプロンプトに置き換え、変更を**保存**します: `Marketing Pitch` : `Create a marketing pitch following Contoso guidelines based on the following draft:`。

演習が完了し、エージェントのプロンプト ツールが作成されました。
