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
テンプレートをインクルード
{% endcomment %}
{% include details.md
  screenshot = data.screenshot
  details = details
%}
