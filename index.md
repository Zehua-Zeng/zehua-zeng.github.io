---
layout: page
title: "Home"
class: home
---

# Hi, I'm Zehua Zeng

<div class="columns" markdown="1">

<div class="intro" markdown="1">
I am a Software Research Engineer at [Intel](https://www.intel.com/), where I build full-stack applications and interactive visualization tools for large-scale semiconductor design and manufacturing. My work spans software engineering, data visualization, machine learning, and scalable data systems, with a focus on transforming complex engineering data into intuitive tools that enable real-time analysis and informed decision-making.

I earned my Ph.D. in [Computer Science](https://www.cs.umd.edu/) from the [University of Maryland, College Park](https://www.umd.edu/), where I worked with [Prof. Leilani Battle](https://homes.cs.washington.edu/~leibatt/bio.html) in the [BAttle-Data Lab](https://battle-data-lab.cs.umd.edu) and [UW Interactive Data Lab](https://idl.cs.washington.edu/). My research focused on visualization recommendation systems, interactive visual analytics, and human-centered data analysis. My research has been recognized with multiple paper and dissertation honors at premier visualization venues. I also earned my M.S. in Computer Science from the University of Maryland and my B.S. in Telecommunication Engineering from Beijing University of Posts and Telecommunications.

You can find me on [GitHub](https://github.com/Zehua-Zeng), or [LinkedIn](https://www.linkedin.com/in/zehuazeng/).

</div>

<div class="me" markdown="1">
<picture>
  <source srcset='/images/zehua-umd.avif' type='image/avif' />
  <img
    src='/images/zehua-umd.jpeg'
    alt='Zehua Zeng'>
</picture>

{:.no-list}

- <a href="mailto:{{ site.email }}">{{ site.email }}</a>
</div>

</div>

## Featured Projects

<div class="projects">
  <div class="grid featured-projects">
    {% assign sorted_projects = site.data.projects | sort: 'highlight' %}
    {% for project in sorted_projects %}
      {% if project.highlight %}
        {% include project.html project=project %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<a href="{{ "/projects/" | relative_url }}" class="button">
<i class="fas fa-chevron-circle-right"></i>
Show More Projects
</a>

## Featured Publications

<div class="featured-publications">
  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}
  {% for pub in sorted_publications %}
    {% if pub.highlight %}
      {% assign pub_pdf_url = pub.pdf %}
      {% if pub_pdf_url %}
        {% unless pub_pdf_url contains '://' %}
          {% assign pub_pdf_url_prefix = pub_pdf_url | slice: 0, 1 %}
          {% unless pub_pdf_url_prefix == '/' %}
            {% assign pub_pdf_url = '/' | append: pub_pdf_url %}
          {% endunless %}
          {% assign pub_pdf_url = pub_pdf_url | relative_url %}
        {% endunless %}
      {% endif %}
      <a href="{{ pub_pdf_url }}" class="publication">
        <strong>{{ pub.title }}</strong>
        <span class="authors">{% for author in pub.authors %}{{ author }}{% unless forloop.last %}, {% endunless %}{% endfor %}</span>.
        <i>{% if pub.venue %}{{ pub.venue }}, {% endif %}{{ pub.year }}</i>.
        {% for award in pub.awards %}<br/><span class="award"><i class="fas fa-{% if award == "Best Paper" %}trophy{% elsif award contains "Test-of-Time" %}clock{% else %}award{% endif %}" aria-hidden="true"></i> {{ award }}</span>{% endfor %}
      </a>
    {% endif %}
  {% endfor %}
</div>
