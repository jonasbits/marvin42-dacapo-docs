<b>Användarmanual</b><br>

<b>* Sammanfattning</b><br>
<b>* Installation</b><br>
<b>* Strömförsörjning</b><br>
<b>* Hårdvara</b><br>
<b>* Mjukvara</b><br>
<b>* Fabriksåterställning</b><br>
<b>* Användning</b><br>
<b>* Uppstart</b><br>
<b>* Normal användning</b><br>
<b>* Avstängning</b><br>
<b>* Tilläggsmoduler</b><br>
<b>* Underhåll</b><br>
<b>* FAQ</b><br>
<b>* Hur kunde ni orka göra det här?</b><br>
<b>* Support och Kontakt</b><br>
<br>
<b>Sammanfattning</b><br>
Marvin42 är en robotbil byggd på mechanum-hjul som ger den förmågan att kunna röra sig fritt åt alla håll utan
att svänga.<br> Detta gör att den blir lättare att manövrera i trånga och svårtillgängliga områden. Nedan följer ett antal exempel på användningsområden:<br>
Mappa planlösningar<br>
Utforska svåråtkomliga platser som t.ex. ventilationstrummor och rörledningar<br>
Radioaktiva zoner<br>
Olycksdrabbade områden<br>
Bombdesarmering<br>
Spaning, minröjning och andra militära ändamål<br>
Bevakning<br>
Nöje<br>
<br>
<b>Installation</b><br>
<b>Strömförsörjning</b><br>
Robotbilen och joystick drivs med 2st 3.7V 18650-batterier vardera.<br>
<br>
<b>Hårdvara</b><br>
Hårdvaran är monterad och klar för användning vid köp av produkt.<br>
<br>
<b>Mjukvara</b><br>
All mjukvara är installerad och konfigurerad vid köp av produkt.<br>
<br>
<b>Fabriksåterställning</b><br>
Nedan följer steg för fabriksåterställning (under förutsättning att användaren har relevanta tekniska förkunskaper)<br>
* Ladda ned och flasha minneskortet (microSD) med Raspbian Buster Lite.<br>
* Sätt in minneskortet i Raspberry Pi Zero och starta  roboten.<br>
* Använd SSH för att logga in med användaren pi och lösenord raspberry.<br>
* Anslut till valfritt WiFi med internet-åtkomst.<br>
* Uppdatera systemet med sudo apt update och sedan sudo apt upgrade. <br>
* Detta kan ta en längre tid, kontrollera batteristyrka eller använd den medföljande USB-kabel.<br>
* Installera de nödvändigaste programmen sudo apt install git libserialport.<br>
* Klona följande repon: <br>
* git clone https://github.com/albrdev/marvin42-dacapo-networking.git <br>
* git clone https://github.com/albrdev/marvin42-dacapo-configs.git<br>
* Gå till ena repot: cd marvin42-dacapo-networking<br>
* Bygg programmet genom att köra: make release<br>
* Gå till andra repot: cd marvin42-dacapo-configs<br>
* Kör make<br>
<br>
<b>Användning</b><br>
<b>Uppstart</b><br>
Robot: Starta genom att slå på strömbrytaren. En lampa på Arduino Mega samt Raspberry Pi Zero skall lysa. <br>Processen tar ett par sekunder.<br>
Joystick: Starta genom att slå på strömbrytaren. Joysticken är parad med roboten och skall ansluta och fungera automatiskt.<br>
<br>
<b>Normal användning</b><br>
Roboten styrs med hjälp av medföljande joystick.<br>
Denna har två analoga styrspakar och ett hastighetsreglage.<br>
Vänster styrspak: Styr själva robotens körriktning. Spaken har ett dödmansgrepp som stannar när den släpps och <br>måste därför hållas in i körriktningen under hela den tid roboten önskas vara i rörelse.<br>
Höger styrspak: Roterar roboten med- eller motsols, beroende på åt vilken riktning spaken har på X-axeln. <br>Y-axeln ignoreras helt.<br>
Hastighetsreglage: Ökar hastigheten genom att vrida reglaget framåt (från användaren). Minskar hastigheten genom<br> att vrida reglaget bakåt (mot användaren).<br>
<br>
<b>Avstängning</b><br>
Robot: Stängs av genom att slå av strömbrytaren. Robotbilen sparar inget väsentligt, såsom position eller <br>
rotation mellan uppstarter. Eventuellt sparas diverse inhemska systemloggar på Raspberry Pi Zero<br>
Joystick: Stängs av genom att slå av strömbrytaren. Joystick sparar inget väsentligt, såsom senaste riktning/<br>
hastighet mellan uppstarter, och därför bör hastighetsreglage manuellt återställas till max. innan uppstart.<br>
Ingen programvara är beroende av strömförsörjning för att inte raderas i från minnet.<br>
Om någon utrustning har nollställts, se sektion för återställning. <br>
<br>
<b>Tilläggsmoduler</b><br>
Ultrasonic modulen kan monteras på roboten om det behövs data för att kunna kartlägga ett utrymme som bara roboten klarar av att utforska<br>
<br>
<b>Underhåll</b><br>
Byte av TT-motorerna kan behöva göras eftersom vi kör dem ?out of spec?, alltså lite under 8 volt, medans spec säger 3-6 volt.<br>
<br>
<b>FAQ</b><br>
<b>Hur kunde ni orka göra det här?</b><br>
Vi sparade inget för att orka simma tillbaka!<br>
<br>
<b>Varför ger ni inte upp?</b><br>
Vi ger aldrig upp, vi slutar inte försöka!<br>
<br>
<b>Support och Kontakt</b><br>
Hårdvara: Jonas Ö<br>
Mjukvara: Alexander B<br>
Dokumentation: Sebastian C<br>
