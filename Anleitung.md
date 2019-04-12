# openHab/MQTT Anleitung

## 1. MQTT auf openHabian einrichten

1.1 openHabian starten
![MQTTHabian1](/images/anleitung/habian1.jpg)

1.2 "sudo openhabian-config" auführen und sich anmelden
![MQTTHabian2](/images/anleitung/habian2.jpg)

1.3 Optional Components auswählen
![MQTTHabian3](/images/anleitung/habianmqtt1.jpg)

1.4 Mosquitto auswählen
![MQTTHabian4](/images/anleitung/habianmqtt2.jpg)

1.5 Continue auswählen 
![MQTTHabian5](/images/anleitung/habianmqtt3.jpg)

Nun ist der MQTT Broker auf dem openHabian-System installiert und man kann loslegen.

## 2. ESP für MQTT einrichten

2.1 Nach dem Start der Anwendung auf dem ESP öffnet dieser ein lokales Netzwerk zu welchem man sich verbinden muss.
![espmqtt1](/images/anleitung/espmqtt1.jpg)

2.2 Configure WiFi auswählen
![espmqtt2](/images/anleitung/espmqtt2.jpg)

2.3 Netzwerk, in welchem die Aktoren und Sensoren sich befinden, auswählen und wenn vorhanden das Passwort eingeben.
![espmqtt3](/images/anleitung/espmqtt3.jpg)

2.4 MQTT Server eintragen und MQTT Thing eintragen
![espmqtt4](/images/anleitung/espmqtt4.jpg)

2.5 Nach dem drücken auf den Save-Button werden die Credentials gespeichert
![espmqtt5](/images/anleitung/espmqtt5.jpg)

Nach einem Neustart der Microcontroller-Anwendung senden die Aktoren und Sensoren nun ihre Daten an den MQTT Broker.

## 3. MQTT im PaperUI eintragen

3.1 Unter Add-On's das MQTT Binding downloaden
![MQTTHab1](/images/anleitung/MQTTStep1.png)

3.2 Unter INBOX das nun angezeigten MQTT Binding auswählen
![MQTTHab2](/images/anleitung/MQTTStep2.png)

3.3 Add Manually auswählen
![MQTTHab3](/images/anleitung/MqttStep3.png)

3.4 MQTT Broker auswählen
![MQTTHab4](/images/anleitung/MQTTStep4.PNG)

3.5 Port und IP des Brokers auswählen
![MQTTHab5](/images/anleitung/MQTTStep5.PNG)

## 4. Things im PaperUI hinzufügen

4.1 Unter INBOX nun nach dem auswählen des MQTT Bindings, Generic MQTT Thing auswählen
![ThingHab1](/images/anleitung/ThingStep1.PNG)

4.2 Bei der Bridge Selection den richtigen MQTT Broker auswählen
![ThingHab2](/images/anleitung/ThingStep2.PNG)

Nun kann man alle wichtigen Informationen für das Thing hinzufügen bzw. ändern. Das fertige Thing findet man im Menü unter Things.

## 5. Channel (Funktion) zum Thign hinzufügen

5.1 Unter Things das richtige Thing auswählen und auf das Plus neben Channels drücken. Nun öffnet sich die Channelmaske und der User kann alle nötigen Informationen eingeben. Wichtig sind hierbei vorallem die MQTT Broker Topics.
![ChannelHab1](/images/anleitung/Channel1.PNG)

## 6. Channel linken

6.1 Zum Erstellen eines Linkes einfach auf den blauen Kreis neben dem vorhandenen Channel drücken.
![LinkHab1](/images/anleitung/Link1.png)

6.2 In der Linkmaske alle wichtigen Informationen eingeben und auf link drücken.
![LinkHab2](/images/anleitung/Link2.png)

Geschafft! Das fertige Thing wird nun unter Control aufgelistet.
