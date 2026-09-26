<h2 id="publications" class="pub-section-title">Publications{% if site.google_scholar or site.dblp %} <span class="pub-ext-links">{% if site.google_scholar %}<a href="{{ site.google_scholar }}" target="_blank" rel="noopener">Google Scholar</a>{% endif %}{% if site.dblp %}<a href="{{ site.dblp }}" target="_blank" rel="noopener">DBLP</a>{% endif %}</span>{% endif %}</h2>

<div class="publications">

{% if site.data.preprints.main and site.data.preprints.main.size > 0 %}
<h2 class="year">Preprints</h2>

<ol class="bibliography">
{% for link in site.data.preprints.main %}
{% include publication-item.html link=link %}
{% endfor %}
</ol>
{% endif %}

{% assign cutoff = site.pub_archive_year | default: 0 | plus: 0 %}
{% assign publications_by_year = site.data.publications.main | group_by: "year" | sort: "name" | reverse %}
{% assign older_pubs = "" | split: "" %}

{% for year_group in publications_by_year %}
{% assign yr = year_group.name | plus: 0 %}
{% if yr <= cutoff %}
{% assign older_pubs = older_pubs | concat: year_group.items %}
{% else %}

<h2 class="year">{{ year_group.name }}</h2>

<ol class="bibliography">
{% for link in year_group.items %}
{% include publication-item.html link=link %}
{% endfor %}
</ol>

{% endif %}
{% endfor %}

{% if older_pubs.size > 0 %}

<h2 class="year">{{ cutoff }} and Before</h2>

<ol class="bibliography">
{% for link in older_pubs %}
{% include publication-item.html link=link %}
{% endfor %}
</ol>

{% endif %}

</div>
