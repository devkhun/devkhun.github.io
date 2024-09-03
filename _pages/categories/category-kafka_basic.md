---
title: "Kafka"
layout: archive
permalink: categories/kafka_basic
author_profile: true
sidebar:
  nav: "sidebar-category"
---


{% assign posts = site.categories.kafka_basic %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
