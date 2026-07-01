# <%= @title %>

Marked ermöglicht verschiedene Syntaxen zum Einfügen einer Datei in eine andere.

## Marked Syntax

Sie können externe Dateien in ein einzelnes Vorschaudokument einbinden, indem Sie die spezielle Syntax `<<[path/file]` am Anfang einer Zeile verwenden. Über und unter der Zeile sollten sich Leerzeilen befinden. Es wird davon ausgegangen, dass der Pfad relativ zum Hauptdokument ist, es sei denn, er beginnt mit einem Schrägstrich (`/`) oder einer Tilde (`~`). Schrägstrich (Stammverzeichnis) und Tilde (Heimverzeichnis) können verwendet werden, um absolute Pfade zu Dateien zu definieren. Wenn sich die externen Dateien im selben Ordner wie das Hauptdokument befinden, ist kein Pfad erforderlich. Geben Sie einfach den Dateinamen (Groß-/Kleinschreibung und einschließlich Erweiterung) in die eckigen Klammern ein.

Sie können die Metadaten-Header „Include Base“ oder „Transclude Base“ verwenden, um den Basisspeicherort für eingeschlossene Dateien zu ändern, z. B.:

Transclude-Basis: ~/Desktop

*Beachten Sie, dass Sie beim Anzeigen von Dokumenten mit enthaltenen Dateien „I“ (Umschalt-i) eingeben können, um zu sehen, welche enthaltene Datei sich im sichtbaren Bereich befindet. Wenn Sie die Eingabetaste drücken, während der Pfad der eingebundenen Datei angezeigt wird, wird die eingebundene Datei im Standardeditor geöffnet.*

Mit dieser Funktion können Sie große Dokumente/Bücher aus mehreren Dateien erstellen (z. B. eine Datei für jedes Kapitel) und dann die Dokumentreihenfolge in einer einzigen Indexdatei festlegen. Es spielt keine Rolle, wie die Dateien benannt sind oder wie die Ordner organisiert sind. Die Datei, die Sie in Marked öffnen, wird als Index betrachtet und die darin aufgeführten Dateien werden einbezogen. Ein Beispiel für eine Indexdatei für ein dreiteiliges Dokument:

Ordnerstruktur:

![][1]

   [1]: images/multifiledocumentstructure.jpg @2x width=316px height=163px class=center

Index.md:

# Dokumenttitel

## Abschnitt 1

<<[Abschnitte/Abschnitt1.md]

## Abschnitt 2

<<[Abschnitte/Abschnitt2.md]

## Abschnitt 3

<<[Abschnitte/Abschnitt3.md]

Beim Öffnen von Index.md in Marked wird der Inhalt mit allen drei darin enthaltenen Dateien angezeigt. Alle enthaltenen Dateien werden auf Änderungen überprüft. Im Gegensatz zum geöffneten Dokument in Marked hängt die enthaltene Dateiverfolgung von Spotlight ab, um Aktualisierungen zu erhalten, und muss in einem Spotlight-indizierten Ordner auf Ihrer Festplatte vorhanden sein.

Sie können mit [variations of this syntax](Special_Syntax.html#includingcode) auch Codefragmente und Roh-HTML oder Text einbinden.

Der endgültige HTML-Export eines Dokuments, das Includes enthält, enthält HTML-Kommentare, die den relativen Pfad der eingebundenen Datei am Anfang und am Ende des importierten Texts enthalten.

**Hinweis:** Je mehr Dateien in einem Dokument enthalten sind, desto langsamer ist die Gesamtkompilierungszeit der Vorschau. Marked versucht, den Prozess zu optimieren und zwischenzuspeichern, es kann jedoch mit zunehmender Dokumentgröße zu Verzögerungen beim Rendern kommen.

## MultiMarkdown Transclude-Syntax

Sie können auch die Syntax `<!--MKPH0-->` basierend auf der neueren MultiMarkdown-Spezifikation verwenden. Marked erkennt `Transclude Base: path` in MMD-Metadaten und verwendet es als Basis für die Dateitransklusion.

Transclude Base wird nur im übergeordneten Dokument erkannt, nicht in zusätzlich eingebundenen Dokumenten. Alle verschachtelten Includes müssen Pfade haben, die auf der ursprünglichen Transclude-Basis oder auf dem Speicherort des übergeordneten Dokuments basieren.

Die abgeschirmte Codesyntax, die MultiMarkdown zum Einschließen von Dateien ohne Verarbeitung bereitstellt, funktioniert in Marked nicht. Verwenden Sie dazu bitte die Syntax `<<(file)` (Codeblock) oder `<<{file}` (Rohformat).

## IA Writer Block-Syntax

Marked 2.5.11+ unterstützt die IA Writer [Content Block][ia]-Syntax. Dies ist eine Referenz, die mit einem Schrägstrich (`/`) in einer eigenen Zeile beginnt. Dabei kann es sich um ein Codebeispiel, ein Bild, eine Markdown-Datei oder eine CSV-Datei handeln. Alle werden basierend auf der Erweiterung der enthaltenen Datei entsprechend behandelt, und CSVs werden nach Möglichkeit [converted into Markdown][csv]-Tabellen sein.

In IA Writer werden eingebundene Dateien in den iCloud-Container gebracht und erfordern nicht immer „echte“ Pfade. In Marked sollte diese Syntax mit einem absoluten oder relativen Pfad verwendet werden, sofern die enthaltenen Dateien nicht bereits im selben Ordner wie die in der Vorschau angezeigte Datei vorhanden sind. Der erste Schrägstrich wird ignoriert. Wenn es sich also um einen absoluten Pfad handelt, beginnen Sie mit zwei Schrägstrichen.

Ein Codeausschnitt im selben Ordner wie das in der Vorschau angezeigte Dokument:

/snippet.h

Relativer Pfad zu einem Unterverzeichnis namens „images“:

/images/image.png „optionaler Titel“

Absoluter Pfad zum Ordner „Dokumente“:

//Benutzer/Benutzername/Dokumente/content.csv

[ia]: https://github.com/iainc/Markdown-Content-Blocks
[csv]: Creating_Tables_using_CSV_files.html

## Wie Gliederung, Mindmap und CSV-Includes konvertiert werden

Wenn Sie bestimmte Dateitypen mit der Blocksyntax `<<[path]` oder IA Writer einschließen, konvertiert Marked sie, anstatt rohe Dateiinhalte einzufügen. Das Verhalten von Gliederung und Mindmap hängt von der Dateierweiterung und Ihren [Settings: Apps → Mind Maps/Outlines][mindmaps]-Einstellungen ab. CSV/TSV-Dateien werden immer in Markdown-Tabellen konvertiert (siehe [Creating Tables using CSV files][csv]).

| Formatieren | Erweiterung | Wenn „Als Meerjungfrau einbetten“ **aktiviert** ist | Wenn **aus** |
|--------|------------|---------------------|--------------|
| **iThoughts X** | .itmz | Meerjungfrau-Mindmap-Diagramm (Tidy-Tree) | Vorschaubild aus der .itmz |
| **MindManager** | .mmap | Meerjungfrau-Mindmap-Diagramm | Verschachtelte Markdown-Liste |
| **FreeMind** | .mm | Meerjungfrau-Mindmap-Diagramm | Verschachtelte Markdown-Liste |
| **OPML** | .opml | Meerjungfrau-Mindmap-Diagramm | Verschachtelte Markdown-Liste |
| **OmniOutliner** | .ooutline | Meerjungfrau-Mindmap-Diagramm | Verschachtelte Markdown-Liste |
| **Fahrrad** | .bike | Meerjungfrau-Mindmap (Dateiname als Stammknoten) | Verschachtelte Markdown-Liste (kein Dokumenttitel) |
| **CSV / TSV** | .csv, .tsv | Markdown Tabelle ||
| **RTF / RTFD** | .rtf, .rtfd | Markdown über RTF-Konvertierung (siehe [RTF and RTFD Support](RTF_Support.html)) ||
| **PDF** | .pdf | Markdown über PDF-Konvertierung beim Öffnen als Hauptdokument (siehe [PDF Support](PDF_Support.html)) ||

Für jedes Umriss-/Mindmap-Format gibt es unter *Mindmaps/Umrisse* ein eigenes Kontrollkästchen (Mindmaps, OPML-Dateien, Fahrradumrisse, OmniOutliner-Umrisse). Beim Ausschalten eines Formats wird das „Aus“-Verhalten nur für diesen Typ verwendet. Siehe [Embedding Mind Maps and Outlines](Embedding_Mind_Maps_and_Outlines.html) für Formatdetails und [Settings: Apps][mindmaps] zum Ändern dieser Optionen. Einzelheiten zur CSV-Konvertierung finden Sie unter [Creating Tables using CSV files][csv].

[mindmaps]: Settings_Apps.html#MindMapsOutlines

## Buchformate

Marked unterstützt auch Indexdateien in Formaten wie [Leanpub][lp], [GitBook][gb] und mmd\_merge (MultiMarkdown). In Buchformat-Indizes enthaltene Dateien werden auf Änderungen überwacht und das Ergebnis ist eine vollständige Vorschau Ihres kompilierten Dokuments, genau wie im Beispiel „Index.md“ oben.

### Leanpub

Wenn Sie die Option im {% prefspane Apps %} unter Leanpub/GitBook-Unterstützung aktivieren, werden Dateien mit dem Namen „Book.txt“ automatisch als Leanpub-Indexdateien behandelt. Das ältere Format „frontmatter:“ wird ebenfalls erkannt.

[Leanpub documentation.][lpdocs]

Leanpub Book.txt-Beispiel:

Frontmatter:
    Danksagungen.txt
    Vorwort.txt
    Einführung.txt
    Hauptangelegenheit:
    Markdown.txt
    Beispielbücher.txt
    Einfügen von Images.txt


### mmd_merge

Für mmd\_merge erfordert Marked, dass die erste Zeile „#merge“ ist (ein spezieller Marked-Trigger für mmd\_merge, der als Kommentar behandelt und von anderen Prozessoren ignoriert wird).

[mmd_merge documentation.][mmdm]

mmd_merge-Beispiel:

#verschmelzen
    metadata.txt
    Kapitel-1.md
        Unterkapitel-1-1.md
        Unterkapitel-1-2.md
    Kapitel-2.md
        Unterkapitel-2-1.md
        Unterkapitel-2-2.md
    FAQ.md
    Danksagungen.md

### GitBook

Die GitBook-Formatierung verwendet eine Markdown-Liste, um die Struktur und das Inhaltsverzeichnis zu erstellen. Wenn die GitBook-Unterstützung im {% prefspane Apps %} unter Leanpub/GitBook-Unterstützung aktiviert ist, wird eine Datei mit dem Namen SUMMARY.md gelesen und automatisch in das mmd_merge-Format konvertiert, was eine vollständige Vorschau Ihres GitBook-Dokuments ermöglicht.

[GitBook documentation.][gbdocs]

GitBook SUMMARY.md-Beispiel:

# Zusammenfassung

* [Part I](part1/README.md)
        * [Writing is nice](part1/writing.md)
        * [GitBook is nice](part1/gitbook.md)
    * [Part II](part2/README.md)
        * [We love feedback](part2/feedback_please.md)
        * [Better tools for authors](part2/better_tools.md)

GitBook erlaubt die Verwendung von Ankern im Inhaltsverzeichnis von SUMMARY.md, aber Marked ignoriert diese und schließt das Basisdokument nur einmal ein.

[gbdocs]: https://github.com/GitbookIO/gitbook/blob/master/docs/pages.md
[lp]: http://leanpub.com/
[lpdocs]: https://leanpub.com/help/manual#leanpub-auto-how-to-set-the-books-structure
[mmdm]: http://fletcher.github.io/peg-multimarkdown/#howdoisplitamultimarkdowndocumentintoseveralparts
[gb]: https://www.gitbook.com/

## Funktionen zur Vorschau von Dokumenten mit mehreren Dateien

![Included File Boundaries][2]

   [2]: images/includeboundaries.png @2x width=859px height=239px class=center

Wenn Sie ein Dokument anzeigen, das enthaltene Dateien enthält, können Sie zwei Funktionen nutzen, um herauszufinden, welche Datei Sie gerade betrachten.

* **Tastatur:** Durch Drücken von {% kbd shift I %} wird kurz ein Popup mit dem Titel der Datei angezeigt, die derzeit an der Bildlaufposition der Vorschau sichtbar ist.
    * Durch Drücken von {% kbd Return %} im Anschluss an {% kbd I %} wird die angezeigte Datei mit Ihrem externen Editor bearbeitet.
* **Maus:** Wenn Sie im Zahnradmenü ({% kbd ctrl cmd B %}) die Option „Grenzen der enthaltenen Dateien anzeigen“ auswählen, wird auf der linken Seite der Vorschau ein farbiger Balken hinzugefügt, der segmentiert ist, um den Anfang und das Ende der enthaltenen Dateien anzuzeigen. Es werden auch verschachtelte Includes angezeigt. Wenn Sie mit der Maus über einen Abschnitt dieser Leiste fahren, wird der Name der Datei angezeigt, die er darstellt. Wenn Sie darauf klicken, wird diese Datei im von Ihnen gewählten Editor geöffnet.