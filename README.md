Achtung: im Moment ist die interrne SPannungsversorgung auf der Hauptplatine abgeklemmt !!! (Grund: Sensor muß mit 12 VDC versorgt werden)

# Lora-TTN-Vegawell52-Water-level-meter
Vegawell52 with Ursalink UC11-N1 868MHz

*Vorstellung der Hardware*

 - Sensor: Vegawell 52 
 - Node: Ursalink UC11-N1 868MHz 
 - Netzteil: Omron S8VK-C12024

Vorbereitungen / Aufbau / Anschlüsse
Node vorbereiten, dazu muß der Deckel geöffnet werden

 - einstellen AI2 input = 4-20mA (DIP-Schalter)
 - einstellen Vout für Interface2 = 12 Volt (DIP-Schalter)
 - mitgeliefertes USB-Datenkabel mit Spannungsversorgung  anschließen und Node einrichten
 - ohne Sensor prüfen, ob das Gerät im TTN angemeldet ist

Spannungsversorgung Node UC11-N1   Standard M12/4 Kabel
*Ansicht Stecker vom Node*

 - Pin 1 = GND (-) 
 - Pin 2 = USB D+ 
 - Pin 3 = USB D- 
 - Pin 4 = VCC (5-24 Volt DC)

Kabel (Standard Sensor Kabel M12/4 (Buchse wird benötigt)

 - 1 = weiss 
 - 2 = blau 
 - 3 = schwarz 
 - 4 = braun

damit wird der Node angeschlossen am Netzteil mit

 - braun = GND 
 - weiss = 24 VDC

Sensor Vegawell anschließen

 - blau   = Signal 4-20mA 
 - braun  = VDC+ 
 - shield = GND

damit ergeben sich für das Kabel zum Node

 - blau vom Sensor wird gürn zum Node 
 - braun vom Sensor wird orange zum Node 
   shield vom Sensorkabel wird schwarz zum Node

der Node wird per mitgelieferten USB Kabel am PC eingerichtet, dafür benötigt man die Software URSALINK Toolbox in der aktuellen Version die erstmalige Einrichtung und Anbindung in eine TTN Application ist sehr gut in der Bedienungsanleitung vom Node beschrieben.

Nach der Einrichtung wird der Node mit dem Netzteil betrieben, damit auch der Sensor mit ausreichend Spannung (12 Volt) versorgt werden kann. Die Umrechnung der Stromstärke in Wassertiefe ist einfach und wird nach folgenden Überlegungen gemacht:

*Text folgt*

--------------

**Rechenbeispiel:**
Sensor hat einen Meßbereich analog 4-20mA
dies entspricht 0-40 kPa ( 0-0,4 bar)
4,00 mA = 0 Meter = 0kPa
20,00 mA =  ?    
pro 10m Wassertiefe 100kPa
also 1m Wassertiefe 10kPa
und damit 1kPa = 10cm
damit 20mA = 40kPa = 0,4 bar 

16mA quantitaviver Wert (20-4=16) entsprechen 40kPa
1mA = 2,5kPa
0,4mA = 1kPa = 10 cm

**Test vom Sensor mit einem 10L Eimer Wasser:**
Meßwert = 4,06mA  im leeren Eimer
Einfüllen von Wasser: 4,91mA
4,91 - 4,06 = 0,85mA Änderung
1mA = 2,5 kPa
0,85mA = 2,125 kPa
1kPa=10cm
2,125 kPa = 21,25 cm Wasserpegel
*dieser Wert wurde mit dem Zollstock überprüft: 22cm Wassertiefe im Eimer*

dann wurde etwa die Hälfte vom Eimer ausgegossen
neuer Messwert 4,57mA
4,57 - 4,06 = 0,51 mA Änderung
1mA = 2,5 kPa
0,51mA = 1,275 kPa
1kPa=10cm
1,275 KPa = 12,75cm Wasserpegel
*dieser Wert wurde wieder mit dem Zollstock überprüft: 13cm Wassertiefe im Eimer*
