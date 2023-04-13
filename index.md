---
title: Alexander J. Root
layout: home
---

<table border="0" cellpadding="0">
<!-- <td valign="top" style="min-width:140px;">
<img src="/assets/zurich.jpg" width="160">
</td> -->
<td valign="top">
PhD Student<br/>
Department of Computer Science<br/>
Stanford University<br/>
Office: 464 Gates<br/>
<!-- <a href="mailto:ajroot@stanford.edu">ajroot [at] stanford [dot] edu</a><br/> -->
<a href="/assets/cv.pdf">Curriculum Vitae</a><br/>
<a href="https://scholar.google.com/citations?user=ePuWx50AAAAJ&hl=en&oi=sra">Google Scholar</a><br/>
<!-- <a href="https://twitter.com/rootjalex">Twitter</a><br/> -->
<a href="https://github.com/rootjalex/">Github</a>
</td>
<td valign="top" style="min-width:140px;position: relative;text-align: end;padding-right: 2em;">
<img src="/assets/zurich.jpg" width="160">
</td>
<!-- <td valign="top" style="padding:2.5%;width:40%;max-width:40%">
<img src="/assets/zurich.jpg" width="160">
<a href="/assets/zurich.jpg"><img style="width:100%;max-width:100%" alt="profile photo" src="/assets/zurich.jpg" class="hoverZoomLink"></a>
</td> -->
</table>




I am a Stanford CS PhD student advised by <a href="https://fredrikbk.com">Fredrik Kjolstad</a>,
currently working on sparse data reorganization. My research interests broadly include domain-specific
languages, compilers, and architectures for high-performance numerical computing, with an emphasis on
visual computing applications. I am generously supported by the NSF GFRP and a Stanford School of Engineering fellowship.


I graduated with my bachelor's ('21) and master's ('22) from MIT, working under <a href="https://people.csail.mit.edu/jrk/">Jonathan Ragan-Kelley</a>
and <a href="https://andrew.adams.pub">Andrew Adams</a>, where I worked on vector instruction selection,
fixed-point computation, and bounds inference. I also interned with Andrew, <a href="https://people.csail.mit.edu/skamil/">Shoaib Kamil</a>,
and <a href="https://maaz139.github.io">Maaz Bin Safeer Ahmad</a> at Adobe Research in the summers of 2021 and 2022, on the same topics.
Part of my undergraduate work on fixed-point computation was advised by <a href="https://people.csail.mit.edu/fredo/">Fr&eacute;do Durand</a>.


Much of my research in undergrad and my masters was applied to the <a href="https://halide-lang.org/">Halide</a> compiler,
and I remain somewhat active in the language's development.

<h2 class="tableheading">Publications</h2>

<table border="0">
  {% for pub_keyval in site.data.publications %}
    <tr>
      {%- assign pub = pub_keyval[1] -%}
      <td>
        <b><a href="{{pub_keyval[0]}}.html" style="color: #464646">{{ pub.title }}</a></b><br/>
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
        {%- endfor -%}<br/>
        <i>{{ pub.venue }}
        {%- if pub.venuenote %}
        ({{ pub.venuenote }})
        {%- endif -%}
        {%- if pub.volume -%}
        , Volume {{ pub.volume }}
        {%- endif -%}
        {%- if pub.issue -%}
        , Issue {{ pub.issue }}
        {%- endif -%}
        </i>, {{ pub.month }} {{ pub.year }}<br/>
        {%- if pub.award -%}
          <i><b>{{ pub.award }}</b></i><br/>
        {%- endif -%}
        <p><a href="{{pub_keyval[0]}}.html"><img src="/assets/link.png" alt="link" width="20"/> Website</a>
        {% if pub.pdf %}
          <a href="{{ pub.pdf }}"><img src="/assets/doc.png" alt="pdf" width="20"/> Paper</a>
        {% endif %}
        {% if pub.code %}
          <a href="{{ pub.code }}"><img src="/assets/code.png" alt="code" width="20"/> Code</a>
        {% endif %}
        </p>
      </td>
      <!-- <td valign="top" width="20">
        <a href="{{ pub_keyval[0] }}.html"><img src="/assets/link.png" alt="link" /></a>
        {% if pub.pdf %}
            <a href="{{ pub.pdf }}"><img src="/assets/doc.png" alt="pdf" /></a>
	      {% elsif pub.url %}
            <a href="{{ pub.url }}"><img src="/assets/doc.png" alt="pdf" /></a>
        {% endif %}
        {% if pub.code %}
            <a href="{{ pub.code }}"><img src="/assets/code.png" alt="code" /></a>
        {% endif %}
        {% if pub.movie %}
          <a href="{{ pub.movie }}"><img src="/assets/movie.png" alt="youtube" /></a>
        {% endif %}
      </td> -->
    </tr>
    <tr>
    </tr>
{% endfor %}
</table>

<h2 class="tableheading">Teaching</h2>
<table border="0">
{%- for teaching_keyval in site.data.teaching %}
  {%- assign teaching= teaching_keyval[1] -%}
  <tr>
  <td> 
    <b>
    {%- if teaching.url -%}
    <a href="{{teaching.url}}">
    {%- endif -%}
    {{teaching.title}}
    {%- if teaching.url -%}
    </a>
    {%- endif -%}
    </b><br/>{{teaching.role}}
	  <br/>{{teaching.month}} {{teaching.year}}, {{teaching.venue}}
  </td>
  </tr>
{% endfor %}
</table>


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