---
layout: page
title: Témoignages
permalink: /testimonials
---
{% assign testimonials = site.coll_testimonials | sort: "index" %}


<ul class="tab" data-tab="47e7fac6-28a7-4470-a67b-1e7406c42f73" data-name="temoignages">

      <li class="active">
          
          <a id="PJC" href="#">PJC </a>
      </li>
  
      <li>
          <a id="OrgasPJC" href="#">Orgas PJC </a>
      </li>
  
      <li>
          <a id="MIP" href="#">MIP </a>
      </li>
  
      <li>
          <a id="LeadersMIP" href="#">Leaders MIP </a>
      </li>
  
</ul>
<ul class="tab-content" id="47e7fac6-28a7-4470-a67b-1e7406c42f73" data-name="temoignages">
  
      <li class="active">
<br/>

{{ testimonials[0].content }}

      </li>
      <li>
<br/>

{{ testimonials[1].content }}

      </li>
      <li>
<br/>

{{ testimonials[2].content }}

      </li>
      <li>
<br/>

{{ testimonials[3].content }}


      </li>
</ul>
