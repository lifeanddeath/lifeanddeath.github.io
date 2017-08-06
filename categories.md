---
layout: page
title: Categories
---
{% comment %}
=======================
The purpose of this snippet is to list all the tags you have in your site.
=======================
{% endcomment %}
{% for tag in tags %}
	<a href="#{{ tag | slugify }}"> {{ tag }} </a>
{% endfor %}



{% comment %}
=======================
The purpose of this snippet is to list all your posts posted with a certain tag.
=======================
{% endcomment %}
{% for tag in tags %}
	<h2 id="{{ tag | slugify }}">{{ tag }}</h2>
	<ul>
	 {% for post in site.posts %}
		 {% if post.tags contains tag %}
		 <li>
		 <h3>
		 <a href="{{ post.url }}">
		 {{ post.title }}
		 <small>{{ post.date | date_to_string }}</small>
		 </a>
		 {% for tag in post.tags %}
			 <a class="tag" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
		 {% endfor %}
		 </h3>
		 </li>
		 {% endif %}
	 {% endfor %}
	</ul>
{% endfor %}












<div class="tags-expo">
  <div class="tags-expo-list">
    {% for tag in site.categories %}
    <a href="#{{ tag[0] | slugify }}" class="post-tag">{{ tag[0] }}</a>
    {% endfor %}
  </div>
  <hr/>
  <div class="tags-expo-section">
    {% for tag in site.categories %}
    <h2 id="{{ tag[0] | slugify }}">{{ tag[0] }}</h2>
    <ul class="tags-expo-posts">
      {% for post in tag[1] %}
        <a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
      <li>
        {{ post.title }}
      <small class="post-date">{{ post.date | date_to_string }}</small>
      </li>
      </a>
      {% endfor %}
    </ul>
    {% endfor %}
  </div>
</div>
