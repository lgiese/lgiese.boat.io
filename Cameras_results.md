---
layout: gallery
title: Output Raspberry Pi Camera
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
    
The Raspberry Pi Camera was programmed, that it takes a picture once per minute (see <a href="{{ 'cam_engl.html' | absolute_url }}">Equipment-Cameras</a>). In the end it looks like the following:
    
<!--style="width: 600px; height: 400px; top: 6px; left: 700px; opacity: 1;" -->
<!-- Container for the image gallery -->
        <div class="demo-gallery">
            <ul id="lightgallery" class="list-unstyled row">
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/RaspiCam/RaspiCam1.JPG 375, assets/images/RaspiCam/RaspiCam1.JPG 480, assets/images/RaspiCam/RaspiCam1.JPG 800" data-src="{{ 'assets/images/RaspiCam/RaspiCam1.JPG' | absolute_url }}" data-sub-html="<h4>RaspiCam1</h4><p>Picture 1: Trees and bushes at the river bank. Pictures are taken by Mr. Turtle from the Lahn river (Marburg/Germany).</p>">
                    <a href="assets/images/RaspiCam/RaspiCam1.JPG">
                        <img class="image" src="assets/images/RaspiCam/RaspiCam1.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="{{ 'assets/images/RaspiCam/RaspiCam2.JPG' | relative_url }} 375, {{ 'assets/images/RaspiCam/RaspiCam2.JPG' | relative_url }} 480, {{ 'assets/images/RaspiCam/RaspiCam2.JPG' | relative_url }} 800" data-src="{{ 'assets/images/RaspiCam/RaspiCam2.JPG' | relative_url }}" data-sub-html="<h4>RaspiCam2</h4><p>Picture 2: Trees and bushes at the river bank. Pictures are taken by Mr. Turtle from the Lahn river (Marburg/Germany).</p>">
                    <a href="{{ 'assets/images/RaspiCam/RaspiCam2.JPG' | relative_url }}">
                        <img class="image" src="{{ 'assets/images/RaspiCam/RaspiCam2.JPG' | relative_url }}">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/RaspiCam/RaspiCam3.JPG 375, assets/images/RaspiCam/RaspiCam3.JPG 480, assets/images/RaspiCam/RaspiCam3.JPG 800" data-src="{{ 'assets/images/RaspiCam/RaspiCam3.JPG' | absolute_url }}" data-sub-html="<h4>RaspiCam3</h4><p>Picture 3: Trees and bushes at the river bank. Pictures are taken by Mr. Turtle from the Lahn river (Marburg/Germany).</p>">
                    <a href="assets/images/RaspiCam/RaspiCam3.JPG">
                        <img class="image" src="assets/images/RaspiCam/RaspiCam3.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/RaspiCam/RaspiCam4.JPG 375, assets/images/RaspiCam/RaspiCam4.JPG 480, assets/images/RaspiCam/RaspiCam4.JPG 800" data-src="{{ 'assets/images/RaspiCam/RaspiCam4.JPG' | absolute_url }}" data-sub-html="<h4>RaspiCam4</h4><p>Picture 4: Trees and bushes at the river bank. Pictures are taken by Mr. Turtle from the Lahn river (Marburg/Germany).</p>">
                    <a href="assets/images/RaspiCam/RaspiCam4.JPG">
                        <img class="image" src="assets/images/RaspiCam/RaspiCam4.JPG">
                    </a>
                </div>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/RaspiCam/RaspiCam5.JPG 375, assets/images/RaspiCam/RaspiCam5.JPG 480, assets/images/RaspiCam/RaspiCam5.JPG 800" data-src="{{ 'assets/images/RaspiCam/RaspiCam5.JPG' | absolute_url }}" data-sub-html="<h4>RaspiCam5</h4><p>Picture 5: Trees and bushes at the river bank. Pictures are taken by Mr. Turtle from the Lahn river (Marburg/Germany).</p>">
                    <a href="assets/images/RaspiCam/RaspiCam5.JPG">
                        <img class="image" src="assets/images/RaspiCam/RaspiCam5.JPG">
                    </a>
                <div class="justified-gallery" style="width: 680px; height: 340px; top: 6px; left: 4px;" data-responsive="assets/images/RaspiCam/RaspiCam6.JPG 375, assets/images/RaspiCam/RaspiCam6.JPG 480, assets/images/RaspiCam/RaspiCam6.JPG 800" data-src="{{ 'assets/images/RaspiCam/RaspiCam6.JPG' | absolute_url }}" data-sub-html="<h4>RaspiCam6</h4><p>Picture 6: Trees and bushes at the river bank. Pictures are taken by Mr. Turtle from the Lahn river (Marburg/Germany).</p>">
                    <a href="assets/images/RaspiCam/RaspiCam6.JPG">
                        <img class="image" src="assets/images/RaspiCam/RaspiCam6.JPG">
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

<section>
    
<ul class="pagination">
        <li><a href="{{ 'Lidar_results.html' | absolute_url }}" class="button">Prev</a></li>
        <li><a href="{{ 'Sonar_results.html | absolute_url }}" class="page active">1</a></li>
        <li><a href="{{ 'Lidar_results.html' | absolute_url }}" class="page active">2</a></li>
        <li><a href="{{ 'Cameras_results.html' | absolute_url }}" class="page active">3</a></li>
        <li><a href="{{ 'Sonar_results.html | absolute_url }}" class="button">Next</a></li>
</ul>