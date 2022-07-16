# day
A simple blog where you can only write one article a day

## デプロイ
1. このレポジトリをimportしてください
2. Settings -> Actions -> Enable (importすると設定が無効になるため)
3. `_config.yml`を設定
4. _days/2022.md 以下を編集
5. Wait a few minutes for GitHub Actions to finish.
6. Change the Source branch setting of GitHub Pages to gh-pages.
![](https://i.gyazo.com/b658c1560fe784561aacd6fb592b3be0.png)

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
