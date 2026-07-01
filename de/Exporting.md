# <%= @title %>

Verwandeln Sie Ihren Markdown in ein fertiges Dokument.

## Export nach Vorschau

Die Vorschau von Marked ist die Grundlage für den Export – was Sie im Vorschaufenster sehen, ist das, was Sie in PDF, DOCX, EPUB und anderen Formaten erhalten (modulo-exportspezifische Einstellungen wie Ränder, Kopfzeilen und Paginierung). Richten Sie Ihren Stil ein, lesen Sie ihn zunächst in der Vorschau Korrektur und exportieren Sie ihn dann, wenn das Dokument fertig ist. Den vollständigen Vorschau-Workflow finden Sie unter [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html).

## Das Export-Panel [Schublade]

![Export Panel][export-panel]

Das **Export-Panel** ist ein tastaturgesteuertes Panel im Spotlight-Stil, das schnellen Zugriff auf alle Exportoptionen bietet. Öffnen Sie es, indem Sie auf das Exportsymbol in der Statusleiste klicken oder {% kbd shift cmd e %} drücken.

![Export Button][expbut]

Mit dem Exportbereich können Sie Ihr Dokument als HTML, einseitiges PDF, paginiertes PDF, RTF-Paket oder als Microsoft Word DOC- oder DOCX-Datei speichern. Sie können die Datei auch in einer neuen Markdown-Datei (Marked-spezifische Funktionen werden gerendert und deren Ergebnisse einbezogen), einem offenen Dokument (ODT) oder als OPML zur Verwendung in anderen Anwendungen speichern.

## Kopieren HTML

Verwenden Sie die Funktion „HTML kopieren“, um den HTML-Quellcode für Ihre Vorschau problemlos in Ihre Zwischenablage zu kopieren. Sie können es im Zahnradmenü auswählen oder einfach {% kbd shift cmd C %} drücken. Der kopierte HTML ist ein Snippet, das in einen Blog, ein Forum oder ein HTML-Dokument eingefügt werden kann.

Sie müssen sich zum Kopieren nicht in der Quellansicht befinden. Geben Sie bei fokussierter Vorschau (klicken Sie darauf) einfach {% kbd shift cmd C %} ein und Sie sehen eine Popup-Meldung, die Sie darüber informiert, dass sich die Quelle in Ihrer Zwischenablage befindet.

## Speichern HTML

![][exporthtmlaccessory]



Mit dem Befehl „Speichern HTML“, der über das Zahnradmenü oder durch einfaches Eingeben von **{% kbd cmd S %}** zugänglich ist, können Sie ein vollständiges Dokument speichern, das zum Teilen oder Veröffentlichen bereit ist.

Sie können optional einen der Stile von Marked (oder einen Ihrer [custom styles][custom]) in Ihren Export einbeziehen, sodass Sie ein gebrauchsfertiges Dokument erhalten, in dem die erforderliche Formatierung bereits eingebettet ist.

Darüber hinaus können Sie alle im Dokument enthaltenen lokalen Bilder in den exportierten HTML einbetten, sodass Sie ein eigenständiges Dokument haben, das überall gehostet werden kann, ohne dass die Bilder mit verschoben werden müssen. Dies funktioniert nur mit Bildern, auf die auf Ihrem lokalen Laufwerk mit relativen oder absoluten Pfaden verwiesen wird. Vermeiden Sie die Verwendung von `file:///`-Pfaden, wenn Sie diese Funktion nutzen möchten.

## Exportieren Sie Markdown nach PDF auf dem Mac

Print/PDF Preview ({% kbd cmd P %}) öffnet einen Standard-Druckdialog. Jeder Vorschaustil in Marked verfügt über eigene begleitende Druckstile, die Hintergründe entfernen, Schriftgrößen ändern und Rahmen bereitstellen. Die Vorschau wird basierend auf dem aktuell ausgewählten Stil gedruckt.

Im Druckdialogfeld sind die Schaltflächen „PDF“ und „Vorschau“ hervorzuheben. PDF bietet Ihnen verschiedene Optionen für den Export nach PDF (basierend auf Ihren verfügbaren Anwendungen) und Preview exportiert eine PDF-Version direkt nach Preview.app, wo Sie sie speichern oder per E-Mail versenden können.

Das Drucken nach PDF mit dieser Methode umfasst die Paginierung. Beim Drucken auf Papier oder PDF können Seitenumbrüche manuell eingefügt werden, indem Sie [<!--MKPH1--> syntax][break] verwenden oder Optionen in {% prefspane Export %} festlegen, um Kopfzeilen der ersten und/oder zweiten Ebene als Abschnittstrenner zu verwenden.

Es besteht auch die Präferenz, horizontale Linien (`<hr>`) beim Drucken in Seitenumbrüche umzuwandeln. Dadurch wird die vom Tag erstellte Zeile durch einen Seitenumbruch ersetzt und aus der endgültigen Ausgabe entfernt. Die Vorschau bleibt von dieser Einstellung unberührt.

![Print Margins][printmargins]

Seitenränder können im {% prefspane Export %} festgelegt werden und wirken sich auf die gedruckte und paginierte PDF-Ausgabe aus.

Sie können die Randeinstellungen pro Dokument mit dem Metadatenschlüssel `Margins:` überschreiben. Werte werden als Punkte interpretiert; Einheitensuffixe wie `px`, `pt` und `em` werden ignoriert. Verwenden Sie zwei Zahlen für vertikale und horizontale Ränder (`10 20`) oder vier Zahlen für oben, rechts, unten und links (`10, 20, 10, 20` oder `10 20 10 20`). Metadatenränder überschreiben die {% prefspane Export %}-Einstellungen.

### Kopf- und Fußzeilen

Im {% prefspane Export %} definierte Kopf- und Fußzeilen werden oben und unten auf jeder gedruckten oder im paginierten PDF gespeicherten Seite und im DOCX-Export angezeigt. Sie können beliebigen Text oben links, oben in der Mitte, oben rechts, unten links, unten in der Mitte und unten rechts einfügen. Der zentrierte Text wird auf der Seite zentriert ausgerichtet. Die folgenden Variablen werden bei Verwendung in den Zeichenfolgen ersetzt:

%title = Dokumenttitel
    %date = Aktuelles Datum
    %time = Aktuelle Zeit
    %page = Aktuelle Seitenzahl
    %total = Gesamtseitenzahl
    %path = Dateisystempfad zum Dokument
    %filename = Nur der Dateiname des Dokuments
    %basename = Der Dateiname ohne Erweiterung
    %logo/%image = Ein Logo, das in den Kopf-/Fußzeileneinstellungen im Bildbereich festgelegt ist
    %%(text) = Text, der nur auf der ersten Seite gedruckt werden soll
    %h1/h2/h3/h4/h5/h6 = Abschnittstitel basierend auf Markdown-Überschriften
    %sep(X) = Text, der zwischen Abschnittstiteln platziert werden soll, wenn ein Unterabschnitt vorhanden ist

**Drucken und paginieren PDF** lösen `%h1`--`%h6` unter Verwendung der Paginierung von Marked auf, sodass auf jeder Seite die auf dieser Seite sichtbare Überschriftenhierarchie angezeigt wird. `%sep(X)` und `%md_*` Metadatenvariablen werden auch in der print/PDF-Ausgabe unterstützt.

**DOCX export** bettet `%logo`/`%image` in die Kopf- oder Fußzeile von Word ein (skaliert auf ca. 50 Pixel Höhe, passend zur Druckvorschau). Überschriftenplatzhalter werden zu Word-**STYLEREF**-Feldern, die auf die exportierten `Heading 1`--`Heading 6`-Stile verweisen. Word aktualisiert diese Felder, wenn das Dokument geöffnet wird, basierend auf dem eigenen Layout und den Seitenumbrüchen von Word – nicht der Vorschau-Paginierung von Marked. `%md_*` Metadatenvariablen werden beim Export einmal ersetzt, genau wie in print/PDF. `%sep(X)` wird nicht in DOCX Kopf-/Fußzeilen konvertiert.

`%title` verwendet alle in MultiMarkdown-Metadaten-Headern definierten „Titel:“-Informationen, andernfalls wird auf den Dateinamen ohne Dateierweiterung zurückgegriffen. Um einen Titel mithilfe von MMD-Metadaten zu definieren, fügen Sie Folgendes in die erste Zeile des Dokuments ein:

Titel: Der Titel Ihres Dokuments

Folgen Sie der Zeile mit einer Leerzeile (oder anderen Metadaten, die Sie definieren möchten, gefolgt von einer Leerzeile).

Sie können auch jeden MMD-Metadatenschlüssel als Variable verwenden, indem Sie ihm `%md_` voranstellen und die Wörter des Schlüssels als Zeichenfolge in Kleinbuchstaben kombinieren. Wenn Ihr Dokument beispielsweise oben einen Metadatenschlüssel hat, wie zum Beispiel:

Funky Monkey: Der verrückteste Affe

Wenn Sie dann `%md_funkymonkey` in einem Header-Feld verwenden, wird „The funkiest Monkey“ an der Stelle dieses Headers in das exportierte Dokument eingefügt. Bei Dokumenten, die diesen bestimmten Schlüssel nicht enthalten, bleibt das Feld leer, sodass Sie selektiv Kopfzeilen basierend auf Metadaten hinzufügen können.

Siehe [Date and Time Formats](Exporting.html#dateandtimeformats) für die Formatcodes `%date` und `%time`.

Über die Einstellung „Seitennummerierungsoffset“ kann eingestellt werden, bei welcher Nummer die Seitenzahlen beginnen. Wenn Sie beispielsweise ein Inhaltsverzeichnis auf der ersten Seite haben und die Nummerierung auf der zweiten Seite als Seite 1 beginnen soll, legen Sie den Offset auf -1 fest. Seite 2 ist nun Seite 1 in der Kopf-/Fußzeile (`%page`) und die Gesamtseitenzahl (`%total`) wird entsprechend angepasst.

Sie können auch eine Kopf-/Fußzeilenschriftart für ein bestimmtes Dokument angeben, indem Sie die Metadaten MMD oben in der Datei verwenden:

Schriftart für Kopfzeile: Mensch

Beachten Sie, dass bei Verwendung eines Schriftfamiliennamens eine Standardschriftart ausgewählt wird. Sie können eine Variation angeben, indem Sie den Systemnamen der Schriftart verwenden. Im Fall von Helvetica Neue Ultralight würden Sie beispielsweise „Header-Schriftart: HelveticaNeueUltralight“ verwenden.

Darüber hinaus können Sie mit den Metadaten eine Schriftgröße für die Kopf-/Fußzeile pro Dokument angeben:

Schriftgröße der Kopfzeile: 10

### Datums- und Uhrzeitformate

Die Felder **Datumsformat** und **Zeitformat** in {% prefspane Export %} steuern, wie `%date` und `%time` in Kopf- und Fußzeilen gerendert werden. Beide Felder verwenden Formatcodes im Strftime-Stil: ein `%` gefolgt von einem Buchstaben. Literaler Text (z. B. `-`, `:` oder Leerzeichen) wird unverändert kopiert.

**Beispiele**

%m-%d-%Y → 20.06.2026 (das Standarddatumsformat von Marked)
    %I:%M %p → 15:45 Uhr (das Standardzeitformat von Marked)
    %Y-%m-%d → 20.06.2026
    %B %d, %Y → 20. Juni 2026
    %a %H:%M → Fr 15:45

**Gemeinsame Formatcodes**

| Code | Beispiel | Beschreibung |
| ---- | ------- | ----------- |
| `%Y` | 2026 | Vierstellige Jahreszahl |
| `%y` | 26 | Zweistellige Jahreszahl |
| `%m` | 06 | Monat (01--12) |
| `%B` | Juni | Vollständiger Monatsname |
| `%b` | Juni | Abgekürzter Monatsname |
| `%d` | 20 | Tag des Monats (01--31) |
| `%e` | 20 | Tag des Monats (mit Leerzeichen aufgefüllt) |
| `%A` | Freitag | Vollständiger Wochentagsname |
| `%a` | Fr | Abgekürzter Wochentagsname |
| `%H` | 15 | Stunde, 24 Stunden (00--23) |
| `%I` | 03 | Stunde, 12 Stunden (01--12) |
| `%M` | 45 | Minute (00--59) |
| `%S` | 07 | Sekunde (00--59) |
| `%p` | PN | AM oder PM |
| `%x` | (Gebietsschema) | Bevorzugtes Datum des Gebietsschemas |
| `%X` | (Gebietsschema) | Bevorzugte Zeit des Gebietsschemas |
| `%c` | (Gebietsschema) | Bevorzugtes Datum und Uhrzeit des Gebietsschemas |

**Druck und paginiertes PDF** unterstützen den vollständigen oben festgelegten strftime-Stil sowie zusätzliche Codes wie `%j` (Tag des Jahres), `%U`/`%W` (Wochennummer), `%z` (Zeitzonenoffset) und `%Z` (Zeitzonenname). Eine vollständige Referenz finden Sie unter [Open Group strftime specification](https://pubs.opengroup.org/onlinepubs/9699919799/functions/strftime.html).

**DOCX export** unterstützt die in der Tabelle oben aufgeführten Codes. Weniger verbreitete Codes können ignoriert oder unverändert weitergegeben werden.

Verwenden Sie **Standardformate wiederherstellen** in {% prefspane Export %}, um auf `%m-%d-%Y` und `%I:%M %p` zurückzusetzen.

### Kopf- und Fußzeilen pro Dokument

Sie können Kopf- und Fußzeilen für jedes Dokument einzeln angeben, indem Sie die MultiMarkdown-Metadaten ganz oben im Dokument verwenden:

Kopfzeile links drucken: %title
    Header-Center drucken: %basename
    Kopfzeile rechts drucken: %date
    Fußzeile rechts drucken: %page/%total

Diese überschreiben alle Einstellungen in den Einstellungen. Beachten Sie, dass Sie HTML-Kommentare verwenden können, wenn Sie einen anderen Prozessor als MultiMarkdown verwenden und nicht möchten, dass Ihre Kopfzeilen im Dokument selbst angezeigt werden. Stellen Sie dabei sicher, dass Sie vor dem Schließen des Kommentars eine Leerzeile lassen:

<!--
    Kopfzeile links drucken: %title
    Header-Center drucken: %basename
    Kopfzeile rechts drucken: %date

->

## Speichern PDF

Diese Option speichert Ihre Vorschau direkt in einer PDF-Datei auf Ihrem Laufwerk. Ihr Dokument wird vollständig und ohne Seitenumbrüche gerendert. Um die Paginierung in Ihre Ausgabe einzubeziehen, verwenden Sie die Optionen Print/PDF im [Export Panel](#drawer).

## RTF Exportoptionen

Marked kann RTF-Daten (Rich Text Format) direkt in Ihre Zwischenablage exportieren. Wählen Sie einfach den Befehl „Rich Text kopieren“ aus dem Zahnradmenü.

Marked kann Ihre Datei auch als **RTFD**-Datei (Rich Text Format) speichern. Das RTFD-Format ist ein Bundle-Format, das eine RTF-Datei und alle im Dokument eingebetteten Bilder enthält.

## DOCX exportieren

Durch den Export als DOCX wird ein gültiges Microsoft Word-Dokument erstellt, dessen Elemente wie Überschriften, Kopf-/Fußzeilen, Hervorhebungen, Listen usw. alle gültigen Word-Stilen zugeordnet sind. Das bedeutet, dass Sie ganz einfach Ihr eigenes Design in Word anwenden können.

Weitere Informationen zum Word-Import und -Export finden Sie unter [Working with DOCX][DOCX].

## Markdown nach EPUB exportieren

Marked kann 100 % gültige, 100 % zugängliche EPUB-Dokumente exportieren. Wählen Sie den Exporttyp EPUB, geben Sie Metadaten wie Titel, Autor und Datum an und fügen Sie optional ein Titelbild hinzu. Die gespeicherte Datei ist in jedem EPUB-Viewer lesbar.

Die für den EPUB-Export erforderlichen Metadaten können in die Datei selbst eingefügt werden, unabhängig davon, ob es sich um ein Markdown-Dokument, eine Scrivener-Datei (einschließlich einer `metadata`-Seite) oder ein anderes Buchformat handelt. Die zu verwendenden Schlüssel sind:

```yaml
title: Your Document Title
author: Your Name
cover image: path/to/image.jpg
```

Der Titelbildschlüssel kann einen Pfad relativ zum Basisdokument oder einen absoluten Pfad enthalten. PNG- oder JPG-Dateien sind akzeptabel.

Wenn der Titel nicht festgelegt ist, wird standardmäßig der Dateiname des Originaldokuments verwendet. Wenn der Autor nicht festgelegt ist, wird standardmäßig der vollständige Name Ihres macOS-Benutzers verwendet.

Das Datum wird immer auf das aktuelle Datum gesetzt und kann derzeit nicht mit Metadaten geändert werden. Es kann jedoch zum Zeitpunkt des Speicherns geändert werden, solange die Formatierung (ISO) erhalten bleibt.

### Veröffentlichung auf Amazon Kindle (KDP)

EPUB ist ein offenes Format, das von vielen Lese-Apps und Stores (Apple Books, Kobo und anderen) verwendet wird, nicht nur von Kindle. Wenn Sie über [Kindle Direct Publishing (KDP)](https://kdp.amazon.com/) veröffentlichen, exportieren Sie EPUB aus Marked und laden Sie diese Datei auf KDP hoch. Amazon konvertiert es für Leser in sein eigenes Kindle-Lieferformat (KFX).

KDP akzeptiert mehrere Manuskriptformate, darunter EPUB und DOCX (die Marked auch exportieren kann). Die Anforderungen finden Sie unter [supported eBook formats](https://kdp.amazon.com/en_US/help/topic/G200634390) und [eBook manuscript formatting guide](https://kdp.amazon.com/en_US/help/topic/G200645680) von Amazon.

**MOBI ist nicht erforderlich.** KDP akzeptiert keine MOBI-Uploads mehr für neue Titel (einschließlich Bücher mit festem Layout, Stand März 2025). Marked exportiert MOBI nicht und Sie benötigen keine separate „Kindle“- oder Mobipocket-Datei für KDP. Wenn Sie die Layout-Tools von Amazon bevorzugen, können Sie ein Buch auch mit [Kindle Create](https://kdp.amazon.com/help/topic/G8UZKZD45RTQNNVT) vorbereiten, wodurch KPF-Dateien erstellt werden.

Vor dem Hochladen möchten Sie möglicherweise mit dem kostenlosen [Kindle Previewer](https://kdp.amazon.com/help/topic/G202131170) von Amazon überprüfen, wie Ihr EPUB auf Kindle-Geräten aussieht. Dabei handelt es sich um optionale Drittanbietersoftware von Amazon, die nicht Teil von Marked ist.

## Profile exportieren

Mit Exportprofilen können Sie verschiedene Sätze von Exporteinstellungen speichern und schnell zwischen ihnen wechseln. Dies ist besonders nützlich, wenn Sie regelmäßig Dokumente für verschiedene Zwecke exportieren – zum Beispiel ein Profil für druckfertige PDFs mit bestimmten Rändern und Kopfzeilen und ein anderes für webfertige HTML mit eingebetteten Stilen.

### Exportprofile verwenden

Wenn Sie Marked zum ersten Mal starten, wird automatisch ein „Standard“-Profil mit Ihren aktuellen Exporteinstellungen erstellt. Sie können Profile in den Exportdialogen (PDF Exportieren, HTML speichern usw.) mithilfe des Profil-Popup-Menüs oben im Dialog anzeigen und auswählen.

**Erstellen eines neuen Profils:**

1. Passen Sie Ihre Exporteinstellungen im {% prefspane Export %} oder in einem beliebigen Exportdialog an
2. Klicken Sie im Exportdialog auf das Profil-Popup-Menü und wählen Sie „Profil hinzufügen…“.
3. Geben Sie einen Namen für Ihr Profil ein (z. B. „Druckqualität“ oder „Webexport“).
4. Die aktuellen Einstellungen werden als dieses Profil gespeichert

**Profil laden:**

- Wählen Sie im Popup-Menü eines beliebigen Exportdialogs ein Profil aus
- Alle Exporteinstellungen werden sofort aktualisiert, um mit den gespeicherten Werten dieses Profils übereinzustimmen

**Änderungen an einem Profil speichern:**

- Nachdem Sie Änderungen an den Exporteinstellungen vorgenommen haben, erscheint neben dem Profil-Popup die Schaltfläche „Speichern“.
- Klicken Sie auf „Speichern“, um das aktuelle Profil mit Ihren Änderungen zu aktualisieren
- Die Schaltfläche ist nur aktiviert, wenn nicht gespeicherte Änderungen vorliegen

**Profile verwalten:**

- Wählen Sie „Profile verwalten…“ aus dem Profil-Popup-Menü, um das Profilverwaltungsfenster zu öffnen
- Von dort aus können Sie:
  - **Profile umbenennen**, indem Sie auf den Namen doppelklicken
  - **Duplizieren** Sie ein Profil, um darauf basierend ein neues zu erstellen
  - Profile **löschen** (das „Standard“-Profil kann nicht gelöscht werden)
  - Alle verfügbaren Profile in einer Liste anzeigen

### Was Exportprofile erfassen

Exportprofile speichern alle exportbezogenen Einstellungen, einschließlich:

- **PDF Einstellungen**: Seitengröße, Ränder, Kopf-/Fußzeilen, Schriftarten, Seitenumbrüche, Inhaltsverzeichnis
- **HTML Export**: Stileinbettung, Bildeinbettung, Syntaxhervorhebung, mathematische Darstellung
- **Markdown Verarbeitung**: Textumbruch, Linkformatierung, Prozessorregeln
- **CriticMarkup**: Exporttyp und Verarbeitungsoptionen
- **Syntaxhervorhebung**: Spracherkennung und Hervorhebungseinstellungen
- **Math Rendering**: MathJax/KaTeX Integration und Gleichungsnummerierung
- **Bildverarbeitung**: Einbettungsoptionen, Kopierverhalten, Pfadeinstellungen
- **Typografie**: Silbentrennung, Witwen/Waisen, Schriftgrößen
- **Exportverhalten**: Dateibenennungseinstellungen, Konfliktlösung

Profile funktionieren für alle Exporttypen: Markdown, HTML, Fortlaufend PDF, Paginiert PDF, EPUB, DOCX, ODT, TextBundle, RTF und OPML.

### Profilspeicherung

Profile werden in Ihrem Anwendungssupport-Ordner gespeichert unter:

~/Library/Application Support/Marked/ExportProfiles.plist

Das bedeutet, dass Ihre Profile auch dann bestehen bleiben, wenn Sie die App-Einstellungen zurücksetzen, und dass sie App-Updates überdauern. Sie können diese Datei sichern, um Ihre Profile über Installationen hinweg beizubehalten.

### Tipps zur Verwendung von Exportprofilen

- **Erstellen Sie Profile für gängige Arbeitsabläufe**: Wenn Sie regelmäßig für den Druck oder das Web exportieren, erstellen Sie für jeden separate Profile
- **Beschreibende Namen verwenden**: Profilnamen wie „Print – Letter“ oder „Web – Embedded Styles“ machen deutlich, wofür jedes Profil gedacht ist
- **Häufig speichern**: Die Schaltfläche „Speichern“ erscheint immer dann, wenn Sie Änderungen vorgenommen haben – klicken Sie darauf, um Ihre Anpassungen beizubehalten
- **Mit vorhandenen Profilen beginnen**: Verwenden Sie „Duplizieren“ im Verwaltungsfenster, um Variationen vorhandener Profile zu erstellen, anstatt bei Null anzufangen

[break]: Special_Syntax.html#pagebreaks
[DOCX]: Working_with_DOCX.html
[custom]: Custom_Styles.html
[dropbox]: http://dropbox.com
[expbut]: images/ExportButton.png @2x width=534px height=256px class=center
[export-panel]: images/export-panel-800.jpg @2x width=800 class=center
[exporthtmlaccessory]: images/SaveHTML.png @2x width=740px height=229px class=center
[printmargins]: images/PrintMargins.jpg @2x width=329px height=144px class=center