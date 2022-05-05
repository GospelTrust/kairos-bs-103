---
index: 1
layout: lesson
type: syllabus
---

{% assign week = site.data.course[page.collection] %}
{% assign index = page.index | minus: 1 %}
{% assign item = week.items[index] %}
{% assign videos = site.data.videos[page.type] %}

`{{ item.title }}`

{% for v in videos %}
  {% include youtube.html id=v %}
  {% assign size = videos | size %}
  {% if forloop.index != size %}<hr />{% endif %}
{% endfor %}

{% include handouts/{{ page.type }}.md %}
