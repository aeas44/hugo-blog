# ブログ更新の流れ

## 新規ポストの作成

```sh
$ hugo new post/hello-world.md
```

そして `content/post/hello-world.md` をマークダウンで編集する。

## 編集

```sh
$ hugo server -t hugo-hikari-theme --buildDrafts
```

書きかけの記事も含めてローカルにウェブサーバを立ち上げる。

## 記事のビルド

```
$ hugo -D -t hugo-hikari-theme
```

`public` の下にビルド結果が保存される。

## GitHub Pages への反映

`public` ディレクトリを `aeas44.github.io` リポジトリに移して `git push` する。
