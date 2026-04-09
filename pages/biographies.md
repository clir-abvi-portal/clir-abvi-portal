---
title: Biographies
layout: page
permalink: /biographies/
---
<div class="biographies-content" markdown="1">

# Black Religious Leaders of Iowa
## 1900-1930

{:.pt-4}

Featured here are brief biographies, or vignettes, of religious leaders of Iowa. The Bystander newspaper from this site was used to create many of the vignettes. The vignettes include each person’s name, birth and death dates, roles, and biography. To learn more about each person, select their name in the listing below.

{% capture letters %}{% for item in site.data.biographies %}{{ item.person_name | slice: 0 | capitalize }};{% endfor %}{% endcapture %}
{%- assign uniqueLetters = letters | split: ';' | uniq | sort -%}
{%- assign glossary = site.data.biographies | sort: "person_name" -%}

<div class="bio-nav">
    <div class="nav-title">Navigate by Last Name</div>
    <div class="text-center">
        {% for letter in uniqueLetters %}
        <a href="#{{ letter }}" class="letter-link">{{ letter }}</a>
        {% endfor %}
    </div>
</div>

## Background

Faith traditions and churches played a central role in the creation of communities in the United States. In the 1840s and early 1850s Black communities developed in eastern Iowa, especially in Muscatine and Keokuk where African Methodist Episcopal (AME) congregations organized. The presence of Black religious groups in these communities is unsurprising as Lee County (Keokuk) led the state with 245 Black residents and Muscatine County (Muscatine) was second with 112 Black residents as of 1860. 

After the Civil War, Iowa’s Black population grew from 5,762 in 1870 to 9,516 in 1880. As coal mining began to play a major role in Iowa’s economy in the late 1800s, the Black population  continued to increase. By 1920, Iowa’s Black population reached a pre-World War II peak of 19,005. It is in this period (1900 - 1930) where Black Baptist and Methodist congregations were present in large and small communities across the southern half of the state including Taylor and Page Counties in southwest Iowa, Jasper, Polk, Mahaska, Wapello, and Boone Counties in  central Iowa, and Scott, Muscatine, Des Moines, and Lee Counties in the east. Congregations of various denominations also existed in the cities of Waterloo, Mason City, Cedar Rapids, and Sioux City.

This period of review is also when the Iowa State Bystander newspaper became a vital source of information for the Black community in Iowa and neighboring states. Publisher John L. Thompson had correspondents reporting on community activities in various cities and towns. The newspaper provided important insights into the men and women who served religious functions in Iowa. Newspapers, along with governmental records, city directories, and other primary sources, provide biographical information to shed light on these overlooked figures in Iowa, regional, and national history.

<div>

{% for letter in uniqueLetters %}
<div class="bio-section-header" id="{{ letter }}">
    <div class="letter-badge">{{ letter }}</div>
    <div class="section-line"></div>
</div>

<div class="bio-entries">
{% for item in glossary %}
{%- assign x = item.person_name | slice: 0 | capitalize -%}
{%- if x == letter -%}
    <div class="bio-entry">
        <a href="{{ '/biographies/' | append: item.objectid | append: '.html' | relative_url }}" class="bio-name">
            {{ item.person_name }}
        </a>
        <div class="bio-role">{{ item.person_role }}</div>
    </div>
{%- endif -%}
{%- endfor -%}
</div>

{%- endfor -%}

</div>
