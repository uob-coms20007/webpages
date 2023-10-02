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
<p>Links to the lecture synopsis, problem sheets and their solutions will appear here as the unit progresses.</p>
<br/>
<table class="pure-table-striped pure-table">
  <thead>
    <tr> 
      <th style="text-align:center">University<br>Week</th>
      <th style="text-align:center">Monday 10am Q&A<br><span style="font-weight:normal;font-style:italic">(MVB 2.11/1.15)</span></th>
      <th style="text-align:center">Monday 11am Lab<br><span style="font-weight:normal;font-style:italic">(MVB 2.11/1.15)</span></th>
      <th style="text-align:center">Thursday 3pm Lecture<br><span style="font-weight:normal;font-style:italic">(PHYS G.42)</span></th>
      <th style="text-align:center">Friday 3pm Lecture<br><span style="font-weight:normal;font-style:italic">(Queens 1.40)</span></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="5" style="text-align:center">Welcome Week</td>
    </tr>
{% for calendar_week in (1..12) %}
  {% if calendar_week <= 6 %}
    {% assign logical_week = calendar_week %}
  {% else %}
    {% assign logical_week = calendar_week | minus: 1 %}
  {% endif %}
  {% if calendar_week == 6 %}
    <tr>
      <td colspan="5" style="text-align:center">Reading Week</td>
    </tr>
  {% elsif calendar_week == 12 %}
    <tr>
      <td colspan="5" style="text-align:center">Revision Week</td>
    </tr>
  {% else %}
    <tr> 
    {% assign lec_one_idx = logical_week | minus:1 | times:3 | minus:1 %}
      <td style="text-align:center"><a href="#lecture{{ lec_one_idx | plus: 1 }}">Week {{ calendar_week }}</a></td>
      <td style="text-align:center"> 
    {% if calendar_week == 1 %}n / a
    {% elsif site.data.lectures[lec_one_idx] %}
        <a href="#lecture{{ lec_one_idx | plus:1 }}">{{ site.data.lectures[lec_one_idx].title }}</a>
    {% endif %}
      </td>  
      <td style="text-align:center">
    {% if calendar_week == 1 %}n / a{% endif %}
    {% capture qns_name %}/questions/sheet{{ calendar_week }}.pdf{% endcapture %}
    {% capture ans_name %}/answers/sheet{{ calendar_week }}.pdf{% endcapture %}
    {% assign qns = false %}
    {% assign ans = false %}
    {% for static_file in site.static_files %}
      {% if static_file.path == qns_name %}
        {% assign qns = true %}
      {% endif %}
      {% if static_file.path == ans_name %}
        {% assign ans = true %}
      {% endif %}
    {% endfor %}
    {% if qns %}
        <a href="{{ qns_name | remove_first: "/" }}" target="_blank">qns</a>  
    {% endif  %}
    {% if ans %}
        / <a href="{{ ans_name | remove_first: "/" }}" target="_blank">ans</a>  
    {% endif %}
      </td>
      <td style="text-align:center">
    {% assign lec_two_idx = logical_week | minus:1 | times:3 %}
    {% if site.data.lectures[lec_two_idx] %}
        <a href="#lecture{{ lec_two_idx | plus:1 }}">{{ site.data.lectures[lec_two_idx].title }}</a>
    {% endif %}
      </td>
      <td style="text-align:center"> 
    {% assign lec_three_idx = logical_week | minus:1 | times:3 | plus:1 %}
    {% if site.data.lectures[lec_three_idx] %}
        <a href="#lecture{{ lec_three_idx | plus:1 }}">{{ site.data.lectures[lec_three_idx].title }}</a>
    {% endif %}
      </td>
    </tr>
  {% endif %}
{% endfor %}
  </tbody>
</table>
</div>

<div>
<!-- <h3>Drop-in sessions:</h3>
<p>Unfortunately, the recordings have various sound and video issues, but may still be useful to you.  I have not uploaded the very first two drop-ins because most of the blackboard work was unfortunately off-screen and so not captured by the recording.</p>
<ul>
  <li><a href="https://mediasite.bris.ac.uk/Mediasite/Play/e75efdb89aa3474db956fd000c02e71c1d" target="_blank">2/12</a> - Goedel numbering trees, induction, bijections and isomorphisms </li>
  <li><a href="https://mediasite.bris.ac.uk/Mediasite/Play/e81047362dc241779c007876e60b6d8c1d" target="_blank">9/12</a> - deciding things, semi-deciding vs deciding</li>
  <li><a href="https://mediasite.bris.ac.uk/Mediasite/Play/4b309d0640d0487ab0785f4c13c953391d" target="_blank">16/12 (1)</a> - semantics of procedures </li>
  <li><a href="https://mediasite.bris.ac.uk/Mediasite/Play/4b309d0640d0487ab0785f4c13c953391d" target="_blank">16/12 (2)</a> - reductions</li>
</ul> -->
<div>

<hr/>


<!-- <img class="icon" src="assets/icons8-calendar-100.png"/>
<h2>Day by day</h2>

<div style="margin:0em 2em 0em 2em">
  <div>It is helpful to think of each week of this unit as running Monday 1pm until the following Monday 1pm.  The pattern of working described below is strongly recommended.</div>
  <div><img src="assets/weekly.svg" style="margin:2em 1em 2em 1em; max-width:40em" width="100%"/></div>
  <div>
    <b style="margin:1em">A</b> Watch all the lecture videos and spend at least 2 hours on the problem sheet<br/>
    <b style="margin:1em">B</b> Work on the problem sheet in the lab and get help from the TAs<br/>
    <b style="margin:1em">C</b> Spend up to another 2 hours finishing the problem sheet<br/>
    <b style="margin:1em">D</b> Participate in the online Q&A with the lecturers to resolve any remaining concerns
  </div>
</div>

<hr/> -->

<img class="icon" src="assets/icons8-calendar-100.png">
<h2 id="wbyw">Lecture List</h2>
<p>Lecture synopses will appear here as the unit progresses.</p>

<div style="margin-left: 2em">

{% assign lec_num = 1 %}
{% for lec in site.data.lectures %}

<h3 id="lecture{{ lec_num }}">
  {% if lec.replay %}[<a href="{{lec.replay}}" target="_blank">REPLAY</a>]{% endif %} 
  {% assign week_posn = lec_num | modulo: 3 %}
  {% if lec_num <= 14 %}
    {% assign week = lec_num | divided_by: 3 | plus: 1 %}
  {% else %}
    {% assign week = lec_num | divided_by: 3 | plus: 2 %}
  {% endif %}
 Week {{week}}, {% if week_posn == 1 %}Thursday{% elsif week_posn == 2 %}Friday{% else %}Monday{% endif %}: {{ lec.title }}
</h3>
<p>
  {{ lec.description | markdownify }}
</p>
{% if lec.notes %}
<p><i>Notes:</i> 
  <ul>
  {% for n in lec.notes %}
    <li>
      <a href="{{n}}" target="_blank">{{ n }}</a>
    </li>
  {% endfor %}
  </ul>
</p>
{% endif %}
{% if lec.refs %}
<p><i>References:</i>
  <ul>
  {% for r in lec.refs %}
    <li>{{ r | markdownify }}</li>
  {% endfor %}
  </ul>
</p>
{% endif %}
{% assign lec_num = lec_num | plus:1 %}
{% endfor %}
</div>

<hr/>

<div style="text-align: center; margin:0em 2em 2em 2em">
  Icons in this course are from the '<a href="https://icons8.com/icons/carbon-copy" target="_blank">Hand Drawn</a>' icon collection by <a href="https://icons8.com/" target="_blank">Icons8</a>.
</div>