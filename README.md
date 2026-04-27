# book-aws-webapp-step-by-step

「 **AWS体験ステップブック　～既存構成から始めるサーバーレス化！～** 」 本で利用するサンプルコードです。

https://nextpublishing.jp/book/19461.html


本書籍のそれぞれの章・節で利用するサンプルコードは、以下を参照ください。

> ## 正誤表：一部のコラムでレイアウトの崩れがあります
>
> 本書の一部のコラムで、レイアウトが崩れている部分があります。
> 
> 該当箇所と、本来のレイアウト表示については、[こちら](./column-display-support/README.md)を参照ください。
> 

<br><br>

---

# 1章：

サンプルコードはありません。

<br><br>

---

# 2章：

## §2.4 ローカルサーバーでアプリを起動しログイン動作を確認

* `./backend` フォルダー内の [README.md](./backend/README.md) の節「§2.4 ローカルサーバーでアプリを起動しログイン動作を確認」を参照してください。

## §2.5 EC2 ベースでの公開に必要なインフラをAWSに構築

### §2.5.3 アプリ一式をZipで格納するS3バケットの作成
<!-- P.25 -->

* `./infrastructure/cloudformation/1-create-s3-for-appzip` フォルダー内の [README.md](./infrastructure/cloudformation/1-create-s3-for-appzip/README.md) の節「§2.5.3 アプリ一式をZipで格納するS3バケットの作成」を参照してください。


### §2.5.4 CloudFormationの構成内容と適用前準備

* `./infrastructure/cloudformation/2-backend-infra-vpc-ec2` フォルダー内の [README.md](./infrastructure/cloudformation/2-backend-infra-vpc-ec2/README.md) の節「§2.5.4 CloudFormationの構成内容と適用前準備」を参照してください。



### §2.5.5 CloudFormationでEC2等を作成し、アプリを配置する

* `./infrastructure/cloudformation/2-backend-infra-vpc-ec2` フォルダー内の [README.md](./infrastructure/cloudformation/2-backend-infra-vpc-ec2/README.md) の節「§2.4.4 EC2やVPCなど作成し、アプリを配置する」を参照してください。



### §2.5.8 HTTPSドメインに合わせてアプリ側を再設定する

* `./backend` フォルダー内の [README.md](./backend/README.md) の節「[§2.5.8 HTTPSドメインに合わせてアプリ側を再設定する](./backend/README.md#258-httpsドメインに合わせてアプリ側を再設定する)」を参照してください。




<br><br><br>

---

# 3章：

## §3.1 フロントエンドの設定を変更してビルド

* `./frontend` フォルダー内の [README.md](./frontend/README.md) の節「[§3.1 フロントエンドの設定を変更してビルド](./frontend/README.md#31-フロントエンドの設定を変更してビルド)」を参照してください。

## §3.2 S3とCloudFrontを組み合わせてフロントエンドをHTTPS公開

### §3.2.1 フロントエンド用のS3作成し、フロントエンドをアップロード

* `./infrastructure/cloudformation/3-create-s3-for-static-spa` フォルダー内の [README.md](./infrastructure/cloudformation/3-create-s3-for-static-spa/README.md) の節「§3.2.1 フロントエンド用のS3作成し、フロントエンドをアップロード」を参照してください。


## §3.3 バックエンドの設定を変更して再公開

* `./backend` フォルダー内の [README.md](./backend/README.md) の節「[§3.3 バックエンドの設定を変更して再公開](./backend/README.md#33-バックエンドの設定を変更して再公開)」を参照してください。



<br><br><br>

---

# 4章：

## §4.1 APIの実装をLambdaでの呼び出し用に切り出し、Zip にしてS3に配置

* `./infrastructure/lambda` フォルダー内の [README.md](./infrastructure/lambda/README.md) の「[§4.1 APIの実装をLambdaでの呼び出し用に切り出し、ZipにしてS3に配置](./infrastructure/lambda/README.md#41-apiの実装をlambdaでの呼び出し用に切り出しzip-にしてs3に配置)」節を参照してください。

## §4.2 API Gatewayを経由したLambda関数のエンドポイントを公開

* `./infrastructure/lambda` フォルダー内の [README.md](./infrastructure/lambda/README.md) の節「[§4.2 API Gatewayを経由したLambda関数のエンドポイントを公開](./infrastructure/lambda/README.md#42-api-gatewayを経由したlambda関数のエンドポイントを公開)」を参照してください。

## §4.3 フロントエンドの設定を変更して再公開

* `./frontend` フォルダー内の [README.md](./frontend/README.md) の節「[§4.3 フロントエンドの設定を変更して再公開](./frontend/README.md#43-フロントエンドの設定を変更して再公開)」を参照してください。


