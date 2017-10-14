---
layout: page
title: Projects
permalink: /projects/
---

<table border=0>
<ul>
{% for pr in site.data.projects %}
  <tr>
  <td>
  <img src="{{ site.baseurl }}{{pr.img}}" width="800px" height="auto" alt={{pr.alttext}}>
  </td>
  <td>
      <div><u>{{pr.type}}</u>:  <b>{{pr.title}}</b> </div>
    <div><i>{{pr.authors}}</i> {{pr.location}} ({{pr.date}})</div>
    {{pr.desc}} {{pr.link}}
  </td>
  </tr>
{% endfor%}
</ul>
</table>

