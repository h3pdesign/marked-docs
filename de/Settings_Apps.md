# <%= @title %>

Optionen im {% prefspane Apps %}:

(Siehe [Additional App Support](Additional_Application_Support.html))

![Settings: Apps][1]

[1]: images/screenshots/preferences-Apps.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Allgemeine Einstellungen

Texteditor
: Wählen Sie einen Texteditor aus, um das aktuelle Dokument zu empfangen, wenn Sie {% kbd cmd E %} eingeben.

Bearbeiten Sie neue Dateien automatisch
: Wenn Sie den Befehl „Neue Datei“ verwenden, öffnet diese Option automatisch die erstellte Datei in dem von Ihnen gewählten externen Editor.

Links zu Textdateien sollten geöffnet werden in:
: Bestimmen Sie das Verhalten von Marked, wenn ein in einem Vorschaufenster angeklickter Link zu einer lokalen Textdatei führt.

Bildeditor
: Wählen Sie eine Anwendung aus, die geöffnet werden soll, wenn mit der rechten Maustaste auf ein lokales Bild geklickt und „Bild bearbeiten“ ausgewählt wird.

Bildanmerkungs-/Markup-Editor
: Wählen Sie eine Anwendung aus, die geöffnet werden soll, wenn mit der rechten Maustaste auf ein lokales Bild geklickt und „Bild mit Anmerkungen versehen“ ausgewählt wird.

Wenn kein Editor ausgewählt ist, zeigt Marked beim Bearbeiten oder Kommentieren ein Menü der installierten Anwendungen an. Das Menü enthält gängige Markdown-, Bild- und Anmerkungstools, die Sie auf Ihrem Mac finden, eine Option **Andere…** zum Auswählen einer beliebigen App aus `/Applications` und **Immer diese App verwenden** (standardmäßig aktiviert), um Ihre Auswahl als Standard zu speichern. Verwenden Sie die Schaltfläche „Löschen“ (Kreis mit einem X) neben jedem Auswahlsteuerelement in {% prefspane Apps %}, um eine Auswahl zu entfernen und zur Auswahl zurückzukehren.

### Anwendungsspezifische Einstellungen

Kommentare und Anmerkungen standardmäßig anzeigen
: Wenn diese Option aktiviert ist, werden in Scrivener-, Fountain-, Word- und CriticMarkup-Dokumenten erstellte Anmerkungen in der Vorschau hervorgehoben angezeigt. Deaktivieren Sie das Kontrollkästchen, um es vollständig auszublenden. Diese können auch beim Lesen eines Dokuments über das Menü {% appmenu Gear, Proofing ({{ctrl}}{{cmd}}C)%} umgeschaltet werden.
: Wenn Kommentare aktiviert sind, werden Kommentare und Fußnoten in einer Seitenleiste angezeigt. Wenn Sie mit der Maus über einen Kommentar fahren, wird auf die Stelle im Dokument hingewiesen, an der er vorkommt.

#### DocC

[(Info on DocC Support)](DocC_Support.html)

DocC-Bildverweise auflösen
: Lösen Sie in einem `.docc` Dokumentationskatalog erweiterungslose `![](ImageName)` Verweise auf Bilder im Katalogordner `Resources` auf, einschließlich der Varianten `~dark` und `@2x`.

Lösen Sie dunkle und @2x-Bildvarianten auf
: Erkennen Sie bei lokalen Bildern mit einer Dateierweiterung (`images/icon.png`) die Begleitdateien `~dark` und `@2x` im selben Ordner und geben Sie ein entsprechendes `<picture>`-Markup aus. Funktioniert in jedem Markdown- oder HTML-Dokument, nicht nur in DocC-Katalogen. Siehe [Image Variants](Image_Variants.html).

#### Hookmark

Hook://-URLs in Bildern und Links auflösen
: Marked kann von Hookmark erstellte URLs lesen und sie in ihren Pfad auf der Festplatte auflösen.

#### Leanpub/GitBook

Aktivieren Sie die Leanpub-Unterstützung
: Interpretieren Sie Dateien mit dem Namen `Book.txt` als Indexdateien und verarbeiten Sie die spezielle Leanpub-Syntax.

Aktivieren Sie die GitBook-Unterstützung
: Interpretieren Sie Dateien mit dem Namen `SUMMARY.md` als Indexdateien für die GitBook-Dokumentation.

#### Markdownifier

Verwenden Sie Inline-Links
: Markdown-Dokumente, die mit dem Markdownifier erstellt wurden, verwenden Inline- statt Referenzlinks.

#### MarsBearbeiten

Beitragstitel als Markdown-Header (h1) einfügen
: Verwenden Sie den Titel des ausgewählten Beitrags als Markdown-Header.

Metadaten als Tabelle anzeigen
: Wenn aktiviert, werden Metadaten wie Kategorien und Titel als Markdown-Tabelle in der Vorschau angezeigt.

#### Ordner

Sehen Sie sich diese Erweiterungen nur in der Vorschau an
: Beim Öffnen eines Ordners sucht Marked nach dem zuletzt geänderten Dokument und verwendet standardmäßig Erweiterungen wie `md`, `mmd` und `html`. Die Liste hier überschreibt die Standardeinstellung.

#### Scrivener

[(Info on Scrivener Support)](Scrivener_Support.html)

Fügen Sie Dokumenttitel als Markdown-Header ein
: Analysieren Sie den Titel von Seiten und verschachtelten Seiten, um hierarchische Markdown-Header zu erstellen.

Fügen Sie Kompilierungsmetadaten (Titel, Autor) hinzu, wenn diese fehlen
: Wenn ein Scrivener-Projekt kein `metadata`-Dokument oder keinen vorhandenen MultiMarkdown-Header hat, stellen Sie Titel und Autor aus den Kompilierungseinstellungen des Projekts voran (`Settings/compile.xml`).

.scriv-Dateien in Scrivener öffnen, wenn sie in Marked geöffnet werden
: Wenn ein Scrivener-Dokument in Marked geöffnet wird, wird es automatisch auch in Scrivener geöffnet.

#### Wort

Änderungsverfolgung konvertieren <-> CriticMarkup
: Wenn aktiviert, wird die Änderungsverfolgung in Word-Dokumenten beim Import in CriticMarkup konvertiert, und CriticMarkup wird beim Exportieren von DOCX-Dateien in Word-Änderungsverfolgung konvertiert.

#### Mind Maps/Outlines {#MindMapsOutlines}

Als Mermaid-Mindmaps einbetten
: Jedes Kontrollkästchen steuert ein enthaltenes Format. Wenn **aktiviert**, wird die enthaltene Datei in ein Mermaid-Mindmap-Diagramm (Aufgeräumtes-Tree-Layout) konvertiert. Wenn **aus**, verwendet Marked die Alternative für dieses Format.
: **Mindmaps** – iThoughts X (.itmz), MindManager (.mmap), FreeMind (.mm). Wenn aktiviert: Meerjungfrau-Mindmap. Wenn deaktiviert: iThoughts bettet sein Vorschaubild ein; MindManager und FreeMind konvertieren in verschachtelte Markdown-Listen.
: **OPML Dateien** (.opml). Wenn aktiviert: Meerjungfrau-Mindmap. Wenn deaktiviert: verschachtelte Markdown-Liste.
: **OmniOutliner-Umrisse** (.ooutline). Wenn aktiviert: Meerjungfrau-Mindmap. Wenn deaktiviert: verschachtelte Markdown-Liste (oder ggf. Checkliste).
: **Fahrradumrisse**. Wenn aktiviert: Meerjungfrau-Mindmap. Wenn deaktiviert: verschachtelte Markdown-Liste.