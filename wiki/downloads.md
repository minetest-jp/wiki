---
title: ダウンロード
date: 2018-03-01
custom-style: >-
  .red {color: #FF0000}
---
{% comment %}短縮{% endcomment %}
{% assign version = site.minetest.latest_version %}

Minetestの最新バージョン({{ version }})をダウンロードできます。

- toc
{:toc}

# Windows

[64bit版](https://github.com/minetest/minetest/releases/download/{{ version }}/minetest-{{ version }}-win64.zip)  
[32bit版 (MinGW)](https://github.com/minetest/minetest/releases/download/{{ version }}/minetest-{{ version }}-win32-mingw.zip)  
[32bit版 (MSVC)](https://github.com/minetest/minetest/releases/download/{{ version }}/minetest-{{ version }}-win32-msvc.zip)

# macOS

[Homebrew](http://brew.sh)を導入している場合は`brew install homebrew/games/minetest`でもインストールできます。

[安定版](https://github.com/krondor-game/minetest/releases/tag/stable)  
[最新版](https://github.com/krondor-game/minetest/releases)

# Linux

[Debian](https://packages.debian.org/search?keywords=minetest)  
[Ubuntu / Linux Mint](http://packages.ubuntu.com/search?keywords=minetest)  
[Ubuntu / Linux Mint (PPA)](https://launchpad.net/~minetestdevs/+archive/ubuntu/stable)  
[Fedora](https://apps.fedoraproject.org/packages/minetest)  
[openSUSE](http://software.opensuse.org/package/minetest)  
[Mageia](http://mageia.madb.org/package/show/name/minetest)  
[Arch Linux](https://www.archlinux.org/packages/?q=minetest)  
[Gentoo](http://packages.gentoo.org/package/games-action/minetest)

Git･デイリービルド  
[Arch Linux](https://aur.archlinux.org/packages/minetest-git)  
[Arch Linux (leveldb)](https://aur.archlinux.org/packages/minetest-git-leveldb)  
[Ubuntu / Linux Mint](https://code.launchpad.net/~minetestdevs/+archive/daily-builds/+packages)

# Android

注意: 海賊版がGoogle Playに出回っているようです。
{: class="red"}

[Google Play](https://play.google.com/store/apps/details?id=net.minetest.minetest)  
[F-Droid](https://f-droid.org/repository/browse/?fdid=net.minetest.minetest)

# その他のプラットフォーム

[FreeBSD](http://www.freshports.org/games/minetest)

# ソースコード

[Minetest](https://github.com/minetest/minetest/archive/master.zip)  
[Minetest Game](https://github.com/minetest/minetest_game/archive/master.zip)
