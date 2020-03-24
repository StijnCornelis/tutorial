# Tutotial Slender game
## Hardware 
- Arduino Uno
- sensoren om hartslag te meten
- computer met beeldscherm
- aansluitkabels


## Software
 - Arduino software (https://www.arduino.cc/en/main/software)
 - Visual studio 2019
 - Unity (https://unity3d.com/get-unity/download/archive) version 2019.2.8
 
 ##  1) Arduino tutorial
 - Neem de Arduino erbij en sluit deze aan op je computer met de bijhorende USB kabel
 - Installeer nu de software met de link die hierboven staat
 - Wij gebruiken een Pulse sensor voor ons project
 - Neem deze er bij en sluit deze als volgt aan:
 - Soldeer de volgende kabels op uw Pulse sensor indien dit nog niet gebeurd is: 
   - Zwart => GND(Ground)
   - Rood => 3V3 (3,3 Volt)
   - Blauw => SDA
   - Geel =>SCL
   - Wit=>RST(Reset)
   - Oranje => MFIO 
- Nu deze aan uw sensor hangen kan je je sensor aansluiten aan de Arduino: 
  - Zwart=> GND
  - Rood => 3V3
  - Blauw=> SDA
  - Geel => SCL 
  - Wit=>RST(Reset)
  - Oranje => MFIO
 
  ![Image description](https://media.discordapp.net/attachments/509367562157555713/688758590143463464/20200219_163057.jpg?width=368&height=655)
 - Nu de sensor is aangesloten en de arduino verbonden is met je computer, kan het programma gedownload worden (https://github.com/aliekens/pulse_sensor_tutorial)
 - Als dit geïnstalleerd is kan je het exporteren naar je bibliotheek in Ardruino IDE onder: Sketch > Include Library > Add .ZIP library...
 - Dit bestand is het standaardprogramma dat je zal gebruiken voor deze sensor aan het sturen. 
 - Moest je echt niets snappen van Arduino's en wil je meer leren: (http://wiki.opengarage.org/index.php/Arduino_tutorial)
 ## 2) Installatie Unity + Unity Hub
 https://unity3d.com/get-unity/download/archive
 
 ## 3) Installatie Visual Studio
 Download de community versie van 2019 op <br>
 https://visualstudio.microsoft.com/vs/
 
 ## 4) Project downloaden van deze github en openen.
 
 Wanneer je deze github hebt gedownload via deze link:
 
<br>https://github.com/Crazykelpi/Medicman
ga je deze unzippen. Hierna ga je je Unity openen en je merkt dat de unity hub gaat openen. Je gaat er eerst voor moeten zorgen dat je een license hebt voor alle programma's. Dit doe je door een account te maken bij Unity en hierdoor krijg je een gratis license.
Wanneer dit allemaal in orde is, druk je op de 'Add'-knop om een nieuwe project in te laden. Je kiest de juiste map en vervolgens klik je op 'Map selecteren'. Nu gaat je project laden en als het geladen is dubbelklik je erop om het te doen starten. Unity gaat open.

 
 ## 5) Scripts bespreken en evenuteel aanpassen
 U kan de scripts openen door naar unity te gaan en dan naar project > Assets > Scripts te gaan. Hier zie je een aantal c# bestanden. Als je er op klikt, opent  Visual studio 2019. In dit hoofstuk besrpeken wat elk script doet en waar u eventuele parameters kunt afspreken.
 - datahandler <br>
Dit is het script dat de data van de arduino zal inlezen en formateren om te displayen in het spel en te gebruiken in algoritmes. 
We raden aan om hier niets aan te passen, omdat je hier veel verkeerd kunt doen en dan krijg je geen hartslag meer in het spel.
- Footsteps<br>
 Dit script zorgt vooral voor de geluiden: de voetstappen, maar ook het geluid dat je hoort wanneer je een papier neemt, de klokgeluiden etc.
  Ook worden hier bijgehouden hoeveel papiertjes je hebt verzamelt.
  
  Je kan de geluiden aanpassen door in unity op 'scene1' te klikken en dan op 'Player'. Scroll daar naar beneden tot je 'footsteps (Script)' ziet.
  Hier mag je het geluid 'heartbeat', 'scream' en 'heavybreathing' vervangen door een geluid naar keuze.
  Je kan een geluid in unity slepen door het geluid naar keuze vanop je computer naar de unity files te slepen en in 'assets' te stoppen. 
  (zorg dat je weet waar je het geluid steekt zodat je het in unity terugvindt. Als je het geluid in assets hebt gestoken kan je onder project 
  zoeken naar de naam van het bestand. Sleep je bestand naar het script en laat het los op het geluid dat je wilt veranderen.
  
   !!!!VERANDER 'sound', 'siren' en countText NIET!!!!!
  'scream' wordt afgespeeld wanneer je de eerste of tweede papiertje vindt en als je in level 2 of hoger zit.
  'heartbeat' wordt afgespeeld wanneer je het derde of 4de papiertje vindt en als je in level 3 of hoger zit.
  'heavybreathing' wordt afgespeeld wanneer je het vijfde papiertje vindt en als je in level 4 of hoger zit.
  
  Pas hier in het script zelf niets aan.
- Game Over scene <br>
Als slenderman je te pakken heeft, zal je het gameoverscherm zien. Dit script zorgt er voor dat de knoppen 'try again' je terug naar  het
startscherm brengen en de 'quit' button zorgt ervoor dat je stopt met spelen.
Scroll naar beneden om iets aan te passen bij de "//"
- Light Toggle <br>
Dit script zorgt ervoor dat je zakklamp schijnt. In normale omstandigheden zal hij 99% van de tijd licht geven en 1% niet, om het effect te creëren dat de zaklamp flikkert.
Wanneer slenderman dichterbij is, zal de zaklamp feller flikkeren (50% van de tijd is het licht uit).<br>
Op lijn 22 en 27 kan je hier met de parameters spelen, in het script zelf staat de nodige uitleg.
- Mouse Look<br>
Dit script zorgt ervoor dat je in het spel kan rondkijken door je muis te bewegen. Verander hier niets aan, want anders draait alles in de soep.
- Move Player<br>
Dit script is verantwoordelijk voor alle bewegingen van de speler. De snelheid en de input van de knoppen die ervoor zorgen dat je kan bewegen. De snelheid va nde speler kan je aanpassen op lijn 11.
- Move Slender<br>
Dit script zorgt ervoor dat slender beweegt vanaf het moment dat je je eerste papiertje vindt. Hier wordt vooral de snelheid van slender
aangepast. Dit is afhankelijk van hoe van slender is (hoe verder weg hoe sneller), maar ook in welk level je bevindt (hoe hoger het level hoe sneller).<br>
Hier kan je aeen aantal parameters aanpassen waardoor het spel vroeger of later eindigt op lijn 24 en 35. Ook kan je de snelheid van slender doen aanpassen vanaf lijn 45. Er staat alrijd voldoende uitleg zodat je weet wat je aan het aanpassen bent.
- Normal Heartbeat <br>
Hier berekenen we de gemiddelde hartslag van de speler, om te bepalen wanneer we de hartslagtekst in het rood laten gaan en of je naar
het volgende level mag gaan. <br>
Pas hier niets aan.
- Pause Menu <br>
Dit is het pausemenu, hier wordt er voor gezorgd dat je niet meer kan rondkijken en dat er een pausemenu verschijnt. Ook wordt de tijd stilgezet om te vermijden dat jij en slender kunnen bewegen.<br>
Hier pas je ook niets aan.
- Rotator <br>
Dit script zorgt ervoor dat de papiertjes ronddraaien. <br>
We raden aan om hier niets aan te passen.
- Rotate to player <br>
Dit script zorgt ervoor dat slender altijd naar de speler kijkt. <br>
We raden aan om hier niets aan te passen.
- Sounds <br>
Hier wordt ervoor gezorgdt dat als de speler te dicht bij slenderman komt, er een geluid (seenSound) wordt afgespeeld.
Je kan hier het 'seenSound' aanpassen. Zie het script 'Footsteps' voor meer informatie. 'seenSound' wordt afgespeeld als je binnen 30 afstand van slender bent. <br>
Scroll naar beneden om iets aan te passen bij de "//".
- stress level
 Dit script zorgt voor alles dat met de (stress)levels te maken heeft. Het laten zien van de tijd tussen de levels tot de verschillende effecten. <br>
Scroll naar beneden om te kijken wat je kan aanpassen bij de "//".
- Turn to slender <br>
Dit script zorgt ervoor dat wanneer je te dicht bij slender komt je naar hem draait en een jumpscare krijgt.<br>
Pas hier niets aan.
- Won <br>
Dit script zorgt ervoor dat er knoppen komen die je de mogelijkheid geven om opnieuw te spelen of het spel af te sluiten. <br>
Je mag hier aanpassing doen bij de '//'.

## 6) Spel starten

Wanneer je de nodige aanpassingen hebt gedaan zorg je ervoor dat alle scripts worden gesaved door simpelweg op ctrl + s in visual studio te drukken op je toetsenbord. Doe dit niet op 1 script maar op alle verschillende scripten dat je hebt aangepast.
Om het spel te doen starten ga je terug naar Unity en druk je bovenaan op de play button en het spel zou moeten starten.<br>
Veel plezier!





  
