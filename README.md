# Amazon SageMaker の Factorization Machines を使用したレコメンダ システムの構築

## Contents

ノートブック: `fm_amazon_recommender_japanese.ipynb`

## 設定のステップ
1. SageMaker のノートブックインスタンスを作成する。 

    AWS コンソールにログインし、SageMaker に移動します。 SageMakerは機械学習セクションか、コンソールの上部にある検索ボックスを使用して見つけることができます。 SageMaker ダッシュボードには、真値、ノートブック、トレーニング、推論など、すべての主要コンポーネントへのリンクが含まれています。 「ノートブック」のカテゴリの １ つ目が「ノートブックインスタンス」です。 そのリンクをクリックします。

1. オレンジ色の 「ノートブックインスタンスの作成」 ボタンをクリックします。

    以下の内容を入力してください。

    - インスタンスの名前を ```rec-engine-workshop```入力します。
    - インスタンスタイプを ```ml.m5.4xlarge```と選択します。
    - IAM ロール では [新しいロールの作成] を選択します。
            - 「任意の S3 バケット」を選択します。
            - 「ロールの作成」ボタンをクリックします。
    - VPC なし
	- Git リポジトリにて、「このノートブックインスタンスのみにパブリック Git リポジトリのクローンを作成する」を選択し、リポジトリの URL を https://github.com/rumiio/sagemaker-rec-engine-demo.git と指定して下さい。
    - 再び、「このノートブックインスタンスのみにパブリック Git リポジトリのクローンを作成する」を選択し、リポジトリの URL を https://github.com/skrinak/personalize-amzn-rec.git と指定して下さい。
    - ライフサイクル設定なし
    - カスタム暗号化なし

    上記入力後、「ノートブックインスタンスの作成」 をクリックします。

    SageMaker ノートブックインスタンスのプロビジョニングには約 3 分程かかります。 この間、ステータスが*Pending*と表示されます。
    

# sagemaker-rec-demo

**Building a Recommender System with Amazon SageMaker Factorization Machines and BlazingText**


## Contents

Notebook: `fm_amazon_recommender.ipynb`

### Main Workshop:
- Background (Factorization Machines)
- Setup
	- Spin up SageMaker hosted notebook instance in console
	- Add SageMaker IAM policy to this SageMaker notebook to allow S3 read/write access
	- Create new S3 bucket (first cell)
	- Import necessary libraries (second cell)
- Dataset
	- Overview
	- Source: [Amazon Reviews Public Dataset](https://s3.amazonaws.com/amazon-reviews-pds/readme.html)
	- Features
- Data preprocessing
- Training
	- Create SageMaker estimator
	- Launch training job
- Host
	- Deploy endpoint to perform inference


### Extra Credit: 
- Background (New challenges, word2vec, BlazingText)
- Data Augmentation
- Dimensionality reduction with t-SNE
- Train
- Host




