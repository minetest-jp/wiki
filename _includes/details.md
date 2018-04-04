{% comment %}
  引数:
    screenshot: スクリーンショット画像名
    details: 情報のリスト
      キー: <dt>に表示される見出し
      値: <dd>に表示される説明
{% endcomment %}

{% assign IMAGE_DIR = site.github.url | append: "/images" %}
{% assign IMAGE_ALT = "スクリーンショット" %}

<p>
  {% if include.screenshot %}
    {% assign screenshot = IMAGE_DIR | append: include.screenshot %}
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
    {% for detail in include.details %}
      <dt>{{ detail[0] }}</dt>
      <dd>{{ detail[1] }}</dd>
    {% endfor %}
  </dl>
</p>
