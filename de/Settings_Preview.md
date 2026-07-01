# <%= @title %>

Optionen im {% prefspane Preview %}:

![Settings: Preview][1]

[1]: images/screenshots/preferences-Preview.jpg @2x width=714px height=1031px class=preferencepane-scroll

### Vorschau des Verhaltens

Aktivieren Sie die Minikartennavigation
: Erstellt eine visuelle Karte des Dokuments, die angezeigt wird, wenn „0“ gedrückt wird. Beim Rendern großer Dokumente kann es zu kurzen Verzögerungen kommen.

Abschnitte mit Schlagzeilen werden ausgeblendet
: Durch Klicken auf ein Überschriftenelement wird der Abschnitt zwischen diesem und der nächsten Überschrift ausgeblendet.

Erfordert einen {% kbd cmd %}-Klick
: Wenn diese Option aktiviert ist, werden Schlagzeilen nur dann minimiert/erweitert, wenn bei gedrückter Befehlstaste darauf geklickt wird.

Synchronisieren Sie Vorschau und Quell-Scroll
: Wenn Ihr Editor dies unterstützt, scrollen Sie in der Vorschau so, dass sie mit der entsprechenden Stelle im Quelldokument übereinstimmt.

Geschwindigkeitsablesung mit Bildlaufposition synchronisieren
: Halten Sie das [Speed Reading](Speed_Reading.html)-Overlay an der Vorschau-Bildlaufposition ausgerichtet. Sie können dies auch über das Speed ​​Read-Overlay umschalten.

### Scrollen Sie zum Bearbeiten

Scrollen Sie zum Bearbeiten
: Beim Aktualisieren der Vorschau kann Marked den ersten Punkt ermitteln, an dem sich das Dokument geändert hat, und automatisch dorthin scrollen. Dadurch bleibt die Vorschau mit Ihrer aktuellen Position im Dokument, das Sie bearbeiten, synchronisiert. Die neueste Bearbeitungsmarkierung ist der erste Unterschied im Dokument seit der letzten Aktualisierung. Wenn Sie „Differenzreihenfolge umkehren“ aktivieren, wird stattdessen der letzte Unterschied im Dokument (von oben nach unten) als die letzte Bearbeitung betrachtet.

Markierung für die letzte Bearbeitung anzeigen
: An der Stelle der ersten erkannten Bearbeitung erscheint eine kleine rote Markierung. Schalten Sie dies aus, um es unsichtbar zu machen. (Erfordert **Zum Bearbeiten scrollen**.)

Alle Diff-Marker anzeigen
: Wenn dies aktiviert ist, werden alle Unterschiede zwischen der letzten Aktualisierung und dem aktuellen Inhalt im Randbereich hervorgehoben. Sie können durch die Änderungen navigieren und sie mit <kbd>e</kbd> (vorwärts) und {% kbd shift E %} (rückwärts) in die Mitte der Ansicht scrollen.

Umgekehrte Diff-Reihenfolge
: Wenn dies aktiviert ist, werden Unterschiede in umgekehrter Reihenfolge (von unten nach oben) markiert. Dies wirkt sich auf die Navigation aus, sodass <kbd>e</kbd> nach oben und {% kbd shift E %} nach unten navigiert. Die „letzte Bearbeitung“ wird zur letzten Änderung im Dokument.

### Zusätzliche Funktionen

Das Inhaltsverzeichnis verfolgt die Bildlaufposition
: Das Inhaltsverzeichnis hebt den aktuellen Abschnitt hervor.

Popup-Statistiken zur Textauswahl
: Zeigt ein Popup-Fenster zur Wortanzahl für den ausgewählten Text an, wenn eine Auswahl getroffen wird.

Link-Popover aktivieren
: Zeigt ein Popup-Menü an, wenn auf externe Links geklickt und vor der Freigabe gedrückt gehalten wird.

URLs bei Aktualisierung automatisch validieren
: URLs beim Laden und Aktualisieren von Dokumenten validieren. Zeigt Ergebnisse nur an, wenn Fehler vorliegen.
: Dies wird [link validation](Link_Validation.html) jedes Mal ausgeführt, wenn das Dokument aktualisiert wird (wenn Sie über eine große Anzahl von Links verfügen, kann dies ein langsamer Prozess sein und sollte vermieden werden).

### Wiki-Verlinkung

Konvertieren Sie [[Wiki-Links]]
: Aktivieren Sie die [wiki navigation](Wiki_Navigation.html)-Syntax von Marked für die `[[wiki link]]`-Syntax.

Standarderweiterung
: Die Dateinamenerweiterung Marked wird beim Auflösen von Wiki-Links verwendet, die keine Erweiterung enthalten (z. B. `md`).

### Aussehen

Dunkler Modus
: Zeigt alle Fenster im Modus „Hoher Kontrast“ mit dunklem Chrom und, falls verfügbar, der invertierten Version des aktuellen Stils an (gilt möglicherweise nicht für Custom-Stile).

Systemeinstellung anpassen
: Schalten Sie den Dunkelmodus automatisch um, wenn der macOS-Dunkelmodus systemweit aktiviert oder deaktiviert wird.

Vollständigen Pfad im Fenstertitel anzeigen
: Wenn aktiviert, zeigt Marked den vollständigen Pfad zum aktuellen Dokument im Fenstertitel an.