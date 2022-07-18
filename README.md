# day
A simple blog where you can only write one article a day

## 特徴

## デプロイ
1. このレポジトリの**Use this template**ボタンを押します
![](https://i.gyazo.com/thumb/480/f4bc4e39acf3d40bb4314ef38c395863.png)
1. Owner(オーナー)とRepository Name(レポジトリ名)を設定して**Create repository from template**
![](https://i.gyazo.com/thumb/480/0d8f2e4b208bda05a0f10b1d5c990709.png)
1. `_config.yml`を編集(Webインターフェースからできます)
   - `url` -> ユーザー名.github.io 
   - `baseurl` -> 作成したレポジトリの名前
   - ![](https://i.gyazo.com/thumb/480/263a51a1c9a4818f4f1218d6ef68b457.png)
1. GitHub Actionsが終了するまで数分待ちます...
![](https://i.gyazo.com/thumb/480/7424c860a749555b90f41dc47df66237.png)
1. GitHub PagesのSourceを`gh-pages`に設定します
![](https://i.gyazo.com/thumb/480/b658c1560fe784561aacd6fb592b3be0.png)
1. GitHub Actionsの`page build and deployment`が成功していたらリンク先にブログが開設されています
![](https://i.gyazo.com/thumb/480/f7529faa49226540f312b19174c41644.png)

## 記事を編集する
- _days/以下のmarkdown
4. _days/2022.md 以下を編集

## 独自ドメインにデプロイ
1. あらかじめ自分のドメイン管理アプリを設定
1. CNAMEファイルを追加
1. _config.yml の url と baseurl を書き換え
1. DNS Check in Progressが終わるまでしばらく待つ
1. Enforce HTTPS を設定
   - 参考: https://day.ongaeshi.me/20220709

## Deploy
1. Fork to your reposiytory.
2. Checkout.
```
$ git checkout https://github.com/yourname/day.git
$ mkdir day
```
3. Change `_config.yml` to your environment.
4. Push to github.com
```
$ git add .
$ git commit -m "Change _config.yml for my environment"
$ git push
```
5. Wait a few minutes for GitHub Actions to finish.
6. Change the Source branch setting of GitHub Pages to gh-pages.
![](https://i.gyazo.com/b658c1560fe784561aacd6fb592b3be0.png)

## Test locally
```
$ bundle install
$ ruby ./days_to_posts.rb
$ jekyll serve --watch
```
