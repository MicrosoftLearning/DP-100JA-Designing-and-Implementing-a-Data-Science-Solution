# ラボ 1B: Azure Machine Learning ツールの操作

このラボでは、Azure Machine Learning ワークスペースを操作するためのさまざまなツールについて説明します。

## 開始する前に

このラボを開始する前に、[前のラボ](Lab01A.md)の手順に従って Azure Machine Learning ワークスペースを作成しておく必要があります。

## タスク 1: コンピューティング インスタンスでの Azure ML SDK の使用

ほとんどのアセット管理タスクを実行して、*Studio* インターフェイスで環境をセットアップできますが、構成タスクをスクリプト化して、繰り返しと自動化を容易にすることも重要です。

1. [Azure Machine Learning Studio](https://ml.azure.com) のワークスペースの**コンピューティング** ページで、**コンピューティング インスタンス** タブを表示し、必要に応じて、前のラボで作成したコンピューティング インスタンスが開始されるまで定期的に **更新** をクリックします。
2. ブラウザーで Azure Machine Learning Studio の Web ページを更新して、認証セッションの有効期限が切れていないことを確認します。次に、コンピューティング インスタンスの **Jupyter** リンクをクリックして、新しいタブで Jupyter Notebook を開きます。メッセージが表示されたら、Azure サブスクリプションに関連付けられている Microsoft アカウントを使用してサインインします。
3. Notebook 環境で、新しい **ターミナル** を作成します。これにより、コマンド シェルを含む新しいタブが開きます。
4. Azure Machine Learning SDK はコンピューティング インスタンス イメージに既にインストールされていますが、このコースで必要なオプション パッケージを使用して、最新バージョンを確実に使用できます。次のコマンドを入力して SDK パッケージを更新します。

```bash
    pip install --upgrade azureml-sdk[notebooks,automl,explain]
```

    > **詳細情報** : Azure ML SDK とそのオプション コンポーネントのインストールの詳細については、「[Azure ML SDK ドキュメント](https://docs.microsoft.com/python/api/overview/azure/ml/install?view=azure-ml-py)」を参照してください。

5. 次に、次のコマンドを実行して、現在のディレクトリを **Users** ディレクトリに変更し、このコースの演習で使用する Notebooks を取得します。

    ```bash
    cd Users
    git clone https://github.com/MicrosoftLearning/DP100
    ```

6. コマンドが完了したら、ターミナル タブを閉じ、Jupyter Notebook ファイル Explorer でホーム ページを表示します。次に、**Users** フォルダーを開きます - このラボの残りの部分で使用するファイルを含む **DP100** フォルダーが含まれています。
7. **ユーザー/DP100** フォルダーで、「**01B - Intro to the Azure ML SDK.ipynb**」を開きます。次に、Notebook 内の注意事項を読み、各コード セルを順番に実行します。
8. Notebook 内のコードの実行が終了したら、**ファイル** メニューの **閉じて停止**をクリックして閉じ、Python カーネルをシャットダウンします。その後、すべての Jupyter ブラウザー タブを閉じます。
9. Azure Machine Learning Studio の **コンピューティング** ページで、コンピューティング インスタンスを選択し、**停止** をクリックしてシャットダウンします。

## タスク 2: Visual Studio Online の環境を設定する

Azure Machine Learning でコンピューティング インスタンスを使用すると、独自の Python インストールを管理しなくても、Azure ML を操作するための Python 環境を簡単に管理できます。ただし、独自のグラフィカルな Python 開発環境を使用する場合があります。このコースでは、インストールを簡略化するために Visual Studio Online を使用しますが、Azure Machine Learning SDK を使用する原則は Python 環境と同じです。

> **注**: Visual Studio Online は、執筆時点では *プレビュー* 段階にあります。予期しないエラー メッセージが表示される場合があります。

1. 新しいブラウザー タブで、[https://online.visualstudio.com](https://online.visualstudio.com) に移動し、**作業の開始** をクリックします。
2. Azure へのサインインに使用したのと同じ Microsoft の資格情報を使用して、Visual Studio Online にサインインします。
3. 次の設定で新しい環境を作成し、メッセージが表示されたら、Azure サブスクリプションで料金プランを作成します。
    - **環境名**: *お好みの一意の名前*
    - **Git リポジトリ**: MicrosoftLearning/DP100
    - **インスタンス タイプ**: Standard (Linux)
    - **アイドル状態になってから中断するまでの時間**: 30 分
4. 環境が作成されるのを待ってから、その名前をクリックして接続します。

    Visual Studio Online は、Web ブラウザーで使用できる Visual Studio Code のホストされたインスタンスです。Visual Studio Code は、*拡張機能* のインストールを通じてさまざまなプログラミング言語をサポートする一般的なコード編集環境です。Python を使用するには、この環境を **DP100** リポジトリから作成したときに、一般的に使用される Python パッケージと共にインストールされた Microsoft Python 拡張機能が必要です。

    ホストされる Visual Studio Code 環境には、Python の 3 つのインストール (バージョン 2.7.13、3.5.3、3.8.0) が含まれています。Python **3.5.3** 仮想環境を使用します。独自のインストールでは、Python のインストール、仮想環境の作成、必要なパッケージのインストールを担当します。このラボでは、Python の一般的な構成のほとんどを行いますが、Azure Machine Learning SDK をインストールする必要があります。

5. Visual Studio Online 環境で、DP100 リポジトリの内容が読み込まれるのを待ってから、アプリケーション メニュー (**&#9776;**) で、**表示**メニューの **コマンド パレット** をクリックします (または Ctrl+Shift+P を押します)。次に、パレットで、コマンド **Python: Create Terminal** を入力します。これにより、Visual Studio Online インターフェイスの下部に Python ターミナル ウィンドウが開きます。

    > **ヒント**: *Python の場合: ターミナルを作成* コマンドが表示されない場合は、ブラウザーを更新し、環境を再読み込みしてから、もう一度やり直してください。

6. ターミナル ウィンドウで、次のコマンドを入力して、Python 3.5.3 仮想環境が定義されているディレクトリに変更します。

	```bash
    cd /usr/bin
    ```

7. 次のコマンドを使用して、Azure Machine Learning SDK (オプションの *Notebooks* 追加パッケージ) をインストールします。

    ```bash
    sudo pip install azureml-sdk[notebooks]
    ```

8. ターミナル ウィンドウを閉じます。

## タスク 3: Visual Studio Online で Azure ML SDK を使用する

Python 開発環境ができたので、Azure Machine Learning SDK を使用できます。まず、Azure Machine Learning ワークスペースに接続するために必要な構成情報を取得する必要があります。

1. 新しいブラウザー タブで、必要に応じて、[https://portal.azure.com](https://portal.azure.com) にサインインして、Azure portal を開きます。
2. 前のラボで作成した Azure Machine Learning ワークスペース リソースを開き、その **概要**ページで、**config.json のダウンロード** をクリックし、ファイルをローカル コンピューターにダウンロードします。
3. ダウンロードした **config.json** ファイルをテキスト エディターで開き、内容をクリップボードにコピーします。このファイルには、ワークスペースへの接続に必要な構成情報が含まれています。
4. Visual Studio Online で、VS Online ワークスペースのルート フォルダーに **config.json** という名前の新しいファイルを作成します。
5. コピーした構成情報を Visual Studio Online ワークスペースの新しい config.json ファイルに貼り付け、保存します。
6. Visual Studio Online で、**01B - Intro to the Azure ML SDK.ipynb** を開きます - これは Visual Studio Online オンライン内の Jupyter Notebook インターフェイスに読み込まれます。Jupyter Notebooks インターフェイスを初めて使用するときに読み込むにはしばらく時間がかかる場合があり、Notebook の JSON 表現を含むウィンドウと Notebook ビジュアル インターフェイスを含む 2 つのウィンドウが短時間に表示される場合があります。
7. Notebook が読み込まれたら、Visual Studio Online インターフェイスの左下にある現在の Python 仮想環境をクリックします。これは、リポジトリの設定に基づいて **Python 3.5.3** に変更されているはずですが、その仮想環境を再度選択します (Notebook はメタデータに示されている別のバージョンで作成されています)。
8. Azure Machine Learning Notebook VM Jupyter 環境と同様に、各コード セルを順番に実行して、Notebook 内の注意事項を読みます。

## タスク 4: Visual Studio Code Azure Machine Learning の拡張機能を使用する

Visual Studio Online (または Visual Studio Code のローカル インストール) で Azure Machine Learning を使用する場合、Azure Machine Learning 拡張機能を使用すると、コード開発環境や Azure Machine Learning Studio Web インターフェイスを切り替えることなく、ワークスペース内のリソースを簡単に操作できます。

1. Visual Studio Online で、**拡張機能** タブ (&#8862;) をクリックし、"Azure Machine Learning" を検索します。次に、Microsoft から **Azure Machine Learning** 拡張機能をインストールします。拡張機能がインストールされたら、**必要な再ロード** ボタンをクリックして、拡張機能を使用して環境をリロードします。
2. Visual Studio Online で、**Azure** タブ (***&Delta;***) をクリックし、**Azure Machine Learning** セクションで、サブスクリプションと Azure Machine Learning ワークスペースを展開します。
3. **コンピューティング** を展開し、ワークスペースで作成した **aml-cluster** コンピューティング リソースが **ローカル** コンピューティング リソースと共に一覧表示されていることを確認します。この場合、Visual Studio Online が環境をホストしていることを表しています。ローカル コンピューター上およびワークスペースで定義されるコンピューティング リソース上で、Azure Machine Learning コードの実験を実行できます。
4. Visual Studio Online ブラウザー タブを閉じます。
