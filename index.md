---
layout: page
title: Hitting the Foul Pole
tagline: Your new favorite Twins blog
---
{% include JB/setup %}

{% for node in site.posts limit:5 %}
<h2><a href="{{BASE_PATH}}{{node.url}}">{{node.title}}</a> <small>{{node.date | date_to_string}} {%if node.author%}by {{node.author}}{%endif%}</small></h2>
{{node.content}}
<hr />
{% endfor %}

