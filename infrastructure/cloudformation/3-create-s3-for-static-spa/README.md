# §3.2.1 フロントエンド用のS3バケットを作成し、ビルド済みファイルをアップロード

## 本節の前提条件

[frontend](../../../frontend/README.md) の節「[§3.1](../../../frontend/README.md#31-フロントエンドの設定を変更してビルド)」で  
ビルドされたファイルが `frontend/dist` 配下に出力されていることを確認しておいてください。

## 本節の操作手順

本文の案内にしたがって、S3バケットを作成してください。以下の CloudFormation テンプレートを使用します。  
※節「[§2.5.3](../1-create-s3-for-appzip/README.md#253-アプリ一式をzipで格納するs3バケットの作成)」で使用したテンプレートとは異なります。

* **リスト3.3**: フロントエンドをホスティングするためのS3バケットを作成するテンプレート
    * [s3-bucket-for-frontend-public-spa.yaml](./s3-bucket-for-frontend-public-spa.yaml)

S3バケットを作成したら、本文の手順にしたがって `frontend/dist` 配下のファイルをアップロードしてください。

