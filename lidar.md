---
layout: page
title: LidarLite
---

### Lidar Lite Raspberry Pi Sensor

<span class="image left">
      <img src="{{ 'assets/images/LidarServos.JPG ' | absolute_url }}" alt=""/>
      Image 1 *LidarLite and 2 Servos*
</span>

<h3>Script Lidar Position (Servos):</h3>

    import RPi.GPIO as GPIO
    import time
    from lidar_lite import Lidar_Lite
    import datetime

    lidar = Lidar_Lite()
    connected = lidar.connect(1)
    if connected < -1:
        print( "Not Connected")

    servoPIN1 = 24
    servoPIN2 = 23

    GPIO.setmode(GPIO.BCM)

    GPIO.setup(servoPIN1, GPIO.OUT)
    GPIO.setup(servoPIN2, GPIO.OUT)

    p1 = GPIO.PWM(servoPIN1, 50) # GPIO  als PWM mit 50Hz
    p2 = GPIO.PWM(servoPIN2, 50) # GPIO  als PWM mit 50Hz

    p1.start(2.5) # Initialisierung
    p2.start(2.5) # Initialisierung

    erg = []

    # Umrechnung Grad in Tastverhaeltnis je servo
    def setservo1(winkel):
        if winkel < 0:
            winkel = 0
        if winkel > 180:
            winkel = 180
        pwm = winkel/18 + 2.5
        p1.ChangeDutyCycle(pwm)

    def setservo2(winkel):
        if winkel < 0:
            winkel = 0
        if winkel > 180:
            winkel = 180
        pwm = winkel/18 + 2.5
        p2.ChangeDutyCycle(pwm)

    def move():
        erg = []
        lid =[]
        c = 0
        t1 = time.time()
        for i in range(58, 102, 4):
            setservo1(i)
            time.sleep(0.1)
            if c in [x for x in range(0, 150) if x%2 == 0 ]:
                for j in range(30, 95, 5):
                    setservo2(j)
                    time.sleep(0.1)
                    dist = lidar.getDistance()
                    erg.append( [chr(date.datetime.now(), i, j,dist] )
                    #lid.append(lidar.getDistance())
                    print(i,j, dist)
                c = c+1
            else:
                for j in range (95,30,-5):
                    setservo2(j)
                    time.sleep(0.1)
                    dist = lidar.getDistance()
                    erg.append( [chr(date.datetime.now(),i, j,dist] )
                    #print(dist)
                    #lid.append(lidar.getDistance())
                    print(i,j, dist)
                c = c+1

        for i in range(114, 70, -4):
            setservo1(i)
            time.sleep(0.1)
            if c in [x for x in range(0, 150) if x%2 == 0 ]:
                for j in range(30, 95, 5):
                    setservo2(j)
                    time.sleep(0.1)
                    dist = lidar.getDistance()
                    erg.append( [chr(date.datetime.now(),i, j,dist] )
                    #lid.append(lidar.getDistance())
                    #print(i,j, dist)
                c = c+1
            else:
                for j in range (95,30,-5):
                    setservo2(j)
                    time.sleep(0.1)
                    dist = lidar.getDistance()
                    erg.append( [chr(date.datetime.now(),i, j,dist] )
                    #print(dist)
                    #lid.append(lidar.getDistance())
                    #print(i,j, dist)
                c = c+1
            #print(i, j,dist)
        #GPIO.setup(servoPIN1, GPIO.OUT)
        #GPIO.setup(servoPIN2, GPIO.OUT)
        #p1 = GPIO.PWM(servoPIN1, 50) # GPIO  als PWM mit 50Hz
        #p2 = GPIO.PWM(servoPIN2, 50) # GPIO  als PWM mit 50Hz
        #p1.start(2.5) # Initialisierung
        #p2.start(2.5) # Initialisierung

        #print(i,j, dist)
        #print(c)
        #t2 =time.time()
        #print(t2-t1)
        #print(erg)
        return(erg)

    #    try:
    #        # Endlosschleife Servoansteuerung
    #    while True:
    #        t1 = time.time()
    #        test = move()
    #        t2 = time.time()
    #        print(t2-t1)
    #    except KeyboardInterrupt:
    #    # Abbruch mit [Strg][C],
    #    GPIO.cleanup()


<h3>Script Lidar Run:</h3>

    import smbus
    import time

    class Lidar_Lite():
        def __init__(self):
            self.address = 0x62
            self.distWriteReg = 0x00
            self.distWriteVal = 0x04
            self.distReadReg1 = 0x8f
            self.distReadReg2 = 0x10
            self.velWriteReg = 0x04
            self.velWriteVal = 0x08
            self.velReadReg = 0x09

    def connect(self, bus):
        try:
            self.bus = smbus.SMBus(bus)
            time.sleep(0.5)
            return 0
        except:
            return -1

    def writeAndWait(self, register, value):
        self.bus.write_byte_data(self.address, register, value);
        time.sleep(0.02)

    def readAndWait(self, register):
        res = self.bus.read_byte_data(self.address, register)
        time.sleep(0.02)
        return res

    def readDistAndWait(self, register):
        res = self.bus.read_i2c_block_data(self.address, register, 2)
        time.sleep(0.02)
        return (res[0] << 8 | res[1])

    def getDistance(self):
        self.writeAndWait(self.distWriteReg, self.distWriteVal)
        dist = self.readDistAndWait(self.distReadReg1)
        return dist

    def getVelocity(self):
        self.writeAndWait(self.distWriteReg, self.distWriteVal)
        self.writeAndWait(self.velWriteReg, self.velWriteVal)
        vel = self.readAndWait(self.velReadReg)
        return self.signedInt(vel)

    def signedInt(self, value):
        if value > 127:
            return (256-value) * (-1)
        else:
            return value

### Waterproof Ultrasonic Distance Measuring Module

<span class="image right">
    {%include images/SonarWaterproof.md %}
    Image 2 *JSN-SR04T (from raspberrypi-spy.co.uk)*
</span>

After the first tests with the HR-SR04 module and water resistance problems, the JSN-SR04T Waterproof Ultrasonic Distance Measuring Module was chosen. The module also requires +5V as power supply. Measurement distances is accurate about 0.5 cm and the maximum distance is 4.5 meters.

After the first successful tests in the dry, using the same script as the HR-SR04, we had to determine that the watertightness of the ultrasonic sensor only refers to the probe, i.e.Â it can be used in rain and **not under water**. In that time, it was also difficult to attach the sonor to the body of the boat in order to achieve a good vertical depth measurement in the water.

Price: **around 18 Euro**

Examples for hardware setup and code examples:

[https://www.raspberrypi-spy.co.uk/2016/10/waterproof-ultrasonic-distance-measuring-module/#prettyPhoto](https://www.raspberrypi-spy.co.uk/2016/10/waterproof-ultrasonic-distance-measuring-module/#prettyPhoto)

### Advisement on MB7354 HRXL-MaxSonar-WRS5

<span class="image left">
    {%include images/SonarMaxbotix.md %}
    Image 3 *MB7354 (from maxbotix.com)*
</span>

The MB7354 â€œHRXL-MaxSonar-WRS5 was selected as the third test module. One reason for the selection was the weather resistance described by the manufacturer and the robust PVC housing. Actually intended for measuring snow depths, the module is equipped with an internal filter and a temperature sensor. The resolution of the sensor is specified as 1 mm at a maximum range of 5m. **As the use under water is not recommended, this sensor was not tested.**

Price: **40 $**

Further informations and product specifications:

[https://www.maxbotix.com/Ultrasonic\_Sensors/MB7354.htm](https://www.maxbotix.com/Ultrasonic_Sensors/MB7354.htm)

[https://www.maxbotix.com/documents/HRXL-MaxSonar-WRS\_Datasheet.pdf](https://www.maxbotix.com/documents/HRXL-MaxSonar-WRS_Datasheet.pdf)

### **Final Selection**: Deeper Samrt Sonar Pro+

<span class="image fit">
    {%include images/SonarDeeper.md %}
</span>
Image 4 *Deeper Sonar (from deepersonar.com)* 

The final selection was the **Deeper Smart Sonar Pro+**, a fish finder sonar.The Deeper Sonar can be connected to a smartphone via Wi-Fi and continuously transmits data. The â€œSmart fishig app from Deeper can be used to view the data. In addition, the Deeper Sonar has an integrated GPS and does not need to be connected to the Raspberry via cable connections. some information about features and technology from the Deeper website:

*   Extended scannig depth of 80m
*   Dual Beam sonar for detailed scanning (290kHz 15A) and wide area coverage (90kHz 55A) by 15 scans per second
*   Wi-Fi range around 100m
*   Sensor weight = 100g and diameter = 65mm
*   Two threads (diameter 5mm) for fastening hooks or threaded rods

**Data export:** The GPS positions, time values and depth (in cm) are first buffered on the mobile phone (Deeper App). The data can then be sent via WiFi to a Google Drive address. A download of the data as.csv file is possible for further analysis.

Price: **235,90 Euro**

Further informations:

[https://deepersonar.com/en/deeper-smart-sonar-pro-plus/](https://deepersonar.com/en/deeper-smart-sonar-pro-plus/) [https://deepersonar.com/en/reading-your-deeper-sonar/](https://deepersonar.com/en/reading-your-deeper-sonar/)

<div class="box alt">
				<div class="row 50% uniform">
              <div class="6u 12u$(medium) "><span class="image fit"><img src={%include images/SonarDeeperFun1.md %} width="10%" height="10%" alt=""/></span></div>
              <div class="6u 12u$(medium) "><span class="image fit"><img src={%include images/SonarDeeperFun2.md %} width="10%" height="10%" alt=""/></span></div>
        </div>
</div>

Image 5/6 *Function Deeper Sonar (from deepersonar.com)*

### **Deeper** tests and attachment to the boat

<span class="image right">
    <img src={%include images/SonarRoboarm.md %} width="10%" height="10%" alt=""/>
    Image 7 *Robot Arm (design by JHKBuilder 2018)*
</span>


**1\. First Attachment**

The first attachment to the original self printed boat body worked with a simple line or fishing line. The distance between boat and deeper was about 1m. The function of the Deeper and the accuracy of the depth determination could therefore be tested on the Lahn river while it was in motion. The only problem was the GPS connection. Due to the deeperâ€™s strong buoyancy and the boatâ€™s stern waves, the deeper often came under water and interrupting the GPS signal.

**2\. Second Attachment**

To prevent the deeper from swaying too much on the water surface, the idea of attaching the deeper to a robot arm was born. After a short search, the â€œRobot Arm (SG90) was printed on the 3D printer. This should gently press the deeper onto the surface of the water to prevent build-up. Furthermore, the deeper could have been lifted out of the water if the sensor was not needed. The robot arm was too weak to lift the 100g deeper and the load too light to keep the deeper on the water surface.

**Robot Arm (SG90)** [https://www.thingiverse.com/thing:2848795](https://www.thingiverse.com/thing:2848795) (.stl data available here)

<span class="image fit">
    {%include images/SonarDeeperRobo.md %}
    Image 8 *Deeper attachment by Robot Arm*
</span>

**3\. Third Attachent at the final catermaran**

The Deeper was attached to the final Katerman by a simple and effective system (see Image 9 and 10). A threaded rod (diameter 5mm) was fixed on the thread integrated in the deeper and locked with a nut. The length of the threaded rod and the weight of the nuts used now determines the load which keeps the deeper constantly on the water surface. The threaded rod is covered with insulating tape to prevent it from sticking. The deepener can be secured with a cord and the supplied fastening ring.

<div class="box alt">
				<div class="row 50% uniform">
              <div class="6u 12u$(medium) "><span class="image fit"><img src={%include images/SonarDeeperAtt1.md %} width="10%" height="10%" alt=""/></span></div>
              <div class="6u 12u$(medium) "><span class="image fit"><img src={%include images/SonarDeeperAtt2.md %} width="10%" height="10%" alt=""/></span></div>
        </div>
</div>
Image 9/10 *Deeper attachment by threaded bolt*

<ul class="pagination">
    <li><span class="button">Prev</span></li>
    <li><a href="#" class="page">1</a></li>
    <li><a href="{{ 'sonarsensor.html' | absolute_url }}" class="page active">2</a></li>
    <li><a href="#" class="page">3</a></li>
    <li><a href="{{ 'cam.html' | absolute_url }}" class="page">4</a></li>
    <li><a href="#" class="page">5</a></li>
    <li><a href="#" class="button">Next</a></li>
</ul>