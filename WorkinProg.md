---
layout: page
title: Gallery
---

<section>
	<header class="major">
		<h2>Work in Progress</h2>
	</header>
<!-- Container for the image gallery -->
<div class="container">

  <!-- Full-width images with number text -->
  <div class="mySlides">
    <div class="numbertext">1 / 6</div>
      <img src="{{ 'assets/images/WorkinProg/WIP1.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">2 / 6</div>
      <img src="{{ 'assets/images/WorkinProg/WIP2.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">3 / 6</div>
      <img src="{{ 'assets/images/WorkinProg/WIP3.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">4 / 6</div>
      <img src="{{ 'assets/images/WorkinProg/WIP4.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">5 / 6</div>
      <img src="{{ 'assets/images/WorkinProg/WIP5.jpg' | absolute_url }}" style="width:100%">
  </div>

  <!-- Next and previous buttons -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>

  <!-- Image text -->
  <div class="caption-container">
    <p id="caption"></p>
  </div>

  <!-- Thumbnail images -->
  <div class="row">
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/WorkinProg/WIP1.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(1)" alt="3D printed boat with motor, accu, rudder and ship wave">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/WorkinProg/WIP2.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(2)" alt="Glueing the boat top 1">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/WorkinProg/WIP3.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(3)" alt="Glueing the boat top 2">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/WorkinProg/WIP4.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(4)" alt="Connecting RasPi-Cam 1">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/WorkinProg/WIP5.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(5)" alt="Connecting RasPi-Cam 2">
    </div>
  </div>
</div>


<section>
    
