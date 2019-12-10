Projektspecifikation <br> 
Rollfördelning:  Alexander B (binärprotokol-ansvarig),  Jonas Ö (breadboard-ansvarig),  Sebastian C (scrum master) <br> 
Användning:  <br>
Deployment på ny hårdvara: - Ladda upp motor sketch till Arduino UNO ( med Motor Shield )<br>
 - Flasha nytt SD kort till Raspberry Pi<br>
 - Justera WiFi lösen efter behov<br>
 - Klona gitrepos ( med flaggan --recurse-submodules ) <br>
 - Bygg binärfiler <br>
 - Justera IP-address efter behov<br>
 - Lägg in autostart med t.ex. crontab <br> 
 - Koppla upp breadboard med bl.a. voltage divider för UART enligt Fritizing-ritning<br>
 - Ladda upp joystick sketch till LoLin D1 mini <br>
 - Justera WiFi lösen och IP-address efter behov <br>
 - Koppla upp breadboard med bl.a. voltage divider för att mäta spänning i batteri <br>
 
Användning av fjärrkontroll: <br>
- Slå på strömmen på både robot och fjärr. <br>
- Tryck på framåt eller bakåt knappen. Justera riktning med rotary encoder joystick. Tryck in rotary encoder knappen för att nollställa riktningen. <br>
- Tryck på reset knappen på Uno för att stanna roboten. <br>
- Slå av strömmen på både robot och fjärr <br>
- Alternativt använd GPIO-shutdown knappen på Raspberry Pi för att göra en snällare avstängning.   <br>
 
Design: <br>
Vi tog en redan införskaffad Arexx RP5 robot och skrev ut en platta för att fästa våra olika komponenter. <br>
Vi hittade en Motor Shield r3 ( Adafruit ) och provade exempel-koden. <br>
Sedan kämpade vi med att få RX/TX att fungera mellan Uno och Rpi. <br>
Vi tillverkade en knapp som bryter UART tillfälligt medans  vi laddar upp en ny sketch till Uno. <br>
 
Under utvecklingsstadiet använde vi en Raspberry Pi 3, för att kompileringen gick snabbare. <br>
Men färdig produkt fungerar med en Rasbperry Pi Zero W som är energisnålare. <br>
 
Ovan visar ett UML diagram TCP/UDP kommunikation mellan Rpi och LoLin   <br>

Kod: <br>
meta repo ?https://github.com/albrdev/marvin42-dacapo <br>
 1. Arduino Uno + Motor Shield <br>
 https://github.com/albrdev/marvin42-dacapo-motor_controller <br>
 
Research: git clone ?https://github.com/snowlab/arduino-motor-shield-r3/? som jag forkat ifrån https://github.com/gallingern/<br>
arduino-motor-shield-r3? som bygger på https://github.com/pololu/dual-vnh5019-motor-shield <br>
 
2. Raspberry Pi 3 eller Zero https://github.com/albrdev/marvin42-dacapo-networking <br>
 
3. WeMos LoLin D1 mini https://github.com/albrdev/marvin42-dacapo-joystick_client <br>
 
Dokumentation repo med export av detta Google Docs https://github.com/jonasbits/marvin42-dacapo-docs <br>
 
Presentation <br>
 
https://docs.google.com/presentation/d/1beX7hva5HjMFXKNHn2rgH45J-gQc98lq1z0H9HMiB3w/edit#slide=id.p <br>
 
Stämningsfull musik till presentationen. Chamillionaire - The Sound Of Revenge Ridin’ <br>
 
Flow chart <br>
 
Robby RP5 -> Motor shield -> Arduino Uno -> UART -> Rpi zero -> Plattkabel Kamera <br>
 
SoftwareSerial verkar inte trivas med vår motorShield <br>
 
(Efterforskningar behövs för att konvertera 5v logik till 3v3 logik angående WeMos/LoLin D1) <br>
 
Work log <br>
 
Datum Alex comments Basse comments Jonas comments <br>
2019-09-12 Nätverksklasser rpi cam 3d printed for Robby<br>
2019-09-13 Nätverksklasser arduino serial Joystick -> A0 -> LoLin <br>
2019-09-16 Nätverksklasser Byggt/lött voltage divider <br>
Byggt voltage divider <br>
2019-09-17 Kod för nätverk/motorer, kopplat kablar <br>
n/a Kopplat kablar, spelat VR <br>
2019-09-18 Lyckats styra motorer via nätverket, testning <br>
Monterat hårdvara, kopplat kablar, testning <br>
Testning, byggt joystick, tappat bort sin dator <br>
2019-09-19 Utökat användargränssnitte t för client CLI webcam caseholder <br>
Kopplat 2x18650 av/på, volt-reg till 5.2v, wake/halt rpi switch. <br>
2019-09-20 Testat joystick, refaktorisering testat joystick,  OpenScad ritning med 3d-printade delar vi valt ut. <br>
2019-09-25   LM317 voltage regulator <br>
2019-0-26 hittat buggar,sUART Byggt robotfjärr, till trådlös, förberett voltmätare på robot samt joystick Kämpat med volt div <br>
2019-09-27  kollat på gyro hårdvara inklusive kopplingar via gpio till rpi Arangerat för rpi zero <br>
2019-09-29   Undersökt batteri konfiguration 2S2P <br>
  
Before pictures <br>
 
After pictures <br>
 
Build log<br>
 https://www.thingiverse.com/thing:3140027/#18650_battery_holder <br>
 https://www.thingiverse.com/thing:2144416/#RP5_exp_plate <br>
 https://www.thingiverse.com/thing:3862767/#rpiCamMount <br>
 https://www.thingiverse.com/thing:1162200#joypadCase <br>
 https://www.electrokit.com/produkt/kamerakort-for-raspberry-pi-zero/ <br>
 
 
Links<br>
 https://github.com/gallingern/arduino-motor-shield-r3<br>
 https://www.m.nu/esp8266-shields/battery-shield-for-wemos-d1-mini<br>
 https://wiki.wemos.cc/products:d1_mini_shields:motor_shield<br>
 https://wiki.wemos.cc/products:d1:d1<br>
 https://www.arduino.cc/en/uploads/Main/arduino_MotorShield_Rev3-schematic.pdf<br>
 https://www.arduino.cc/en/Tutorial/SerialPassthrough <br>
 https://www.baldengineer.com/5-voltage-divider-circuits.html <br>
 https://www.sparkfun.com/products/9032? - joystick som liknar våran 10k Ohm <br>
 http://www.ohmslawcalculator.com/voltage-divider-calculator <br>
 https://www.baldengineer.com/5-voltage-divider-circuits.html<br>
 https://www.raspberrypi.org/documentation/hardware/raspberrypi/schematics/rpi_SCH_Zero W_1p1_reduced.pdf  <br>

More Links<br> 
 https://picamera.readthedocs.io/en/latest/recipes2.html#web-streaming<br>
 https://www.w3schools.com/tags/att_meta_http_equiv.asp<br>
 https://thepihut.com/products/keyes-rotary-encoder-module <br>
 https://github.com/modmypi/Rotary-Encoder/blob/master/rotary_encoder.py <br>
 https://www.conrad.se/p/arexx-bandsats-rp5rp6-passar-till-rp6-rp5-191333 <br>
 https://patrick.welfringer.lu/sos/waves/drwho/exterminated_you_will_be.wav<br>
 http://www.wavsource.com/snds_2018-06-03_5106726768923853/movies/lost_in_space/los t_in_space_robot_online.wav <br>
 https://unix.stackexchange.com/questions/109804/crontabs-reboot-only-works-for-root <br>
 https://www.instructables.com/id/Arduino-Battery-Voltage-Indicator/ <br>
 
 # marvin42-dacapo-docs<br>
 Repo of docs regarding the marvin42-dacapo project<br>
