{% comment %}
  引数:
    type: 表示するdetailsの種類
    list: 表示するデータのリスト
      キー: アンカー名
      値: データ:
        'name': データ名
{% endcomment %}

{% capture template_name %}details-{{ include.type }}.md{% endcapture %}
{% capture keys %}
  {% for data in include.list %}
    {{ data[0] }}
  {% endfor %}
{% endcapture %}

{% assign sorted_keys = keys | split: " " | sort %}
{% for key in sorted_keys %}
{% assign data = include.list[key] %}

# {{ data.name }} {#{{ key }}}

{% include {{ template_name }}
  data_list = include.list[key]
%}
{% endfor %}
