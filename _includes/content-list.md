{% comment %}
引数:
  list: 表示するデータのリスト
    キー: アンカー名
    値: データ:
      name: データ名
{% endcomment %}

<!-- 全アンカー名をスペース区切りで結合 -->
{% capture anchors %}
{% for data in include.list %} {{ data[0] }} {% endfor %}
{% endcapture %}

<!-- anchorsを空白で区切ってソート -->
{% assign sorted-anchors = anchors | split: " " | sort %}

<!-- ソートしたアンカー順でリスト展開 -->
<!-- NOTE: Markdownはインデントできないのでforの中身はインデントなし -->
{% for anchor in sorted-anchors %}
{% assign content-data = include.list[anchor] %}
# {{ content-data.name }} {#{{ anchor }}}
{% include content.md data=content-data %}
{% endfor %}
