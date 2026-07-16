# <%= @title %>

De functie 'scrollen om te bewerken' in Marked houdt de verschillen bij tussen de laatste en de laatste update en probeert het punt te vinden waarop u uw meest recente wijzigingen hebt aangebracht. Marked houdt dit altijd bij en er verschijnt een kleine rode lijn in het voorbeeld om u de locatie van de eerste gedetecteerde wijziging te laten zien. In het gedragsvoorkeurenpaneel kunt u 'Scrollen naar eerste bewerking' inschakelen. Wanneer een voorbeeld wordt bijgewerkt, wordt de weergave voorzichtig naar die locatie gescrolld.

Als "Scroll naar eerste bewerking" is uitgeschakeld, kunt u in het voorbeeld nog steeds op elk gewenst moment op de "e"-toets drukken om naar het laatst opgeslagen bewerkingspunt te gaan.


### Opmerkingen over "Scroll om te bewerken" [notes-on-scroll-to-edit]

Dit is een functie die geweldig is als hij werkt, maar er zijn veel complicaties. Vooral de eerste paar keer dat het document wordt bijgewerkt, kan er wat schokkerigheid in de scroll optreden. Als uw wijzigingen zich allemaal binnen één heel groot element bevinden (bijvoorbeeld een te lange alinea), kan het alleen met de markering dichtbij komen. Op dezelfde manier, als u een of twee woorden aan het einde van het document toevoegt, wordt de wijzigingsmarkering in het bovenstaande element geplaatst totdat er voldoende inhoud is om in het nieuwe element te verankeren.