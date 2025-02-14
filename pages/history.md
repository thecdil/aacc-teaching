---
title: History
layout: page-narrow
permalink: /history.html
---

## A Comprehensive Timeline of Idaho History 

{% assign periods = site.data.idaho-timeline | map: 'period' | uniq %}
{% for period in periods %}
{% assign dates = site.data.idaho-timeline | where: 'period', period | map: 'date' | uniq %}
------
{:.mt-5}

### {{ period }}
{:.mt-5}

{% for date in dates %}{% assign items = site.data.idaho-timeline | where: 'date', date %}
- **{{ date }}:** {% for item in items %}
    - {{ item.event }}{% endfor %}

{% endfor %}
{% endfor %}
