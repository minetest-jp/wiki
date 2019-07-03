---
title: アップデート情報
date: 2019-7-3
---

公式Wikiに記載されてあるアップデート内容を大まかにまとめたものです。
細かい変更点は公式Wikiの[Changelog](http://dev.minetest.net/Changelog)や、Githubの[コミットログ](https://github.com/minetest/minetest/commits/stable-0.4)をご覧ください。

- toc
{:toc}

# 5.0.1 (2019/3/31リリース)

主にエンジン周りのバグを修正したリリースです。

# 5.0.0 (2019/3/5リリース)

メジャーアップデートです。0.4.xとのネットワーク互換性はありません。また従来のModの一部が正しく動かなくなっている場合があります。

今回からバージョン表記が`メジャーアップデート.マイナーアップデート.バグ修正アップデート`になりました。

## マップ

- Carpathianマップジェネレータが追加されました。

## 操作

- 自動ジャンプ機能が追加されました。

- Android: 操作が十字キーからジョイスティックに変更されました。

## インターフェイス

- 「サブゲーム」が「ゲーム」に名称変更されました。

- ゲーム･Mod･テクスチャパックをオンラインで検索･導入できる機能が追加されました。メインメニュー内「コンテンツ」タブから利用できます。

## コマンドと権限

- hasprivコマンドとkillコマンドが追加されました。

- zoom権限が削除されました。

## グラフィック･サウンド

- 雲の中でFogが濃くなるようになりました。

- 腕に慣性が付くようになりました。

- ブロックの落下する音が追加されました。

- 液体の中を歩く音が追加されました。

- ミュート設定が追加されました。

## 開発者向け

以下の変更点はほんの一部です。公式Wikiの[Changelog](http://dev.minetest.net/Changelog)を確認することを推奨します。

- ゲームやMod内のテキストの多言語対応ができるようになりました。

- [Formspecのテーマ機能が追加されました。](https://forum.minetest.net/viewtopic.php?t=20646)

- `minetest.env`名前空間が廃止されました。代わりに`minetest`名前空間を使用してください。

- `nodeupdate`が廃止されました。代わりに`minetest.check_for_falling`を使用してください。

- depends.txtとdescription.txtが非推奨になりました。代わりにmod.confやgame.confを使用してください。

- modpack.txtが非推奨になりました。代わりにmodpack.confを使用してください。

- [ObjectRefの一部のメンバ関数名が変更されました。](https://github.com/minetest/minetest/commit/63c892e)

- `player:get/set_attribute`が非推奨になりました。代わりに`player:get_meta`を使用してください。

# 0.4.17.1

バグ修正リリースです。

## Minetest

- ポーズメニューで上下キーを押したときにクラッシュする問題を修正

- `void log_deprecated(lua_State*, const string&): A fatal error occured: lua_getstack() failed`のエラーを修正

## API

- chat_send_playerとchat_send_allで送信されるテキストの文字エンコードを修正

# 0.4.17

バグ修正リリースです。

## Minetest

- <a href="commands#shutdown">shutdownコマンド</a>のパラメータが2つ以上の場合にシャットダウンの遅延時間が反映されない問題を修正

- フォントに無効なパスを指定した場合に起動不能になる問題を修正
