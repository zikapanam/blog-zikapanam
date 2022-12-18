---
layout: page
title: Témoignages
permalink: /testimonials
---
<h2>Témoignages PJC</h2>
<section class="customer-revs">
  <div class="rectangle"></div>

  <!-- Slideshow container -->
  <div class="slideshow-container">

{% assign sortedtestimonials = site.testimonials_pjc | sort: "index" %}

{% for testimonial in sortedtestimonials %}

    <!-- Full-width slides/quotes -->
    <div class="mySlides">
      <div class="mySlidesContainer">
        <q>
          {{ testimonial.content | remove: "<p>" | remove: "</p>" }}
        </q>
      </div>
      <p class="author">Par: <span>{{ testimonial.author }}</span><br/><span>{{ testimonial.attribution }}</span></p>
    </div>
{% endfor %}

    <!-- Next/prev buttons -->
    <a class="slide-prev">&#10094;</a>
    <a class="slide-next">&#10095;</a>

  </div><!-- END slidehow-container -->

  <!-- Dots/bullets/indicators -->
  <div class="dot-container">
  {% for testimonial in sortedtestimonials %}
    <span class="dot"></span>
  {% endfor %}
  </div>

</section>

<script>
let slides = document.getElementsByClassName("mySlides");
let dots = document.getElementsByClassName("dot");
let prev = document.querySelector(".slide-prev");
let next = document.querySelector(".slide-next");

if (!slides.length == 0) {
  let slideIndex = 1;
  showSlides(slideIndex);

  function plusSlides(n) {
    showSlides((slideIndex += n));
  }

  let currentSlide = function (n) {
    showSlides((slideIndex = n));
  };

  function showSlides(n) {
    if (n > slides.length) {
      slideIndex = 1;
    }

    if (n < 1) {
      slideIndex = slides.length;
    }

    for (i = 0; i < slides.length; i++) {
      slides[i].style.display = "none";
    }

    for (i = 0; i < dots.length; i++) {
      dots[i].className = dots[i].className.replace(" slide-active", "");
    }

    slides[slideIndex - 1].style.display = "block";
    dots[slideIndex - 1].className += " slide-active";
  }
}

prev.addEventListener("click", () => {
  plusSlides(-1);
});

next.addEventListener("click", () => {
  plusSlides(1);
});

</script>

