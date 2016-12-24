---
layout: page
title: Category
share: false
comment: false
description: "Etiketlerine göre sınıflandırılmış gönderiler."
---

{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
<!-- site_tags: {{ site_tags }} -->
{% assign tag_words = site_tags | split:',' | sort %}
<!-- tag_words: {{ tag_words }} -->

<div id="tags">
  <ul class="tags">
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] | strip_newlines }}{% endcapture %}
    <li><a href="#{{ this_word | cgi_escape }}" class="tag">{{ this_word }} ({{ site.tags[this_word].size }})</a></li>
  {% endunless %}{% endfor %}
  </ul>

  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] | strip_newlines }}{% endcapture %}
  <h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>
  {% for post in site.tags[this_word] %}{% if post.title != null %}
  <a href="{{ post.url }}">{{ post.title }}</a><br>
  {% endif %}{% endfor %} 
  <br/><br/>
  <br/>
  {% endunless %}{% endfor %}
</div>
