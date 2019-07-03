---
title: よくある質問とトラブルシューティング
#date:
---

- toc
{:toc}

# Modの入れ方がわからない

[Modの導入方法]({{ site.baseurl }}/mod-installing.html)のページをご覧ください。

# Modを入れるとエラーが発生する

有効化しているModのフォルダ名にハイフンや記号が入っていないか確認し、あれば名前から消してください。
<br>
入っていなかったり変更しても動かない場合、Mod自体に問題があると思われます。

# 日本語が入力できない

残念ながらできません。

# 敵・動物がいない

Minetest Gameには実装されていませんが、Modで追加することができます。
<br>
[Mobを追加するModの一覧]({{ site.baseurl }}/content/mob.html)をご覧ください。

# 空の飛び方が分からない

コマンドで`/grantme fly`を実行し、Kキーを押してください。

# ブロックが赤い (Androidなど)

シェーダに対応していません。
設定からシェーダーを無効にしてください。

# 起動しない・ワールドに入れない (Windows)

フォルダ階層に日本語が含まれていると起動できません。ユーザ名が日本語などで対処できない場合はCドライブ直下にMinetestを保存してください。

# 画面の明るさを変えたい

詳細設定メニューの「グラフィック > ゲーム内 > 詳細 > ガンマ」から変更できます。

# TNTの爆破範囲を変えたい

詳細設定メニューの「ゲーム > Minetest Game > TNT radius」から変更できます。

# Minetestの更新方法が分からない (Windows)

古いバージョンから新しいバージョンに以下のファイルとフォルダを移動してください。

<dl>
  <dt>ファイル:</dt>
  <dd>minetest.conf</dd>

  <dt>フォルダ:</dt>
  <dd>
    worlds<br>
    mods (Modを導入している場合)<br>
    textures (テクスチャパックを導入している場合)<br>
    games (サブゲームを導入している場合のみ移動、中のminetest_gameフォルダは移動しない)
  </dd>

  <dt>ファイル:</dt>
  <dd>minetest.conf</dd>
</dl>

# エラーメッセージの一覧

## Failed to enable mod

Modのフォルダ名に記号が入っています。
記号を削除してください。

## Failed to load and run

Modのフォルダ名が間違っているか、Mod自体に不具合があります。

## Generating dummy image

テクスチャが存在しない場合に表示されます。
ゲームプレイに支障はありませんが、一部のグラフィックが正しく表示されない場合があります。

## Unresolved name conflicts for mods

同じ名前のModが複数保存されている際に表示されます。
重複しているModを削除してください。