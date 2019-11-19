---
lab:
    title: 'ラボ 3 - AutoML と HyperDrive を使用する'
    module: 'モジュール 3: Azure Machine Learning service で機械学習を自動化する'
---

# ラボ 3 - AutoML と HyperDrive を使用する

## ラボ 3.0: 目的

ここでは、次の内容を学習します。

- 機械学習パイプラインについて理解する
- Azure Machine Learning service AutoML と HyperDrive について理解する
- Azure Machine Learning service の AutoML を使用してモデルを推奨する Python スクリプトを作成する
- Python スクリプトから推奨モデルをテストする



## 概要

このラボでは、以前に手動で作成したモデルよりもパフォーマンスの優れたモデルがあるかどうかを確認します。ここでは、Azure Machine Learning service の AutoML と HyperDrive を使用して、さまざまな種類の分類モデルを同時に実行し、その結果を比較して、最適なモデルを推奨することにします。これにより、最適なモデルを選択する時間を短縮できるため、ソリューションを早く提供できます。 

## ラボ 3: リソース

ラボ フォルダーにある次のファイルを使用します。

名前                            | 説明
----                            | -----------
Starter_Lab3_Notebook.ipynb     | 使用するラボ ノートブック。  これを Notebook プロジェクトにインポートして開きます。 


Azure Notebook プロジェクトの作成とノートブックのインポートの詳細については、https://docs.microsoft.com/ja-jp/azure/notebooks/quickstart-migrate-local-jupyter-notebook を参照してください。

Azure Notebook へのデータのアップロードの詳細については、https://docs.microsoft.com/ja-jp/azure/notebooks/work-with-project-data-files を参照してください。



## 前提条件

このラボを始める前に、次のものが必要です。
- 無料の Azure Notebooks サービスのサインアップ  
- Azure Machine Learning service ワークスペースをプロビジョニングできる Azure サブスクリプション。
