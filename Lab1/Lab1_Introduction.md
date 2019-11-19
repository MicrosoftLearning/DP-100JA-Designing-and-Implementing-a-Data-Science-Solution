---
lab:
    title: 'ラボ 1 - Azure Notebooks でモデルをトレーニングする'
    module: 'モジュール 1: Azure でデータ サイエンスを行う'
---

# ラボ 1 - Azure Notebooks でモデルをトレーニングする

## ラボ 1.0: 目的

このラボでは、次の内容を学習します。

- Python で Azure ノートブックを使用する。これはクラウド ベースの Jupyter Notebook サービスです。
- 探索的データ分析を実行する。
- 機械学習モデル機能を作成する。
- オープン ソース ベースの分類予測モデルをトレーニングする。

このラボの主な目標は、受講者に Azure Notebooks を使用して説明し、Adventure Works の使用例を紹介することです。

## 概要

Python とオープン ソース パッケージの scikit-learn を使用して、Azure Notebooks で分類モデルをトレーニングします。その一環として、データを理解するためにいくつかの基本的な探索的データ分析を実行する必要があります。  次に、モデル トレーニングで使用する機能を作成する必要があります。最後に、モデルをトレーニングして評価します。注:  この段階では、Azure サービスは使用しません。 

チームのデータ エンジニアから、必要なすべてのデータを含む CSV 形式のデータ抽出ファイルが提供されます。  スターター ラボ ノートブックでは、このラボで行う必要があるタスクについて説明します。 



## ラボ 1: リソース

ラボ フォルダーにある次のファイルを使用します。

名前                            | 説明
----                            | -----------
Starter_Lab1_Notebook.ipynb     | 使用するラボ ノートブック。  これを Notebook プロジェクトにインポートして開きます。 
AWData.csv                      | Adventure Works のデータ抽出ファイル。このファイルを Azure Notebook プロジェクトにアップロードします。 

Azure Notebook プロジェクトの作成とノートブックのインポートの詳細については、https://docs.microsoft.com/ja-jp/azure/notebooks/quickstart-migrate-local-jupyter-notebook を参照してください。

Azure Notebook へのデータのアップロードの詳細については、https://docs.microsoft.com/ja-jp/azure/notebooks/work-with-project-data-files を参照してください。



## 前提条件

このラボを始める前に、次のものが必要です。
- 無料の Azure Notebooks サービスのサインアップ  
