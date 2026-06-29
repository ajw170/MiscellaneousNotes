---
layout: default
title: Notes
---

<h1>Technical Notes</h1>
<p>Random technical notes for personal reference.</p>

<ul class="notes-list">
  {% assign sorted_notes = site.notes | sort: 'date' | reverse %}
  {% for note in sorted_notes %}
  <li>
    <a href="{{ note.url | relative_url }}">{{ note.title }}</a>
    {% if note.date %}<span class="note-date"> — {{ note.date | date: "%Y-%m-%d" }}</span>{% endif %}
    {% if note.tags and note.tags.size > 0 %}
    <span class="note-tags">
      {% for tag in note.tags %}[{{ tag }}] {% endfor %}
    </span>
    {% endif %}
  </li>
  {% endfor %}
</ul>
