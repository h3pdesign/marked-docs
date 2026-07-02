# <%= @title %>

Als een bestand opgenomen via [Marked's include syntax or IA Writer block syntax][include] een CSV- of TSV-extensie heeft, zal Marked proberen het te parseren en te converteren naar een MultiMarkdown tabel. Dit werkt met de meeste standaardformaten, inclusief door komma's en tabs gescheiden formaten, maar ook met extra scheidingstekens en formaten voor aanhalingstekens die automatisch worden gedetecteerd.

Een voordeel van het gebruik van CSV-bestanden in plaats van het schrijven van Markdown tabellen is dat regeleinden in cellen automatisch worden geconverteerd naar `<br>` tags. Dit moet handmatig worden gedaan om regeleinden op te nemen bij het schrijven van MultiMarkdown-tabellen, waardoor u extra tijd bespaart.

Even terzijde: er is een uitstekende app genaamd [TableFlip][] die het bewerken van tabellen in uw document veel eenvoudiger maakt. Het is de moeite waard om eens te kijken als u vaak met tabelgegevens werkt.

Inbegrepen CSV-bestanden worden gecontroleerd op wijzigingen, dus er kunnen aanvullende bewerkingen worden uitgevoerd in het originele CSV-bestand en Marked zal het voorbeeld automatisch bijwerken bij het opslaan.

Geconverteerde tabellen worden opgenomen in de Markdown-export, dus Marked kan worden gebruikt om documenten samen te stellen die gestructureerde gegevens bevatten en om één enkel bestand te exporteren.

[include]: Multi-File_Documents.html
[TableFlip]: http://tableflipapp.com/