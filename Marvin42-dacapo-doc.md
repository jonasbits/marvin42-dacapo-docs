Projektspecifikation 
 
Rollf�rdelning:  Alexander B (bin�rprotokol-ansvarig),  Jonas � (breadboard-ansvarig),  Sebastian C (scrum master) 
 
Anv�ndning:  Deployment p� ny h�rdvara: - Ladda upp motor sketch till Arduino UNO ( med Motor Shield ) - Flasha nytt SD kort till Raspberry Pi - Justera WiFi l�sen efter behov - Klona gitrepos ( med flaggan --recurse-submodules ) - Bygg bin�rfiler - Justera IP-address efter behov - L�gg in autostart med t.ex. crontab 
 
- Koppla upp breadboard med bl.a. voltage divider f�r UART enligt Fritizing-ritning - Ladda upp joystick sketch till LoLin D1 mini - Justera WiFi l�sen och IP-address efter behov - Koppla upp breadboard med bl.a. voltage divider f�r att m�ta sp�nning i batteri 
 
Anv�ndning av fj�rrkontroll: - Sl� p� str�mmen p� b�de robot och fj�rr. - Tryck p� fram�t eller bak�t knappen. Justera riktning med rotary encoder joystick. Tryck in rotary encoder knappen f�r att nollst�lla riktningen. - Tryck p� reset knappen p� Uno f�r att stanna roboten. - Sl� av str�mmen p� b�de robot och fj�rr - Alternativt anv�nd GPIO-shutdown knappen p� Raspberry Pi f�r att g�ra en sn�llare avst�ngning.   

 Design: 
 
 
Vi tog en redan inf�rskaffad Arexx RP5 robot och skrev ut en platta f�r att f�sta v�ra olika komponenter. Vi hittade en Motor Shield r3 ( Adafruit ) och provade exempel-koden. Sedan k�mpade vi med att f� RX/TX att fungera mellan Uno och Rpi. Vi tillverkade en knapp som bryter UART tillf�lligt medans  vi laddar upp en ny sketch till Uno. 
 
Under utvecklingsstadiet anv�nde vi en Raspberry Pi 3, f�r att kompileringen gick snabbare. Men f�rdig produkt fungerar med en Rasbperry Pi Zero W som �r energisn�lare. 
 
Ovan visar ett UML diagram TCP/UDP kommunikation mellan Rpi och LoLin   

 Kod 
meta repo ?https://github.com/albrdev/marvin42-dacapo 
 1. Arduino Uno + Motor Shield https://github.com/albrdev/marvin42-dacapo-motor_controller 
 
Research: git clone ?https://github.com/snowlab/arduino-motor-shield-r3/? som jag forkat ifr�n https://github.com/gallingern/arduino-motor-shield-r3? som bygger p� https://github.com/pololu/dual-vnh5019-motor-shield 
 
2. Raspberry Pi 3 eller Zero https://github.com/albrdev/marvin42-dacapo-networking 
 
3. WeMos LoLin D1 mini https://github.com/albrdev/marvin42-dacapo-joystick_client 
 
Dokumentation repo med export av detta Google Docs https://github.com/jonasbits/marvin42-dacapo-docs 
 
 
Presentation 
 
https://docs.google.com/presentation/d/1beX7hva5HjMFXKNHn2rgH45J-gQc98lq1z0H9HMi B3w/edit#slide=id.p 
 
St�mningsfull musik till presentationen. Chamillionaire - The Sound Of Revenge Ridin� 
 
Flow chart 
 
Robby RP5 -> Motor shield -> Arduino Uno -> UART -> Rpi zero -> Plattkabel Kamera 
 
SoftwareSerial verkar inte trivas med v�r motorShield 
 
(Efterforskningar beh�vs f�r att konvertera 5v logik till 3v3 logik ang�ende WeMos/LoLin D1) 
 
Work log 
 
Datum Alex comments Basse comments Jonas comments 2019-09-12 N�tverksklasser rpi cam 3d printed for Robby 2019-09-13 N�tverksklasser arduino serial Joystick -> A0 -> LoLin 
2019-09-16 N�tverksklasser Byggt/l�tt voltage divider 
Byggt voltage divider 
2019-09-17 Kod f�r n�tverk/motorer, kopplat kablar 
n/a Kopplat kablar, spelat VR 
2019-09-18 Lyckats styra motorer via n�tverket, testning 
Monterat h�rdvara, kopplat kablar, testning 
Testning, byggt joystick, tappat bort sin dator 
    2019-09-19 Ut�kat anv�ndargr�nssnitte t f�r client CLI webcam caseholder 
 Kopplat 2x18650 av/p�, volt-reg till 5.2v, wake/halt rpi switch.  2019-09-20 Testat joystick, refaktorisering testat joystick,  OpenScad ritning med 3d-printade delar vi valt ut. 2019-09-25   LM317 voltage regulator 2019-0-26 hittat buggar,sUART Byggt robotfj�rr, till tr�dl�s, f�rberett voltm�tare p� robot samt joystick K�mpat med volt div 2019-09-27  kollat p� gyro h�rdvara inklusive kopplingar via gpio till rpi Arangerat f�r rpi zero 2019-09-29   Unders�kt batteri konfiguration 2S2P 
 
  
Before pictures 
 
 
After pictures 
 
 
Build log https://www.thingiverse.com/thing:3140027/#18650_battery_holder https://www.thingiverse.com/thing:2144416/#RP5_exp_plate https://www.thingiverse.com/thing:3862767/#rpiCamMount https://www.thingiverse.com/thing:1162200#joypadCase https://www.electrokit.com/produkt/kamerakort-for-raspberry-pi-zero/ 
 
 
Links https://github.com/gallingern/arduino-motor-shield-r3 https://www.m.nu/esp8266-shields/battery-shield-for-wemos-d1-mini https://wiki.wemos.cc/products:d1_mini_shields:motor_shield https://wiki.wemos.cc/products:d1:d1 https://www.arduino.cc/en/uploads/Main/arduino_MotorShield_Rev3-schematic.pdf https://www.arduino.cc/en/Tutorial/SerialPassthrough https://www.baldengineer.com/5-voltage-divider-circuits.html https://www.sparkfun.com/products/9032? - joystick som liknar v�ran 10k Ohm http://www.ohmslawcalculator.com/voltage-divider-calculator https://www.baldengineer.com/5-voltage-divider-circuits.html https://www.raspberrypi.org/documentation/hardware/raspberrypi/schematics/rpi_SCH_Zero W_1p1_reduced.pdf  
More Links https://picamera.readthedocs.io/en/latest/recipes2.html#web-streaming https://www.w3schools.com/tags/att_meta_http_equiv.asp https://thepihut.com/products/keyes-rotary-encoder-module https://github.com/modmypi/Rotary-Encoder/blob/master/rotary_encoder.py https://www.conrad.se/p/arexx-bandsats-rp5rp6-passar-till-rp6-rp5-191333 
 
https://patrick.welfringer.lu/sos/waves/drwho/exterminated_you_will_be.wav http://www.wavsource.com/snds_2018-06-03_5106726768923853/movies/lost_in_space/los t_in_space_robot_online.wav 
 
https://unix.stackexchange.com/questions/109804/crontabs-reboot-only-works-for-root https://www.instructables.com/id/Arduino-Battery-Voltage-Indicator/ 
 
 # marvin42-dacapo-docs
Repo of docs regarding the marvin42-dacapo project
