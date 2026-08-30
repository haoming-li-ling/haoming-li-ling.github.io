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


{% for section in site.data.output %}
<h2>{{ section.section }}</h2>
<table>
  <colgroup>
    <col style="width:5ex">
    <col>
    <col>
  </colgroup>  
  <tbody>
    {% for item in section.papers %}
    <tr>
      <td class="date">{{ item.year }}</td>
      <!-- <td>{{ item.month }}</td> -->
      <!-- <td>&nbsp;&nbsp;&nbsp;</td> -->
      <td>
        <b class="title">{{ item.title }}</b>
        {% if section.section == "Journal Articles" %}
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
