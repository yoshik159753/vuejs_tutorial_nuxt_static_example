# nuxt-static-example

> Nuxt.js project

## Build Setup

``` bash
# install dependencies
$ npm install # Or yarn install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, checkout the [Nuxt.js docs](https://github.com/nuxt/nuxt.js).

## MEMO

静的ファイルを生成するには下記のコマンドを実行する。

`npm run generate`

生成した静的ファイルを docker で動作確認する場合には、 dist ディレクトリに移動して下記のコマンドを実行する。

``` bash
docker run -dit --name nuxtjs -p 8080:80 -v `pwd`:/usr/local/apache2/htdocs/ httpd

# 後処理
docker stop nuxtjs
docker rm nuxtjs
```
