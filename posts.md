---
title: Posts
layout: default
permalink: /posts/
---

<style>

a {
  text-decoration: none;
  color: #002145;
}

a:hover {
  color: #97D4E9;
  text-decoration: none !important;
  cursor: pointer;
  margin: auto
}

#div-style {
  width: 100%; 
  display:inline-block;
  float:left;
  text-align: center;
  font-size: 25px;
}

</style>

<!-- New Post -->

{% for post in site.posts %}
<div id="div-style">
    <a href="/~jsefas{{ post.url }}">
    {% assign words = post.title | replace: '_', ' ' | split: ' ' %} 
    {% capture titlecase %}{% for word in words %}{{ word | capitalize | append: ' ' }}{% endfor %}{% endcapture %}
    {{ titlecase }}
    </a>
    <span style="color:gray"> - {{ post.date | date: "%a, %d %B %Y" }} </span>
</div>
{% endfor %}
