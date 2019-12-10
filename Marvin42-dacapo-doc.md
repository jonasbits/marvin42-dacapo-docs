Projektspecifikation 
 
Rollfördelning:  Alexander B (binärprotokol-ansvarig),  Jonas Ö (breadboard-ansvarig),  Sebastian C (scrum master) 
 
Användning:  Deployment på ny hårdvara: - Ladda upp motor sketch till Arduino UNO ( med Motor Shield ) - Flasha nytt SD kort till Raspberry Pi - Justera WiFi lösen efter behov - Klona gitrepos ( med flaggan --recurse-submodules ) - Bygg binärfiler - Justera IP-address efter behov - Lägg in autostart med t.ex. crontab 
 
- Koppla upp breadboard med bl.a. voltage divider för UART enligt Fritizing-ritning - Ladda upp joystick sketch till LoLin D1 mini - Justera WiFi lösen och IP-address efter behov - Koppla upp breadboard med bl.a. voltage divider för att mäta spänning i batteri 
 
Användning av fjärrkontroll: - Slå på strömmen på både robot och fjärr. - Tryck på framåt eller bakåt knappen. Justera riktning med rotary encoder joystick. Tryck in rotary encoder knappen för att nollställa riktningen. - Tryck på reset knappen på Uno för att stanna roboten. - Slå av strömmen på både robot och fjärr - Alternativt använd GPIO-shutdown knappen på Raspberry Pi för att göra en snällare avstängning.   

 Design: 
 
 
Vi tog en redan införskaffad Arexx RP5 robot och skrev ut en platta för att fästa våra olika komponenter. Vi hittade en Motor Shield r3 ( Adafruit ) och provade exempel-koden. Sedan kämpade vi med att få RX/TX att fungera mellan Uno och Rpi. Vi tillverkade en knapp som bryter UART tillfälligt medans  vi laddar upp en ny sketch till Uno. 
 
Under utvecklingsstadiet använde vi en Raspberry Pi 3, för att kompileringen gick snabbare. Men färdig produkt fungerar med en Rasbperry Pi Zero W som är energisnålare. 
 
Ovan visar ett UML diagram TCP/UDP kommunikation mellan Rpi och LoLin   

 Kod 
meta repo ?https://github.com/albrdev/marvin42-dacapo 
 1. Arduino Uno + Motor Shield https://github.com/albrdev/marvin42-dacapo-motor_controller 
 
Research: git clone ?https://github.com/snowlab/arduino-motor-shield-r3/? som jag forkat ifrån https://github.com/gallingern/arduino-motor-shield-r3? som bygger på https://github.com/pololu/dual-vnh5019-motor-shield 
 
2. Raspberry Pi 3 eller Zero https://github.com/albrdev/marvin42-dacapo-networking 
 
3. WeMos LoLin D1 mini https://github.com/albrdev/marvin42-dacapo-joystick_client 
 
Dokumentation repo med export av detta Google Docs https://github.com/jonasbits/marvin42-dacapo-docs 
 
 
Presentation 
 
https://docs.google.com/presentation/d/1beX7hva5HjMFXKNHn2rgH45J-gQc98lq1z0H9HMi B3w/edit#slide=id.p 
 
Stämningsfull musik till presentationen. Chamillionaire - The Sound Of Revenge Ridin’ 
 
Flow chart 
 
Robby RP5 -> Motor shield -> Arduino Uno -> UART -> Rpi zero -> Plattkabel Kamera 
 
SoftwareSerial verkar inte trivas med vår motorShield 
 
(Efterforskningar behövs för att konvertera 5v logik till 3v3 logik angående WeMos/LoLin D1) 
 
Work log 
 
Datum Alex comments Basse comments Jonas comments 2019-09-12 Nätverksklasser rpi cam 3d printed for Robby 2019-09-13 Nätverksklasser arduino serial Joystick -> A0 -> LoLin 
2019-09-16 Nätverksklasser Byggt/lött voltage divider 
Byggt voltage divider 
2019-09-17 Kod för nätverk/motorer, kopplat kablar 
n/a Kopplat kablar, spelat VR 
2019-09-18 Lyckats styra motorer via nätverket, testning 
Monterat hårdvara, kopplat kablar, testning 
Testning, byggt joystick, tappat bort sin dator 
    2019-09-19 Utökat användargränssnitte t för client CLI webcam caseholder 
 Kopplat 2x18650 av/på, volt-reg till 5.2v, wake/halt rpi switch.  2019-09-20 Testat joystick, refaktorisering testat joystick,  OpenScad ritning med 3d-printade delar vi valt ut. 2019-09-25   LM317 voltage regulator 2019-0-26 hittat buggar,sUART Byggt robotfjärr, till trådlös, förberett voltmätare på robot samt joystick Kämpat med volt div 2019-09-27  kollat på gyro hårdvara inklusive kopplingar via gpio till rpi Arangerat för rpi zero 2019-09-29   Undersökt batteri konfiguration 2S2P 
 
  
Before pictures 
 
 
After pictures 
 
 
Build log https://www.thingiverse.com/thing:3140027/#18650_battery_holder https://www.thingiverse.com/thing:2144416/#RP5_exp_plate https://www.thingiverse.com/thing:3862767/#rpiCamMount https://www.thingiverse.com/thing:1162200#joypadCase https://www.electrokit.com/produkt/kamerakort-for-raspberry-pi-zero/ 
 
 
Links https://github.com/gallingern/arduino-motor-shield-r3 https://www.m.nu/esp8266-shields/battery-shield-for-wemos-d1-mini https://wiki.wemos.cc/products:d1_mini_shields:motor_shield https://wiki.wemos.cc/products:d1:d1 https://www.arduino.cc/en/uploads/Main/arduino_MotorShield_Rev3-schematic.pdf https://www.arduino.cc/en/Tutorial/SerialPassthrough https://www.baldengineer.com/5-voltage-divider-circuits.html https://www.sparkfun.com/products/9032? - joystick som liknar våran 10k Ohm http://www.ohmslawcalculator.com/voltage-divider-calculator https://www.baldengineer.com/5-voltage-divider-circuits.html https://www.raspberrypi.org/documentation/hardware/raspberrypi/schematics/rpi_SCH_Zero W_1p1_reduced.pdf  
More Links https://picamera.readthedocs.io/en/latest/recipes2.html#web-streaming https://www.w3schools.com/tags/att_meta_http_equiv.asp https://thepihut.com/products/keyes-rotary-encoder-module https://github.com/modmypi/Rotary-Encoder/blob/master/rotary_encoder.py https://www.conrad.se/p/arexx-bandsats-rp5rp6-passar-till-rp6-rp5-191333 
 
https://patrick.welfringer.lu/sos/waves/drwho/exterminated_you_will_be.wav http://www.wavsource.com/snds_2018-06-03_5106726768923853/movies/lost_in_space/los t_in_space_robot_online.wav 
 
https://unix.stackexchange.com/questions/109804/crontabs-reboot-only-works-for-root https://www.instructables.com/id/Arduino-Battery-Voltage-Indicator/ 
 
 # marvin42-dacapo-docs
Repo of docs regarding the marvin42-dacapo project
