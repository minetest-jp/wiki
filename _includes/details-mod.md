{% comment %}
引数: なし (assignされたdata変数を参照)
{% endcomment %}

{% comment %}
空のリストを作成
{% endcomment %}
{% assign details = "" | split: "|" %}

{% comment %}
リンク
{% endcomment %}
{% if data.links %}
  {% capture link_list %}
    <nav>
      {% for link_data in data.links %}
        {% if forloop.first != true %}/{% endif %}
        <a href="{{ link_data.url }}">{{ link_data.text }}</a>
      {% endfor %}
    </nav>
  {% endcapture %}

  {% assign links = "" | split: "|" %}
  {% assign links = links | push: "リンク" %}
  {% assign links = links | push: link_list %}
  {% assign details = details | push: links %}
{% endif %}

{% comment %}
開発者
{% endcomment %}
{% assign author = "" | split: "|" %}
{% assign author = author | push: "開発者" %}
{% assign author = author | push: data.author %}
{% assign details = details | push: author %}

{% comment %}
説明
{% endcomment %}
{% assign description = "" | split: "|" %}
{% assign description = description | push: "説明" %}
{% assign description = description | push: data.description %}
{% assign details = details | push: description %}

{% comment %}
依存Mod
{% endcomment %}
{% if data.depends %}
  {% capture depend_list %}
    <nav>
      {% for depend in data.depends %}
        {% if depend.url %}
          <a href="{{ depend.url }}">{{ depend.text }}</a>{% if forloop.last != true %},{% endif %}
        {% else %}
          {{ depend.text }}{% if forloop.last != true %},{% endif %}
        {% endif %}
      {% endfor %}
    </nav>
  {% endcapture %}

  {% assign depends = "" | split: "|" %}
  {% assign depends = depends | push: "依存Mod" %}
  {% assign depends = depends | push: depend_list %}
  {% assign details = details | push: depends %}
{% endif %}

{% comment %}
対応･連携可能Mod
{% endcomment %}
{% if data.depends-optional %}
  {% capture optionally_depend_list %}
    <nav>
      {% for depend in data.depends-optional %}
        {% if depend.url %}
          <a href="{{ depend.url }}">{{ depend.text }}</a>{% if forloop.last != true %},{% endif %}
        {% else %}
          {{ depend.text }}{% if forloop.last != true %},{% endif %}
        {% endif %}
      {% endfor %}
    </nav>
  {% endcapture %}

  {% assign depends_optional = "" | split: "|" %}
  {% assign depends_optional = depends_optional | push: "依存Mod(任意)" %}
  {% assign depends_optional = depends_optional | push: optionally_depend_list %}
  {% assign details = details | push: depends_optional %}
{% endif %}

{% comment %}
テンプレートをインクルード
{% endcomment %}
{% include details.md
  screenshot = data.screenshot
  details = details
%}
