# <%= @title %>

U kunt uw eigen JavaScript van CDN's toevoegen of door onbewerkte code te plakken.

## Een opmerking over Marked Dirigent

De eenvoudigste manier om aangepast JavaScript te implementeren dat varieert tussen documenttypen en locaties is met [Marked Conductor][conductor]. Hiermee kunt u een YAML-configuratie gebruiken om scripts toe te voegen met behulp van 'filters'. Bekijk de [Conductor page][conductor] voor details, en zie de [sample config][sample config] voor voorbeelden.

[conductor]: https://brettterpstra.com/projects/conductor/
[sample config]: https://github.com/ttscoff/conductor-config/

## JavaScript's toevoegen van CDN's [cdns]

![][1]

   [1]: images/screenshots/AdditionalJavascript.jpg @2x width=592px height=576px class=center

U kunt JavaScript CDN-URL's toevoegen in het venster "Aanvullende scripts", toegankelijk via {% prefspane Style %}. Voer CDN-URL's in, één per regel. Voeg geen `<script>` tags toe, alleen de URL:

```
https://cdn.jsdelivr.net/gh/user/repo@version/file
https://cdn.jsdelivr.net/npm/micromark-extension-gfm-strikethrough@2.1.0/lib/html.min.js
```

> Merk op dat jQuery al is opgenomen in het voorbeeldvenster.

Deze scripts worden aan het einde van het voorbeeld ingevoegd, vóór de documenttag. Zie [Including Raw JavaScript](#rawjs) als je een init-functie moet aanroepen of elke keer dat de preview dat doet, moet updaten. Om de DOM te inspecteren en fouten in deze scripts op te sporen in een live Marked preview, kunt u Safari's Web Inspector toevoegen zoals beschreven in [WebKit Inspector](Writing_Custom_CSS.html#webkitinspector).


### Inclusief Raw JavaScript [rawjs]

In het onderste tekstveld van het venster Aanvullende scripts kunt u onbewerkt JavaScript invoegen. Dit wordt opgenomen in een `<script></script>` paar, dus neem dat niet op in de invoer. Dit veld kan elke JavaScript-opdracht bevatten die u nodig hebt om een ​​meegeleverde bibliotheek te initialiseren, DOM-wijzigingen uit te voeren of wat u maar wilt doen in een WebKit-weergave. jQuery is al opgenomen voor het gemak van DOM-manipulatie.

Deze scripts worden alleen uitgevoerd als het venster voor het eerst wordt geladen. Wanneer de Preview wordt bijgewerkt, gebeurt dit door delen van de DOM te vervangen, dus scripts die moeten reageren op de bijgewerkte inhoud moeten dit doen met behulp van [Hooks](Embedding_Scripts.html#hooks).

Neem in het onbewerkte JavaScript-veld een aanroep als deze op:

```javascript
Marked.hooks.register('update', function() { myCustomFunction(); });
```