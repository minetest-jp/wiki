{% comment %}
引数:
  type: 表示するdetailsの種類
  list: 表示するデータのリスト
    キー: アンカー名
    値: データ:
      name: データ名
{% endcomment %}

{% comment %}
アンカー名でソートする
{% endcomment %}

{% comment %}
全てのアンカー名を一つの文字列にする
{% endcomment %}
{% capture keys %}
  {% for data in include.list %}
    {{ data[0] }}
  {% endfor %}
{% endcapture %}

{% comment %}
アンカー名を空白で区切ってソートする
{% endcomment %}
{% assign sorted_keys = (keys | split: " " | sort) %}

{% comment %}
使用するテンプレートファイル名
{% endcomment %}
{% capture template %}details-{{ include.type }}.md{% endcapture %}

{% comment %}
ソートしたアンカーリストでFor実行
{% endcomment %}
{% for key in sorted_keys %}
  {% comment %}
  assignした変数はinclude先でも参照できる
  アンカー名で参照
  {% endcomment %}
  {% assign data = include.list[key] %}

  {% comment %}
  Markdownはインデント不可
  {% endcomment %}
# {{ data.name }} {#{{ key }}}

  {% comment %}
  テンプレートを表示
  同じくインデント不可
  {% endcomment %}
{% include {{ template }} %}
{% endfor %}
