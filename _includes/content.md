<!-- 渡されてきたデータ -->
{% assign data = include.data %}

{% if data.screenshot %}
  {% capture IMAGE_DIR %}{{ site.baseurl }}/{{ site.wiki.img_dir }}{% endcapture %}
  {% assign IMAGE_ALT = "スクリーンショット" %}
  {% assign screenshot = IMAGE_DIR | append: data.screenshot %}
  <amp-img
    class  = "screenshot"
    layout = "responsive"
    height = "1"
    width  = "2"
    alt    = "{{ IMAGE_ALT }}"
    src    = "{{ screenshot }}"
    tabindex>
  </amp-img>
{% endif %}

<dl>
  {% if data.platform %}
    <dt>プラットフォーム</dt>
    <dd>{{ data.platform }}</dd>
  {% endif %}

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

    <dt>依存Mod</dt>
    <dd>{{ depend_list }}</dd>
  {% endif %}

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

    <dt>依存Mod(任意)</dt>
    <dd>{{ optionally_depend_list }}</dd>
  {% endif %}

  {% if data.author %}
    <dt>開発者・製作者</dt>
    <dd>{{ data.author }}</dd>
  {% endif %}

  {% if data.description %}
    <dt>説明</dt>
    <dd>{{ data.description }}</dd>
  {% endif %}

  {% if data.links %}
    {% capture link_list %}
      {% for link_data in data.links %}
        {% if forloop.first != true %}/{% endif %}
        {% assign url = link_data.url | replace: "%BASEURL%", site.baseurl %}
        <a href="{{ url }}">{{ link_data.text }}</a>
      {% endfor %}
    {% endcapture %}

    <dt>リンク</dt>
    <dd>{{ link_list }}</dd>
  {% endif %}
</dl>
