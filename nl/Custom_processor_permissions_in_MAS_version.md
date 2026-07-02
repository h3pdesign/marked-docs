# Custom processorrechten in MAS-versie

Vanwege sandbox-beperkingen kan de Mac App Store-versie van Marked bepaalde soorten binaire tools niet als aangepaste processors uitvoeren. Als u deze beperking tegenkomt, zijn er een paar stappen die u kunt proberen.

1. Zorg ervoor dat u naar **Marked** Instellingen ({% kbd cmd , %}) in het venster **Geavanceerd** bent gegaan en op 'Toestemmingen bijwerken' hebt geklikt. Hiermee wordt geprobeerd Marked toegang te verlenen tot uw gehele standaardschijf, waardoor problemen met scripts en hulpprogramma's worden opgelost die toegang moeten krijgen tot tijdelijke mappen en niet-standaardlocaties.
2. Probeer een script te gebruiken. Verwijs naar het hulpprogramma dat u wilt uitvoeren (multimarkdown, kramdown, enz.) in een shellscript. Het kan een bash-, Ruby-, Perl- of Python-script zijn. Stel vervolgens de processor in Geavanceerde instellingen in op de gerelateerde shell of het bijbehorende uitvoerbare bestand, en de parameters op de locatie van het script. Ik kan bijvoorbeeld een bash-script maken dat is opgeslagen in ~/scripts/mmd_wrapper.sh:

#!/bin/bash
        kat | /usr/local/bin/multimarkdown

Maak het vervolgens uitvoerbaar (`chmod a+x ~/scripts/mmd_wrapper.sh`) en stel mijn Custom Processorinstellingen in:

Processor: /bin/bash
        Argumenten: /Users/me/scripts/mmd_wrapper.sh
3. Sommige uitvoerbare bestanden (vooral Pandoc) werken gewoon niet binnen sandboxing. Neem in dit geval contact met mij op via het foutvenster dat verschijnt tijdens de uitvoering om een ​​crossgrade-licentie voor de directe versie te ontvangen.

