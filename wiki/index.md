---
title: トップページ
date: 2018-4-18
custom-style: >-
  .carousel {
    margin: auto;
    max-width: 500px;
    max-height: 380px;
  }
custom-head: >-
  <script async custom-element="amp-carousel" src="https://cdn.ampproject.org/v0/amp-carousel-0.1.js"></script>
---

<div class="carousel">
  <amp-carousel type="slides" layout="responsive" autoplay loop delay="2000" width="500" height="380">
    <amp-img layout="fill" src="{{ site.wiki.images_dir }}/screenshot/1.png"></amp-img>
    <amp-img layout="fill" src="{{ site.wiki.images_dir }}/screenshot/2.png"></amp-img>
  </amp-carousel>
</div>

# このサイトについて

このサイトは[Minetest](http://www.minetest.net)の**非公式**Wikiです。  
旧Wikiはこちらからアクセスできます: [minetest.wiki.fc2.com](http://minetest.wiki.fc2.com/)

# Minetestとは？

[Minetest](http://www.minetest.net)は、InfiniMinerや[Minecraft](https://minecraft.net)に似たフリーゲームです。
ソースコードは[GitHub](https://github.com/minetest/minetest)にあり、LGPLライセンスのもとで公開されています。

Minetestは厳密にはゲームエンジンであり、Minetest Gameと呼ばれるゲームが同梱されています。
Minetest Gameでは、ブロックで建築したり、洞窟を探検したり、作物を育てたりできます。
公式フォーラムではMinetest Game以外のゲームも配布されています。

MinetestはModとテクスチャパックに対応しています。
Modにはブロックを追加するものからワールド全体を変えるものまで様々です。
このWikiのModリストや、公式フォーラムから探してみましょう。

現在のMinetestのバージョンは{{ site.minetest.latest_version }}です。アップデートの内容は[アップデート情報](changelog)をご覧ください。
