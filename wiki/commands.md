---
title: コマンド
date:
---

利用できるコマンドの一覧です。
MinetestおよびMinetest Gameで利用できるもののみ掲載しています。

チャットメッセージの先頭に「/」を入力し、その後にコマンドを入力します。
ゲーム中に/キーを押すと「/」が入力された状態でチャット画面が開きます。
また、F10キーで表示できるコンソールから実行することもできます。

- toc
{:toc}

# Minetest

## me

`/me <メッセージ>`

自分のプレイヤー名をメッセージの文頭に挿入し、チャットに送信するコマンド。
[shout権限](privileges#shout)が必要。

## admin

`/admin`

サーバ管理者のプレイヤー名を表示するコマンド。

## help

`/help`

プレイヤーが使用できるコマンドの一覧を表示する。

`/help all`

プレイヤーが使用できるコマンドとその説明を表示する。

`/help privs`

全ての[権限](privileges)を表示する。

`/help <コマンド名>`

指定したコマンドの説明を表示する。

## privs

`/privs`

自分が持っている[権限](privileges)を表示する。

`/privs <プレイヤー名>`

指定したプレイヤーの持つ[権限](privileges)を表示する。

## msg

`/msg <プレイヤー名> <メッセージ>`

指定したプレイヤーにのみメッセージを送信する。
[shout権限](privileges#shout)が必要。

## giveme

`/giveme <アイテム名> <個数>`

指定したアイテムを入手する。
[give権限](privileges#give)が必要。

## give

`/give <プレイヤー名> <アイテム名> <個数>`

指定したプレイヤーに指定したアイテムを与える。
[give権限](privileges#give)が必要。

## pulverize

`/pulverize`

今手に持っているアイテムを削除する。

## teleport

これらは[teleport権限](privileges#teleport)が必要。

`/teleport <x,y,z>`

指定したXYZ座標にテレポートする。

`/teleport <プレイヤー名>`

指定したプレイヤーの場所にワープする。

`/teleport <プレイヤー名> <x,y,z>`

指定したプレイヤーを指定したXYZ座標にテレポートさせる。
[bring権限](privileges#bring)が必要。

`/teleport <プレイヤー名１> <プレイヤー名２>`

プレイヤー名１で指定したプレイヤーをプレイヤー名２で指定したプレイヤーの位置にテレポートさせる。
[bring権限](privileges#bring)が必要。

## setpassword

`/setpassword <プレイヤー名> <パスワード>`

指定したプレイヤーのパスワードを変更する。
[password権限](privileges#password)が必要。

## clearpassword

`/clearpassword <プレイヤー名>`
指定したプレイヤーのパスワードを空にする。
[password権限](privileges#password)が必要。

## grant

`/grant <プレイヤー名> <権限名>`

指定したプレイヤーに[権限](privileges)を与える。
[権限](privileges)名にallと入力すると使用可能なすべての[権限](privileges)が与えられる。
[privs権限](privileges#privs)が必要。

## revoke

`/revoke <プレイヤー名> <権限名>`

指定したプレイヤーから[権限](privileges)を剥奪する。
[権限](privileges)名にallと入力すると削除可能なすべての[権限](privileges)を剥奪する。
[privs権限](privileges#privs)が必要。
※シングルプレイヤーの[権限](privileges)からinteract、shout、basic_privs、privsを外すことはできません。

## kick

`/kick <プレイヤー名> <切断理由>`

指定したプレイヤーをBANし、切断したプレイヤー名では接続できなくなる。
切断理由は切断した相手に伝わる。
[kick権限](privileges#kick)が必要。

## ban

`/ban <プレイヤー名>`

指定したプレイヤーをBANし、切断したプレイヤーのIPでは接続できなくなる。
プレイヤー名を指定しない場合はBANしたプレイヤーの一覧が表示される。
[ban権限](privileges#ban)が必要。

## unban

`/unban [プレイヤー名|IPアドレス]`

指定したプレイヤーのBANを解除する。
[ban権限](privileges#unban)が必要。

## status

`/status`

サーバーの詳細が表示される。

## mods

`/mods`

サーバーで使用されているModの一覧が表示される。

## time

`/time <時間>`

ゲーム内時間を指定した時間に変更する。
0または24000は真夜中、12000は昼になる。
[settime権限](privileges#settime)が必要。

`/set -n time_speed <時間の早さ>`

昼と夜のサイクルの早さを変更する。
標準の早さは72に設定されている。
[server権限](privileges#server)が必要。

## spawnentity

`/spawnentity <エンティティ名>`

指定したエンティティを出現させる。
標準の早さは72に設定されている。
[give権限](privileges#give)と[interact権限](privileges#interact)が必要。

## shutdown

`/shutdown`

サーバーをシャットダウンする。
[server権限](privileges#server)が必要。

## set

これらは[server権限](privileges#server)が必要。

`/set <変数名>`

サーバーのminetest.conf内の変数のパラメータを表示する。

`/set <変数名> <新しい値>`

一時的に変数のパラメータを変更する。

`/set -n <変数名> <値>`

指定した変数名と値で新規パラメータを作成する。

## clearobjects

`/clearobjects`

マップ上の全てのオブジェクトとエンティティを削除する。
ブロックは削除されない。
時間がかかる。。
[server権限](privileges#server)が必要。

## auth_reload

`/auth_reload`

プレイヤーの[権限](privileges)とパスワードを再読み込みする。
[server権限](privileges#server)が必要。

## deleteblocks

これらは[server権限](privileges#server)が必要。

`/deleteblocks here [半径]`

プレイヤーの位置を中心に半径内のマップ変更を元に戻す。
半径を省略した場合はプレイヤーと重なっているブロックが元に戻される。

`/deleteblocks <x,y,z> <x,y,z>`

2つの座標内のマップ変更を元に戻す。

## rollback

これらは[rollback権限](privileges#rollback)が必要。

`/rollback_check <範囲> <秒>`

プレイヤーが行った行動（ブロック破壊など）を確認する。

`/rollback <プレイヤー名> <秒>`

指定したプレイヤーが行った行動を元に戻す。
何秒前か指定すると、指定した秒数より後に行った行動は元に戻る。

`/rollback <アクター名> <秒>`

指定したアクターが行った行動を元に戻す。

## profiler

# Minetest Game

## home

`/home`

設定したホームの位置にテレポートするコマンド。
ホームを設定していない場合は動作しない。
[home権限](privileges#home)が必要。

## sethome

`/sethome`

現在の位置をホームとして設定するコマンド。
[home権限](privileges#home)が必要。
