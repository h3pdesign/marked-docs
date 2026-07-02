# <%= @title %>

Opties in de {% prefspane Advanced %}:

![Settings: Advanced][1]

[1]: images/screenshots/preferences-Advanced.jpg @2x width=689px height=1031px class=preferencepane-scroll

YAML en Pandoc-metagegevens
: - __Negeren:__ Laat het precies zoals het in het document staat, handig als uw processor of preprocessor daadwerkelijk de YAML gebruikt.
: - __Verwijderen vóór weergave__: het blok YAML wordt gestript
: - __Behandelen als MMD metadata:__ Converteert het YAML of Pandoc metadatablok naar het MultiMarkdown formaat.

Strip MultiMarkdown Metagegevenskoppen
: Als dit is ingeschakeld, worden de MultiMarkdown-metagegevens bovenaan het document verwijderd voordat het wordt weergegeven.
: Dit kan handig zijn als u een niet-MultiMarkdown processor gebruikt die anders de metagegevens in het weergegeven document zou weergeven. De metagegevens worden nog steeds gelezen voordat ze worden verwijderd, dus de Marked-specifieke syntaxis wordt nog steeds herkend.

Gehoste afbeeldingen in cache plaatsen
: Marked slaat standaard geen afbeeldingen op in het voorbeeld, omdat het deze afbeeldingen controleert op wijzigingen en deze onmiddellijk bijwerkt. Als u afbeeldingen gebruikt waarnaar wordt verwezen via een web-URL, kunt u het cachen van die afbeeldingen inschakelen om de weergave bij langzamere verbindingen te versnellen.

Analyseer leesbaarheidsstatistieken
: Als u [statistics](Document_Statistics.html) liever niet wilt laten berekenen, wordt deze verwerking uitgeschakeld. Dit kan enkele prestatieverbeteringen opleveren bij zeer grote documenten. Het aantal tekens, woorden en zinnen blijft functioneren.

Gebruik het hele systeem Zoek plakbord
: Met deze optie kan Marked de zoekterm ophalen die u het laatst in een andere editor hebt gebruikt, en alles waarnaar in Marked wordt gezocht, wordt ook de zoekopdracht in andere toepassingen. Als u dit uitschakelt, wordt de zoekfunctie van Marked onafhankelijk.

Gebruik {% kbd cmd E %} voor Zoeken met selectie
: Standaard opent {% kbd cmd E %} de standaardeditor. Als deze optie is ingeschakeld, zal {% kbd cmd E %} functioneren zoals in de meeste tekstbewerkingsprogramma's, waarbij de geselecteerde tekst wordt gebruikt voor Zoeken, en Openen in Editor kan worden geactiveerd met {% kbd opt cmd E %}.

Debug-modus
: Schakelt logboekregistratie voor foutopsporing in. Gebruik dit voor uw eigen probleemoplossing en bij het melden van een probleem. Selecteer __Help->Debug Log openen__ om de activiteit te bekijken.
: Als u _All_ instelt, worden infoberichten, waarschuwingen en foutmeldingen weergegeven. U kunt ook instellen dat alleen fouten of fouten en waarschuwingen worden weergegeven.

Instellingen Back-up
: u kunt een back-up van uw instellingen maken in een JSON-bestand dat kan worden gebruikt om instellingen te herstellen of over te zetten naar een nieuwe machine.