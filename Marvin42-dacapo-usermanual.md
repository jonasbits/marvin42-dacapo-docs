<b>Anv�ndarmanual</b><br>

<b>* Sammanfattning</b><br>
<b>* Installation</b><br>
<b>* Str�mf�rs�rjning</b><br>
<b>* H�rdvara</b><br>
<b>* Mjukvara</b><br>
<b>* Fabriks�terst�llning</b><br>
<b>* Anv�ndning</b><br>
<b>* Uppstart</b><br>
<b>* Normal anv�ndning</b><br>
<b>* Avst�ngning</b><br>
<b>* Till�ggsmoduler</b><br>
<b>* Underh�ll</b><br>
<b>* FAQ</b><br>
<b>* Hur kunde ni orka g�ra det h�r?</b><br>
<b>* Support och Kontakt</b><br>
<br>
<b>Sammanfattning</b><br>
Marvin42 �r en robotbil byggd p� mechanum-hjul som ger den f�rm�gan att kunna r�ra sig fritt �t alla h�ll utan
att sv�nga.<br> Detta g�r att den blir l�ttare att man�vrera i tr�nga och sv�rtillg�ngliga omr�den. Nedan f�ljer ett antal exempel p� anv�ndningsomr�den:<br>
Mappa planl�sningar<br>
Utforska sv�r�tkomliga platser som t.ex. ventilationstrummor och r�rledningar<br>
Radioaktiva zoner<br>
Olycksdrabbade omr�den<br>
Bombdesarmering<br>
Spaning, minr�jning och andra milit�ra �ndam�l<br>
Bevakning<br>
N�je<br>
<br>
<b>Installation</b><br>
<b>Str�mf�rs�rjning</b><br>
Robotbilen och joystick drivs med 2st 3.7V 18650-batterier vardera.<br>
<br>
<b>H�rdvara</b><br>
H�rdvaran �r monterad och klar f�r anv�ndning vid k�p av produkt.<br>
<br>
<b>Mjukvara</b><br>
All mjukvara �r installerad och konfigurerad vid k�p av produkt.<br>
<br>
<b>Fabriks�terst�llning</b><br>
Nedan f�ljer steg f�r fabriks�terst�llning (under f�ruts�ttning att anv�ndaren har relevanta tekniska f�rkunskaper)<br>
* Ladda ned och flasha minneskortet (microSD) med Raspbian Buster Lite.<br>
* S�tt in minneskortet i Raspberry Pi Zero och starta  roboten.<br>
* Anv�nd SSH f�r att logga in med anv�ndaren pi och l�senord raspberry.<br>
* Anslut till valfritt WiFi med internet-�tkomst.<br>
* Uppdatera systemet med sudo apt update och sedan sudo apt upgrade. <br>
* Detta kan ta en l�ngre tid, kontrollera batteristyrka eller anv�nd den medf�ljande USB-kabel.<br>
* Installera de n�dv�ndigaste programmen sudo apt install git libserialport.<br>
* Klona f�ljande repon: <br>
* git clone https://github.com/albrdev/marvin42-dacapo-networking.git <br>
* git clone https://github.com/albrdev/marvin42-dacapo-configs.git<br>
* G� till ena repot: cd marvin42-dacapo-networking<br>
* Bygg programmet genom att k�ra: make release<br>
* G� till andra repot: cd marvin42-dacapo-configs<br>
* K�r make<br>
<br>
<b>Anv�ndning</b><br>
<b>Uppstart</b><br>
Robot: Starta genom att sl� p� str�mbrytaren. En lampa p� Arduino Mega samt Raspberry Pi Zero skall lysa. <br>Processen tar ett par sekunder.<br>
Joystick: Starta genom att sl� p� str�mbrytaren. Joysticken �r parad med roboten och skall ansluta och fungera automatiskt.<br>
<br>
<b>Normal anv�ndning</b><br>
Roboten styrs med hj�lp av medf�ljande joystick.<br>
Denna har tv� analoga styrspakar och ett hastighetsreglage.<br>
V�nster styrspak: Styr sj�lva robotens k�rriktning. Spaken har ett d�dmansgrepp som stannar n�r den sl�pps och <br>m�ste d�rf�r h�llas in i k�rriktningen under hela den tid roboten �nskas vara i r�relse.<br>
H�ger styrspak: Roterar roboten med- eller motsols, beroende p� �t vilken riktning spaken har p� X-axeln. <br>Y-axeln ignoreras helt.<br>
Hastighetsreglage: �kar hastigheten genom att vrida reglaget fram�t (fr�n anv�ndaren). Minskar hastigheten genom<br> att vrida reglaget bak�t (mot anv�ndaren).<br>
<br>
<b>Avst�ngning</b><br>
Robot: St�ngs av genom att sl� av str�mbrytaren. Robotbilen sparar inget v�sentligt, s�som position eller <br>
rotation mellan uppstarter. Eventuellt sparas diverse inhemska systemloggar p� Raspberry Pi Zero<br>
Joystick: St�ngs av genom att sl� av str�mbrytaren. Joystick sparar inget v�sentligt, s�som senaste riktning/<br>
hastighet mellan uppstarter, och d�rf�r b�r hastighetsreglage manuellt �terst�llas till max. innan uppstart.<br>
Ingen programvara �r beroende av str�mf�rs�rjning f�r att inte raderas i fr�n minnet.<br>
Om n�gon utrustning har nollst�llts, se sektion f�r �terst�llning. <br>
<br>
<b>Till�ggsmoduler</b><br>
Ultrasonic modulen kan monteras p� roboten om det beh�vs data f�r att kunna kartl�gga ett utrymme som bara roboten klarar av att utforska<br>
<br>
<b>Underh�ll</b><br>
Byte av TT-motorerna kan beh�va g�ras eftersom vi k�r dem ?out of spec?, allts� lite under 8 volt, medans spec s�ger 3-6 volt.<br>
<br>
<b>FAQ</b><br>
<b>Hur kunde ni orka g�ra det h�r?</b><br>
Vi sparade inget f�r att orka simma tillbaka!<br>
<br>
<b>Varf�r ger ni inte upp?</b><br>
Vi ger aldrig upp, vi slutar inte f�rs�ka!<br>
<br>
<b>Support och Kontakt</b><br>
H�rdvara: Jonas �<br>
Mjukvara: Alexander B<br>
Dokumentation: Sebastian C<br>
