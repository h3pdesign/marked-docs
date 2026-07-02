# <%= @title %> [toc]

## Licentiecode is al gebruikt [license_code_has_already_been_utilized]

Als u een nieuwe installatie van Marked 2 uitvoert en de foutmelding "Licentiecode is al gebruikt" krijgt bij het invoeren van uw licentie, <a href="mailto:me@bretterpstra.com">neem dan contact met mij op</a> en vraag een nieuwe licentie aan. **Vermeld het e-mailadres waarmee u zich heeft geregistreerd en/of uw huidige licentiecode.**

Vroege licenties gegenereerd voor Marked hadden een gebruikslimiet in plaats van een machinelimiet, dus drie installaties (zelfs op dezelfde machine) zouden activeringen opgebruiken. Deze limieten zijn gecorrigeerd in recenter gegenereerde licenties. Door een licentie van Marked 2 te kopen, kunt u Marked 2 installeren op elke machine die u bezit, dus aarzel niet om een ​​vervanging te vragen als u problemen ondervindt.

[Table of contents](#toc)

## Sitelicenties en educatieve kortingen [site_licenses_and_educational_discounts]

Site-/bulklicenties met korting zijn beschikbaar voor Marked 2. Als u een aankooplink wilt aanvragen, neemt u contact op met <a href="mailto:me@brettterpstra.com">Brett</a> en geeft u het aantal licenties op dat u wilt kopen.

**Kortingen**

- 5-9: **10% korting**
- 10-19: **12% korting**
- 20-49: **15% korting**
- 50+: **20% korting**

Er is ook een educatieve korting beschikbaar voor zowel de directe versie als de Mac App Store-versie. Voor de Mac App Store zijn standaard onderwijskortingen van Apple ingeschakeld. Als u een directe versie met educatieve korting wilt kopen, <a href="mailto:me@bretterpstra.com">neemt u contact met mij op</a> en vraagt ​​u een kortingsbon aan.

[Table of contents](#toc)

## Een URL valideert niet of retourneert "Onbekend" [a_url_wont_validate_or_returns_unknown]

Marked's [link validation](http://marked2app.com/help/Link_Validation.html) gebruikt een standaard HEAD-verzoek om te bepalen of een link geldig is. Alles anders dan een resultaat van 200 (succes) zal een onbekende of een fout opleveren als het een veel voorkomende foutcode is, zoals 404 (niet gevonden) of 500 (serverfout). URL's achter authenticatie (zoals Apple Developer-URL's of iets waarvoor inloggen vereist is om toegang te krijgen) zullen een "onbekend" retourneren, net als bepaalde sites zoals Amazon.com waar de server bizarre responscodes retourneert. Hier kan Marked niet veel aan doen.

[Table of contents](#toc)

## Custom processorrechten in MAS-versie [custom_processor_permissions_in_mas_version]

Vanwege sandbox-beperkingen kan de Mac App Store-versie van Marked 2 bepaalde soorten binaire tools niet als aangepaste processors uitvoeren. Als u deze beperking tegenkomt, zijn er een paar stappen die u kunt proberen.

1. Zorg ervoor dat u naar **Marked 2** Voorkeuren (⌘,) in het paneel **Geavanceerd** bent gegaan en op 'Toestemmingen bijwerken' hebt geklikt. Hiermee wordt geprobeerd Marked toegang te verlenen tot uw gehele standaardschijf, waardoor problemen met scripts en hulpprogramma's worden opgelost die toegang moeten krijgen tot tijdelijke mappen en niet-standaardlocaties.
2. Probeer een script te gebruiken. Verwijs naar het hulpprogramma dat u wilt uitvoeren (multimarkdown, kramdown, enz.) in een shellscript. Het kan een bash-, Ruby-, Perl- of Python-script zijn. Stel vervolgens de processor in Geavanceerde voorkeuren in op de gerelateerde shell of het bijbehorende uitvoerbare bestand, en de parameters op de locatie van het script. Ik kan bijvoorbeeld een bash-script maken dat is opgeslagen in ~/scripts/mmd_wrapper.sh:
    
        #!/bin/bash
        kat | /usr/local/bin/multimarkdown
    
    Maak het vervolgens uitvoerbaar (`chmod a+x ~/scripts/mmd_wrapper.sh`) en stel mijn Custom Processorvoorkeuren in:

Processor: /bin/bash
        Argumenten: /Users/me/scripts/mmd_wrapper.sh
3. Sommige uitvoerbare bestanden (vooral Pandoc) werken gewoon niet binnen sandboxing. Neem in dit geval contact met mij op via het foutvenster dat verschijnt tijdens de uitvoering om een ​​crossgrade-licentie voor de directe versie te ontvangen.

[Table of contents](#toc)

## Intra-documentlinks in geëxporteerde PDFs [intra-document_links_in_exported_pdfs]

De PDF-export van Marked maakt momenteel gebruik van de afdrukfuncties van WebKit. Eén gevolg hiervan is dat (interne) koppelingen binnen een document, inclusief die in een inhoudsopgave, niet naar andere punten in het document springen. Dit lijkt niet iets te zijn dat Apple van plan is te repareren in de versie van WebKit die Marked 2 gebruikt.

In sommige gevallen kunt u goede resultaten behalen door HTML met ingesloten stijl te exporteren en vervolgens uw webbrowser te gebruiken om af te drukken naar PDF. U krijgt niet alle exportfuncties van Marked, maar doorgaans wel een PDF met werkende interne links. Het is voorlopig een afweging.

[Table of contents](#toc)

## Relatieve paden in opgenomen bestanden [relative_paths_in_included_files]

Bestanden die zijn opgenomen met de [include syntax][include] van Marked, evenals [Scrivener files][scriv], kunnen relatieve paden gebruiken om naar andere bestanden te verwijzen. (_**Opmerking:** dit is niet van toepassing op bestanden die zijn opgenomen met de `/file` syntaxis van IA Writer of CSV-bestanden_). Vanaf recente versies (2.5.10+) zijn deze paden _relatief ten opzichte van het opgenomen bestand_, en niet het basisbestand.

Gegeven een bestands-/mapstructuur als deze:

- basisbestand.md
    - submap
        - opgenomen_bestand.md
    - afbeeldingen
        - afbeelding1.jpg

Als `included_file.md` via een relatief pad naar image1.jpg verwijst, moet het worden geschreven als `../images/image1.jpg`, _not_ `images/image1.jpg`. (`..` geeft de bovenliggende map aan) .

[include]: http://marked2app.com/help/Multi-File_Documents.html
[scriv]: http://marked2app.com/help/Scrivener_Support.html

[Table of contents](#toc)

## Hoe haal ik een verloren licentie op (directe versie) [how_do_i_retrieve_a_lost_license_direct_version]

Als u een licentie bent kwijtgeraakt die u voor Marked 2 via Paddle hebt gekocht, kunt u deze ophalen op [my.paddle.com](https://my.paddle.com/). Als u problemen ondervindt bij het inloggen, kunt u een zoekopdracht aanvragen via een privéverzoek op de [support site](http://support.markedapp.com).

[Table of contents](#toc)

## Problemen met in-app-aankopen (Foutdomein=Paddle-code=0 "(null)") [in-app_purchase_issues_error_domainpaddle_code0_null]

Paddle liet me onlangs weten dat IAP's kapot zijn en dat ze niet van plan zijn deze te repareren omdat niet genoeg ontwikkelaars ze hebben geïmplementeerd. (Wat voor mij net zo frustrerend is als voor jou.) Het echt frustrerende is dat ze niet zijn gestopt met het toestaan ​​van betalingen, dus ik moet aankopen handmatig terugbetalen totdat er iets wordt gedaan aan de manier waarop met de licenties wordt omgegaan. Er wordt verondersteld dat er in de komende weken een nieuw systeem zal worden uitgerold, dus als je bereid bent te wachten, zal ik er alles aan doen om ervoor te zorgen dat alle huidige aankopen van de Spelling/Grammatica IAP worden gehonoreerd via welk systeem dan ook.

Als u liever een terugbetaling heeft, kunt u mij <a href="mailto:me@bretterpstra.com">rechtstreeks een e-mail sturen</a> met het e-mailaccount dat is gebruikt voor de licentie of de transactie-ID uit de kassabon.

**Update:** Paddle heeft de nieuwe IAP-oplossing officieel aangekondigd en zal worden geïmplementeerd zodra deze publiekelijk beschikbaar is. Huidige licenties voor in-app-aankoop (Spelling/Grammatica) worden automatisch gemigreerd en er wordt een nieuwe couponcode verstrekt. Dit zou binnenkort moeten gebeuren.

[Table of contents](#toc)

## Omheinde codeblokken binnen ingesprongen codeblokken [fenced_code_blocks_inside_indented_code_blocks]

In tamelijk zeldzame omstandigheden wilt u misschien de hekken van een omheind codeblok laten zien. Normaal gesproken zou dit kunnen worden bereikt in Markdown door de afgeschermde code te laten inspringen, waardoor een ingesprongen "letterlijk" blok wordt geforceerd dat het afgeschermde codeblok bevat, dat vervolgens onverwerkt zou blijven. Marked verwerkt afgeschermde code op een andere manier (als onderdeel van de mogelijkheid om met meerdere syntaxisopties te werken), dus om dit te bereiken moet je een dubbele afrastering gebruiken. Omdat u een willekeurig aantal backticks of tildes kunt gebruiken om een ​​codeblok af te schermen (zolang de openings- en sluitingstelling overeenkomen, kunt u gewoon twee hekken van verschillende lengte gebruiken. Bijvoorbeeld

    `````
    ```
    Actual fenced code
    ```
    `````

[Table of contents](#toc)

