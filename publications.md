---
layout: default
title: Publications
body_class: page-publications
---

{% assign publication_groups = site.data.publications | group_by: "year" | sort: "name" | reverse %}
<div class="publication-groups">
    {% for group in publication_groups %}
        <section class="publication-year-group" aria-labelledby="publications-{{ group.name }}">
            <h2 id="publications-{{ group.name }}">{{ group.name }}</h2>
            <div class="publication-list">
                {% for publication in group.items %}
                    {% include publication.html publication=publication %}
                {% endfor %}
            </div>
        </section>
    {% endfor %}
</div>
