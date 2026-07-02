# <%= @title %>

Opties in de {% prefspane Processor %}:

![Settings: Processor][1]

[1]: images/screenshots/preferences-Processor.jpg @2x width=689px height=1031px class=preferencepane


### Verwerk Markdown met

Standaard Markdown-processor. De Kortingsprocessor heeft de voorkeur voor GitHub gebruikers, MultiMarkdown is ideaal voor schrijvers. Marked compenseert enkele verschillen tussen de syntaxis. Zie __Help->Markdown Referentie__ voor aanvullende informatie.

Custom Regels
: Gebruik de knop Custom Regels om de Custom Regeleditor te openen, zodat u verwerkingsopties en documenttransformaties kunt bepalen op basis van criteria. Zie de [Custom Processor documentation](Custom_Processor.html) voor details.

Nieuwe documenten gebruiken custom
: Selecteer preprocessor en/of processor om regelverwerking voor nieuwe documenten automatisch in te schakelen. Als u Custom regels gebruikt, wilt u deze waarschijnlijk allebei ingeschakeld hebben.

### HTML

Genereer ID's voor koppen
: Genereer header-ID's op basis van de inhoud van de h1-h6-tag.

Gebruik willekeurige voetnoot-ID's
: Genereer willekeurige voetnoot-ID's om conflicten te voorkomen wanneer meerdere documenten op één pagina worden weergegeven.

Verwerk Markdown binnen HTML
: Standaard wordt Markdown binnen de HTML tags meestal genegeerd. Deze optie dwingt Marked om door te gaan met de verwerking binnen blokelementen. Houd er rekening mee dat sommige markeringen problemen kunnen veroorzaken.


### Weergave

Bewaar regeleinden in alinea's
: Respecteer regeleinden in alineatekst en vervang deze door harde onderbrekingen in plaats van aaneenschakeling met de vorige regel.

Geef GitHub selectievakjes weer
: Render `- [ ]` en `- [x]` voor het maken van selectievakjes in lijsten. Selectievakjes worden weergegeven als voorbeeld, maar zijn niet functioneel binnen Marked.

\#Tekst is tag
: Hiermee kunnen hashtags (`#` onmiddellijk gevolgd door tekst zonder spatie) worden geïnterpreteerd als tags, niet als koppen. Deze functionaliteit is standaard voor Bear-gebruikers.
: __Stijltags__ zorgt ervoor dat tags worden weergegeven met "capsule"-opmaak om ze te onderscheiden van tekst. Als dit is ingeschakeld, kunnen tags worden weergegeven/verborgen met {% appmenu {{gear}}, Proofing, Show Comments %}.

![#Text is tag enabled][textistag]

[textistag]: images/textistag.jpg @2x width=896px height=274px class=center

Geef `==highlight==` en `~~delete~~` weer
: Als deze optie is ingeschakeld, wordt `==highlight==` tekst weergegeven als een HTML `<mark>` tag, die als een gele markering verschijnt, tenzij anders gewijzigd door een stijl. Bovendien wordt de syntaxis `~~delete~~` weergegeven met een tag `<del>`.

: Als __Render as CriticMarkup__ is ingeschakeld, wordt de syntaxis `==highlight==` en `~~delete~~` geconverteerd naar CriticMarkup, die vervolgens kan worden weergegeven in de originele, opmaak- en bewerkte weergaven.

Geef `~text~` weer als onderstrepingsteken
: Als deze optie is ingeschakeld, wordt `~text~` omgeven door enkele tildes onderstreept weergegeven. Dit is in strijd met de MultiMarkdown-syntaxis voor subscript en is standaard uitgeschakeld.