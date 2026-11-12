---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
sitemap: false
---

{% include base_path %}

{% for post in site.pages %}
  {% if post.title and post.sitemap != false %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

{% if site.posts.size > 0 %}
<h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}
{% endif %}

{% for collection in site.collections %}
  {% unless collection.output == false or collection.label == "posts" or collection.docs.size == 0 %}
<h2>{{ collection.label | capitalize }}</h2>
  {% for post in collection.docs %}
    {% include archive-single.html %}
  {% endfor %}
  {% endunless %}
{% endfor %}
