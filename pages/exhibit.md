---
title: Exhibit
layout: about
permalink: /exhibit.html
# include CollectionBuilder info at bottom
credits: False
accessibility: False
# Edit the markdown on in this file to describe your collection
# Look in _includes/feature for options to easily add features to the page
---

{% include feature/jumbotron.html heading="Vignettes of Des Moines: Religious Leaders' Biographies and Church Histories" text=false position=bottom objectid="https://titanapi.minisisinc.com/api/links/492768c0ab2f4b059262034753227522/uuid/e1784fd5298647099ff78bdf2c2333cd/access" %} 

<div class="people-page">

  <div class="people-intro">
      <p class="people-dek">
      These brief biographies highlight individuals represented in a selected group
    </p>
    <p>
      of digitized resources from the collection. 
</p>
<p>
      This section will include the intro paragraph.
</p>
<p>
      there will be multiple lines
    </p>
  </div>

  {% assign paragraph_fields = "paragraph1|paragraph2|paragraph3|paragraph4|paragraph5" | split: "|" %}

  {% for person in site.data.people %}
  <section
    class="person-entry"
    aria-labelledby="person-{{ forloop.index }}"
  >
  <div class="person-heading-block">
    {% if person.person_name and person.person_name != "" %}
    <h2 id="person-{{ forloop.index }}" class="person-name-full">
      {{ person.person_name }}
    </h2>
    {% endif %}

    {% if person.person_year and person.person_year != "" %}
    <p class="person-year">{{ person.person_year }}</p>
    {% endif %}

    {% if person.person_role and person.person_role != "" %}
    <p class="person-role">{{ person.person_role }}</p>
    {% endif %}
  </div>

    <div class="row person-grid g-4 g-lg-5 {% cycle '', 'flex-md-row-reverse' %}">
      <div class="col-md-4 col-lg-4">
        <figure class="person-figure">
          <img
            src="{{ person.image | relative_url }}"
            alt="{{ person.alt }}"
            class="img-fluid person-image"
          >
          {% if person.caption and person.caption != "" %}
          <figcaption class="person-caption">
            {{ person.caption }}
          </figcaption>
          {% endif %}
        </figure>
      </div>

      <div class="col-md-8 col-lg-8">
        <div class="person-text">
          
          <div class="person-body">
            {% for field in paragraph_fields %}
              {% assign text = person[field] %}
              {% if text and text != "" %}
              <p>{{ text }}</p>
              {% endif %}
            {% endfor %}
          </div>
        </div>
      </div>
    </div>
  </section>

  {% unless forloop.last %}
  <hr class="person-divider">
  {% endunless %}
  {% endfor %}

</div>