---
title: トップページ
date: 2017-12-2
custom-style: >-
  .center {
    text-align: center;
  }
  .news {
    color: #fff;
    background-color: #808080;
  }
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

**Minetest JP Wikiへようこそ。**
このサイトは[Minetest](http://www.minetest.net)の**非公式**Wikiです。旧Wikiはこちらからアクセスできます: [minetest.wiki.fc2.com](http://minetest.wiki.fc2.com/)
{:class="center"}

**お知らせ: (2017/12/2) WikiをGithub Pagesに移行しました。**
{:class="center news"}

現在の最新バージョンは{{ site.minetest.latest_version }}です。アップデートの内容は[アップデート情報](changelog)をご覧ください。
{:class="center"}

# Minetestとは？
[Minetest](http://www.minetest.net)は[Minecraft](https://minecraft.net)風のサンドボックス系フリーゲームです。ブロックで建築したり、洞窟を探検したり、作物を育てたりと、広い世界で自由に遊ぶことができます。
また、MinetestはModに対応しています。Modにはブロックを追加するものからワールド全体を変えるものまで、様々なものがあります。その他の拡張要素として、テクスチャパックとサブゲームがあります。
