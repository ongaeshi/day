# day
ファイル構造の制約を受けずに記事が書けるブログシステムです。  
1つのファイルから複数の記事を出力することも、長い記事を別ファイルに分けることも可能です。

## 記事の追加
- `_days/`以下にマークダウン形式(`.md`)で記事を書きます
- `# 2022-07-19`のように日付を付けた見出しを作ると中身がその日の投稿になります
- `# 2022-07-19 今日の出来事`のように日付の後ろに空白を開けてテキストを書くとタイトルになります

## 例
_days/2022.md
- → https://ongaeshi.github.io/day/20220717
- → https://ongaeshi.github.io/day/20220715

```markdown
# 2022-07-17 Hello, World!
Day is a blogging system that allows you to write articles without being restricted by file structure.

# 2022-07-15 Image
![](https://i.gyazo.com/6aa6ecbf28b6af9f5684487bc42f2620.gif)

.
.
```

_days/a_long_article.md
- → https://ongaeshi.github.io/day/20220716

```markdown
# 2022-07-16
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eget laoreet tortor. Suspendisse potenti. Nam maximus enim eget metus aliquam, in fermentum sem pharetra. Integer ultrices felis id tristique suscipit. Suspendisse lorem massa, lobortis bibendum pellentesque viverra, porttitor a nunc. Proin tortor augue, ornare laoreet volutpat vel, dignissim sit amet sapien. Nullam vestibulum feugiat ante id ultrices. Maecenas ut vehicula turpis, ut iaculis nibh. Nunc maximus ipsum at lorem vestibulum, eget convallis quam aliquam.
.
.
```

## セットアップ
1. このレポジトリの**Use this template**ボタンを押します
![](https://i.gyazo.com/f4bc4e39acf3d40bb4314ef38c395863.png)
1. Owner(オーナー)とRepository Name(レポジトリ名)を設定して**Create repository from template**ボタンを押します
![](https://i.gyazo.com/thumb/480/0d8f2e4b208bda05a0f10b1d5c990709.png)
1. `_config.yml`を編集(Webインターフェースからできます)
   - `url` -> ユーザー名.github.io (ユーザー名は自身のGitHubアカウント名に置き換え)
   - `baseurl` -> 作成したレポジトリの名前
   - ![](https://i.gyazo.com/thumb/480/263a51a1c9a4818f4f1218d6ef68b457.png)
1. GitHub Actionsが終了するまで数分待ちます...
1. GitHub PagesのSourceを`gh-pages`に設定します
![](https://i.gyazo.com/thumb/480/cf34893a2a572e6c3d0c482fcf3cf153.png)
1. GitHub Actionsの`page build and deployment`が成功していたらリンク先にブログが開設されています
![](https://i.gyazo.com/thumb/480/f7529faa49226540f312b19174c41644.png)

## 独自ドメイン
1. あらかじめドメイン管理アプリに設定を追加
   - 例: `CNAME 3600 ユーザー名.github.io` (ユーザー名は自身のGitHubアカウント名に置き換え)
1. CNAMEファイルを追加
   - 例: https://github.com/ongaeshi/day_ongaeshi/blob/master/CNAME
1. _config.yml の url と baseurl を書き換え
   - 例: https://github.com/ongaeshi/day_ongaeshi/blob/master/_config.yml#L5-L6
1. DNS Check in Progressが終わるまでしばらく待つ
1. Enforce HTTPS を設定
   - 参考: https://day.ongaeshi.me/20220709

## ローカル環境で動かしたい
基本Jekyllですが`_posts`を生成するためのRubyスクリプトを実行する必要があります。

```
$ git clone https://github.com/ongaeshi/day
$ cd day
$ bundle install
$ ruby ./days_to_posts.rb
$ jekyll serve --watch
```
