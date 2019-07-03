---
title: トップページ
date: 2019-3-27
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
    <amp-img layout="fill" src="{{ site.wiki.img_dir }}/screenshot/1.png"></amp-img>
    <amp-img layout="fill" src="{{ site.wiki.img_dir }}/screenshot/2.png"></amp-img>
  </amp-carousel>
</div>

# このサイトについて

このサイトは[Minetest](http://www.minetest.net)の**非公式**Wikiです。

# Minetestとは？

**Minetest** (マインテスト) は、[InfiniMiner](http://www.zachtronics.com/infiniminer)や[Minecraft](https://www.minecraft.net/ja-jp)に似た[オープンソース](https://ja.wikipedia.org/wiki/オープンソース)のフリーゲームです。
ソースコードは[GitHub](https://github.com/minetest/minetest)にあり、[LGPLライセンス](https://ja.wikipedia.org/wiki/GNU_Lesser_General_Public_License)のもとで公開されています。

Minetestは**厳密にはゲームエンジン**であり、**Minetest Game**と呼ばれるゲームが同梱されています。
Minetest Gameでは、ブロックで建築したり、洞窟を探検したり、作物を育てたりできます。
[公式フォーラム](https://forum.minetest.net)ではMinetest Game以外のゲームも配布されています。

Minetestは**Modとテクスチャパックに対応**しています。
Modにはブロックを追加するものからワールド全体を変えるものまで様々です。
このWikiのModリストや、[公式フォーラム](https://forum.minetest.net)から探してみましょう。

現在のMinetestのバージョンは**{{ site.minetest.latest_version }}**です。アップデートの内容は[アップデート情報]({{ site.baseurl }}/changelog.html)をご覧ください。
