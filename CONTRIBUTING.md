# 編集

編集方法とガイドラインです。

- [コミットについて](#コミットについて)
- [Markdownの構文について](#markdownの構文について)
- [目次の追加](#目次の追加)
- [ページ更新日について](#ページ更新日について)
- [YAML Front Matterで利用できる独自のパラメータについて](#yaml-front-matterで利用できる独自のパラメータについて)
- [Modリスト/ツールリスト/テクスチャパック/サブゲーム/配布マップの追加方法について](#modリストツールリストテクスチャパックサブゲーム配布マップの追加方法について)
- [修正の提案、TODOについて](#修正の提案todoについて)
- [紹介する動画について](#紹介する動画について)


## コミットについて

Forkしたリポジトリからプルリクエストを行ってください。

[minetest-jp](https://github.com/minetest-jp)のメンバーは直接コミットしていただいても構いません。

## Markdownの構文について

基本的にGithubと同じ書式です。

ただし、以下の違いがあります。

- Markdown要素内にHTML要素を書けます。
 - 例えば、Markdownのコードブロック(\`\`\`~\`\`\`)内にHTML要素を書いた場合もHTML要素として認識されます。(但し、HTMLブロック内でMarkdown構文は使用できません)

## 目次の追加

目次を追加したい場所に以下を挿入してください。
```
- toc
{:toc}
```

## ページ更新日について

ページ更新の際はYAML Front Matterにdate(更新日)を書いていただけるとありがたいです。
YAML Front Matterで利用できる独自パラメータについては後述します。

## YAML Front Matterで利用できる独自のパラメータについて

<dl>
  <dt>date</dt>
  <dd>
    更新日時です。20XX-XX-XXのように記述します。<br>
    例: 2112-9-3, 2038-1-19, 2000-11-2
  </dd>

  <dt>custom-style</dt>
  <dd>追加のCSSです。そのページでのみ使用されるCSSはここに記述します。</dd>

  <dt>custom-head</dt>
  <dd>追加のヘッダです。そのページでのみ使用されるscriptタグなどはここに記述します。</dd>
</dl>

## Modリスト/ツールリスト/テクスチャパック/サブゲーム/配布マップの追加方法について

`_data`内にあるページ名と同名のフォルダにymlファイルを追加します。スクリーンショットは`images`内の同名フォルダに追加します。
ファイル名がソートに使用されます。ファイル名にハイフンは使用できません。

書式は以下の通りです。
```yml
# 名前
name: "Hogehoge Mod"

# 作者名
author: "hogehoger"

# スクリーンショットのパス
# imagesフォルダからのパスを指定します。
screenshot: "/mods-decor/hogehoge.png"

# プラットフォーム名 (ツールのみ使用可能)
platform: "Windows / Linux"

# 説明文
# HTMLも使用できます。
description: "hogehogeを追加するModです。"

# 関連リンクリスト
# フォーラムへのリンクやダウンロードリンクなど。
links:
  -
    text: "フォーラム"
    url:  "https://forum.minetest.net"
  -
    text: "ダウンロード"
    url:  "https://github.com/"

# 依存Modリスト (Modのみ使用可能)
depends:
  -
    text: "TU-KA Mod"
    url:  "mods-decor#tu_ka" # Wiki内へのリンクも使用可能です。
  -
    text: "FooBarMod"
    url:  "https://forum.minetest.net"

# 連携可能/対応Modリスト (Modのみ使用可能)
depends_optional:
  -
    text: "Piyopiyo Mod"
    url:  "mods-decor#piyopiyo"
  -
    text: "42"
    url:  "https://forum.minetest.net"
```

## 修正の提案、TODOについて

GithubのProjectsにあるTODOリストに追加していただけるとありがたいです。

## 紹介する動画について

動画紹介に載せる動画は掲載許可を取ったもののみでお願いいたします。
