---
layout: default
title: schedule
---

{% assign question_sheets = site.static_files | where: "question", true %}
{% assign answer_sheets = site.static_files | where: "answer", true %}

{% assign question_names = question_sheets | map: "basename" | join: "," | remove: "sheet" %}
{% assign answer_names = answer_sheets | map: "basename" | join: "," | remove: "sheet" %}

<img class="icon" src="/bbcswebdav/xid-15830569_4"/>
<h2>At a glance</h2>

<div style="margin-left: 2em">
<table class="pure-table-striped pure-table">
  <!-- <thead>
    <tr> 
      <th>Week</th><th>By</th><th>Theme</th><th>Videos</th><th>Problems</th>
    </tr>
  </thead> -->
  <tbody>
    <tr>
      <td colspan="3" style="text-align:center">Welcome Week</td>
    </tr>
    {% for week in site.data.weeks %}
    {% if week.num == 6 %}
    <tr>
      <td colspan="3" style="text-align:center">Reading Week</td>
    </tr>
    {% elsif week.num == 12 %}
    <tr>
      <td colspan="3" style="text-align:center">Revision Week</td>
    </tr>
    {% else %}
    <tr> 
      <td><a href="#week{{ week.num }}">Week {{ week.num }}: {{week.theme}}</a></td><td>{{week.videos}}</td>
      <td>
        {% if question_names contains week.num %}
        <a href="questions/sheet{{ week.num }}.pdf">qns</a>
        {% endif %}
        {% if answer_names contains week.num %}
         / <a href="answers/sheet{{ week.num }}.pdf">ans</a>
        {% endif %}
      </td>
    </tr>
    {% endif %}
    {% endfor %}
  </tbody>
</table>
</div>

<hr/>

<img class="icon" src="/bbcswebdav/xid-15830569_4">
<h2>Week by week</h2>

<div style="margin-left: 2em">

{% for week in site.data.weeks %}
{% unless week.num == 6 or week.num == 12 %}

<h3 id="week{{ week.num }}">Week {{ week.num }}: {{ week.theme }}</h3>
<p> - <i style="font-size:90%">Lectured by {{ week.lecturer | replace: "SR", "Steven Ramsay" | replace: "FD", "François Dupressoir" | replace: "AK", "Alex Kavvos" }}</i></p>
{{ week.description | markdownify }}
  <ul>
    {% if week.videos %}
    <li>Videos:</li>
    {% endif %}
    {% if question_names contains week.num %}
    <li>
      Labs: <a href="questions/sheet{{ week.num }}.pdf">qns</a>{% if answer_names contains week.num %} / <a href="answers/sheet{{ week.num }}.pdf">ans</a>{% endif %}
    </li>
    {% endif %}
    {% if week.references %}
    <li>Reference:<br/>
        <div style="margin-left:1em">
        {% for ref in week.references %}
          - <a href="{{ ref }}">{{ ref | split: '/' | last | split: '#' | last | replace: '-', ' ' }}</a><br/>
        {% endfor %}
        </div>
    </li>
    {% endif %}
  </ul>

{% endunless %}
{% endfor %}
</div>