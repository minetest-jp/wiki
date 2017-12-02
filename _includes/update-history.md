{% comment %}
引数: なし
{% endcomment %}

{% comment %}
Markdownの作成
{% endcomment %}
{% capture list %}
  {% comment %}
  全てのページのリストを更新日時でソート
  {% endcomment %}
  {% assign sorted_pages = (site.pages | sort: "date") %}

  {% comment %}
  逆順(新しいものから)でFor実行
  {% endcomment %}
  {% for page in sorted_pages reversed %}
    {% comment %}
    更新日時未記入の場合スキップ
    {% endcomment %}
    {% if page.date == null %}
      {% continue %}
    {% endif %}

    {% comment %}
    日付を書式化
    {% endcomment %}
    {% assign date = (page.date | date: "%Y-%m-%d") %}

    {% comment %}
    日付がループ前のものと一致しない場合
    {% endcomment %}
    {% if date != current_date %}
      {% comment %}
      split用文字
      {% endcomment %}
      {% if current_date %}\\{% endif %}

      {% comment %}
      日付見出し
      {% endcomment %}
      **{{ date }}**

      {% comment %}
      変数のスコープが切れないことを利用
      {% endcomment %}
      {% assign current_date = date %}
    {% endif %}

    {% comment %}
    改行
    {% endcomment %}
    <br>

    {% comment %}
    リンクの挿入
    {% endcomment %}
    [{{ page.title }}]({{ site.github.url }}/{{ page.url }})
  {% endfor %}
{% endcapture %}

{% comment %}
"\\"で区切ったリスト
{% endcomment %}
{% assign lines = (list | split: "\\") %}
{% for line in lines %}
{% comment %}
改行、空白を取り除いて表示
Markdownはインデント不可
{% endcomment %}
{{ line | strip_newlines | strip }}
{% endfor %}
