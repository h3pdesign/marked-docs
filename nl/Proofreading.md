# <%= @title %>

Ga naar de proefleesmodus vanuit het tandwielmenu. Dit is een experimentele functie die voornamelijk is ontworpen voor redacteuren die tekst van anderen ontvangen en commentaar moeten geven en feedback moeten geven.

De proefleesmodus bevriest documentupdates, waardoor wordt voorkomen dat annotaties en notities verloren gaan wanneer het document wordt vernieuwd. Er verschijnt een rode indicator in de bovenste balk om u eraan te herinneren dat de proefleesmodus actief is.

Toetsenbordnavigatie, bladwijzers en trefwoordmarkering zijn allemaal mogelijk tijdens het proeflezen.

## Annotaties

Als u in de proefleesmodus tekst in het document selecteert, wordt er een pop-up gegenereerd waarin u uit verschillende typen markering kunt kiezen. Klik op het type markering dat u aan de tekst wilt toevoegen, of annuleer door op de knop 'Annuleren' te klikken of door buiten de pop-up te klikken.

## Opmerkingen

![Annotations][1]

[1]: images/Annotating.jpg class=center

Zodra een hoogtepunt is toegevoegd, kunt u er korte notities aan toevoegen door op de hoogtepunt te klikken. De pop-up bevat nu een tekstveld waarin u eventuele opmerkingen kunt invoeren die relevant zijn voor de gemarkeerde tekst. Notities kunnen worden verwijderd en bewerkt door op een markering te klikken die al een notitie bevat.

Notities worden **alleen** geëxporteerd bij het opslaan in HTML. Hoogtepunten blijven in de meeste exportformaten behouden, inclusief RTF en PDF.

## Spellingcontrole

In de proefleesmodus heeft u toegang tot de systeembrede spellingcontrole via het tandwielmenu: {% appmenu {{gear}}, Proofing, Highlight All Spelling Errors %}. Bij grote documenten zal dit langzaam zijn en er zal een waarschuwing worden weergegeven die u waarschuwt als het proces meer dan 30 seconden duurt. Omdat de spellingcontrole niet werkt in de webvoorbeeld van Marked, is er een "hack" geïmplementeerd om dit te laten werken, en deze is niet snel.

Zodra de spellingcontrole is uitgevoerd, kunt u het venster Spellingsschattingen openen om grammaticacontrole in te schakelen en suggesties voor het oplossen van fouten te bekijken. Marked *kan* deze niet bewerken, u moet teruggaan naar uw originele document om gebruik te kunnen maken van de resultaten.

*Snelkoppelingen:* {% kbd ctrl opt cmd S %} voert de spellingcontrole uit. {% kbd ctrl opt cmd N %} gaat naar de volgende fout in het document, en {% kbd ctrl opt cmd G %} toont het gissingenpaneel.