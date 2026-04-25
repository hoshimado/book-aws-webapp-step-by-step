# §2.5.4 CloudFormationの構成内容と適用前準備

本節で提示している
「**リスト2.12**：EC2やVPC等の内部ネットワークとサーバーを作成するテンプレート（抜粋）」
のファイル全体は以下です。

* [infrastructure1-ec2base.yaml](./infrastructure1-ec2base.yaml)

本CloudFormationテンプレートを実際にCloudFormationにアップロードするのは次の節
「§2.5.5」になります。



# §2.5.5 CloudFormationでEC2等を作成し、アプリを配置する

## 本節の前提条件

[1-create-s3-for-appzip](./infrastructure/cloudformation/1-create-s3-for-appzip/README.md)の節「§2.5.3」の案内にしたがって、S3にzipファイルがアップロード済みであること。

## 本節の操作手順

本文の案内にしたがって、EC2やVPCなどのリソース一式を作成します。

以下のCloudFormationテンプレート（上述のファイルと同一です）を一度エディターで開き、
L70行目あたりにあるコメント「※自身の環境のS3バケット名に合わせて書き換えてください」の直後の値を、
節「§2.5.3 アプリ一式をZipで格納するS3バケットの作成」で作成した**S3バケット名に修正して、上書き保存**してください。

その後に、修正済みのファイルを使用してください。


* [infrastructure1-ec2base.yaml](./infrastructure1-ec2base.yaml)






