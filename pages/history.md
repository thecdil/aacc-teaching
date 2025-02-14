---
title: History
layout: page-narrow
permalink: /history.html
---

## A Comprehensive Timeline of Idaho History 

{% assign periods = site.data.idaho-timeline | map: 'period' | uniq %}
<div class="accordion my-4" id="timelineAccordion">{% for period in periods %}{% assign dates = site.data.idaho-timeline | where: 'period', period | map: 'date' | uniq %}
    <div class="accordion-item border-primary border-2">
        <h2 class="accordion-header">
            <button class="accordion-button collapsed fs-3" type="button" data-bs-toggle="collapse" data-bs-target="#collapse{{ period | slugify }}" aria-expanded="false" aria-controls="collapse{{ period | slugify }}">
                {{ period }}
            </button>
        </h2>
        <div id="collapse{{ period | slugify }}" class="accordion-collapse collapse" >
            <div class="accordion-body">
                <ul>{% for date in dates %}{% assign items = site.data.idaho-timeline | where: 'date', date %}
                    <li>
                        <strong>{{ date }}:</strong>
                        <ul>{% for item in items %}
                            <li>{{ item.event }}</li>
                        {% endfor %}
                        </ul>
                    </li>{% endfor %}
                </ul>
            </div>
        </div>
    </div>{% endfor %}
</div>
