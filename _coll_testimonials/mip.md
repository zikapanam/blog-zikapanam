---
title: Membres MIP
tabname: mip
index: 3
---
{% assign sortedtestimonials = site.testimonials_mip | sort: "index" %}
{% assign tabn = "mip" %}

<section class="customer-revs{{ tabn }}">
  <div class="rectangle{{ tabn }}"></div>

<!-- Next/prev buttons -->

	<!-- Dots/bullets/indicators -->
	<div class="dot-container{{ tabn }}">
	{% for testimonial in sortedtestimonials %}
	<span class="dot{{ tabn }}"></span>
	{% endfor %}
	</div>

  <!-- Slideshow container -->
  <div class="slideshow-container{{ tabn }}">

	<a class="slide{{ tabn }}-prev">&#10094;</a>
	<a class="slide{{ tabn }}-next">&#10095;</a>

{% for testimonial in sortedtestimonials %}

    <!-- Full-width slides/quotes -->
    <div class="mySlides{{ tabn }}">
      <div class="mySlidesContainer{{ tabn }}">
        <p class="author">
        Par: <span>{{ testimonial.author }}</span>
        <br/><span>{{ testimonial.attribution }}</span>
        </p>
        <div style="min-height:200px">
        <div style="float: left;margin: 0px 10px 10px 0px">
          <p><img src="{{ testimonial.avatar }}" style="border: 1px solid black;" width="150"/></p>
          <p>
          {% if testimonial.photographe_link %}
          <a href="{{ testimonial.photographe_link }}" target="_blank">Photographe</a>
          {% endif %}
          </p>
        </div>
        <q>
          {{ testimonial.content | remove: "<p>" | remove: "</p>" }}
        </q>
        </div>
      </div>
    </div>
{% endfor %}


  </div><!-- END slidehow-container -->
</section>

<script>
let slides{{ tabn }} = document.getElementsByClassName("mySlides{{ tabn }}");
let dots{{ tabn }} = document.getElementsByClassName("dot{{ tabn }}");
let prev{{ tabn }} = document.querySelector(".slide{{ tabn }}-prev");
let next{{ tabn }} = document.querySelector(".slide{{ tabn }}-next");

if (!slides{{ tabn }}.length == 0) {
  let slideIndex{{ tabn }} = 1;
  showSlides{{ tabn }}(slideIndex{{ tabn }});

  function plusSlides{{ tabn }}(n) {
    showSlides{{ tabn }}((slideIndex{{ tabn }} += n));
  }

  let currentSlide{{ tabn }} = function (n) {
    showSlides{{ tabn }}((slideIndex{{ tabn }} = n));
  };

  function showSlides{{ tabn }}(n) {
    if (n > slides{{ tabn }}.length) {
      slideIndex{{ tabn }} = 1;
    }

    if (n < 1) {
      slideIndex{{ tabn }} = slides{{ tabn }}.length;
    }

    for (i = 0; i < slides{{ tabn }}.length; i++) {
      slides{{ tabn }}[i].style.display = "none";
    }

    for (i = 0; i < dots{{ tabn }}.length; i++) {
      dots{{ tabn }}[i].className = dots{{ tabn }}[i].className.replace(" slide{{ tabn }}-active", "");
    }

    slides{{ tabn }}[slideIndex{{ tabn }} - 1].style.display = "block";
    dots{{ tabn }}[slideIndex{{ tabn }} - 1].className += " slide{{ tabn }}-active";
  }
}

prev{{ tabn }}.addEventListener("click", () => {
  plusSlides{{ tabn }}(-1);
});

next{{ tabn }}.addEventListener("click", () => {
  plusSlides{{ tabn }}(1);
});
</script>

