---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
---

{% for book in site.data.bookfair offset:1 %}
    {% if book.Title %}
<div class="book">
        {% if book.Picture contains "http" %}
<img src="{{ book.Picture }}" alt="Image of {{ book.Title }}">
        {% endif %}
        {% if book.CoopLink %}
<p markdown="1"><i>[{{ book.Title }}]({{ book.CoopLink }})</i> by {{ book.Author}} for {{ book.Price}}</p>
        {% else %}
<p><i>{{ book.Title }}</i> by {{ book.Author}} for {{ book.Price}}</p>
        {% endif %}
</div>
    {% endif %}
{% endfor %}