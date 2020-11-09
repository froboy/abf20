---
layout: page
title: Early Reader
permalink: /early_reader/
---

{% for book in site.data.bookfair offset:1 %}
    {% if book.Title and book.Age == page.title %}
<div class="book">
        {% if book.Picture contains "http" %}
<img src="{{ book.Picture }}" alt="Image of {{ book.Title }}" class="cover">
        {% endif %}
        {% if book.Student %}
<img src="{{ site.baseurl }}/assets/img/student.jpg" alt="This book was recommended by a student." class="icon">
        {% endif %}
        {% if book.Parent %}
<img src="{{ site.baseurl }}/assets/img/parent.png" alt="This book was recommended by a parent." class="icon">
        {% endif %}
        {% if book.Marsha %}
<img src="{{ site.baseurl }}/assets/img/marsha.jpg" alt="This book was recommended by Marsha." class="icon">
        {% endif %}
        {% if book.Award %}
<img src="{{ site.baseurl }}/assets/img/award.png" alt="This book is an award winner." class="icon">
        {% endif %}
        {% if book.CoopLink %}
<p markdown="1"><i>[{{ book.Title }}]({{ book.CoopLink }})</i> by {{ book.Author}} for {{ book.Price}}</p>
        {% else %}
<p><i>{{ book.Title }}</i> by {{ book.Author}} for {{ book.Price}}</p>
        {% endif %}
</div>
    {% endif %}
{% endfor %}