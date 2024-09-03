---
title: "Java"
layout: archive
permalink: categories/java_basic
author_profile: true
sidebar:
  nav: "sidebar-category"
---


{% assign posts = site.categories.java_basic %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
