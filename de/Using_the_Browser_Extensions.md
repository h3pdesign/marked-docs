# <%= @title %>

Marked enthält Browsererweiterungen, mit denen Sie Seiten-URLs oder ausgewählte Inhalte direkt an Marked 3 senden können.

## Installieren

Von [https://markedapp.com/extensions](https://markedapp.com/extensions) herunterladen und installieren:

- Firefox / Zen
- Chrom / Brave / Edge
- Safari (im Paket enthalten)

## So funktioniert die Erweiterung

Wenn Sie auf eine Erweiterungsschaltfläche klicken, wird eine benutzerdefinierte URL geöffnet, die von Marked 3 unter Verwendung des Schemas `x-marked-3://markdownify` verarbeitet wird.

### `Markdownify URL`

Klicken Sie im Erweiterungs-Popup auf **`Markdownify URL`**, um die aktuelle Seiten-URL an Marked zu senden.

### `Markdownify Selection`

Klicken Sie im Erweiterungs-Popup auf **`Markdownify Selection`**, wenn Sie eine Auswahl auf der Seite haben.

Marked empfängt den HTML für die aktuelle Auswahl und wandelt ihn in Markdown um.

### Abschnitt auswählen (Blockauswahlmodus)

![][1]

[1]: images/marked-3-chrome-1.jpg width=1280px height=800px class=center

Klicken Sie auf **Abschnitt auswählen**, um in den „Abschnittsauswahlmodus“ zu gelangen:

- Bewegen Sie den Mauszeiger über die Seite, um Blockelemente hervorzuheben, die Sie auswählen können.
- Klicken Sie auf einen Block, um ihn sofort an Marked zu senden (einmaliges Senden).
- Klicken Sie bei gedrückter Befehlstaste auf Blöcke, um mehrere Blöcke auszuwählen (klicken Sie bei gedrückter Befehlstaste erneut, um einen Block zu entfernen).
- Drücken Sie die Eingabetaste, um die aktuell ausgewählten Blöcke zu senden.
- Drücken Sie Esc, um den Abschnittsauswahlmodus abzubrechen.

Während der Auswahl bietet das Popup auch Zoomsteuerungen, die Ihnen beim Klicken auf kleine oder dichte Abschnitte helfen:

![][2]

[2]: images/marked-3-chrome-2.jpg width=1280px height=800px class=center

- `-` zoomt heraus
- **An Höhe anpassen** zoomt so, dass die Seite der Höhe des Ansichtsfensters entspricht
- `+` zoomt hinein