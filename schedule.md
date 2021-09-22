---
layout: default
title: schedule
---

{% capture nowunix %}{{'now' | date: '%s' }}{% endcapture %}
{% capture weekunix %}{{ 60 | times: 60 | times: 24 | times: 7 }}{% endcapture %}
{% capture startunix  %}{{ '2021-09-27' | date: '%s'  }}{% endcapture %}

{% assign question_sheets = site.static_files | where: "question", true %}
{% assign answer_sheets = site.static_files | where: "answer", true %}

{% assign question_names = question_sheets | map: "basename" | join: "," | remove: "sheet" %}
{% assign answer_names = answer_sheets | map: "basename" | join: "," | remove: "sheet" %}

<img class="icon" src="assets/icons8-schedule-100.png"/>
<h2>At a glance</h2>

<div style="margin-left: 2em">
<p>Links to the lecture videos, problem sheets and their solutions will appear here as the unit progresses.  Check <a href="#wbyw">below</a> for the links alongside accompanying information.</p>
<br/>
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

<img class="icon" src="assets/icons8-calendar-100.png"/>
<h2>Day by day</h2>

<div style="margin:0em 2em 0em 2em">
  <div>It is helpful to think of each weeks of this unit as running Monday 1pm until the following Monday 1pm.  The pattern of working described below is strongly recommended.</div>
  <div><img src="assets/weekly.svg" style="margin:2em 1em 2em 1em; max-width:40em" width="100%"/></div>
  <div>
    <b style="margin:1em">A</b> Watch all the lecture videos and spend at least 2 hours on the problem sheet<br/>
    <b style="margin:1em">B</b> Work on the problem sheet in the lab and get help from the TAs<br/>
    <b style="margin:1em">C</b> Spend up to another 2 hours finishing the problem sheet<br/>
    <b style="margin:1em">D</b> Participate in the online Q&A with the lecturers to resolve any remaining concerns
  </div>
</div>

<hr/>

<img class="icon" src="assets/icons8-timeline-week-100.png">
<h2 id="wbyw">Week by week</h2>

<div style="margin-left: 2em">

{% for week in site.data.weeks %}
{% unless week.num == 6 or week.num == 12 %}

<h3 id="week{{ week.num }}">Week {{ week.num }}: {{ week.theme }}</h3>
<p> - <i style="font-size:90%">Lectured by {{ week.lecturer | replace: "SR", "Steven Ramsay" | replace: "FD", "François Dupressoir" | replace: "AK", "Alex Kavvos" }}</i></p>
{{ week.description | markdownify }}
  {% capture this_week_unix %}{{ week.num | minus: 1 | times: weekunix | plus: startunix }}{% endcapture %}
  {% capture next_week_unix %}{{ week.num | times: weekunix | plus: startunix }}{% endcapture %}
  {% if this_week_unix <= nowunix %}
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
          - <a href="{{ ref }}" target="_blank">{{ ref | split: '/' | last | split: '#' | last | replace: '-', ' ' }}</a><br/>
        {% endfor %}
        </div>
    </li>
    {% endif %}
  </ul>
  {% endif %}

{% endunless %}
{% endfor %}
</div>

<hr/>

<div style="text-align: center; margin:0em 2em 2em 2em">
  Icons in this course are from the '<a href="https://icons8.com/icons/carbon-copy" target="_blank">Hand Drawn</a>' icon collection by <a href="https://icons8.com/" target="_blank">Icons8</a>.
</div>