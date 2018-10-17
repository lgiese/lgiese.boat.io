---
layout: page
title: Gallery
---

<section>
	<header class="major">
		<h2>Test Runs</h2>
	</header>
<!-- Container for the image gallery -->
<div class="container">

  <!-- Full-width images with number text -->
  <div class="mySlides">
    <div class="numbertext">1 / 8</div>
      <img src="{{ 'assets/images/TestRun/TR1.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">2 / 8</div>
      <img src="{{ 'assets/images/WorkinProg/WIP2.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">3 / 8</div>
      <img src="{{ 'assets/images/TestRun/TR3.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">4 / 8</div>
      <img src="{{ 'assets/images/TestRun/TR4.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">5 / 8</div>
      <img src="{{ 'assets/images/TestRun/TR5.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">6 / 8</div>
      <img src="{{ 'assets/images/TestRun/TR6.jpg' | absolute_url }}" style="width:100%">
  </div>
  
  <div class="mySlides">
    <div class="numbertext">7 / 8</div>
      <img src="{{ 'assets/images/TestRun/TR7.jpg' | absolute_url }}" style="width:100%">
  </div>

  <div class="mySlides">
    <div class="numbertext">8 / 8</div>
      <img src="{{ 'assets/images/TestRun/TR8.jpg' | absolute_url }}" style="width:100%">
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
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR1.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(1)" alt="3D printed boat with motor, accu, rudder and ship wave">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR2.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(2)" alt="Glueing the boat top 1">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR3.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(3)" alt="Glueing the boat top 2">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR4.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(4)" alt="Connecting RasPi-Cam 1">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR5.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(5)" alt="Connecting RasPi-Cam 2">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR6.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(6)" alt="AHH, Water in the boat!">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR7.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(5)" alt="Connecting RasPi-Cam 2">
    </div>
    <div class="column">
      <img class="demo cursor" src="{{ 'assets/images/TestRun/TR8.jpg' | absolute_url }}" style="width:100%" onclick="currentSlide(6)" alt="AHH, Water in the boat!">
    </div>
  </div>
</div>

<video width="320" height="240" controls>
  <source src="{{ 'assets/images/TestRun/VideoTR4_Komp11.mp4' | absolute_url }}" type="video/mp4">
Your browser does not support the video tag.
</video>

<section>
    
