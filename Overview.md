---
layout: page
title: Overview - Sensors and more
---

<p> Mr. Turtle is currently equipped with a Sonar-, Lidar- and a Temerature-Sensor. A Raspberry Pi 3 is logging the data and controlling how the single parts are working via simple programs. Additionally we need two servos to control driving direction. Several accus, two Motors and propellers, the Ardu-Pilot and an additional GPS are also on board. This page gives an Overview of: </p>

<ul>
    <li>the functioning of the platform</li>
    <li>how the equipment is set up on the platform</li>
    <li>how the equipment is connected to each other</li>
</ul>

<h2>Platform and Equipment</h2>

<span class="image fit">
      <img src="{{ 'assets/images/Platform_setup.JPG ' | absolute_url }}" alt=""/>
      Fig. 1: **Platform Setup**
      *Turtle-Platform (brown bounding box) with current equipment. Waterproof boxes (yellow bounding boxes) contain electronic devices like Raspberry Pis, Handy, Batteries, Pixhawk, Power module and ESC. 2 Servos are in charge of changing the Lidar position and another 2 servos change the rotor position. A waterproof temperature sensor and the Sonar are connected to the platform by wires and are dragged behind the Turtle.  [Foto of Pixhawk/Motor: © PX4 Dev Team. License: CC BY 4.0](https://docs.px4.io/en/assembly/quick_start_pixhawk.html)*
</span>

<h3>Drive</h3>

<p> Mr. Turtle´s drive is controlled by the 3DR Pixhawk (Fig. 1), which is a flight controller for drones. It enables to steer the platform manually via Telemetry or in automatic mode via GPS. The Pixhawk is connected to two servos, one for each propeller in the back of the boat. We 3D-printed a mounting for the motors (Fig. 2), which can be stably attached to the servos. This way, the servos can turn the propellers around a vertical axis and the Turtle can change driving direction. The motors spin the rotors and are driven by the Pixhawk. Power is provided by 2 (or more) 14V Lithium Ion Polymer batteries.</p>

<h3>Raspberry Pi & Sensors</h3>

<span class="image left">
      <img src="{{ 'assets/images/Sensors_boat_fritz.JPG ' | absolute_url }}" alt=""/>
      Fig. 3: *LidarLite, 2 servos to change Lidar position and a temperature sensor connected to Raspberry Pi*
</span>

<p> The Raspberry Pi, which is connected to the Temperature Sensor and the Lidar in Fig. 1 is responsible for storing data and controlling the functioning of the Sensors. In Fig. 3 you see, how the wiring of a setting containing Sonar-, Lidar- and a Temerature-Sensor and two servos is done. The servos are integrated in a mounting for the Lidar. Thank´s to this mounting the Lidar can be turned around a horizontal and a vertical axis. A more detailed description of the wiring and functioning of the Sensors can be found in the following pages of the Equipment-menu.</p>

<h3>Drive</h3>

<p> The Deeper-Sonar is losely connected to the Turtle by a simple string. Like this it is drifting behind the platform on the water surface. It is working independently and is connected to a on-board mobile phone (Fig. 1) via wifi. Due to the Deeper-software data can´t be directly stored on the RasPi.</p>

<h3> Literature/Info</h3>

<ul>
    <li><a href="https://tutorials-raspberrypi.de/raspberry-pi-temperatur-mittels-sensor-messen/">https://tutorials-raspberrypi.de/raspberry-pi-temperatur-mittels-sensor-messen/</a></li>
    <li><a href="https://mobiusstripblog.wordpress.com/2016/12/26/first-blog-post/ ">https://mobiusstripblog.wordpress.com/2016/12/26/first-blog-post/ </a></li>
    <li><a href="https://www.instructables.com/id/Raspberry-Pi-Tutorial-How-to-Use-a-Buzzer/">https://www.instructables.com/id/Raspberry-Pi-Tutorial-How-to-Use-a-Buzzer/</a></li>
    <li><a href="https://codingworld.io/project/der-servo-am-raspberry-pi">https://codingworld.io/project/der-servo-am-raspberry-pi</a></li>
    <li><a href="https://www.datenreise.de/raspberry-pi-wie-verwendet-man-ein-breadboard-steckplatine-anleitung/">https://www.datenreise.de/raspberry-pi-wie-verwendet-man-ein-breadboard-steckplatine-anleitung/</a></li>
</ul>