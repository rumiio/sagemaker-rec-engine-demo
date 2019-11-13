

# Building a Recommender System with Amazon SageMaker Factorization Machines and BlazingText

## Contents

We will be using the `fm_amazon_recommender.ipynb` notebook. 

## Workshop Instructions

1. Go to SageMaker console. Create a new SageMaker notebook instance with the following configuration: 
   - Enter a name without undercore. You can use hyphen but not underscore between words.
   - Choose instance type such as **ml.m4.4xlarge**.
   - Create a new SageMaker IAM role with access to **any S3 bucket**
   - No VPC, etc. needed
   - **Git repository** section
      - From the dropdown list, choose “Clone a public Git repository to this notebook instance only” option. 
      - Insert the following link in **Git repository URL** 
https://github.com/rumiio/sagemaker-rec-engine-demo 

1. It would take a couple of minutes for the notebook instance to be ready. Once the status changes from *pending* to *InService*, click on the **Open Jupyter** link.

    It will bring up the Jupyter environment. Click on the **fm_amazon_recommender.ipynb** to get started on your lab. 
 
 
 ### Contents of the notebook.
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


Following is instructions written in Japanese.
# Amazon SageMaker の Factorization Machines を使用したレコメンダ システムの構築

## Contents

ノートブック: `fm_amazon_recommender_japanese.ipynb`

## 設定のステップ
1.  マネージメントコンソールのメインの画面から、SageMaker のコンソールへ移動する。

    AWS コンソールにログインし、SageMaker に移動します。 SageMakerは機械学習セクションか、コンソールの上部にある検索ボックスを使用して見つけることができます。 SageMaker ダッシュボードには、真値、ノートブック、トレーニング、推論など、すべての主要コンポーネントへのリンクが含まれています。 「ノートブック」のカテゴリの １ つ目が「ノートブックインスタンス」です。 そのリンクをクリックします。

1. SageMaker のノートブックインスタンスを作成する。オレンジ色の 「ノートブックインスタンスの作成」 ボタンをクリックして下さい。

    そして、以下の内容を入力してください。

    - インスタンスの名前を ```rec-engine-workshop```入力。
    - インスタンスタイプを ```ml.m5.4xlarge```と選択。
    - IAM ロール では [新しいロールの作成] を選択。
            - 「任意の S3 バケット」を選択。
            - 「ロールの作成」ボタンをクリックして下さい。
    - VPC なし
	- Git リポジトリにて、「このノートブックインスタンスのみにパブリック Git リポジトリのクローンを作成する」を選択し、リポジトリの URL を https://github.com/rumiio/sagemaker-rec-engine-demo.git と指定して下さい。
    - 再び、「このノートブックインスタンスのみにパブリック Git リポジトリのクローンを作成する」を選択し、リポジトリの URL を https://github.com/skrinak/personalize-amzn-rec.git と指定して下さい。
    - ライフサイクル設定なし
    - カスタム暗号化なし

    上記入力後、「ノートブックインスタンスの作成」 をクリックします。

    SageMaker ノートブックインスタンスのプロビジョニングには約 3 分程かかります。 この間、ステータスが*Pending*と表示されます。

1. S3 のバケットを作成する。この際 SageMaker と同じリージョンで行って下さい。
    

