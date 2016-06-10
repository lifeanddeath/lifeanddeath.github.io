---
layout: post
title: First Post ! :)
category: General
tags: [general]
---

My new official website has just been opened ! <br>
Good luck to everyone 10.06.2016 ! :)




{% comment %}
=======================
The purpose of this snippet is to list all the tags you have in your site.
=======================
{% endcomment %}
{% for tag in tags %}
	<a href="#{{ tag | slugify }}"> {{ tag }} </a>
{% endfor %}

