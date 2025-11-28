---
lab:
  title: '1.3:提案されたプロンプトを追加する'
---

# 提案されたプロンプトを追加する

この演習では、前の演習で作成した宣言型エージェントを更新して 6 つの適切なおすすめプロンプトを追加します。

この演習の所要時間は約 **10** 分です。

## 提案されるプロンプトを定義する

Copilot Studio で以下を行います。

1. **Product support** エージェントの **[概要]** ページに移動します。
1. 会話型エージェント作成ウィザードで、作成時にエージェントに対して推奨されるプロンプトが生成されたことに注目してください。 エージェントの機能に基づいて、これらを、より適切なプロンプトに置き換えてみましょう。
1. **[おすすめプロンプト]** セクションで、**[編集]** アイコンを選択します。
1. 既存のプロンプトを以下に置き換えます。

      `Eagle Air` : `Tell me about Eagle Air`

      `Return policy` : `What is the returns policy`              

      `Product information` : `Can you provide information on a specific product?` 

      `Product troubleshooting` : `I'm having trouble with a product. Can you help me troubleshoot the issue?` 

      `Repair information ` : `Can you provide information on how to get a product repaired?`
      
      `Contact support` : `How can I contact support for help?`

1. **[保存]** を選択して変更を保存します。 

## エージェントを再公開する

更新したエージェントを Microsoft 365 Copilot に公開しましょう。

1. エージェントの変更が正常に保存されたら、Copilot Studio のエージェントの概要ページの右上にある **[公開]** を選択します。
1. 開いたモーダル ウィンドウで、**[公開]** を選択します。
1. 開いた **[可用性オプション]** ウィンドウで、**[共有リンク]** 見出しの下にある **[コピー]** を選択します。
    ![[可用性オプション] ウィンドウのスクリーンショット。](../Media/availability-options-share-link.png)
1. Web ブラウザーの別のタブで、エージェントの共有リンクを**貼り付け**て **Enter** キーを押します。 **Product support** エージェントについて説明するウィンドウが表示されます。
1. エージェントの名前の下にある **[今すぐ更新]** を選択して、Product support エージェントの変更点を公開します。 エージェントが更新されるまで、しばらく待ちます。
1. 更新が完了したら、モーダル ウィンドウを閉じます。 ブラウザーで Microsoft 365 Copilot に移動しない場合は、左側のメニューまたは Microsoft 365 ポータルの **[アプリ]** メニューから **[Copilot]** を選択します。

## エージェントを Microsoft 365 Copilot でテストする

1. **Microsoft 365 Copilot** のサイド パネルのエージェントの一覧で **Product Support** を見つけ、それを選択し、イマーシブ エクスペリエンスを入力して、エージェントと直接チャットします。 Copilot Studio で定義したおすすめプロンプトがユーザー インターフェイスに表示されることに注目してください。

    ![Product support エージェントのスターター プロンプトを示す、Microsoft Edge の Microsoft 365 Copilot のスクリーンショット。](../Media/product-support-starter-prompts.png)
1. おすすめプロンプトを**選択**し、メッセージを**送信**して、応答を確認します。
