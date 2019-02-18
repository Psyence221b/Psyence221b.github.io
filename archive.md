---
# Test for archive page
layout : list

# The title of the page.
title: Archive

# Setting `menu` will generate an entry in the sidebar.
menu: true
order: 10
---

# Tag

{% for tag in site.iterable.tags %}
<h3>{{ tag.name }}</h3>
<ul>
	{% for post in tag.posts %}
		<li><a href="{{ post.url }}">{{ post.title }}</a></li>
		<time>{{ post.date | date: "%e %B %Y" }}</time>
	{% endfor %}
</ul>
{% endfor %}


# Date

{% for post in site.posts %}
	{% capture month %}{{ post.date | date: '%m%Y' }}{% endcapture %}
	{% capture nmonth %}{{ post.next.date | date: '%m%Y' }}{% endcapture %}
		{% if month != nmonth %}
			{% if forloop.index != 1 %}</ul>{% endif %}
			<h3>{{ post.date | date: '%B %Y' }}</h3><ul>
		{% endif %}
	<li><a href="{{ post.url }}">{{ post.title }}</a></li>
	<time>{{ post.date | date: "%e %B %Y" }}</time>
{% endfor %}
