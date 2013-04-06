**[Box 1](/box001/index.html)**

<ul class="listing">
{% for post in site.posts %}
  {% capture b %}{{ post.box }}{% endcapture %}
  {% capture y %}{{ post.date | date:"%Y" }}{% endcapture %}
  {% if b == "box001" %}
    {% if year != y %}
      {% assign year = y %}
      <li class="listing-seperator">{{ y }}</li>
    {% endif %}
    <li class="listing-item">
      <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time> <br/>
      <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endif %}
{% endfor %}
{% assign year = "0" %}
</ul>

All Pages with YAML and title

<ul class="listing">
{% for x in site.pages %}
    <li class="listing-item">
      <a href="{{ site.url }}{{ x.url }}" title="{{ x.title }}">{{ x.title }}</a>
    </li>
{% endfor %}
</ul>

All Pages with YAML url only

<ul class="listing">
{% for x in site.pages %}
    <li class="listing-item">
      {{ x.url }}
    </li>
{% endfor %}
</ul>