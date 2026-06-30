---
layout: default
title: Home
---

<h1>Miscellaneous Technical Notes</h1>
<p>Random technical notes and code snippets for personal reference.</p>

<h2>Notes</h2>
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

<h2>Snippets</h2>
<ul class="snippets-list">
  {% assign sorted_snippets = site.snippets | sort: 'date' | reverse %}
  {% for snippet in sorted_snippets %}
  <li>
    <a href="{{ snippet.url | relative_url }}">{{ snippet.title }}</a>
    {% if snippet.language %}<span class="snippet-language"> ({{ snippet.language }})</span>{% endif %}
    {% if snippet.date %}<span class="snippet-date"> — {{ snippet.date | date: "%Y-%m-%d" }}</span>{% endif %}
    {% if snippet.tags and snippet.tags.size > 0 %}
    <span class="snippet-tags">
      {% for tag in snippet.tags %}[{{ tag }}] {% endfor %}
    </span>
    {% endif %}
  </li>
  {% endfor %}
</ul>
