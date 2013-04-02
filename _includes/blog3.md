[BOX 3](/blog3/index.html)

<ul class="listing">
{% for page in site.hello  %}
  {% capture c %}{{page.category}}{% endcapture %}
  {% capture y %}{{page.date | date:"%Y"}}{% endcapture %}
  
    {% if year != y %}
      {% assign year = y %}
      <li class="listing-seperator">{{ y }}</li>
    {% endif %}
    <li class="listing-item">
      <time datetime="{{ page.date | date:"%Y-%m-%d" }}">{{ page.date | date:"%Y-%m-%d" }}</time>
      <a href="{{ site.url }}{{ page.url }}" title="{{ page.title }}">{{ page.title }}</a>
    </li>
    
{% endfor %}
</ul>