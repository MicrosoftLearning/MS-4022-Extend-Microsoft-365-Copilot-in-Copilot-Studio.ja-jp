---
lab:
  title: Copilot Studio のラボのセットアップ
  description: この演習では、Microsoft Copilot Studio ポータルにアクセスし、残りのラボ全体で使用する環境を作成します。
  duration: 10 minutes
  level: 200
  islab: true
  primarytopics:
    - Microsoft 365
    - Microsoft Copilot Studio
---

# Power Platform 環境を作成する

## Power Platform 管理センター

ラボの演習を開始する前に、作業を行う開発環境を作成する必要があります。

1. Web ブラウザーを開き、`https://admin.powerplatform.microsoft.com/manage/environments` に移動し、この演習の資格情報を使用してサインインします。

1. メッセージが表示されたら、サインインしたままにするオプションを選びます。

1. 表示されているポップアップ メッセージをすべて閉じます。

### Dataverse を既定の環境に追加する

1. **Contoso (既定)** 環境の省略記号 (**...**) を選択し、**[Dataverse の追加]** を選びます。

   ![Power Platform 管理センターで既定の環境に Dataverse を追加します。](../media/add-dataverse.png)

1. 既定の設定をすべてそのままにして、**[追加]** を選択します。

### 新規環境の作成

1. **[環境]** ページで、**[+ 新規]** を選択して、次の設定で新しい環境を作成します。

   - **種類**: 開発者
   - **地域**: 既定の地域
   - **名前**: *自分の名前*
   - **環境グループ**: なし
   - **これをマネージド環境にする**: いいえ
   - **新機能を早期に取得する**: いいえ
   - **代理での作成**: いいえ

   ![Power Platform 管理センターで環境を作成します。](../media/create-environment.png)

1. **[次へ]** を選択し、**[Dataverse の追加]** セクションで次のようにします。

   - **言語**: 英語 (米国)
   - **通貨**: USD ($)
   - **サンプル アプリおよびデータの展開**: いいえ

1. **[保存]** を選択し、環境の状態が **[準備完了]** になるまで待ちます (**[更新]** ボタンを使用してディスプレイを更新できます)。

   > [!NOTE]
   > テナントの構成によっては、環境のプロビジョニングに数分かかる場合があります。

   ![Power Platform 管理センターで環境が作成されました。](../media/environment-created.png)

1. 新しいブラウザー タブで、`https://copilotstudio.microsoft.com/` に移動し、メッセージが表示されたらサインインします。

   > [!NOTE]
   > Copilot Studio にアクセスする際に問題が発生した場合は、Power Platform 管理センターで新しく作成した環境の環境 ID をコピーし、URL `https://copilotstudio.microsoft.com/environments/<environment-id>` に貼り付けます。 `<environment-id>` を、コピーした環境 ID に置き換えます。

1. メッセージが表示されたら、**[開始する]** を選択し、既定の国または地域の設定はそのままにしておきます。

1. ウェルカム メッセージはスキップします。

1. ページの右上隅で、環境セレクターを使用して環境を切り替え、作成した環境を選択します。

   ![Copilot Studio で環境を選択します。](../media/select-environment.png)

これで、作業を行う Power Platform 環境が作成されました。
