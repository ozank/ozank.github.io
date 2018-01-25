---
layout: page
title: Testimonials from students
permalink: /testimonials/index.html
---

## Testimonials

Please wait a few seconds until the publication list is updated. You can also have a look at my [Google Scholar](http://scholar.google.com/citations?user=dzuKyxwAAAAJ&hl=en) and [Mendeley](http://www.mendeley.com/profiles/ozan-keysan/) account.

burda bir link [deneme](#deneme)

## 2014

{% for i in (1..10) %}

<div class="image">
<img src="../images/evaluation/ee281_2014/file-{{ i }}.jpg" ><br>
</div>


{% endfor %}


{% for image in site.static_files %}
    {% if image.path contains 'ee281_2014/' %}
        <a href="{{ site.baseurl }}{{ image.path }}" target="_blank">
            <img src="{{ site.baseurl }}{{ image.path }}" alt="" class="img-thumbnail" />
        </a>
    {% endif %}
{% endfor %}

## deneme
