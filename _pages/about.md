---
permalink: /
title: 
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm a PhD candidate in the Department of Economics at University College London (UCL). 

I study applied microeconomics of scientific and technological innovations. 

My PhD advisors are [Hyejin Ku](https://sites.google.com/site/hyejku/) and [Ben Deaner](https://bendeaner.wordpress.com/). I am affiliated with the [Centre for Research and Analysis of Migration (CReAM)](https://www.cream-migration.org/).

Please find my CV [here](/files/cv.pdf). 

Work in progress
======
{% assign working_papers = site.publications | sort: "date" | reverse %}
{% for post in working_papers %}
{% if post.paperurl and post.paperurl != blank %}
### <a href="{{ post.paperurl }}">{{ post.title }}</a>
{% else %}
### {{ post.title }}
{% endif %}

{% if post.venue or post.date %}
*{% if post.venue %}{{ post.venue }}{% if post.date %}, {% endif %}{% endif %}{% if post.date %}{{ post.date | date: "%Y" }}{% endif %}*
{% endif %}

{% if post.coauthors and post.coauthors.size > 0 %}
<p><em>with {% for coauthor in post.coauthors %}{% if coauthor.url and coauthor.url != blank %}<a href="{{ coauthor.url }}">{{ coauthor.name }}</a>{% else %}{{ coauthor.name }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}</em></p>
{% endif %}

{% if post.excerpt and post.excerpt != blank %}
<details>
  <summary class="btn btn--small">Show abstract</summary>

  {{ post.excerpt | markdownify }}
</details>
{% endif %}

{% endfor %}

