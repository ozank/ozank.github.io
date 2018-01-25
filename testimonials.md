---
layout: page
title: Testimonials from students
permalink: /testimonials/index.html
---

## Testimonials

Please wait a few seconds until the publication list is updated. You can also have a look at my [Google Scholar](http://scholar.google.com/citations?user=dzuKyxwAAAAJ&hl=en) and [Mendeley](http://www.mendeley.com/profiles/ozan-keysan/) account.

## deneme

{% assign image_files = site.static_files | where: "image", true %}
{% for myimage in image_files %}
  {{ myimage.path }}
{% endfor %}

## 2014

{% for image in site.static_files %}
    {% if image.path contains './images/evaluation/ee281_2014/' %}
        <a href="{{ site.baseurl }}{{ image.path }}" target="_blank">
            <img src="{{ site.baseurl }}{{ image.path }}" alt="" class="img-thumbnail" />
        </a>
    {% endif %}
{% endfor %}
