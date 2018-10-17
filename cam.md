---
layout: page
title: Cameras
---

Zur Untersuchung des sichbaren Spektrums oberhalb des Wassers soll Mr. TURTLE (The Unmanned Radio Telemetry Limnology-Explorer) mit einer Kamera an Deck ausgestattet werden. Da das Boot mit einem Raspberry Pi ausgestattet werden soll, wurde sich bereits im Vorfeld für die Raspberry Pi Camera V2.1 entschieden. Für die Kamera spricht zunächst der Preis, außerdem eine problemlose Einrichtung mittels Raspberry Pi.

Der folgende Eintrag erklärt die Einrichtung der Raspberry Pi Camera V2.1 und enthält ein Beispielskript zur automatischen Aufnahme von Bildern und eine Beschreibung zur Einrichtung eines Autostartskriptes (crontab).

Auf dem Raspberry Pi wurde zunächst das kostenlose Betriebssystem der Raspberry Pi Foundation "Noobs" installiert. Erhältich unter: <https://www.raspberrypi.org/downloads/noobs/>

Die Kamera wird an die am Raspberry vorgesehene CSI-Schnittstelle gesteckt.

<span class="image left">
    {%include images/Cam1Klee.md %}
    Abbildung 1: *Anschluss der Kamera am Raspberry Pi*
</span>

Anschließend kann die Kamera über die Einstellungen aktiviert werden.

    Einstellungen -> Raspberry-Pi-Konfiguration -> Schnittstellen -> Kamera aktiviert

Alternativ lässt sich die Kamera auch über die Console aktivieren.

    sudo raspi-config -> interfacing options -> Camera enable

Nun kann mit einem beliebigen Editor ein neues Dokument erzeugt werden. Das Dokument dient zum schreiben des Kameraskript. Dieses Skript soll automatisch für eine Minute Bilder im Sekundentakt erzeugen und unter Angabe der Zeit lokal ablegen. Ein Autostartskript führt das Skript anschließend minütlich aus.

    #Bilderverzeihnis 
    IMGDIR='/home/pi/camera' 

    # Zeitstempel 
    TIME=$(date +%d%m%Y_%H:%M)

    # Bildbezeichnung mit laufender, zweistelliger Nummer
    BILD=$Bild%02d 

    # Dateiname erstellen 
    FILENAME=$IMGDIR/$TIME:$BILD.jpg 

    # Bilderfolge aufnehmen
    raspistill -w 1200 -h 800 -tl 1000 -t 58000 -o $FILENAME -n 

Das Skript muss anschließend lokal mit der Dateiendung ".sh" gespeichert werden. Zur weiteren Verwendung wird empfohlen, das Skript unter dem Pfad "/home/pi/camerascript.sh" zu speichern.

Erklärung der Befehle:

    raspistill: Befehl zur Aufnahme von Bildern
    -w           Breite der Auflösung
    -h           Höhe der Auflösung
    -tl 1000:  jede Sekunde wird ein Bild gemacht 
               (der Raspberry Pi ermöglicht kontinuierliche Wiederholungsraten von max. 900)
    -t 58000:  der Zeitraum beträgt 58 Sekunden
    -o           Speicherort
    -n           zum Unterdrücken der Vorschau

Im folgenden wird ein Crontab für das Skript erstellt. Das Skript wird dadurch automatisch nach dem Starten des Raspberrys ausgeführt.

Hierzu in der Konsole

    sudo crontab -e 

eingeben. Beim ersten Aufruf muss ein Editor zum Ausführen ausgewählt werden. Empfohlen wird der leicht bedienbare Editor nano. (2 auswählen und mit Eingabe bestätigen)

Anschließend kann im Crontab die unterste Zeile wie folgend ergänzt werden:

    */1 * * * * sh cameraskript 

Nun speichern des Skriptes mit Strg + o. Wichtig ist der folgende Speicherort:

    /etc/ . /cron.d/crontab

Das Skript wird nun zu jeder vollen Minute ausgeführt. Ausführliche Beschreibungen zur Einrichtung eines Crontabs können unter <https://github.com/mileusna/crontab> nachgelesen werden.

<span class="image right">
    {%include images/CamPanTilt.md %}
    Abbildung 2: *PIMORONI. Tech Treasure for Makers. "<https://shop.pimoroni.com/products/pan-tilt-hat?variant=33704345034>"*
</span>

Die wasserdichte Integration der Kamera auf Deck des Bootes lässt sich vielseitig ermöglichen. Auf dem Boot wurde der Raspberry Pi zusammen mit anderen Bauteilen in eine Kunststoffbox gelegt. Die Kamera wurde aus Zeit- und Kostengründen provisorisch mit einer wasserdichten Folie ummantelt. Online finden sich auch zahlreiche Anleitungen zum 3d Druck von wasserfesten Raspberry Pi Hüllen. Hier ein Beispiel: <https://tinkererblog.wordpress.com/2015/07/28/how-i-designed-a-compact-weatherproof-raspberry-pi-case/>

Zur Bewegung der Kamera wurde zu Testzwecken eine bewegliche Halterung integriert. Dieser "Pan-Tilt HAT" von Pimoroni Ltd. kann vertikal und horizontal ausgerichtet werden.

Umfangreiche Anleitungen zur Verwendung finden sich unter <http://docs.pimoroni.com/pantilthat/#> und <https://github.com/pimoroni/pantilt-hat>


<ul class="pagination">
        <li><span class="button">Prev</span></li>
        <li><a href="#" class="page">1</a></li>
        <li><a href="{{ 'sonarsensor.html' | absolute_url }}" class="page">2</a></li>
        <li><a href="#" class="page">3</a></li>
        <li><a href="{{ 'cam.html' | absolute_url }}" class="page active">4</a></li>
        <li><a href="#" class="page">5</a></li>
        <li><a href="#" class="button">Next</a></li>
</ul>
