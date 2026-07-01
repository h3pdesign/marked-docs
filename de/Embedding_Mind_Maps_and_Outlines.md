# <%= @title %>

Mindmaps und Gliederungen können mit [Marked's include syntax][include] oder [IA Writer block syntax][ia] in Ihre Markdown-Vorschau eingebettet werden. Das Verhalten hängt vom Dateiformat und der Einstellung „Karten als Meerjungfrau-Diagramme einbetten“ in {% prefspane Apps %} unter *Mind Maps/Outlines* ab.

[include]: Multi-File_Documents.html
[ia]: Multi-File_Documents.html#ia-writer-block-syntax

## Unterstützte Formate

### iThoughts X (.itmz)

iThoughts-Mindmap-Dateien sind ZIP-Archive, die Kartendaten und ein optionales Vorschaubild enthalten.

### MindManager (.mmap)

MindManager-Dateien sind ZIP-Archive mit `Document.xml`. Entpackte MindManager-Pakete (ein Ordner mit `Document.xml`) und direkte Pfade zu `Document.xml` werden ebenfalls unterstützt.

### FreeMind (.mm)

FreeMind-Mindmap-Dateien verwenden die Erweiterung `.mm` und speichern Daten als XML. Marked erkennt das FreeMind-Format, indem es prüft, ob der Dateiinhalt mit `<map` beginnt; Wenn nicht (z. B. ein Code-Snippet), wird die Datei als einfacher Text eingefügt. FreeMind-Dateien werden für die Einbettung von Mermaid-Mindmaps unterstützt.

### OPML (.opml)

OPML (Outline Processor Markup Language) ist ein XML-Format für hierarchische Gliederungen, das häufig von Outline-Erstellern und Feed-Readern verwendet wird. iThoughts und andere Apps können nach OPML exportiert werden. Marked konvertiert enthaltene OPML-Dateien in Mermaid-Mindmap-Diagramme.

### Fahrrad (.bike)

Bike.app-Umrisse werden als proprietäre HTML-Dateien (`.bike`) gespeichert. Sie können eine `.bike`-Datei direkt in Marked öffnen: Das Dokument wird als Markdown mit dem Dateinamen (ohne Erweiterung) als Hauptüberschrift (H1), Überschriftenelementen der obersten Ebene als H2, verschachtelten Überschriften als fett gedruckten Listenelementen und Aufgaben als Kontrollkästchen im GitHub-Stil gerendert. Wenn eine `.bike`-Datei über die Include-Syntax eingebunden wird, steuert die Einstellung „Als Mermaid-Diagramm einbetten“ für Bike (in Apps → Mind Maps/Outlines), ob es sich um eine Mermaid-Mindmap (mit dem Dateinamen als Stammknoten) oder eine verschachtelte Markdown-Liste (kein H1) handelt.

## Karten als Meerjungfrauendiagramme einbetten

Wenn **aktiviert** (Standardeinstellung), konvertiert Marked enthaltene Mindmaps und Gliederungen in [Mermaid](https://mermaid.js.org/) Diagramme:

**iThoughts, MindManager, FreeMind, OPML & Bike** – Gerendert als Mermaid-Mindmap-Diagramme mit dem Tidy-Tree-Layout. Bei iThoughts und MindManager bleiben Forminformationen (rund, rechteckig, sechseckig usw.) erhalten, sofern verfügbar. FreeMind (`.mm`) und OPML verwenden dasselbe Mindmap-Format. Fahrradumrisse (`.bike`) verwenden den enthaltenen Dateinamen (ohne Erweiterung) als Mindmap-Stammknoten. Knotenbezeichnungen bestehen aus reinem Text (Links werden zu Linktext; Aufgaben werden als ☐ / ☑-Präfixe angezeigt). Mermaid ist standardmäßig in jeder Markdown-Vorschau enthalten.

**Einschränkung:** Das Einbetten von Mindmaps (Mermaid-Diagramme) funktioniert nicht mit dem Discount-Parser. Verwenden Sie MultiMarkdown, CommonMark (GFM) oder Kramdown für Mindmap-Vorschauen.

Wenn **deaktiviert**:

- **iThoughts** – Das integrierte Vorschaubild (`preview.png`) aus der .itmz-Datei ist als Base64-Bild eingebettet. Der Alternativtext des Bildes verwendet den Dateinamen.
- **MindManager** – Die Gliederung ist als verschachtelte Markdown-Liste eingebettet.
- **FreeMind** – Die Gliederung ist als verschachtelte Markdown-Liste eingebettet.
- **OPML** – Die Gliederung ist als verschachtelte Markdown-Liste eingebettet (keine Mindmap).
- **Fahrrad** – Die Gliederung ist als verschachtelte Markdown-Liste eingebettet (kein H1); Überschriftenelemente der obersten Ebene werden zu H2, verschachtelte Überschriften werden fett dargestellt und Aufgaben werden zu GitHub-Kontrollkästchen.

## Syntax einschließen

Verwenden Sie die gleiche Syntax wie für andere Datei-Includes:

<<[Pfad/zu/map.itmz]
	<<[Pfad/zu/map.mmap]
	<<[Pfad/zu/Karte.mm]
	<<[Pfad/zu/outline.opml]
	<<[path/to/outline.bike]

Oder mit iA Writer-Blocksyntax:

/path/to/map.itmz

Pfade können relativ zum Hauptdokument oder absolut sein (beginnend mit `/` oder `~`). Weitere Informationen finden Sie unter [Multi-File Documents](Multi-File_Documents.html).

## OPML Konvertierung

OPML-Dateien verwenden verschachtelte `<outline>`-Elemente mit einem `text`-Attribut. Wenn „Als Meerjungfrau-Diagramm einbetten“ aktiviert ist (siehe [Settings: Apps](Settings_Apps.html)), erzeugt die Konvertierung eine Meerjungfrau-Mindmap im gleichen Format wie iThoughts und MindManager:

- Untergeordnete Umrisse von `<body>` werden zur obersten Ebene (oder untergeordnete Elemente eines „Gliederungs“-Stamms, wenn es mehrere Elemente der obersten Ebene gibt).
- Verschachtelte Umrisse definieren die Hierarchie
- Fehlendes oder leeres `text` wird als `(unnamed)` angezeigt
- Text wird bereinigt; Sonderzeichen werden für Mermaid maskiert

## Fahrradumbau

Bike-`.bike`-Dateien sind HTML mit einem Stammelement `<ul>` und `<li>`. Elemente können `data-type="heading"` (oberste Ebene → H2 beim Öffnen oder im Listenmodus; verschachtelt → fett) oder `data-type="task"` (GitHub Kontrollkästchen; abgeschlossen, wenn `data-done` einen Zeitstempel hat oder `data-checked` / `data-completed` wahr ist). Inline-Formatierungen und Links im Knotentext werden in Markdown konvertiert. Beim Einbetten als Mermaid-Mindmap wird der Dateiname (ohne Erweiterung) als einzelner Stammknoten verwendet und die Beschriftungen sind als einfacher Text für die Mermaid-Mindmap-Syntax formatiert.