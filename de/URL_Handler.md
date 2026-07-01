# <%= @title %>

Der URL-Handler von Marked bietet zusätzliche Skript- und Workflow-Funktionen. Sie können beispielsweise eine URL in die Notizen einer anderen Anwendung einfügen, die beim Klicken eine Datei in Marked öffnet. Sie können mehrere Aktionen ausführen, wie unten aufgeführt.

## Das URL-Schema

Das URL-Schema von Marked ist `x-marked` und wird mit Optionen wie `x-marked://open?file=/Users/username/Desktop/report.md` aufgerufen.

Sie können gezielt auf Marked 3 abzielen, indem Sie `x-marked-3` anstelle von `x-marked` verwenden. Die Methoden und Parameter sind genau die gleichen wie bei `x-marked`, aber nur Marked 3 reagiert auf `x-marked-3`.

## Aufruf über die Befehlszeile/Skripte

Der Aufruf des URL-Handlers über die Befehlszeile oder ein Skript kann mit dem macOS [<!--MKPH0--> command](http://brettterpstra.com/2014/08/06/shell-tricks-the-os-x-open-command/) erfolgen:

öffne 'x-marked://open?file=filename.md'
	öffne 'x-marked://refresh?file=filename.md'

### Ruft im Hintergrund an

Sie können den Befehl `open` mit dem Flag `-g` aufrufen, um das Ergebnis im Hintergrund auszuführen, ohne den Fokus zu wechseln. Um den Befehl im Hintergrund auszuführen und das Fenster nach oben zu heben, ohne den Fokus zu stehlen:

open -g 'x-marked://open?file=filename.md&raise=true'

## Optionale Parameter

### x-Erfolg

Jeder Befehl kann einen **x-success**-Abfrageparameter bereitstellen. Legen Sie dies auf eine URL fest, die nach der Ausführung des Befehls aufgerufen werden soll. Beispiel: `x-marked://open/?file=filename.md&x-success=ithoughts:`. Sie können auch eine Bundle-ID (z. B. `com.googlecode.iterm`) angeben, um eine Anwendung zu öffnen, die kein URL-Schema hat.

### erheben

Ein **raise**-Parameter kann mit jedem Befehl übergeben werden, der einen `file`-Parameter akzeptiert oder sich auf alle Fenster auswirkt. Nachdem die Aktion ausgeführt wurde, werden die betroffenen Fenster über alle anderen Fenster (alle Anwendungen) angehoben, bevor zurückgegeben oder ein Rückruf ausgeführt wird.

„x-marked://refresh?file=filename.md&raise=true“

### Speedread

Ein **speedread**-Parameter kann mit URL-Handler-Befehlen übergeben werden, die ein Vorschaudokument öffnen (`open`, `paste`, `preview` und `stream`). Stellen Sie `speedread=1` so ein, dass Speed ​​Read automatisch gestartet wird, sobald die Zielvorschau bereit ist.

Beispiele:

x-markiert://open?file=/Users/username/Desktop/report.md&speedread=1

x-marked://preview?text=Some%20text&speedread=1

x-markiert://paste?speedread=1

# Verfügbare Befehle

Die folgenden Befehle stehen dem URL-Handler `x-marked` zur Verfügung.

## addstyle

Fügen Sie Marked einen neuen benutzerdefinierten Stil hinzu.

##### Parameter:

**css**: URL-codierter CSS-Text zum Schreiben in einen benutzerdefinierten Stil. Erforderlich, es sei denn, es wird ein **Datei**-Parameter übergeben.

**Datei**: Vollständiger Pfad (POSIX) zu einer CSS-Datei, die zu Marked hinzugefügt werden soll. Erforderlich, es sei denn, es wird ein **CSS**-Parameter übergeben.

**Name**: Der Name des zu generierenden Stils.

Mit dem Parameter **css** wird dieser beim Schreiben auf die Festplatte sowohl als Dateiname mit dem Zusatz „.css“ als auch als Name des Menüelements verwendet. Es ist für den Parameter **css** erforderlich und für **file** optional (Dateiname wird so verwendet, als ob der Parameter name leer wäre).

x-markiert://addstyle?name=Mein+neuer+Stil&css=...

x-markiert://addstyle?file=/Users/myuser/Custom+Styles/Unicorn.css

Wenn Sie einen Namen mit dem Dateiparameter angeben, erhält das Menüelement diesen Namen anstelle des Dateinamens. Wenn Sie denselben Namen erneut mit einem anderen Pfad verwenden, wird das Menüelement mit dem neuen Pfad aktualisiert, anstatt ein zweites Element mit demselben Namen hinzuzufügen.

## Standardwerte

Benutzereinstellungen festlegen. Akzeptiert eine Liste von Schlüsseln und Werten als Abfrageparameter. Es werden nur vorhandene Schlüssel gesetzt. Wenn die Einstellungsänderung eine Aktualisierung erfordert, werden alle Fenster automatisch aktualisiert, es sei denn, `refresh=0` wird übergeben.

Verwenden Sie für boolesche Werte 1 für wahr und 0 für falsch.

##### Parameter:

**refresh** _(optional)_: Wenn auf 0 gesetzt, ist die automatische Aktualisierung geöffneter Vorschaufenster deaktiviert

* Standard: 1 (wahr)

##### Beispiel:

x-markiert://defaults?syntaxHighlight=1&includeMathJax=0

Die `defaults`-Methode ist hauptsächlich so konzipiert, dass der Entwickler Links zu esoterischen Funktionen hinzufügen kann, die andernfalls möglicherweise nicht in den Einstellungen verfügbar wären. Möglicherweise möchten Sie jedoch bei der Automatisierung einige Standardoptionen umschalten. Einige allgemeine Einstellungen, die Sie möglicherweise während der Automatisierung steuern möchten:

syntaxHighlight
: Syntaxhervorhebung aktivieren oder deaktivieren

includeMathJax
: Interne MathJax-Verarbeitung aktivieren oder deaktivieren

Prozessor
: auf `multimarkdown` oder `mmd` setzen, um den Prozessor auf MultiMarkdown zu ändern, auf `discount` oder `gfm`, um den Rabattprozessor zu verwenden

h1IsPageBreak, h1IsPageBreak, breakBeforeFootnotes
: Automatische Seitenumbrüche beim Export vor den Kopfzeilenebenen 1 und 2 sowie Fußnoten.


## Dingus

Öffnen Sie Markdown Dingus zum Testen verschiedener Markdown-Prozessoren.

x-markiert://dingus

##### Parameter:

**Prozessor** (optional): Geben Sie an, welcher Prozessor standardmäßig ausgewählt werden soll. Gültige Werte:

- `multimarkdown` – MultiMarkdown Prozessor
- `commonmark` – CommonMark (GFM)-Prozessor
- `discount` oder `discount (gfm)` – Rabattprozessor
- `kramdown` – Kramdown-Prozessor

Beispiele:

- `x-marked://dingus?processor=kramdown` – Öffnet mit ausgewähltem Kramdown
- `x-marked://dingus?processor=commonmark` – Öffnet mit ausgewähltem CommonMark (GFM).

*Hinweis:* Dadurch wird das Fenster Markdown Dingus geöffnet, in dem Sie verschiedene Markdown-Prozessoren (MultiMarkdown, CommonMark (GFM), Discount und Kramdown) nebeneinander testen und vergleichen können. Perfekt zum Experimentieren mit der Markdown-Syntax und zum Verständnis der Prozessorunterschiede.

## stylestealer / stehlen

Öffnen Sie das Style-Stealer-HUD. Nützlich, wenn Sie CSS von einer Live-Seite erfassen oder eine manuelle Inhaltsextraktionssitzung ausführen möchten, ohne sie über die Benutzeroberfläche zu starten.

Synonyme: x-marked://stylestealer … , x-marked://steal …

##### Parameter:

**URL** _(optional)_: Eine URL, die im Style Stealer-Fenster vorab ausgefüllt wird. Wenn es weggelassen wird, wird das HUD leer geöffnet.

Beispiele:

- `x-marked://stylestealer?url=https%3A%2F%2Fmarkedapp.com`
- `x-marked://steal/https:%2F%2Fexample.com`

## importurl / markdownify

Öffnen Sie das Fenster „URL importieren“ (Content Extractor), damit Sie die Markdownifier-Pipeline manuell ausführen können. Dadurch wird die Extraktion **nicht** automatisch durchgeführt – dies wird durch den folgenden Befehl `extract` erledigt.

Synonyme: x-marked://importurl … , x-marked://markdownify …

##### Parameter:

**URL** _(optional)_: Füllt das Feld „Import-URL“ vorab aus. Wenn Sie es weglassen, öffnet sich das Fenster mit einem leeren Feld, das darauf wartet, dass Sie einen Link einfügen.
**html** _(optional, nur Markdownify)_: Wenn es auf `x-marked://markdownify` bereitgestellt wird, sollte dies URL-codierter Rohtext HTML sein. Marked konvertiert HTML nach denselben Regeln wie die Zwischenablagevorschau in Markdown und öffnet es in einem transienten Dokument, als ob Sie diesen HTML in ein Zwischenablagevorschaufenster eingefügt hätten.

Beispiele:

- `x-marked://importurl?url=https%3A%2F%2Fexample.com%2Farticle`
- `x-marked://markdownify/https:%2F%2Fnews.ycombinator.com`

## Tun

Führen Sie einen JavaScript-Befehl in einem Dokumentfenster aus. Die gesamte JavaScript-API von Marked ist [documented here](https://markedapp.com/help/jsapi/).

##### Parameter:

**js** _(erforderlich)_: Abfragezeichenfolge, die einen JavaScript-Befehl enthält

* Akzeptiert Pfadparameter, die auf Dateinamen oder „alle“ verweisen.
* Mit / geteilte Pfade durchsuchen mehrere Dateien
* Teilweise Dateinamen ergeben die beste Übereinstimmung

x-markiert://do/filename1/filename2?js=...
		x-markiert://do/all?js=...

**Datei**: Abfrageparameter, der durch Kommas getrennte Pfade/Dateinamen enthält

x-markiert://do?file=filename1,filename2&js=...

Funktioniert im vordersten Fenster, wenn kein Dateiname angegeben ist (oder „all“ nicht übergeben wird)

## helfen

Öffnen Sie das interne Hilfesystem von Marked und geben Sie optional ein Thema an. Dies dient in erster Linie der internen Verwendung, ist aber über eine URL zugänglich. Eine URL zu einem bestimmten Abschnitt kann kopiert werden, indem Sie mit der rechten Maustaste auf das Lesezeichensymbol rechts neben einer Überschrift klicken und __Link kopieren__ auswählen. **Marked 3** In-App-Hilfe und Suche verwenden das Schema `x-marked-3` für diese Links, sodass macOS sie in Marked 3 öffnet, wenn Marked 2 ebenfalls installiert ist; Die folgenden Beispiele verwenden diese Form.

##### Dingus

Öffnen Sie Markdown Dingus zum Testen verschiedener Markdown-Prozessoren.

x-markiert://dingus

######## Parameter:

**Prozessor** (optional): Geben Sie an, welcher Prozessor standardmäßig ausgewählt werden soll. Gültige Werte:

- `multimarkdown` – MultiMarkdown Prozessor
- `commonmark` – CommonMark (GFM)-Prozessor
- `discount` oder `discount (gfm)` – Rabattprozessor
- `kramdown` – Kramdown-Prozessor

Beispiele:

- `x-marked://dingus?processor=kramdown` – Öffnet mit ausgewähltem Kramdown
- `x-marked://dingus?processor=commonmark` – Öffnet mit ausgewähltem CommonMark (GFM).

*Hinweis:* Dadurch wird das Fenster Markdown Dingus geöffnet, in dem Sie verschiedene Markdown-Prozessoren (MultiMarkdown, CommonMark (GFM), Discount und Kramdown) nebeneinander testen und vergleichen können. Perfekt zum Experimentieren mit der Markdown-Syntax und zum Verständnis der Prozessorunterschiede.

##### Parameter:

**Seite** _(optional)_: Der genaue Titel einer vorhandenen Seite, mit optionalem Anker-Hash

x-marked-3://help?page=Document_Statistics

Leerzeichen werden gemäß der Marked-Hilfedatei-Namenskonvention durch Unterstriche ersetzt. Bei der Angabe eines Ankers kann anstelle einer Raute (#) ein Doppelpunkt (:) verwendet werden.

Das Ziel kann allein durch den Pfad (ohne Abfragezeichenfolge) angegeben werden:

x-marked-3://help/Keyword_Highlighting:editingkeywords


## extrahieren

Extrahieren Sie Inhalte aus einer Web-URL und öffnen Sie sie als neues Dokument in Marked.

x-markiert://extract?url=https://example.com

##### Parameter:

**URL** _(erforderlich)_: Die Web-URL, aus der Inhalte extrahiert werden sollen. Muss mit `http://` oder `https://` beginnen

**Fenster** _(optional)_: Name für das Fenster

**id** _(optional)_: Namespace-ID

**base** _(optional)_: Basis-URL für relative Links

**raise** _(optional)_: Auf `true` setzen, um das Fenster nach dem Öffnen anzuheben

**manuell** _(optional)_: Auf `true` setzen, um das manuelle Extraktionsfenster von Style Stealer zu öffnen, anstatt eine automatische Extraktion durchzuführen.

– Wenn `manual=true`, Marked den Style Stealer öffnet, das URL-Feld vorab ausfüllt (falls vorhanden), unterdrückt jedes automatische Öffnen-Dialogfeld und ermöglicht Ihnen die interaktive Auswahl und Extraktion von Stilen/Inhalten vor dem Speichern.
- Wenn weggelassen oder `false`, führt Marked den automatischen Extraktor (Markdownifier) ​​aus und öffnet das Ergebnis direkt als neues temporäres Dokument.

##### Beispiele:

x-markiert://extract?url=https://news.ycombinator.com

x-markiert://extract?url=https://github.com&window=GitHub&raise=true

x-markiert://extract?url=https://example.com/article&manual=true

x-markiert://extract?url=https://blog.example.com/post-title

*Hinweis:* Dieser Befehl verwendet den Inhaltsextraktionsdienst von Marked, um Webseiten abzurufen, saubere Inhalte mithilfe von Readability zu extrahieren, in das Markdown-Format zu konvertieren und das Ergebnis in einem neuen temporären Dokument zu öffnen. Der extrahierte Inhalt enthält Metadaten (Titel, Quell-URL, Datum) und ist als sauberes Markdown formatiert. Perfekt für die schnelle Erfassung und Bearbeitung von Webinhalten.

## offen

Öffnet das angegebene Dokument in Marked.

x-markiert://open?file=/Users/username/Desktop/report.md

##### Parameter:

**Datei** *(erforderlich)*: Der vollständige POSIX-Pfad zum zu öffnenden Dokument oder eine durch Kommas getrennte Liste von Pfaden

**speedread** *(optional)*: Auf `1` setzen, um Speed ​​Read nach dem Öffnen automatisch zu starten.

`open` akzeptiert auch einen Pfad, dessen Komponenten in einer einzigen URL zusammengefasst werden

x-markiert://open/~/nvALT2.2

Wenn der angegebene Dateipfad nicht existiert oder nicht geöffnet werden kann, wird Marked immer noch im Vordergrund stehen. Bei Ausführung ohne den Parameter *file* oder mit einem leeren Wert wird einfach Marked geöffnet.

Marked öffnet auch Dateien, wenn im URL-Handler nur der Pfad einer Datei aufgerufen wird, z.B. `x-marked:///Users/username/Desktop/report.md`.

## Paste

Erstellen Sie ein neues Dokument aus dem aktuellen Inhalt der Zwischenablage.

x-markiert://einfügen

##### Parameter:

**speedread** *(optional)*: Auf `1` setzen, um Speed ​​Read nach dem Öffnen der Zwischenablagevorschau automatisch zu starten.

*Hinweis:* Dadurch wird mit dem Befehl „Vorschau der Zwischenablage“ ein temporäres Dokument erstellt. Jeder Text in Ihrer Zwischenablage wird einem neuen, leeren Dokument hinzugefügt, das dann in Marked geöffnet wird. Wenn es ohne Speichern geschlossen wird, wird es verworfen.

## Vorschau

Vorschau des angegebenen Texts in einem neuen Dokument.

x-marked://preview?text=Some%20text%20to%20%2A%2Apreview%2A%2A%0A

##### Parameter:

**Text** *(erforderlich)*: Der Text, der in die Vorschau eingefügt werden soll. Prozentcodierter Text wird vor der Anzeige des Dokuments entcodiert.

**Speedread** *(optional)*: Auf `1` setzen, um Speed ​​Read nach dem Öffnen des Vorschautextes automatisch zu starten.

## Stream

Öffnen Sie ein Vorschaufenster für die Streaming-Zwischenablage.

x-markiert://stream

##### Parameter:

**speedread** *(optional)*: Auf `1` setzen, um Speed ​​Read nach dem Öffnen der Streaming-Vorschau automatisch zu starten.

*Hinweis:* Dadurch wird mit dem Befehl „Vorschau der Zwischenablage“ ein temporäres Dokument erstellt. Der übergebene Text wird einem neuen, leeren Dokument hinzugefügt, das dann in Marked geöffnet wird. Wenn es ohne Speichern geschlossen wird, wird es verworfen.

## aktualisieren

Aktualisieren Sie eine Dokumentvorschau oder alle geöffneten Vorschauen.

##### Parameter:

**Datei**: Abfrageparameter, der durch Kommas getrennte Pfade/Dateinamen enthält (Dateien müssen derzeit in Marked geöffnet sein). Ein Aufruf ohne den Parameter `file` oder `?file=all` aktualisiert alle geöffneten Fenster.

Der Parameter *file* kann teilweise sein. Marked aktualisiert alle geöffneten Fenster mit einer teilweisen Übereinstimmung im *Dateinamen* (nicht dem vollständigen Pfad). Durch die Übergabe von „all“ werden alle Fenster aktualisiert.

x-markiert://aktualisieren

x-markiert://refresh?file=/Users/username/Desktop/report.md

x-marked://refresh?file=report.md

Wenn der Aufruf ohne `file`-Parameter, aber mit in der URL angegebenen Dokumentpfaden erfolgt, durchsuchen durch / geteilte Pfade mehrere Dateien und unvollständige Dateinamen vervollständigen die beste Übereinstimmung.

x-markiert://refresh/filename1/filename2

## Stil

Legen Sie den Vorschaustil (CSS) für ein oder mehrere Dokumente fest.

##### Parameter:

**css** _(erforderlich)_: Abfragezeichenfolge, die den Namen oder Pfad eines Stils enthält. Stile müssen im Stilmenü von Marked als Standard- oder manuell hinzugefügte benutzerdefinierte Stile vorhanden sein.

* Akzeptiert Pfadparameter, die auf Dateinamen oder „alle“ verweisen.
* Mit / geteilte Pfade durchsuchen mehrere Dateien
* Teilweise Dateinamen ergeben die beste Übereinstimmung

x-markiert://style/filename1/filename2?css=...
		x-markiert://style/all?css=...

**Datei**: Abfrageparameter, der durch Kommas getrennte Pfade/Dateinamen enthält

x-markiert://style?file=filename1,filename2&css=...

Diese Methode wird im vordersten Fenster ausgeführt, wenn kein Dateiname angegeben ist (oder „all“ nicht übergeben wird).


