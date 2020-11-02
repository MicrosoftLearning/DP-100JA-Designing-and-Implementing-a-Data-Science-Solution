# ラボ 1B: Azure Machine Learning ツールの操作

このラボでは、Azure Machine Learning ワークスペースを操作するためのさまざまなツールについて説明します。

## 開始する前に

このラボを開始する前に、[前のラボ](Lab01A.md)の手順に従って Azure Machine Learning ワークスペースを作成しておく必要があります。

## タスク 1: コンピューティング インスタンスでの Azure ML SDK の使用

ほとんどのアセット管理タスクを実行して、*Studio* インターフェイスで環境をセットアップできますが、構成タスクをスクリプト化して、繰り返しと自動化を容易にすることも重要です。

1. [Azure Machine Learning Studio](https://ml.azure.com) のワークスペースの「**コンピューティング**」ページで、「**コンピューティング インスタンス**」タブを表示し、必要に応じて、前のラボで作成したコンピューティング インスタンスが開始されるまで定期的に「**最新の情報に更新**」をクリックします。
2. ブラウザーで Azure Machine Learning Studio の Web ページを更新して、認証セッションの有効期限が切れていないことを確認します。次に、コンピューティング インスタンスの**アプリケーション URI** 列にある **Jupyter** リンクをクリックして、新しいタブで Jupyter Notebook を開きます。メッセージが表示されたら、Azure サブスクリプションに関連付けられている Microsoft アカウントを使用してサインインします。
3. Notebook 環境で、右端の **New** をクリックして **Terminal** を選択し、新しい**ターミナル**を作成します。これにより、コマンド シェルを含む新しいタブが開きます。
4. Azure Machine Learning SDK はコンピューティング インスタンス イメージに既にインストールされていますが、このコースで必要なオプション パッケージを使用して、最新バージョンを確実に使用できます。次のコマンドを入力して SDK パッケージを更新します。

    ```bash
    pip install --upgrade azureml-sdk[notebooks,automl,explain]
    ```

    パッケージの依存関係がインストールされると、警告が表示されることがあります。これは無視してかまいません。

    > **詳細情報**: Azure ML SDK とそのオプション コンポーネントのインストールの詳細については、「[Azure ML SDK ドキュメント](https://docs.microsoft.com/python/api/overview/azure/ml/install?view=azure-ml-py)」を参照してください。

5. 次に、次のコマンドを実行して、現在のディレクトリを **Users** ディレクトリに変更し、このコースの演習で使用する Notebooks を取得します。

    ```bash
    cd Users
    git clone https://github.com/MicrosoftLearning/DP100
    ```

6. コマンドが完了したら、ターミナル タブを閉じ、Jupyter Notebook ファイル Explorer でホーム ページを表示します。次に、**Users** フォルダーを開きます - このラボの残りの部分で使用するファイルを含む **DP100** フォルダーが含まれています。
7. **Users/DP100** フォルダーで、「**01B - Intro to the Azure ML SDK.ipynb**」を開きます。次に、Notebook 内の注意事項を読み、各コード セルを順番に実行します。
8. Notebook 内のコードの実行が終了したら、「**ファイル(File)**」メニューの「**閉じて停止(Close and Halt)**」をクリックして閉じ、Python カーネルをシャットダウンします。その後、すべての Jupyter ブラウザー タブを閉じます。
9. 1 日の Azure Machine Learning の使用が終了したら、Azure Machine Learning studio の「**コンピューティング**」ページで、コンピューティング インスタンスを選択し、「**停止**」をクリックしてシャットダウンします。それ以外の場合は、次のラボ用に実行したままにします。
