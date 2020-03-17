# ラボ 9A: Automated Machine Learning の説明の確認

Automated Machine Learning を使用してモデルをトレーニングする場合、機能の重要性の説明を生成するように実験を構成できます。

## 開始する前に

このラボを開始する前に、このラボで使用する Azure Machine Learning ワークスペースと他のリソースを作成するタスクを含む[ラボ 1A](Lab01A.md) と[ラボ 1B](Lab01B.md) を完了させてください。

## タスク 1: Automated Machine Learning モデルの機能の重要性を確認する

このタスクでは、Automated Machine Learning 実験によって生成される機能の重要性に関する情報について説明します。

1. [Azure Machine Learning Studio](https://ml.azure.com)で、ワークスペースの**コンピューティング** ページを表示し、**コンピューティング インスタンス** タブでコンピューティング インスタンスを開始します。
2. コンピューティング インスタンスが実行されている場合は、ブラウザーで Azure Machine Learning Studio の Web ページを更新して、認証セッションの有効期限が切れていないことを確認します。次に、**Jupyter** リンクをクリックして、新しいブラウザー タブで Jupyter のホーム ページを開きます。
3. Jupyter のホーム ページの**ユーザー/DP100** フォルダーで、**09A - Reviewing Automated Machine Learning Explanations.ipynb** Notebook を開きます。次に、Notebook 内の注意事項を読み、各コード セルを順番に実行します。
4. Notebook 内のコードの実行が終了したら、**ファイル** メニューの**閉じて停止**をクリックして閉じ、Python カーネルをシャットダウンします。その後、すべての Jupyter ブラウザー タブを閉じます。
5. Azure Machine Learning Studio の**コンピューティング** ページで、コンピューティング インスタンスを選択し、**停止**をクリックしてシャットダウンします。
