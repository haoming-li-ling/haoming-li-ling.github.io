---
layout: default
title: Haoming Li's Homepage
---
# Haoming Li
I'm a fifth-year Ph.D. student in linguistics at the Massachusetts Institute of Technology. I received B.A. in Linguistics from the University of Chicago in 2022.

My main areas of interest are semantics, pragmatics, syntax, and their interfaces. 

Specific topics I have covered include:
- modals of permission
- free choice
- inferences of number marking
- distributivity
- universal quantifiers
- _even_
- comparatives
- Across-the-Board constructions
- *wh*-questions
- syntax of Mandarin Chinese
{: .topics}


{% assign output_by_category = site.data.output | group_by: "category" %}
{% for section in output_by_category %}
<h2>{% if section.name == "Journal Article" %}Journal Articles{% elsif section.name == "Talk" %}Talks{% else %}{{ section.name }}{% endif %}</h2>
<table>
  <colgroup>
    <col style="width:5ex">
    <col>
    <col>
  </colgroup>  
  <tbody>
    {% assign items_by_date = section.items | sort: "date" | reverse %}
    {% for item in items_by_date %}
    <tr>
      <td class="date">{{ item.date | slice: 0, 4 }}</td>
      <!-- <td>&nbsp;&nbsp;&nbsp;</td> -->
      <td>
        <b class="title">{{ item.title }}</b>
        {% if item.category == "Journal Article" %}
        <br><em>{{ item.publication }}</em>
        {% else %}
        <br>{{ item.publication }}
        {% endif %}
        {% if item.author %}
        <br>With {{ item.author }}
        {% endif %}
        {% if item.supervisor %}
        <br>Supervisor: {{ item.supervisor }}
        {% endif %}
      </td>
      <td>
        {% for entry in item.resources %}
        {%- if forloop.index != 1 -%}
        <br>
        {%- endif -%}
        <a href="{{ entry.url }}">{{ entry.type }}</a>
        {% endfor %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% endfor %}
