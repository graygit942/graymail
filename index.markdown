---
layout: home
---

Welcome to My Home Page, Website is still being built.

{% assign date = '2026-04-16 14:54:00' %}

- Original date - {{ date }}
- Creation date - {{ date | timeago }}

---

## Posts by Category

{% if site.posts.size > 0 %}
  {% assign sorted_categories = site.categories | sort %}
  {% for category in sorted_categories %}
    <h3>{{ category[0] | capitalize }}</h3>
    <ul>
      {% for post in category[1] %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <span class="post-date">({{ post.date | date: "%b %d, %Y" }})</span>
        </li>
      {% endfor %}
    </ul>
  {% endfor %}
{% else %}
  <p>No posts yet. Check back soon!</p>
{% endif %}