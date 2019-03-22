# openHab

## Übersicht

OpenHab steht für open Home Automation Bus und ist eine Open-Source home automation Plattform. Mit openHab hat man die Möglichkeit eine Vielzahl von anderen Geräten und System zu steuern. Außerdem ist openHab sehr flexible, man kann damit fast alle Home-Automation Wünsche zufrieden stellen, da es zwar schnell und leicht geht, wenn man was einfaches will aber die Komplexität auch ins zigfache steigen kann. An openHab selbst kann man dabei Sensoren (z.B. Thermometer oder Bewegungsmelder) und Aktoren (z.B. Schalter oder Heizungssteuerung) hängen. Großer Vorteil unter openHab ist dabei die Gerätehersteller Unabhängigkeit und die modulare Erweiterbarkeit. Auch ist die gute Dokumentation ein riesiger Vorteil.

OpenHab selbst baut dabei auf dem Eclipse Smarthome Framework auf. Es ist komplett in Java geschrieben und benutzt Apache Karaf mit Eclipse Equinox als eine OSGi runtime und verknüpft dies mit Jetty für einen http-Server.



In der offiziellen openHab Dokumentation stehen 4 wichtige Punkte, welche man auf jeden Fall beachten sollte wenn man damit arbeitet:

- Langsam anfangen und sich hocharbeiten, nicht gleich mit der Tür in das Haus fallen
- Man muss vorbereitet sein auch Zeit zu investieren
- Nicht auf eine Art festlegen wie man sein Ziel erreichen will
- Alle kleinen Erfolge feiern

## Herzstück – EventBus
![Eventbus](/images/eventbus.png)
 

**Begriffe**

Bindings - Stellt die Verbindung zwischen Gerät und Thing her. Dient als Anschluss von Sensoren und Aktoren zu openHab
Things – Entity des Systems
Channels – Verbindung zwischen Thing und Item
Items – Informationen über ein Gerät
Rules – Automatische Aktion, welche durch Bedienung ausgelöst wird
Sitemap – User Interface, welches alle gewünschten Informationen anzeigt

![Übersicht](/images/übersicht.png)


# Binding

Sind Software-Pakete welche manuell vom User installiert werden müssen. Der Hauptnutzen liegt darin, eine Verbindung zwischen Gerät und Thing herzustellen. Bindings kommunizieren mit dem Gerät und „übersetzen“ alle Befehle von und zu openHab zwischen dem Gerät und dem Thing.

Bsp.: MQTT, Hue, Sonos, nest, Ikea Bindings

Für jedes Binding gibt es eine ausreichende Dokumentation, meistens sogar mit komplett lauffähigem Beispiel.

# Things

Entities welche physisch zum System hinzugefügt werden können. Wichtig hierbei ist es, dass Things auch Web-Services sein können oder jeder andere Informations Input.

Wichtige Daten werden im den konfigurations Properties gespeichert, z.B. IP-Adresse oder ein Access-Token.

# Channels

Things stellen Channels zur Verfügung. Sie stellen die verschiedenen Funktionen eines Things da. Channels sind verbunden mit den Items, womit Channels die Verbindung zwischen physischer Schicht und virtueller Schicht darstellen. Wenn eine Verbindung aufgebaut ist reagiert das Thing auf die Events des Items, welches mit dem Channel des Things verbunden ist.

# Items

Stellen eine Funktionalität da, welche vom System benutzt wird da. Items haben einen sogenannten State und werden mit Events benutzt.

![Items und Things](/images/thing.png)
# Rules

Rules werden benutzt um Prozesse zu automatisieren. Es gibt für jede Rule einen Trigger welcher, wenn ausgelöst, ein Skript durchläuft, welches dann alle funktionalen Sachen regelt. Z.B. Um 19 Uhr Licht aus oder wenn jemand an der Tür vorbeigeht Licht auf Rot.

Rules können einfach und schnell im Paper UI, mithilfe der Rules Engine, erstellt werden. Dort kann man alle nötigen Sachen mit ein paar Clicks einstellen. Wem das aber zu einfach ist kann auch die Rules aus programmieren. Dazu eignet sich die openHab Visual Studio Code Extension sehr gut. Als Programmiersprache wird Java benutzt wobei hier eine Abwandlung namens xbase angewandt wird. Wichtig ist auch das man Rules als Setup beim starten des Systems benutzen kann, denn es gibt als Trigger „System started“.

# Sitemap

Sitemaps werden benutzt um Items und Things so aufzubereiten das ihre Informationen Usergerecht angezeigt werden. Diese Sitemaps können dann auf jedmöglichen UI’s angezeigt werden.  

# Setup von openHab

OpenHab kann auf fast jedem System installiert werden. Ist dies aber sinnvoll? Nein, da openHab eigentlich die ganze Zeit laufen muss um ordnungsgemäß zu Arbeiten. Die beste Option ist daher das openHabian Betriebssystem auf einem Raspberry Pi oder auf einem PINE A64 zu installieren. Detailliertes How-To findet man auf der offiziellen openHab Dokumentation.

# Persistence

Wird benutzt um beispielsweise ein System nach Neustart wiederherzustellen oder um Diagramme für das UI bereit zu stellen. OpenHab speichert dabei den State eines Items ab, dabei werden die beliebtesten Datenbanken unterstützt. Unteranderem MongoDB, MySQL, InfluxDB, welche für Datenreihen gedacht ist und RRD4J, welche eine leichtgewichtige Spezialdatenbank ist. Zur grafischen Ausgabe gibt es Charts, welche openHab zur Verfügung stellt und Grafana, welche eine open Plattform für schöne Datavisualisierung ist und extra laufen muss. Hierbei ist Grafana die eindeutig bessere Wahl, benötigt jedoch auch höheren Zeitaufwand.

# UI’s

OpenHab bietet viele verschieden UI’s an. Diese können als Add-On im Standard UI, dem Paper UI installiert werden.

- Paper UI: Interface, welches hilft alle Things, Bindings, usw. richtig einzustellen und zu verbinden.

![PaperUI](/images/paperUI.png)

- Basic UI: Dient zum Anzeigen der Sitemaps und basiert auf Google Material Design Lite. Bietet zusätzlich ein responsives Layout an, womit dieses UI perfekt für alle Bildschirmgrößen ist. Natürlich werden die Werte live upgedatet.


![BasicUI](/images/basicUI.png)

- Cassic UI: Gleich wie Basic UI nur in einem alten IOS Theme.  


![ClassicUI](/images/classicUI.png)

# NodeRed

Programmiertool um Hardware, API’s und online Dienste miteinander zu verbinden. Dabei programmiert man den sogenannten flow in einem Browser. Obwohl NodeRed eigentlich eher visual based ist kann man JavaScript Funktionen benutzen. Dabei baut das Ganze auf Node.js auf, damit ist es extremst leichtgewichtig, welches optimal ist um auf günstiger Hardware zu laufen.  

![NodeRed](/images/nodered.png)
