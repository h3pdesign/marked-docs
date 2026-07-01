# <%= @title %>

Optionen im {% prefspane Export %}:

(Weitere Informationen finden Sie unter [Exporting](Exporting.html))

![Settings: Export][1]

[1]: images/screenshots/preferences-Export.jpg @2x width=920px height=1031px class=preferencepane-scroll

### Profil exportieren

Profil exportieren
: Wählen Sie ein gespeichertes Profil aus dem Popup-Menü aus. Profile speichern einen vollständigen Satz Exporteinstellungen für den schnellen Wechsel zwischen Arbeitsabläufen (z. B. Drucken PDF vs. Web HTML). Siehe [Export Profiles](Exporting.html#export-profiles).

Neu
: Erstellen Sie ein neues Profil aus den aktuellen Einstellungen.

Verwalten
: Öffnen Sie den Profilmanager, um Profile umzubenennen, zu duplizieren oder zu löschen.

### Drucken/PDF

Deaktivieren Sie Links/Hervorhebungen beim Exportieren von PDF oder beim Drucken
: Entfernt beim Drucken die Formatierung (Unterstreichung und Farbe) von Links.

Fügen Sie die URL als Textanmerkung ein
: Beim Drucken oder Exportieren von PDF erscheint die URL für einen Link nach dem verlinkten Text.

Ersetzen Sie horizontale Linien durch Seitenumbrüche
: Horizontale Linien im Dokument in Seitenumbrüche umwandeln (dadurch werden Fußnoten zusätzlich auf eine neue Seite gezwungen).

Bilder beim Kopieren von HTML einbetten
: Wenn diese Option aktiviert ist, wird beim Kopieren von HTML in die Zwischenablage nach lokalen Bildern gesucht und diese mit Base64 codiert, um sie als Daten-URLs in den Quellcode aufzunehmen.

Hintergrundfarben und Bilder drucken
: Standardmäßig wird Marked mit einem weißen Hintergrund gedruckt/exportiert. Wenn Sie Hintergrundfarben und Bilder aus benutzerdefinierten Designs einbinden möchten, aktivieren Sie diese Option.

Vermeiden Sie verwaiste Schlagzeilen
: Diese Option verhindert, dass Überschriften für den nächsten Abschnitt am Ende einer Seite ohne nachfolgenden Inhalt angezeigt werden.

Erstes H1 ausschließen
: Ignorieren Sie die erste Überschrift der ersten Ebene im Dokument, wenn Sie H1-Zeichen als Seitenumbrüche verwenden.

Verwenden Sie die erste H1 als Ersatztitel
: Wenn Sie Apps wie Bear oder die Streaming-Vorschau verwenden, können Sie mit dieser Option den Dateinamen mit dem Inhalt des ersten H1 im Dokument überschreiben. Wenn Metadaten für „Titel“ angegeben werden, haben diese immer Vorrang.

Fügen Sie vorher Seitenumbrüche hinzu
: Verwenden Sie Überschriften der Ebenen 1/2 als Abschnittstrenner und beginnen Sie immer auf einer neuen Seite. Wählen Sie „Fußnoten“, um vor Fußnoten im Dokument immer einen Seitenumbruch einzufügen.

Seitenumbrüche in der Vorschau anzeigen
: Zeigt eine helle gestrichelte Linie an, an der Umbrüche mit der Syntax <!\--BREAK\--> oder durch Aktivieren der Optionen für automatische Umbrüche in den Exporteinstellungen eingefügt werden.

Custom Schriftgröße für Export/Druck
: Wenn festgelegt, wird der gesamte Text basierend auf der ausgewählten Punkteinstellung skaliert (standardmäßig eine Basis von 10 Punkten).

Ränder
: Definieren Sie die Druckränder (in Punkten angegeben) für oben, unten, links und rechts.

Inhaltsverzeichnis ausdrucken
: Automatisches Inhaltsverzeichnis in print/PDF einbinden.

Seitenumbruch danach
: Nach einem eingefügten Inhaltsverzeichnis automatisch zu einer neuen Seite wechseln.

Füllstandsmarkierungen im Inhaltsverzeichnis
: Verwenden Sie die Dropdown-Listen, um die Listenelementmarkierung für jede Einrückungsebene in einem Inhaltsverzeichnis festzulegen.

### Kopf- und Fußzeilen

Konfigurieren Sie Schriftart, Logo, Kopf-/Fußzeilenfelder, Datums- und Uhrzeitformate, Einbindung der ersten Seite, Seitennummerierungsversatz und Ränder. Zu den Feldplatzhaltern gehören `%title`, `%logo`, `%page`, `%total`, `%date`, `%time`, `%h1`, `%h2` und andere.

Platzhalterverweise und Beispiele finden Sie unter [Headers and Footers](Exporting.html#headersandfooters) in [Exporting](Exporting.html). Siehe [Date and Time Formats](Exporting.html#dateandtimeformats) für die Formatcodes `%date` und `%time`.

Auf der ersten Seite einschließen
: Wenn die Option für Kopf- und/oder Fußzeile deaktiviert ist, wird die erste Seite nicht im angegebenen Typ gedruckt.

Datumsformat
: Formatzeichenfolge im Strftime-Stil für `%date` in Kopf- und Fußzeilen. Siehe [Date and Time Formats](Exporting.html#dateandtimeformats).

Zeitformat
: Formatzeichenfolge im Strftime-Stil für `%time` in Kopf- und Fußzeilen. Siehe [Date and Time Formats](Exporting.html#dateandtimeformats).

Versatz der Seitennummerierung
: Wird verwendet, um anzupassen, bei welcher Nummer die Seitenzahlen beginnen. Wenn Sie beispielsweise auf der ersten Seite ein Inhaltsverzeichnis haben und die Nummerierung auf der zweiten Seite beginnen soll, legen Sie den Offset auf -1 fest. Seite 2 ist nun Seite 1 und die Gesamtseitenzahl wird entsprechend angepasst.

Grenze
: Drucken Sie eine horizontale Linie unter der Kopfzeile und/oder über der Fußzeile.

Standardformate wiederherstellen
: Formatzeichenfolgen für Datum und Uhrzeit auf die Standardeinstellungen von Marked zurücksetzen (`%m-%d-%Y` und `%I:%M %p`). Siehe [Date and Time Formats](Exporting.html#dateandtimeformats).