# ラボ 8B: Automated Machine Learning の使用

モデル トレーニングの適切なアルゴリズムと前処理変換を決定するには、多くの推測と実験が必要です。

このラボでは、Automated Machine Learning を使用して、複数のトレーニングを並行して実行することで、モデルに最適なアルゴリズムと前処理手順を決定します。

## 開始する前に

このラボを開始する前に、このラボで使用する Azure Machine Learning ワークスペースと他のリソースを作成するタスクを含む[ラボ 1A](Lab01A.md) と[ラボ 1B](Lab01B.md) を完了させてください。

## タスク 1: Automated Machine Learning の使用

このタスクでは、Automated Machine Learning を使用して、モデル トレーニングに最適なアルゴリズムと前処理変換を決定します。

1. [Azure Machine Learning Studio](https://ml.azure.com) で、ワークスペースの**コンピューティング** ページを表示し、**コンピューティング インスタンス** タブでコンピューティング インスタンスを開始します。
2. コンピューティング インスタンスが実行されている場合は、ブラウザーで Azure Machine Learning Studio の Web ページを更新して、認証セッションの有効期限が切れていないことを確認します。次に、**Jupyter** リンクをクリックして、新しいブラウザー タブで Jupyter のホーム ページを開きます。
3. Jupyter のホーム ページの**Users/DP100** フォルダーで、**08B - Using Automated Machine Learning.ipynb** Notebook を開きます。次に、Notebook 内の注意事項を読み、各コード セルを順番に実行します。
4. Notebook 内のコードの実行が終了したら、**ファイル(Files)** メニューの**閉じて停止(Close and Halt)**をクリックして閉じ、Python カーネルをシャットダウンします。その後、すべての Jupyter ブラウザー タブを閉じます。
5. Azure Machine Learning Studio の**コンピューティング** ページで、コンピューティング インスタンスを選択し、**停止**をクリックしてシャットダウンします。
