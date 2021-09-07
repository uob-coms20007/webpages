---
layout: default
title: schedule
---

![schedule](/bbcswebdav/xid-15830569_4){: .icon }
## Detailed Schedule

<table class="pure-table-striped pure-table">
  <thead>
    <tr> 
      <th>Week</th><th>Lecturer</th><th>Theme</th><th>Videos</th><th>Labs</th>
    </tr>
  </thead>
  <tbody>
  {% for week in site.data.weeks %}
    <tr> 
      <td>{{ week.num }}</td><td>{{week.lecturer}}</td><td>{{week.description}}</td><td>{{week.videos}}</td><td>{{week.labs}}</td>
    </tr>
{% endfor %}
  </tbody>
</table>
