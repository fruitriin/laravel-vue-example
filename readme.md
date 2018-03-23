# Laravel with Vue Exmaple

PHP フレームワーク LaravelはVue.jsを採用しており、最初からパッケージに含まれています。  
しかしながら、デフォルトで有効になっているわけではなく、いくつかの手順を踏まなければなりません。  
このリポジトリでは LaravelでVueを導入する上で一助となるようなことをまとめてみようと思います。

## このリポジトリに含まれるパッケージのバージョン
- Laravel 5.6
- Vue.js 2.5.7

## 必要な環境
- PHP 7.2  
 (Laravel 5.6 だからなので、PHP7.2にできない場合は参考に留めてください。) 
- npm

## 環境構築
ComposerかLaravelInstallerから新しいLaravelプロジェクトを作成した場合には不要ですが、
このリポジトリからチェックアウトした場合、以下の手順が必要になります。

```shell
 composer install #そもそもcomposerがインストールされてません
 cp .env.example .env #このリポジトリからチェックアウトした場合 .envファイルは含まれていません
 php artisan key:generate  #Laravel のApplication IDをGenerateしてください

```

また、ComposerやLaravelInstallerからチェックアウトした場合でも、
npm packageはインストールされていないのでインストールしておきます。

```shell
npm install #比較的最近のnpmはデフォルトが--saveになりました

```

## このリポジトリを試すために必要なこと
Laravelを動作させるのとは別に、vue.jsのコンパイルが必要です。  
開発中はHot Module Reloadにするには npm run hot を使います。

```bash
npm run hot & # Vue CLI で作成したProjectで言うところのの npm run devです！ HMR!
php artisan serve # なんか適当にLocal環境とかで動かしてください
```

また、npm run hotでは静的ファイルへの吐き出しを行わないので、
Productionへ投入する前には下記のコマンドを実施してください。

```bash

npm run product
```

## License

Laravel-Vue-Example is released under the MIT license. 
