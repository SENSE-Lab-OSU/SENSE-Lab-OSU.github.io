---
title: Reference
permalink: /resources/
---


{% assign reference_types = "researchers|students" | split: "|" %}

{% for type in reference_types %}

{% if type == 'researchers' %}
### **For researchers**
 {% elsif type == 'students' %}
### **For students and lab members**
{% endif %}

<div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains type %}
    <div class="list-item">
      <p class="list-post-title">
        <a href="{{ site.baseurl }}{{ post.url }}">- {{ post.title }}</a>
      </p>
    </div>
    {% endif %}
  {% endfor %}
</div>

<hr>
{% endfor %}

### **Useful Blog posts from [Kording Lab](http://kordinglab.com/)**

<div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains 'kording' %}
    <div class="list-item">
      <p class="list-post-title">
        <a href="{{ site.baseurl }}{{ post.url }}">- {{ post.title }}</a> (<small>{{post.date | date: "%m/%d/%y" }}</small>)
      </p>
    </div>
    {% endif %}
  {% endfor %}
</div>

<hr>
