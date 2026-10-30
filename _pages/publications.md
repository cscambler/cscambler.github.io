---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on
  <a href="{{ author.googlescholar }}">my Google Scholar profile</a>.
{% endif %}

{% include base_path %}

{% assign sorted_publications = site.publications | sort: "date" | reverse %}

<div style="height: 20px;"></div>
{% for post in sorted_publications %}

<details style="margin-bottom: 18px;">
  <summary style="cursor: pointer; font-size: 1.05em;">
    <strong>{{ post.title }}</strong>
    <span style="font-size: 0.85em; color: #666;">
      — {{ post.venue }}, {{ post.date | date: "%Y" }}
    </span>
  </summary>

  <div style="padding: 12px 0 12px 22px;">

    {% if post.excerpt %}
      <p>{{ post.excerpt | markdownify }}</p>
    {% endif %}

    {% if post.citation %}
      <p><strong>Recommended citation:</strong>
      {{ post.citation }}</p>
    {% endif %}

    {% if post.paperurl %}
      <p><a href="{{ post.paperurl }}">View paper</a></p>
    {% endif %}

  </div>
</details>

{% endfor %}
