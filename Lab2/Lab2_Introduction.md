---
lab:
    title: 'ラボ 2 - ML モデルを登録してデプロイする'
    module: 'モジュール 2: Azure Machine Learning service でデータ サイエンスを実行する'
---

# ラボ 2 - ML モデルを登録してデプロイする

## ラボ 2.0: 目的

ここでは、次の内容を学習します。

- Azure Machine Learning service を使用してモデルをトレーニングする
- 作成したモデルをワークスペースのレジストリに登録する
- モデル スコアリング スクリプトを作成する
- Python モジュールの依存関係を構成する YAML ファイルを作成する
- コンテナー イメージを作成する
- モデルを Web サービスとしてデプロイする
- デプロイされたモデルを使用して新しいデータをスコアリングする


## 概要

このラボでは、Azure Machine Learning service とその Python SDK を使用して、前回のラボで Azure で開発したモデルをトレーニングします。トレーニングの後、モデルをレジストリに登録し、モデルを Azure Machine Learning service にデプロイするために必要な手順を実行します。 

## ラボ 2: リソース

ラボ フォルダーにある次のファイルを使用します。

名前                            | 説明
----                            | -----------
Starter_Lab2_Notebook.ipynb     | 使用するラボ ノートブック。  これを Notebook プロジェクトにインポートして開きます。 


Azure Notebook プロジェクトの作成とノートブックのインポートの詳細については、https://docs.microsoft.com/ja-jp/azure/notebooks/quickstart-migrate-local-jupyter-notebook を参照してください。

Azure Notebook へのデータのアップロードの詳細については、https://docs.microsoft.com/ja-jp/azure/notebooks/work-with-project-data-files を参照してください。



## 前提条件

このラボを始める前に、次のものが必要です。
- 無料の Azure Notebooks サービスのサインアップ  
- Azure Machine Learning service ワークスペースをプロビジョニングできる Azure サブスクリプション。
