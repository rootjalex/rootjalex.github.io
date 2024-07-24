---
title: Alexander J Root
layout: home
---

<table border="0" cellpadding="0">
<td valign="top">
PhD Student<br/>
Department of Computer Science<br/>
Stanford University<br/>
Office: 464 Gates<br/>
Email: ajroot [at] cs [dot] stanford [dot] edu<br/>
<!-- <a href="mailto:ajroot@stanford.edu">ajroot [at] stanford [dot] edu</a><br/> -->
<a href="/assets/cv.pdf">Curriculum Vitae</a><br/>
<a href="https://scholar.google.com/citations?user=ePuWx50AAAAJ&hl=en&oi=sra">Google Scholar</a><br/>
<!-- <a href="https://twitter.com/rootjalex">Twitter</a><br/> -->
<a href="https://github.com/rootjalex/">Github</a>
</td>
<td valign="top" style="min-width:140px;position: relative;text-align: end;padding-right: 2em;">
<img src="/assets/trip.jpg" width="160">
</td>
</table>




I am a Stanford CS PhD student advised by <a href="https://fredrikbk.com">Fredrik Kjolstad</a>.
I also work closely with <a href="https://andrew.adams.pub">Andrew Adams</a>,
<a href="https://graphics.stanford.edu/~kayvonf/">Kayvon Fatahalian</a>,
and <a href="https://people.csail.mit.edu/jrk/">Jonathan Ragan-Kelley</a>.


My research interests broadly include domain-specific languages, compilers, and architectures
for high-performance numerical computing, with an emphasis on visual computing applications.
I am particularly interested in *performance and productivity*: I aim to make it significantly
easier to write high-performance code. I currently work on compilers for sparse array programming
and high-performance spatial queries (e.g. ray tracing and collision detection).


I graduated with my bachelor's ('21) and master's ('22) from MIT, working under <a href="https://people.csail.mit.edu/jrk/">Jonathan Ragan-Kelley</a>
and <a href="https://andrew.adams.pub">Andrew Adams</a> on vector instruction selection,
fixed-point computing systems, and bounds inference. I also interned with Andrew, <a href="https://people.csail.mit.edu/skamil/">Shoaib Kamil</a>,
and <a href="https://maaz139.github.io">Maaz Bin Safeer Ahmad</a> at Adobe Research in the summers of '21 and '22, on the same topics.
Part of my undergraduate work on fixed-point compute systems was advised by <a href="https://people.csail.mit.edu/fredo/">Fr&eacute;do Durand</a>.


Much of my pre-PhD research was applied to the <a href="https://halide-lang.org/">Halide</a> compiler,
and I remain somewhat active in the language's development.

I am generously supported by the NSF GFRP and a Stanford School of Engineering fellowship.

<!-- <br> -->

<h2 class="tableheading" style="padding-top: 10px;">Publications</h2>

<table border="0" style="margin: 0;">
  {% for pub_keyval in site.data.publications %}
    {%- assign pub = pub_keyval[1] -%}
    {% if pub.preprint != "y" %}
    <tr>
      <td style="margin-left: 1em; text-align: right; flex: 0 0 90px; width: 15%">{{ pub.acronym }} {{ pub.year }}</td>
      <td style="width: 2.5%"></td>
      <td style="font-size: 1.1em; line-height: 1.25; hyphens: none; margin-bottom: 0.2em; text-decoration: underline;">
      {% if pub.abstract %}
        <a href="{{pub_keyval[0]}}.html" style="color: #464646">
      {% endif %}
      {{ pub.title }}
      {% if pub.abstract %}
        </a>
      {% endif %}
      </td>
    </tr>
    <tr>
      <td></td>
      <td style="width: 2.5%"></td>
      <td>
      <!-- for loop of authors -->
        {%- for author in pub.authors -%}
          {%- if forloop.last == true and forloop.length > 1 %}
            and
          {%- endif %}
          {%- if author == "root" %}
            <b><font color="#000000">{{ site.data.authors[author].name }}</font></b>
          {%- elsif author == "root_mit" %}
            <b><font color="#000000">{{ site.data.authors[author].name }}</font></b>
          {%- else %}
            <a href="{{- site.data.authors[author].site -}}" style="color: #464646">{{ site.data.authors[author].name }}</a>
          {%- endif -%}
          {%- if forloop.last == false and forloop.length > 2 -%}
            ,
          {%- endif %}
        {%- endfor -%}
      </td>
    </tr>
    {% if pub.abstract or pub.pdf or pub.code %}
    <tr style="height: 10%;">
      <td></td>
      <td style="width: 2.5%"></td>
      <td style="padding:0px; margin:0px;">
        {% if pub.abstract %}
          <a href="{{pub_keyval[0]}}.html"><img src="/assets/link.png" alt="link" width="20"/> Website</a>
        {% endif %}
        {% if pub.pdf %}
          <a href="{{ pub.pdf }}"><img src="/assets/doc.png" alt="pdf" width="20"/> Paper</a>
        {% endif %}
        {% if pub.code %}
          <a href="{{ pub.code }}"><img src="/assets/code.png" alt="code" width="20"/> Code</a>
        {% endif %}
      </td>
    </tr>
    {%- else %}
    <tr style="height: 10%;">
      <td></td>
      <td style="width: 2.5%"></td>
      <td style="padding:0px; margin:0px;">
        <em>Paper draft coming soon!</em>
      </td>
    </tr>
    {% endif %}
    {% endif %}
    {% endfor %}
</table>

<!-- <br> -->

<h2 class="tableheading" style="padding-top: 20px;">Preprints</h2>

<table border="0" style="margin: 0;">
  {% for pub_keyval in site.data.publications %}
    {%- assign pub = pub_keyval[1] -%}
    {% if pub.preprint == "y" %}
    <tr>
      <td style="margin-left: 1em; text-align: right; flex: 0 0 90px; width: 15%">{{ pub.acronym }} {{ pub.year }}</td>
      <td style="width: 2.5%"></td>
      <td style="font-size: 1.1em; line-height: 1.25; hyphens: none; margin-bottom: 0.2em; text-decoration: underline;">
      {% if pub.abstract %}
        <a href="{{pub_keyval[0]}}.html" style="color: #464646">
      {% endif %}
      {{ pub.title }}
      {% if pub.abstract %}
        </a>
      {% endif %}
      </td>
    </tr>
    <tr>
      <td></td>
      <td style="width: 2.5%"></td>
      <td>
      <!-- for loop of authors -->
        {%- for author in pub.authors -%}
          {%- if forloop.last == true and forloop.length > 1 %}
            and
          {%- endif %}
          {%- if author == "root" %}
            <b><font color="#000000">{{ site.data.authors[author].name }}</font></b>
          {%- elsif author == "root_mit" %}
            <b><font color="#000000">{{ site.data.authors[author].name }}</font></b>
          {%- else %}
            <a href="{{- site.data.authors[author].site -}}" style="color: #464646">{{ site.data.authors[author].name }}</a>
          {%- endif -%}
          {%- if forloop.last == false and forloop.length > 2 -%}
            ,
          {%- endif %}
        {%- endfor -%}
      </td>
    </tr>
    {% if pub.abstract or pub.pdf or pub.code %}
    <tr style="height: 10%;">
      <td></td>
      <td style="width: 2.5%"></td>
      <td style="padding:0px; margin:0px;">
        {% if pub.abstract %}
          <a href="{{pub_keyval[0]}}.html"><img src="/assets/link.png" alt="link" width="20"/> Website</a>
        {% endif %}
        {% if pub.pdf %}
          <a href="{{ pub.pdf }}"><img src="/assets/doc.png" alt="pdf" width="20"/> Paper</a>
        {% endif %}
        {% if pub.code %}
          <a href="{{ pub.code }}"><img src="/assets/code.png" alt="code" width="20"/> Code</a>
        {% endif %}
      </td>
    </tr>
    {%- else %}
    <tr style="height: 10%;">
      <td></td>
      <td style="width: 2.5%"></td>
      <td style="padding:0px; margin:0px;">
        <em>Paper draft coming soon!</em>
      </td>
    </tr>
    {% endif %}
    {% endif %}
    {% endfor %}
</table>

<!-- <br> -->

<h2 class="tableheading" style="padding-top: 20px;">Teaching</h2>
<table border="0" style="margin: 0;">
{%- for teaching_keyval in site.data.teaching %}
  {%- assign teaching= teaching_keyval[1] -%}
  <tr>
  <td> 
    <span style="text-decoration: underline;">
    {%- if teaching.url -%}
    <a href="{{teaching.url}}" style="color: #464646;">
    {%- endif -%}
    {{teaching.title}}
    {%- if teaching.url -%}
    </a>
    {%- endif -%}
    </span><br/>{{teaching.role}}, {{teaching.month}} {{teaching.year}}, {{teaching.venue}}
  </td>
  </tr>
{% endfor %}
</table>

<br/>
<div id=siteUpdate style="text-align: center;"> </div>
<script>
const desiredRepo = "rootjalex.github.io"
const monthNames = ["January", "February", "March", "April", "May", "June",
  "July", "August", "September", "October", "November", "December"
];

var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    let repos = JSON.parse(this.responseText);
    repos.forEach((repo)=>{
      if (repo.name == desiredRepo)
      {
        var lastUpdated = new Date(repo.pushed_at);
        var day = lastUpdated.getUTCDate();
        var month = lastUpdated.getUTCMonth();
        var year = lastUpdated.getUTCFullYear();
        siteUpdate.innerHTML += (`<em>Site Last Updated ${monthNames[month]} ${year}</em><br>`);
      }
    });
  }
};
xhttp.open("GET", "https://api.github.com/users/rootjalex/repos", true);
xhttp.send();
</script>