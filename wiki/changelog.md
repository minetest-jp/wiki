---
title: アップデート情報
date: 2018-8-12
---

アップデート内容を大まかにまとめたものです。
細かい変更点は公式Wikiの[Changelog](http://dev.minetest.net/Changelog)や、Githubの[コミットログ](https://github.com/minetest/minetest/commits/stable-0.4)をご覧ください。

- toc
{:toc}

# 0.4.17 -> 0.4.17.1

バグ修正リリースです。

## Minetest

- ポーズメニューで上下キーを押したときにクラッシュする問題を修正

- `void log_deprecated(lua_State*, const string&): A fatal error occured: lua_getstack() failed`のエラーを修正

## API

- chat_send_playerとchat_send_allで送信されるテキストの文字エンコードを修正

# 0.4.16 -> 0.4.17

バグ修正リリースです。

## Minetest

- <a href="commands#shutdown">shutdownコマンド</a>のパラメータが2つ以上の場合にシャットダウンの遅延時間が反映されない問題を修正

- フォントに無効なパスを指定した場合に起動不能になる問題を修正
