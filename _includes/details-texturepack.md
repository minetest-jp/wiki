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
製作者
{% endcomment %}
{% assign author = "" | split: "|" %}
{% assign author = author | push: "製作者" %}
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
