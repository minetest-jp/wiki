{% comment %}
引数:
  screenshot: スクリーンショット画像名
  details: 情報のリスト
    キー: <dt>に表示される見出し
    値: <dd>に表示される説明
{% endcomment %}

<p>
  {% comment %}
  スクリーンショット
  {% endcomment %}
  {% if include.screenshot %}
    {% comment %}
    スクリーンショット画像のパス
    {% endcomment %}
    {% assign screenshot = (site.github.url | append: "/images" | append: include.screenshot) %}
    <amp-img
      class  = "screenshot"
      layout = "responsive"
      height = "1"
      width  = "2"
      alt    = "スクリーンショット"
      src    = "{{ screenshot }}"
      tabindex>
    </amp-img>
  {% endif %}

  {% comment %}
  詳細情報
  {% endcomment %}
  <dl>
    {% for detail in include.details %}
      <dt>{{ detail[0] }}</dt>
      <dd>{{ detail[1] }}</dd>
    {% endfor %}
  </dl>
</p>
