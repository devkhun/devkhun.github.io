---
title: "Python"
layout: archive
permalink: categories/python_basic
author_profile: true
sidebar:
  nav: "sidebar-category"
---


{% assign posts = site.categories.python_basic %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
