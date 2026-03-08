---
title: Alexander J Root
layout: home
---

<table border="0" cellpadding="0">
<td valign="top">
PhD Candidate<br/>
Department of Computer Science<br/>
Stanford University<br/>
Email: ajroot [at] cs [dot] stanford [dot] edu<br/>
<a href="/assets/cv.pdf">Curriculum Vitae</a><br/>
<a href="https://scholar.google.com/citations?user=ePuWx50AAAAJ&hl=en&oi=sra">Google Scholar</a><br/>
<a href="https://github.com/rootjalex/">Github</a>
<div id="siteUpdate" style="text-align: left; font-size: 0.9em; color: #777; margin-top: 0.4em;"></div>
</td>
<td valign="top" style="min-width:140px;position: relative;text-align: end;padding-right: 2em;">
<img src="/assets/trip.jpg" width="160" alt="Headshot of Alexander J Root">
</td>
</table>


<h3 class="tableheading" style="padding-top: 10px;">About</h3>

I design compilers and programming systems that make it tractable to write high-performance code for irregular computations. My goal is to make asymptotically efficient and architecture-aware code as easy to write as naive code.

<!-- **Academic** -->
I am a PhD candidate in Computer Science at Stanford University, advised by <a href="https://fredrikbk.com">Fredrik Kjolstad</a>.
I also work closely with <a href="https://andrew.adams.pub">Andrew Adams</a>,
<a href="https://graphics.stanford.edu/~kayvonf/">Kayvon Fatahalian</a>,
and <a href="https://people.csail.mit.edu/jrk/">Jonathan Ragan-Kelley</a>.
I received my bachelor's (2021) and master's (2022) from MIT, working under <a href="https://people.csail.mit.edu/jrk/">Jonathan Ragan-Kelley</a>, <a href="https://andrew.adams.pub">Andrew Adams</a>, and <a href="https://people.csail.mit.edu/fredo/">Fr&eacute;do Durand</a>.

<!-- **Industry** -->
I have done research internships on <a href="https://research.nvidia.com/labs/rtr/">NVIDIA's Real-Time Graphics</a> team working on compiling spatial Monte Carlo integrators (2025); on the <a href="https://research.adobe.com/research/systems-languages/">Adobe Research Programming Languages and Performance</a> team working on tree traversal compilers and vector instruction selection (2021 - 2023); and on <a href="https://www.linkedin.com/company/inteonco/">Intel's Inteon</a> team working on automatic scheduling for Halide (2021).

<!-- **Support** -->
I am grateful for support from the <a href="https://blogs.nvidia.com/blog/graduate-fellowship-recipients-2026-2027/">NVIDIA Graduate Fellowship</a> (2026 - 2027), the <a href="https://www.qualcomm.com/research/university-relations/innovation-fellowship/2025-north-america">Qualcomm Innovation Fellowship</a> (2025 - 2026) with <a href="https://cgyurgyik.github.io/">Chris Gyurgyik</a>, the <a href = "https://www.nsf.gov/funding/opportunities/grfp-nsf-graduate-research-fellowship-program">NSF GRFP</a> (2022 - 2025), and a Stanford School of Engineering Fellowship (2022 - 2023).

<!-- <br> -->

<h3 class="tableheading" style="padding-top: 10px;">Research</h3>

My research interests broadly include domain-specific languages, compilers, and architectures
for high-performance numerical computing.
I aim to make it significantly easier to write high-performance code. To that end, I work on
programming systems that enable the productive exploration of work-efficiency, compute, and
memory tradeoffs in irregular applications such as sparse array programming and path tracing.
Some projects I have worked on during my PhD are:

- A push-model user-schedulable language for parallelizing divergent and recursive workloads.
- A language for exploring the memory layout of tree data structures (recursive ADTs).
- Compiling spatial queries on sets into asymptotically efficient tree traversals.
- Automatically determining loop ordering, tiling, and formats for sparse tensor algebra kernels.
- Compiling and fusing shape operators (e.g., reshape) and convolutions for sparse arrays.

At MIT, I worked on vector instruction selection, fixed-point computing systems, and bounds
inference, primarily in the context of the <a href="https://halide-lang.org/">Halide</a> compiler.

<h3 class="tableheading" style="padding-top: 10px;">Publications</h3>

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
      <td style="padding: 0;"></td>
      <td style="width: 2.5%; padding: 0;"></td>
      <td style="font-style: italic; padding: 0; line-height: 1.0">{{ pub.venue }}</td>
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
    <tr aria-hidden="true">
      <td colspan="3" style="height: 0.01em;"></td>
    </tr>
    {% endif %}
    {% endfor %}
</table>

<!-- <br> -->

<h3 class="tableheading" style="padding-top: 20px;">Teaching</h3>
I enjoy teaching and have been involved with compilers classes at both Stanford and MIT. I also TAed MIT's introductory algorithms class.

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


<!-- <div id=siteUpdate style="text-align: center;"> </div> -->
<div>
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
</div>
