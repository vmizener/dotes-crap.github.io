---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

---
# Hero Concepts
{% for item in site.hero_concepts %}
- [{{ item.title }}]({{ item.url }})
{% endfor %}
