---
layout: page
title: bookshelf
permalink: /books/
nav: false
collection: books
---

> I often read books. Sometimes for my work. Sometimes purely out of interest, as a hobby. Sometimes to overcome my own weakness. I'm always glad to get book recommendations.
> To visitors, I recommend "A Gentleman in Moscow" by Amor Towles.

## Books that I am reading, have read, or will read

<!-- prettier-ignore-start -->
<style>
  .book-shelf h1 { color: var(--global-theme-color); }
  .book-shelf ul { display: grid; grid-template-columns: repeat(auto-fill, 136px); gap: 1rem; }
  .book-shelf figure.cover { vertical-align: top; width: 136px; margin: 0; display: flex; flex-direction: column; }
  .book-shelf figure.cover .cover-link { display: flex; flex-direction: column; flex: 1; }
  .book-shelf figure.cover img { width: 136px; height: 200px; object-fit: cover; }
  .book-shelf figure.cover figcaption { margin-top: auto; }
  .book-shelf .cover-meta { width: 0; min-width: 100%; margin: 0.35rem 0 0.25rem; line-height: 1.25; }
  .book-shelf .cover-title { display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; font-size: 0.78rem; font-weight: 600; color: var(--global-text-color); }
  .book-shelf .cover-author { display: block; margin-top: 0.15rem; font-size: 0.7rem; color: var(--global-text-color-light); }
</style>
<div class="book-shelf">
{% assign shelf_year = "" %}
{% for item in site.books reversed %}
{% assign current_year = item.started | date: "%Y" %}
{% if current_year != shelf_year %}
{% unless forloop.first %}</ul>{% endunless %}
<h1 id="y{{ current_year }}">{{ current_year }}</h1>
<ul>
{% assign shelf_year = current_year %}
{% endif %}
<figure class="cover">
<div class="cover-link">
{% if item.cover %}<img alt="{{ item.title }} cover" src="{{ item.cover | relative_url }}?v={{ site.time | date: '%Y%m%d%H%M' }}" style="height:200px">{% elsif item.olid %}<img alt="{{ item.title }} cover" src="https://covers.openlibrary.org/b/olid/{{ item.olid }}-L.jpg?default=false" style="height:200px">{% elsif item.isbn %}<img alt="{{ item.title }} cover" src="https://covers.openlibrary.org/b/isbn/{{ item.isbn }}-L.jpg?default=false" style="height:200px">{% endif %}
<div class="cover-meta"><span class="cover-title">{{ item.title_en | default: item.title }}</span><span class="cover-author">{{ item.author_en | default: item.author }}</span></div>
{% assign status = item.status | downcase | strip %}
{% assign statuses = "abandoned,finished,interested,paused,queued,reading,reread" | split: "," %}
{% if statuses contains status %}<figcaption class="{{ status }}">{{ status | upcase }}</figcaption>{% else %}<figcaption class="uncategorized">UNCATEGORIZED</figcaption>{% endif %}
</div>
</figure>
{% if forloop.last %}</ul>{% endif %}
{% endfor %}
</div>
<!-- prettier-ignore-end -->
