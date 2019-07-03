<!-- 渡されてきたデータ -->
{% assign data = include.data %}

<!-- 空のリストを作成 -->
{% assign details = "" | split: "|" %}

<!-- 依存Mod -->
{% if data.depends %}
  {% capture depend_list %}
    {% for depend in data.depends %}
      {% if depend.url %}
        <a href="{{ depend.url }}">{{ depend.text }}</a>{% if forloop.last != true %},{% endif %}
      {% else %}
        {{ depend.text }}{% if forloop.last != true %},{% endif %}
      {% endif %}
    {% endfor %}
  {% endcapture %}

  {% assign depends = "" | split: "|" %}
  {% assign depends = depends | push: "依存Mod" %}
  {% assign depends = depends | push: depend_list %}
  {% assign details = details | push: depends %}
{% endif %}

<!-- 対応･連携可能Mod -->
{% if data.depends-optional %}
  {% capture optionally_depend_list %}
    {% for depend in data.depends-optional %}
      {% if depend.url %}
        <a href="{{ depend.url }}">{{ depend.text }}</a>{% if forloop.last != true %},{% endif %}
      {% else %}
        {{ depend.text }}{% if forloop.last != true %},{% endif %}
      {% endif %}
    {% endfor %}
  {% endcapture %}

  {% assign depends_optional = "" | split: "|" %}
  {% assign depends_optional = depends_optional | push: "依存Mod(任意)" %}
  {% assign depends_optional = depends_optional | push: optionally_depend_list %}
  {% assign details = details | push: depends_optional %}
{% endif %}

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
