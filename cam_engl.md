---
layout: page
title: Cameras
---

<p>To investigate the visible spectrum beyond the water surface MR TURTLE (The Unmanned Radio Telemetry Limnology-Exlorer) is equipped with a camera on deck. Due to the pre-existing Raspberry Pi the decision was made during the preliminary stages to choose a Raspberry Pi Camera. Furthermore relevant arguments are the cheap price as well as the unproblematic installation.</p>

<p>The following text describes the Raspberry Pi Camera V2.1 installation, including an example for an automatic picture recording script combined with an auto boot script using crontab.</p>

<p>The Raspberry Pi is pre-installed with the free-to-use operating system "Noobs", available on: <a  href="https://www.raspberrypi.org/downloads/noobs/">https://www.raspberrypi.org/downloads/noobs/</a></p>

<p>The Camera is plugged into the CSI-Interface.</p>


<span class="image left">
    {%include images/Cam1Klee.md %}
    Fig. 1: *Camera connected to the Raspberry Pi*
</span>



<p> Afterwards the camera can be activated using the following settings.</p>

    Settings -> Raspberry-Pi-Configuration -> Interfaces -> Camera enable

<p> The camera can be alternatively activated using the console. </p>

    sudo raspi-config -> interfacing options -> Camera enable

<p> Now a new document can be created applying an arbitrary editor. The document will include the camera script, taking pictures each second for one minute and saving them indicating a filename with integrated timestamp. An auto boot script (Crontab) executes the camera script each minute. </p>

    #Picture directory 
    IMGDIR='/home/pi/camera' 

    # timestamp
    TIME=$(date +%d%m%Y_%H:%M)

    # picture label with continuous, binary numbers
    BILD=$Bild%02d 

    # create filename 
    FILENAME=$IMGDIR/$TIME:$BILD.jpg 

    # sequence of images
    raspistill -w 1200 -h 800 -tl 1000 -t 58000 -o $FILENAME -n 

<p>The script should be saved local using the file extension ".sh". For futher investigation it is recommended to save the script using the path "/home/pi/camerascript". </p>

<p>Explanations: </p>

    raspistill: comand to take pictures
    -w          width of resolution
    -h          height of resolution 
    -tl 1000:   taking pictures eath second 
                (Raspberry Pi enables max. 900 (millisecond) continuous repetition rates)
    -t 58000:   period of time
    -o          save location
    -n          to quash the preview

<p>Thereafter a crontab will be created to execute the camera script after booting the Raspberry Pi. </p>

<p>Type into the console </p>

    sudo crontab -e 

<p>An editor has to been choosen before running crontab the first time. The nano editor is easy to handle (select 2 and confirm with enter)</p>

<p>Now add a new last line:</p>

    */1 * * * * sh cameraskript 

<p>Aftwards save the script using Strg + o. The following (memory) location is important.</p>

    /etc/ . /cron.d/crontab

<p> The script will now be executed once per minute. Detailed description handling with crontab can be found here: <a  href="https://github.com/mileusna/crontab">https://github.com/mileusna/crontab</a></p>

<p>There are a lot of possible ways for a water-resistant camera integration. On deck of the TURTLE, the Raspberry has been laid into a waterproof box, the camera tentative wrapped with foil. But there are countless ideas online. For example 3d printing cases: <a href="https://tinkererblog.wordpress.com/2015/07/28/how-i-designed-a-compact-weatherproof-raspberry-pi-case/">https://tinkererblog.wordpress.com/2015/07/28/how-i-designed-a-compact-weatherproof-raspberry-pi-case/</a></p>

<p>To move the camera vertial and horizontal a "Pan-Tilt HAT" by Pimoroni Ltd. has been additionally integrated.</p>

<span class="image right">
    {%include images/CamPanTilt.md %}
    Fig. 2: **PIMORONI** *Tech Treasure for Makers. [https://shop.pimoroni.com/products/pan-tilt-hat?variant=33704345034](https://shop.pimoroni.com/products/pan-tilt-hat?variant=33704345034)* 
</span>

<p>Detailed description can be found here: <a href="http://docs.pimoroni.com/pantilthat/#">http://docs.pimoroni.com/pantilthat/#</a> , <a href="https://github.com/pimoroni/pantilt-hat">https://github.com/pimoroni/pantilt-hat</a></p>

<p class="copyright">&copy; Maximilian Kleebauer. 12. September 2018 </p>

<ul class="pagination">
        <li><span class="button">Prev</span></li>
        <li><a href="#" class="page">1</a></li>
        <li><a href="{{ 'sonarsensor.html' | absolute_url }}" class="page">2</a></li>
        <li><a href="#" class="page">3</a></li>
        <li><a href="{{ 'cam.html' | absolute_url }}" class="page active">4</a></li>
        <li><a href="#" class="page">5</a></li>
        <li><a href="#" class="button">Next</a></li>
</ul>
