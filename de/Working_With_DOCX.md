# <%= @title %>

Marked bietet umfassende Unterstützung für die Arbeit mit Microsoft Word-Dateien. Der typische Arbeitsablauf ist **zuerst Vorschau, dann DOCX exportieren**: Öffnen oder sehen Sie sich Ihren Markdown in Marked an, verfeinern Sie Stile und Korrekturlesen in der Live-Vorschau und exportieren Sie ihn dann nach Word, wenn das Dokument fertig ist.

## Öffnen von DOCX-Dateien

Marked kann eine DOCX-Datei lesen und in eine saubere Datei konvertieren
Markdown. Gültige Stilelemente wie Überschriften und Listen werden verwendet
in ihr Markdown-Äquivalent umgewandelt werden.

Änderungsverfolgung und Kommentare werden konvertiert
CriticMarkup. Highlights werden in `<mark>`-Tags umgewandelt.
ggf. mit Farben.

## Exportieren von DOCX-Dateien

Verwenden Sie die Export-Palette, um eine DOCX-Datei aus Ihrem zu generieren
Markdown. Im Speicherdialog können Sie eine integrierte Datei angeben
Stile --- Dieser Stil kann in Word ganz einfach geändert werden
Öffnen Sie die Themenauswahl und wählen Sie ein neues Thema aus.

### Kopf- und Fußzeilen

Wenn Sie Kopf- und Fußzeilen in {% prefspane Export %} konfigurieren, sind diese im exportierten DOCX enthalten. Standardplatzhalter wie `%title`, `%date`, `%page` und `%total` werden beim Export ersetzt. `%logo` und `%image` betten das Logo aus den Kopf-/Fußzeileneinstellungen ein. `%md_*` Metadatenvariablen werden aus den MultiMarkdown-Metadaten des Dokuments aufgelöst. `%h1`--`%h6` werden zu Word-**STYLEREF**-Feldern, die an die exportierten Überschriftenstile gebunden sind; Word füllt sie aus, wenn Sie das Dokument öffnen. Unter [Exporting](Exporting.html#headers-and-footers) finden Sie die vollständige Variablenliste und die Unterschiede zwischen dem Verhalten von DOCX und print/PDF.

## Änderungsverfolgung

Die CriticMarkup-Syntax in einem Markdown-Dokument wird konvertiert
zur Word-Änderungsverfolgung beim Export nach DOCX. Kommentare
Folgende Einfügungen, Löschungen und Ersetzungen werden durchgeführt
werden bei der Änderungsverfolgung in der rechten Spalte in Word angezeigt
ist aktiviert.

Beim Importieren einer DOCX-Datei in Marked erfolgt die Änderungsverfolgung
in die Tags CriticMarkup und `<mark>` konvertiert werden
angemessen.

## Mathe

Die im Dokument angezeigten MathJax- und Katex-Gleichungen werden zur Anzeige in Word in MathML konvertiert. Diese Konvertierung ist nicht perfekt, stellt aber in den meisten Fällen einen gültigen Mathematikblock im Word-Dokument dar. Dies gilt nur für den Export --- Matheblöcke in Word-Dokumenten werden beim Import nicht konvertiert.

## Custom Exportstile hinzufügen

Sie können Ihre eigenen Exportstile hinzufügen, indem Sie eine Vorlage und eine Datei „styles.xml“ in `~/Library/Application Support/Marked/Custom Word Styles/` einfügen. Um diese zu erstellen:

1. Öffnen Sie eine mit Marked generierte DOCX-Datei in Word
2. Bearbeiten Sie dort im Stileditor die Stile für jedes Element und wählen Sie für jedes Element „Zur Vorlage hinzufügen“ aus.
3. Speichern Sie die Datei DOCX.
4. Erstellen Sie eine Vorlage, indem Sie in der oberen Leiste auf **Design** gehen und im Dropdown-Menü *Vorlage* links auf **Aktuelle Vorlage speichern** klicken. Benennen Sie es so, wie es im Stilmenü Marked angezeigt werden soll, und speichern Sie es unter `~/Library/Application Support/Marked/Custom Word Styles/STYLENAME.thmx`, wobei `STYLENAME` der Name Ihres Stils ist.
5. Gehen Sie zum Finder und suchen Sie die Datei DOCX, die Sie aus Word gespeichert haben. Duplizieren Sie es, benennen Sie die Kopie in `FILENAME.zip` um und doppelklicken Sie zum Entpacken darauf.
6. Im entpackten Dokument sehen Sie einen Ordner „word“, der eine Datei „styles.xml“ enthält. Kopieren Sie die Datei „styles.xml“ in denselben Ordner wie oben und nennen Sie sie `STYLENAME.xml` (wobei `STYLENAME` der Name Ihres Stils ist). Die Dateien `.thmx` und `.xml` sollten denselben Basisnamen haben (nur unterschiedliche Erweiterungen).

Wenn Sie das nächste Mal einen DOCX aus Marked exportieren, wird Ihr neuer Stil im Menü „Stil“ des Dialogfelds „Speichern“ angezeigt.