---
layout: page
title: Témoignages
permalink: /testimonials
---
{% assign testimonials = site.coll_testimonials | sort: "index" %}


{% tabs temoignages %}

{% tab temoignages PJC %}

<br/>

{{ testimonials[0].content }}

{% endtab %}

{% tab temoignages Orga PJC %}

<br/>

{{ testimonials[1].content }}

{% endtab %}

{% tab temoignages MIP %}

<br/>

{{ testimonials[2].content }}

{% endtab %}

{% tab temoignages Leaders MIP %}

<br/>

{{ testimonials[3].content }}

{% endtab %}

{% endtabs %}

