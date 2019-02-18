---
layout: page
title: Temperature
---
<span class="image right">
            <img src="{{ 'assets/images/Temperature.JPG ' | absolute_url }}" alt=""/>
            Fig. 1: Waterproof temperature sensor (DS18B20). The long waterproof wire is led through a grouted whole in the box, where it is connected to the Raspberry Pi.
        </span>

<p> To measure water temperature we bought a waterproof temperature sensor produced py <a  href="https://www.sparkfun.com/products/11050">Sparkfun Electronics</a> (Fig. 1). When Mr. Turtle floats on the water it drifts behind the platform and registers the surface water temperature.</p>

<h3>Setup</h3>

<p>To set up the temperature sensor on the Raspberry Pi we followed instructions on <a  href="https://tutorials-raspberrypi.de/raspberry-pi-temperatur-mittels-sensor-messen/">Raspberry Pi Tutorials</a>. Additionally to the RasPi, wires and a breadboard/printed circuit board we need a 4.7 kΩ resistor.</p>

<h3>Script</h3>

With this Python 2 script the surface temperature is measured:

    import RPi.GPIO as GPIO

    GPIO.setmode(GPIO.BOARD)
    GPIO.setup(12, GPIO.IN)
    def temp_messen():
        # read 1-Wire Slave list
        file = open('/sys/bus/w1/devices/w1_bus_master1/w1_master_slaves')
        w1_slaves = file.readlines()
        file.close()

        # get current temperature for every 1-Wire Slave
        for line in w1_slaves:
            # extract 1-wire Slave
            w1_slave = line.split("\n")[0]
            # read file 1-wire Slave
            file = open('/sys/bus/w1/devices/' + str(w1_slave) + '/w1_slave')
            filecontent = file.read()
            file.close()

            # read temperature values and convert them
            stringvalue = filecontent.split("\n")[1].split(" ")[9]
            temperature = float(stringvalue[2:]) / 1000

            # print tamperature values
            print(str(w1_slave) + ': %6.2f C' % temperature)
        return(temperature)

    temp_messen()

<ul class="pagination">
        <li><a href="{{ 'cam.html' | absolute_url }}" class="button">Prev</a></li>
        <li><a href="{{ 'Overview.html' | absolute_url }}" class="page">1</a></li>
        <li><a href="{{ 'sonarsensor.html' | absolute_url }}" class="page">2</a></li>
        <li><a href="{{ 'lidar.html' | absolute_url }}" class="page">3</a></li>
        <li><a href="{{ 'cam.html' | absolute_url }}" class="page">4</a></li>
        <li><a href="{{ 'temperature.html' | absolute_url }}" class="page active">5</a></li>
        <li><a href="{{ 'Overview.html' | absolute_url }}" class="button">Next</a></li>
</ul>

