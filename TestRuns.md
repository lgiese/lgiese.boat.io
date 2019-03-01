---
layout: gallery
title: Gallery - Test Runs
---

 <head>
       <style type="text/css">
            .demo-gallery > ul .justified-gallery {
              display: block;
              overflow: hidden;
              position: left;
              float: left;
              margin: 1em 0.5em 1em 1em;
              padding-right: 3em;
              border: solid 1px rgba(210, 215, 217, 0.75);
			  border-top: 0;
			  border-left: 0;
              border-bottom: 0;
            }
            .demo-gallery > ul {
             margin-bottom: 0;
            }
            .demo-gallery > ul > li {
                float: left;
                margin-bottom: 15px;
                margin-right: 20px;
                width: 200px;
            }
            .demo-gallery > ul > li a {
              border: 3px solid #FFF;
              border-radius: 3px;
              display: block;
              overflow: hidden;
              position: relative;
              float: left;
            }
            .demo-gallery > ul > li a > img {
              -webkit-transition: -webkit-transform 0.15s ease 0s;
              -moz-transition: -moz-transform 0.15s ease 0s;
              -o-transition: -o-transform 0.15s ease 0s;
              transition: transform 0.15s ease 0s;
              -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
              height: 100%;
              width: 100%;
            }
            .demo-gallery > ul > li a:hover > img {
              -webkit-transform: scale3d(1.1, 1.1, 1.1);
              transform: scale3d(1.1, 1.1, 1.1);
            }
            .demo-gallery > ul > li a:hover .demo-gallery-poster > img {
              opacity: 1;
            }
            .demo-gallery > ul > li a .demo-gallery-poster {
              background-color: rgba(0, 0, 0, 0.1);
              bottom: 0;
              left: 0;
              position: absolute;
              right: 0;
              top: 0;
              -webkit-transition: background-color 0.15s ease 0s;
              -o-transition: background-color 0.15s ease 0s;
              transition: background-color 0.15s ease 0s;
            }
            .demo-gallery > ul > li a .demo-gallery-poster > img {
              left: 50%;
              margin-left: -10px;
              margin-top: -10px;
              opacity: 0;
              position: absolute;
              top: 50%;
              -webkit-transition: opacity 0.3s ease 0s;
              -o-transition: opacity 0.3s ease 0s;
              transition: opacity 0.3s ease 0s;
            }
            .demo-gallery > ul > li a:hover .demo-gallery-poster {
              background-color: rgba(0, 0, 0, 0.5);
            }
            .demo-gallery .justified-gallery > a > img {
              -webkit-transition: -webkit-transform 0.15s ease 0s;
              -moz-transition: -moz-transform 0.15s ease 0s;
              -o-transition: -o-transform 0.15s ease 0s;
              transition: transform 0.15s ease 0s;
              -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
              height: 100%;
              width: 100%;
            }
            .demo-gallery .justified-gallery > a:hover > img {
              -webkit-transform: scale3d(1.1, 1.1, 1.1);
              transform: scale3d(1.1, 1.1, 1.1);
            }
            .demo-gallery .justified-gallery > a:hover .demo-gallery-poster > img {
              opacity: 1;
            }
            .demo-gallery .justified-gallery > a .demo-gallery-poster {
              background-color: rgba(0, 0, 0, 0.1);
              bottom: 0;
              left: 0;
              position: absolute;
              right: 0;
              top: 0;
              -webkit-transition: background-color 0.15s ease 0s;
              -o-transition: background-color 0.15s ease 0s;
              transition: background-color 0.15s ease 0s;
            }
            .demo-gallery .justified-gallery > a .demo-gallery-poster > img {
              left: 50%;
              margin-left: -10px;
              margin-top: -10px;
              opacity: 0;
              position: absolute;
              top: 50%;
              -webkit-transition: opacity 0.3s ease 0s;
              -o-transition: opacity 0.3s ease 0s;
              transition: opacity 0.3s ease 0s;
            }
            .demo-gallery .justified-gallery > a:hover .demo-gallery-poster {
              background-color: rgba(0, 0, 0, 0.5);
            }
            .demo-gallery .video .demo-gallery-poster img {
              height: 48px;
              margin-left: -24px;
              margin-top: -24px;
              opacity: 0.8;
              width: 48px;
            }
            .demo-gallery.dark > ul > li a {
              border: 3px solid #04070a;
            }
            .home .demo-gallery {
              padding-bottom: 80px;
            }
        </style>
<!-- jQuery version must be >= 1.8.0; -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
</head>

<section>
    <body>
<h1>Videos</h1>

<p><span class="image left" data-sub-html="<h4>Test Run 3D printed Boat</h4><p>Water in the boat</p>"><video controls><source src="{{ 'assets/videos/TRboat3D.mp4' | absolute_url }}" type="video/mp4">
                </video><b>Test Run 3D printed Boat</b> Water in the boat</span><h4>3D printed Boat</h4>For the first test drive we connected the boat to a fishing line for security reasons. The boat is quite manoeuvrable but also very shaky while driving. The latter is a big minus concerning our plans to scan riparian vegetation. In addition the wave-powered propulsion system makes it quite difficult to prevent water from penetrating into the boat. We endet up being a hair's breadth away from wet and broken electronics.</p>
                
<p><span class="image right" data-sub-html="<h4>The Catamaran</h4><p>Testing the first catamaran prototype</p>"><video controls><source src="{{ 'assets/videos/TRcatamaran.mp4' | absolute_url }}" type="video/mp4">
                </video><b>Testing the first catamaran prototype</b> Water in the boat</span><h4>The Catamaran</h4>The catamaran is an approach to achieve a more stable drift and more space for the sensors. More mayyybee yes, but stable drift... OOuups... not yet!</p>
                
<p><span class="image left" data-sub-html="<h4>Mr. Turtle #1</h4><p>Smoking motor</p>"><video controls><source src="{{ 'assets/videos/smokingEngine.mp4' | absolute_url }}" type="video/mp4">
                </video><b>Mr. Turtle #1</b> Smoking motor</span><h4>Mr. Turtle #1</h4>Mr. Turtle #1 drifts much more stable on the watersurface. For some reason one of the two motors started smoking when we were testing our first floating platform prototype. Consequently the propulsion system hat to be improved.</p>
                                
<p><span class="image right" data-sub-html="<h4>Mr. Turtle #2</h4><p>Test run of the final version of Mr. Turtle</p>"><video controls><source src="{{ 'assets/videos/index_trans3.mp4' | absolute_url }}" type="video/mp4">
    </video><b>Mr. Turtle #2</b> Manual control mode</span><h4>Mr. Turtle #2</h4>This is a test run of the final Mr. Turtle version without sensors in manual mode. We are testing if updrift is strong enough, the manoevrability in manual mode and the automatic mode. Updrift was strong enough, the platform stayed largely dry. Manoevrability was appropriate for Mr. Turtle´s size and it´s function as a Limno-explorer, what means moving with low speed while performing measurements. One Problem with the propulsion couldn´t be fixed by now: The cogwheels turn discontinously and sometimes get stuck somehow, so it might happend that the propellers have to be rearranged parallel manually.
    </p>
    
<p><span class="image left" data-sub-html="<h4>Mr. Turtle #2</h4><p>Automatic control mode</p>"><video controls><source src="{{ 'assets/videos/TR4automatic.mp4' | absolute_url }}" type="video/mp4">
                </video><b>Mr. Turtle #2</b> Automatic control mode</span>While testing the boat with full sensor equippment we had our biggest success: Automatic mode is working!!!</p>
                
</body>
<hr class="major" />

<section>
<section>    
<body>
<div class="row 200%">
<h1>More Images</h1>
<!--style="width: 600px; height: 400px; top: 6px; left: 700px; opacity: 1;" -->
<!-- Container for the image gallery -->
        <div class="demo-gallery">
            <ul id="lightgallery" class="unstyled row">
                <div class="justified-gallery" style = "width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR1.JPG 375, assets/images/TestRun/TR1.JPG 480, assets/images/TestRun/TR1.JPG 800" data-src="{{ 'assets/images/TestRun/TR1.JPG' | absolute_url }}" data-sub-html="<h4>Preparations1</h4><p>Connecting the Pixhawk with the Lipo to start the first Test run...</p>">
                    <a href="assets/images/TestRun/TR1.JPG">
                        <img class="4u" src="assets/images/TestRun/TR1.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR2.JPG 375, assets/images/TestRun/TR2.JPG 480, assets/images/TestRun/TR2.JPG 800" data-src="{{ 'assets/images/TestRun/TR2.JPG' | absolute_url }}" data-sub-html="<h4>Preparations2</h4><p>Last steps to get ready for sea?!</p>">
                    <a href="assets/images/TestRun/TR2.JPG">
                        <img class="fit-right" src="assets/images/TestRun/TR2.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR3.JPG 375, assets/images/TestRun/TR3.JPG 480, assets/images/TestRun/TR3.JPG 800" data-src="{{ 'assets/images/TestRun/TR3.JPG' | absolute_url }}" data-sub-html="<h4>Preparations3</h4><p>Charging the Camera. The Sonar (black ball) will be connected to the boat by a line.</p>">
                    <a href="assets/images/TestRun/TR3.JPG">
                        <img class="fit-left" src="assets/images/TestRun/TR3.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR4.JPG 375, assets/images/TestRun/TR4.JPG 480, assets/images/TestRun/TR4.JPG 800" data-src="{{ 'assets/images/TestRun/TR4.JPG' | absolute_url }}" data-sub-html="<h4>SavetyStuff1</h4><p>Preparing the safety boat...</p>">
                    <a href="assets/images/TestRun/TR4.JPG">
                        <img class="fit-right" src="assets/images/TestRun/TR4.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR5.JPG 375, assets/images/TestRun/TR5.JPG 480, assets/images/TestRun/TR5.JPG 800" data-src="{{ 'assets/images/TestRun/TR5.JPG' | absolute_url }}" data-sub-html="<h4>SavetyStuff2</h4><p>... And don´t forget the savety west! The Sonar gets a safety fishing rod.</p>">
                    <a href="assets/images/TestRun/TR5.JPG">
                        <img class="fit-left" src="assets/images/TestRun/TR5.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR6.JPG 375, assets/images/TestRun/TR6.JPG 480, assets/images/TestRun/TR6.JPG 800" data-src="{{ 'assets/images/TestRun/TR6.JPG' | absolute_url }}" data-sub-html="<h4>SavetyStuff3</h4><p>The Sonar gets a safety fishing rod 2...</p>">
                    <a href="assets/images/TestRun/TR6.JPG">
                        <img class="fit-right" src="assets/images/TestRun/TR6.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 410px; height: 500px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR7.JPG 375, assets/images/TestRun/TR7.JPG 480, assets/images/TestRun/TR7.JPG 800" data-src="{{ 'assets/images/TestRun/TR7.JPG' | absolute_url }}" data-sub-html="<h4>AfterCheck</h4><p>Is everything alright after the first drive?</p>">
                    <a href="assets/images/TestRun/TR7.JPG">
                        <img class="fit-left" src="assets/images/TestRun/TR7.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 410px; height: 500px; top: 6px; left: 4px;" data-responsive="assets/images/TestRun/TR8.JPG 375, assets/images/TestRun/TR8.JPG 480, assets/images/TestRun/TR8.JPG 800" data-src="{{ 'assets/images/TestRun/TR8.JPG' | absolute_url }}" data-sub-html="<h4>WaterInBoat</h4><p>AAHHH, Water in the boat!</p>">
                    <a href="assets/images/TestRun/TR8.JPG">
                        <img class="fit-right" src="assets/images/TestRun/TR8.JPG">
                    </a>
                </div>                
        </ul>
</div>

<script type="text/javascript">
$(document).ready(function(){
    $('#lightgallery').lightGallery();
});
</script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-mousewheel/3.1.13/jquery.mousewheel.min.js"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/lightgallery/1.6.11/js/lightgallery-all.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/picturefill/3.0.3/picturefill.min.js"></script>

<!-- lightgallery plugins -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/lg-thumbnail/1.1.0/lg-thumbnail.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/lg-fullscreen/1.0.1/lg-fullscreen.min.js"></script>
<script src="{{ 'assets/js/skel.min.js' | absolute_url }}"></script>
<script src="{{ 'assets/js/util.js' | absolute_url }}"></script>
<!--[if lte IE 8]><script src="{{ 'assets/js/ie/respond.min.js' | absolute_url }}"></script><![endif]-->
<script src="{{ 'assets/js/main.js' | absolute_url }}"></script>
</div>
</body> 
<section>