# §3.1 フロントエンドの設定を変更してビルド

## 本節の前提条件

本文の節「§2.6 AWSに公開したWebアプリを動作確認」にて  
「CloudFrontへのHTTPSアクセスのURL」にブラウザーでアクセスできることを
確認済みであることを前提とします。


## 本節の操作手順

本文の案内にしたがって、[./frontend](./) フォルダーの直下に
`.env.production.s3` ファイルを作成してください。
作成したら、「§2.6」で動作確認した「CloudFrontへのHTTPSアクセスのURL」の値を設定します。

なお、初期値が記載されたファイル 
[`env.production.s3.txt`](./env.production.s3.txt) 
を用意しています。  
これをコピーしてリネームした上で、環境に応じた値を編集すると便利です。

環境変数の設定が完了したら、コマンドラインを開き、
`frontend` フォルダー直下に移動します。
その状態で、以下のコマンドを実行して依存モジュールをインストールしてください。

```
npm install
```

続いて、次のコマンドを実行してビルドします。

```
npm run build:s3
```

`frontend/dist`配下に、ビルド（トランスパイル）されたファイルが出力されます。



<br><br><br>

# §3.2.1 フロントエンド用のS3作成し、フロントエンドをアップロード

本節は、[こちら](../infrastructure/cloudformation/3-create-s3-for-static-spa/README.md)を参照ください。


<br><br><br>

---

# §4.3 フロントエンドの設定を変更して再公開

## 本節の前提条件

本文の節「§4.2 API Gatewayを経由したLambda関数のエンドポイントを公開」
の案内にしたがって、
API Gatewayのエンドポイントの応答を確認済みであることを前提とします。


## 本節の操作手順

本文の案内にしたがって、`./frontend` フォルダー直下に
`.env.production.lambda` ファイルを作成してください。

環境変数の設定が完了したら、コマンドラインを開き、
`frontend` フォルダー直下に移動します。
次のコマンドを実行して、ビルドを行ってください。

```
npm run build:lambda
```

`frontend/dist`配下に、ビルドされたファイルが出力されます。





<br><br><br>

# フロントエンド自体の開発・ビルド手順 =================================================

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```



### Compile and Minify for Production

`.\backend`配下の[dist](../backend/dist/)フォルダー出力する。

* [backend](../backend/)側でホスティングしての動作確認用
* 環境変数などの設定は不要

```sh
npm run build
```

#### AWSへの直アップロード用のカスタマイズBuild:S3ホスティング

`.\dist`配下に出力する。

* [.env.production.s3](./.env.production.s3)ファイルを作成して、次の環境変数名を設定すること
    * `VITE_BACKEND_AUTH_URL=＜バックエンドのCloudFrontのHTTPSドメイン＞/`  ※最後にスラッシュを付ける。
    * `VITE_BACKEND_API_URL=＜バックエンドのCloudFrontのHTTPSドメイン＞/`  ※最後にスラッシュを付ける。
* S3でのホスティングを前提に、上記の環境変数の設定でビルドされる。

```sh
npm run build:s3
```

#### AWSへの直アップロード用のカスタマイズBuild:Lambda配置APIへS3ホスティングから通信

`.\dist`配下に出力する。

* [.env.production.lambda](./.env.production.lambda)ファイルを作成して、次の環境変数名を設定すること
    * `VITE_BACKEND_AUTH_URL=＜バックエンドのCloudFrontのHTTPSドメイン＞/`  ※最後にスラッシュを付ける。
    * `VITE_BACKEND_API_URL=＜API GatewayのHTTPSドメイン＞/`  ※最後にスラッシュを付ける。
* S3でのホスティングを前提に、上記の環境変数の設定でビルドされる。

```sh
npm build:lambda
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
