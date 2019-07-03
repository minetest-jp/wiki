{% comment %}
引数:
  type: 表示するコンテンツの種類
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

<!-- detailsタイプからテンプレートファイル名を作成 -->
{% capture template-name %}content-{{ include.type }}.md{% endcapture %}

<!-- ソートしたアンカー順でリスト展開 -->
<!-- NOTE: Markdownはインデントできないのでforの中身はインデントなし -->
{% for anchor in sorted-anchors %}
# {{ include.list[anchor].name }} {#{{ anchor }}}
{% include {{ template-name }} list=include.list key=anchor %}
{% endfor %}
