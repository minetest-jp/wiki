{% comment %}
  引数:
    limit: 表示する日付数
{% endcomment %}

{% assign groups = site.pages | where_exp: "item", "item.date != null" | group_by: "date" | sort: "name" | reverse %}
{% for group in groups limit: include.limit %}
<p>
  <strong>{{ group.name | date: "%Y-%m-%d" }}</strong>
  {% for item in group.items %}
    <br><a href="{{ item.url | remove_first: "/" }}">{{ item.title }}</a>
  {% endfor %}
</p>
{% endfor %}
