<!-- 渡されてきたデータ -->
{% assign data = include.data %}

<!-- 空のリストを作成 -->
{% assign details = "" | split: "|" %}

<!-- 開発者 -->
{% if data.author %}
  {% assign author = "" | split: "|" %}
  {% assign author = author | push: "開発者" %}
  {% assign author = author | push: data.author %}
  {% assign details = details | push: author %}
{% endif %}

<!-- 説明 -->
{% if data.description %}
  {% assign description = "" | split: "|" %}
  {% assign description = description | push: "説明" %}
  {% assign description = description | push: data.description %}
  {% assign details = details | push: description %}
{% endif %}

<!-- リンク -->
{% if data.links %}
  {% capture link_list %}
    {% for link_data in data.links %}
      {% if forloop.first != true %}/{% endif %}
      <a href="{{ link_data.url }}">{{ link_data.text }}</a>
    {% endfor %}
  {% endcapture %}

  {% assign links = "" | split: "|" %}
  {% assign links = links | push: "リンク" %}
  {% assign links = links | push: link_list %}
  {% assign details = details | push: links %}
{% endif %}

<!-- テンプレートをインクルード -->
{% include content.md screenshot=data.screenshot details=details %}
