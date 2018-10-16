---
layout: page
title: The Way of finding the right Sonar Sensor
---

Different Sonar senors (sound navigation and ranging) were tested in additon to the development of the boat. The original goal was to achieve a stable and cost-effective detection of the aquatic bed or river bed morphologie. Sonar systems allow a distance determination based on emitted sound pulses. During the project, four active sonars were tested, which themselves emit signals and receive echoes in order to determine the distance based on the runtime. Tests were carried out on land as well as in various areas of the Lahn river.

### Raspberry Pi Distance Sensor HC-SR04

<span class="image left">
      <img src={%include images/SonarRaspi.md %} width="10%" height="10%" alt=""/>
      Image 1 *HC-SR04 (from tutorials-raspberrypi.de)*
</span>

The ultrasonic module HC-SR04 was the first attempt to find a suitable sensor. According to the producer, the module is suitable for distance measurements between two centimetres and a maximum of three metres. The opening angle of the transmitter is 15Â°. The sensor requires a supply voltage of +5 volts and can easily be connected to a Raspberry via four pins.

Price: around **2 Euro**

Examples for hardware setup and code examples:

[https://pimylifeup.com/raspberry-pi-distance-sensor/](https://pimylifeup.com/raspberry-pi-distance-sensor/)

[https://www.youtube.com/watch?v=xACy8l3LsXI](https://www.youtube.com/watch?v=xACy8l3LsXI)

[https://tutorials-raspberrypi.de/entfernung-messen-mit-ultraschallsensor-hc-sr04/](https://tutorials-raspberrypi.de/entfernung-messen-mit-ultraschallsensor-hc-sr04/) (German)

Although the HC-SR04 provides good measurement results, the main problem was to make the sensor waterproof. While there were considerations to dip the sensor in silicone and provide it with a mobile phone protection film in front of the sensor system, this has not been tested until now.For our tests we used the following script from [https://tutorials-raspberrypi.de/entfernung-messen-mit-ultraschallsensor-hc-sr04/](https://tutorials-raspberrypi.de/entfernung-messen-mit-ultraschallsensor-hc-sr04/), with the modification â€œdistanz = (TimeElapsed \* 34300) / 2 to simulate the runtime for a measurement under water:

    #Bibliotheken einbinden
    import RPi.GPIO as GPIO
    import time
     
    #GPIO Modus (BOARD / BCM)
    GPIO.setmode(GPIO.BCM)
     
    #GPIO Pins zuweisen
    GPIO_TRIGGER = 18
    GPIO_ECHO = 24
     
    #Richtung der GPIO-Pins festlegen (IN / OUT)
    GPIO.setup(GPIO_TRIGGER, GPIO.OUT)
    GPIO.setup(GPIO_ECHO, GPIO.IN)
     
    def distanz():
        # setze Trigger auf HIGH
        GPIO.output(GPIO_TRIGGER, True)
     
        # setze Trigger nach 0.01ms aus LOW
        time.sleep(0.00001)
        GPIO.output(GPIO_TRIGGER, False)
     
        StartZeit = time.time()
        StopZeit = time.time()
     
        # speichere Startzeit
        while GPIO.input(GPIO_ECHO) == 0:
            StartZeit = time.time()
     
        # speichere Ankunftszeit
        while GPIO.input(GPIO_ECHO) == 1:
            StopZeit = time.time()
     
        # Zeit Differenz zwischen Start und Ankunft
        TimeElapsed = StopZeit - StartZeit
        # mit der Schallgeschwindigkeit (34300 cm/s) multiplizieren
        # und durch 2 teilen, da hin und zurueck
        distanz = (TimeElapsed * 34300) / 2
     
        return distanz
     
    if __name__ == '__main__':
        try:
            while True:
                abstand = distanz()
                print ("Gemessene Entfernung = %.1f cm" % abstand)
                time.sleep(1)
     
            # Beim Abbruch durch STRG+C resetten
        except KeyboardInterrupt:
            print("Messung vom User gestoppt")
            GPIO.cleanup()      

### Waterproof Ultrasonic Distance Measuring Module

<span class="image right">
    {%include images/SonarWaterproof.md %}
    Image 2 *JSN-SR04T (from raspberrypi-spy.co.uk)*
</span>

After the first tests with the HR-SR04 module and water resistance problems, the JSN-SR04T â€œWaterproof Ultrasonic Distance Measuring Moduleâ€ was chosen. The module also requires +5V as power supply. Measurement distances is accurate about 0.5 cm and the maximum distance is 4.5 meters.

After the first successful tests in the dry, using the same script as the HR-SR04, we had to determine that the watertightness of the ultrasonic sensor only refers to the probe, i.e.Â it can be used in rain and **not under water**. In that time, it was also difficult to attach the sonor to the body of the boat in order to achieve a good vertical depth measurement in the water.

Price: **around 18 Euro**

Examples for hardware setup and code examples:

[https://www.raspberrypi-spy.co.uk/2016/10/waterproof-ultrasonic-distance-measuring-module/#prettyPhoto](https://www.raspberrypi-spy.co.uk/2016/10/waterproof-ultrasonic-distance-measuring-module/#prettyPhoto)

### Advisement on MB7354 HRXL-MaxSonar-WRS5

<span class="image left">
    {%include images/SonarMaxbotix.md %}
    Image 3 *MB7354 (from maxbotix.com)*
</span>

The MB7354 â€œHRXL-MaxSonar-WRS5â€ was selected as the third test module. One reason for the selection was the weather resistance described by the manufacturer and the robust PVC housing. Actually intended for measuring snow depths, the module is equipped with an internal filter and a temperature sensor. The resolution of the sensor is specified as 1 mm at a maximum range of 5m. **As the use under water is not recommended, this sensor was not tested.**

Price: **40 $**

Further informations and product specifications:

[https://www.maxbotix.com/Ultrasonic\_Sensors/MB7354.htm](https://www.maxbotix.com/Ultrasonic_Sensors/MB7354.htm)

[https://www.maxbotix.com/documents/HRXL-MaxSonar-WRS\_Datasheet.pdf](https://www.maxbotix.com/documents/HRXL-MaxSonar-WRS_Datasheet.pdf)

### **Final Selection**: Deeper Samrt Sonar Pro+

<span class="image fit">
    {%include images/SonarDeeper.md %}
</span>
Image 4 *Deeper Sonar (from deepersonar.com)* 

The final selection was the **Deeper Smart Sonar Pro+**, a fish finder sonar.The Deeper Sonar can be connected to a smartphone via Wi-Fi and continuously transmits data. The â€œSmart fishig appâ€ from Deeper can be used to view the data. In addition, the Deeper Sonar has an integrated GPS and does not need to be connected to the Raspberry via cable connections. some information about features and technology from the Deeper website:

*   Extended scannig depth of 80m
*   Dual Beam sonar for detailed scanning (290kHz 15Â°) and wide area coverage (90kHz 55Â°) by 15 scans per second
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

To prevent the deeper from swaying too much on the water surface, the idea of attaching the deeper to a robot arm was born. After a short search, the â€œRobot Arm (SG90)â€ was printed on the 3D printer. This should gently press the deeper onto the surface of the water to prevent build-up. Furthermore, the deeper could have been lifted out of the water if the sensor was not needed. The robot arm was too weak to lift the 100g deeper and the load too light to keep the deeper on the water surface.

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