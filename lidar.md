---
layout: page
title: Lidar
---

### Garmin Lidar Lite 3

<div class="box alt">
    <div class="row 50% uniform">
        <div class="4u"><span class="image fit">
            <img src="{{ 'assets/images/LidarServos.JPG ' | absolute_url }}" alt=""/>
            Fig. 1: LidarLite and 2 servos. The video (right) demonstrates the servo-driven motion system, which scans the environment.
        </span></div>
        <div class="4u"><video style="width: 610px; height: 433px;" controls>
                <source src="{{ 'assets/images/LidarAtwork_mute.mp4 ' | absolute_url }}" type="video/mp4">
        </video></div>
    </div>
</div>

<p> Garmin Lidar Lite 3 ( Lidar = laser detection and ranging, Fig. 1) is a sensor, which calculates distance by emitting and recieving Laser light. In combination with the servo-driven motion system (Vid. 1) we generate a 3 dimensional point cloud of the environment (see <a href="{{ 'Lidar_results.html' | absolute_url }}">point cloud example</a>).</p>

<h3>Setup</h3>

<span class="image right">
    <img src="{{ 'assets/images/solderedLidar.JPG ' | absolute_url }}" alt=""/>
    Fig. 1: Soldered Lidar, servo and Temperature connections plugged to the Raspberry Pi 3
</span>

<p>To connect the Lidar to the Raspi 3 we used:</p>
<p><li> A Raspberry Pi 3, which is pre-installed with the free-to-use operating system "Noobs", available on: <a  href="https://www.raspberrypi.org/downloads/noobs/">https://www.raspberrypi.org/downloads/noobs/</a></li>
<li>Connection wires</li>
<li>A printed circuit board</li>
<li>1000µF Electrolytic Capacitor</li></p>
<p>It takes four steps to get the lidar running (a more detailed instruction is provided by <a href="https://mobiusstripblog.wordpress.com/2016/12/26/first-blog-post/">Mobius Strip Blog</a>):
<li>Connect the wires the right way. Our result (plus temperature sensor connections) you can see <a href="{{ 'Overview.html' | absolute_url }}">here</a> in Fig. 3 at the page bottom. The wires are soldered to the printed circuit board to guard it against intermittend contact. The result is shown in Fig. 2.</li>
<li>Turn on the I2C pin on the RasPi</li>
<li>Install the I2C tools</li>
<li>In our case the RasPi Kernel needed to be downgraded to version 4.4 before the lidar was communicating with the RasPi (see <a href="https://forum-raspberrypi.de/forum/thread/21114-firmware-u-kernel-downgrade-mit-rpi-update/">Raspberry Pi Forum</a>)</li>
 </p>

<h3>Lidar Script</h3>

The following Python 2 script controls the scanning pattern of the lidar and saves the lidar data. It moves from top to bottom and from left to right. It scans an left-right-angle of 81 degrees and a top-bottom-angle of 35 degrees in total. The angles can be adjusted by editing the skript. 
When the lidar is attached to the platform it is orientated sideways. This way it scans one side of the river.

    #import modules, place lidar_lite.py in the same folder
    import RPi.GPIO as GPIO
    import time
    import csv
    from lidar_lite import Lidar_Lite

    #initialize lidar
    lidar = Lidar_Lite()

    connected = lidar.connect(1)
    if connected < -1:
        print("nema connecta")

    #set pin numbers, board layout, pin mode, pwm freq., start pwm signal at 0 degress
    servo1 = 16
    servo2 = 18
    GPIO.setmode(GPIO.BOARD)
    GPIO.setup(servo1, GPIO.OUT)
    GPIO.setup(servo2, GPIO.OUT)
    p = GPIO.PWM(servo1, 50)
    q = GPIO.PWM(servo2, 50)
    q.start(2.5)
    p.start(2.5)

    #angles for the servos to rotate, x i left and right, y is up and down
    px = [i  * 2.5  for i in reversed(range(16,35))]
    py = [56 + i*2 for i in range(0,11)]
    erg = []


    #runs until ctrl + c is pressed
    try:
        while True:
            #sets servos first y then x
            for y in py:
                q.ChangeDutyCycle(float(y/10.0))
                for x in px:
                    p.ChangeDutyCycle(float(x/10.0))
                    #sleep for more steady movement
                    time.sleep(0.05)
                    time.sleep(0.05)
                    #lidar messearue
                    dist = lidar.getDistance()
                    erg.append([x,y,dist])
            #write csv, append to file after each run
            with open("output.csv", "a") as f:
                writer = csv.writer(f)
                writer.writerows(erg)
            erg = []
        except KeyboardInterrupt:
            p.stop()
            q.stop()
            GPIO.cleanup() 

<ul class="pagination">
        <li><a href="{{ 'sonarsensor.html' | absolute_url }}" class="button">Prev</a></li>
        <li><a href="{{ 'Overview.html' | absolute_url }}" class="pag">1</a></li>
        <li><a href="{{ 'sonarsensor.html' | absolute_url }}" class="page">2</a></li>
        <li><a href="{{ 'lidar.html' | absolute_url }}" class="page active">3</a></li>
        <li><a href="{{ 'cam.html' | absolute_url }}" class="page">4</a></li>
        <li><a href="{{ 'temperature.html' | absolute_url }}" class="page">5</a></li>
        <li><a href="{{ 'cam.html' | absolute_url }}" class="button">Next</a></li>
</ul>