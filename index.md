---
layout: worksheet
title: Welcome
---

## Visual Reactive Programming with Bonsai

This training course will introduce you to the basic concepts of data acquisition and behavioural control using the [Bonsai](http://bonsai-rx.org/){:target="_blank"} visual programming language.

## Slides

{% for page in site.pages %}
{% if page.layout == "slides" %}
[{{ page.title }}]({{ page.url | prepend: site.baseurl }})
{% endif %}
{% endfor %}

## Worksheets

[Manual](https://bonsai-rx.org/docs/articles/installation.html)

[Tutorials](https://bonsai-rx.org/docs/tutorials/acquisition.html)