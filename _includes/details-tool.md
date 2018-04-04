{% comment %}
  引数:
    data_list: データ
{% endcomment %}

{% assign details = "" | split: "|" %}
{% assign data = include.data_list %}

{% comment %}
リンク
{% endcomment %}
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
プラットフォーム
{% endcomment %}
{% if data.platform %}
  {% assign platform = "" | split: "|" %}
  {% assign platform = platform | push: "プラットフォーム" %}
  {% assign platform = platform | push: data.platform %}
  {% assign details = details | push: platform %}
{% endif %}

{% comment %}
テンプレートをインクルード
{% endcomment %}
{% include details.md
  screenshot = data.screenshot
  details = details
%}
