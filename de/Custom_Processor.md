# <%= @title %>


Marked gibt Ihnen die volle Kontrolle über Custom Regeln, Text
Transformationen und die Möglichkeit, eigene Befehle auszuführen oder auszuführen
verschiedene Prozessoren basierend auf übereinstimmenden Dateieigenschaften.


## Verwendung von Custom Präprozessoren/Prozessoren

Um Custom Prozessoren hinzuzufügen, gehen Sie zu {% prefspane Processor %}
und klicken Sie auf **Custom Regeln**.

![][1]

[1]: images/custom-rules-button-800.jpg @2x width=800


Im Regeleditor (auch bekannt als „Dirigent“) können Sie benutzerdefinierte Regeln hinzufügen
Regeln mit Kriterien zum Zuordnen von Dateien basierend auf dem Dateinamen,
Pfad, Übereinstimmungen im Inhalt, Metadaten und sogar ob
Andere Dateien sind im selben Baum wie das Dokument vorhanden
geöffnet. Wenn eine Regel übereinstimmt, werden die für die definierten Aktionen ausgeführt
Regel werden für diese Datei ausgeführt.

> Unterhalb des Feldes Prozessor befinden sich die Kontrollkästchen in „Neu“.
> Dokumente verwenden Benutzerdefiniert:“ legt fest, ob Regeln getestet werden
> überhaupt für Präprozessor- und Prozessorphasen. Im Allgemeinen,
> Lassen Sie diese aktiviert, wenn Sie sie jedoch vollständig überschreiben möchten
> alle benutzerdefinierten Prozessoren, legen Sie diese hier fest.

![Rules Editor][2]

  [2]: images/CustomRules-800.jpg @2x width=800

Um eine neue Regel zu erstellen, verwenden Sie `+`
Klicken Sie auf die Schaltfläche unten in der linken Regelliste. Geben Sie die
Geben Sie einen Namen an und legen Sie ihn als Präprozessor oder Prozessor fest.

Die drei Punkte neben einer Regel zeigen Vorprozessor, Prozessor und Aktiviert an. Es kann nur einer von „Präprozessor“ oder „Prozessor“ hervorgehoben werden, und Sie können auf die Punkte klicken, um den Status der Regel zu ändern.

Präprozessor
: Wird ausgeführt, nachdem die Datei zum ersten Mal verarbeitet wurde, wenn Marked eingeschlossene Dateien hinzufügt, und verarbeitet Stileinstellungen wie GitHub Zeilenumbrüche usw., jedoch vor der Verarbeitungsphase. Das Dokument ist zu diesem Zeitpunkt noch im Rohzustand Markdown und Sie können Änderungen am Inhalt vornehmen, um ihn an den Prozessor weiterzuleiten. Wenn kein Custom-Prozessor übereinstimmt oder keine Aktion „Prozessor ausführen“ in einem übereinstimmenden Custom-Prozessor ausgeführt wird, wird der Standardprozessor ausgeführt.

Prozessor
: Ein Custom-Prozessor ersetzt den integrierten Prozessor, der in {% prefspane Processor %} definiert ist. Es kann alle Aktionen verarbeiten, die ein Präprozessor ausführen kann, und fügt die Aktionen „Befehl ausführen“ und „Prozessor ausführen“ hinzu. Dadurch können Sie einen benutzerdefinierten Befehl ausführen, z. Pandoc oder führen Sie einen anderen integrierten Prozessor für Dateien aus, die den Kriterien entsprechen.

Alle Tabellen im Custom-Regeleditor können nach neu angeordnet werden
Durch Ziehen und Ablegen können Sie die Reihenfolge beeinflussen
Regeln ausgeführt werden, die Reihenfolge der Kriterien im Prädikat
Editor und die Reihenfolge der nacheinander auszuführenden Aktionen.

### Prädikat-Editor

![Predicate Editor][predicate]

[predicate]: images/custom-rules-predicate-800.jpg @2x width=800

Sobald eine Regel hinzugefügt wurde, verwenden Sie zum Definieren den Prädikateditor
Kriterien, die bestimmen, ob die Regel für a ausgeführt wird
angegebene Datei. Verwenden Sie das Dropdown-Menü auf der linken Seite, um eine auszuwählen
Kriterium und verwenden Sie dann die Komparator- und Wertfelder zum Erstellen
das Prädikat.

- _filename_ entspricht nur dem Dateinamen der Datei
- _extension_ entspricht nur der Erweiterung der Datei
- _path_ entspricht dem vollständigen POSIX-Pfad (Unix) der Datei
- _tree_ sucht irgendwo in der Datei nach übereinstimmenden Dateinamen
  Verzeichnisbaum der Datei
- _text_ entspricht dem Textinhalt in der Datei. Vorwärts verwenden
  umgibt den Textwert mit Schrägstrichen, um ihn zu einem regulären Wert zu machen
  Ausdruckssuche.
- _fileIncludes_ testet, ob die Datei enthalten ist
  Dateien (unter Verwendung eines von [Marked's include
  syntaxes](Multi-File_Documents.html)).
- _metaType_ testet, ob die Datei YAML enthält,
  MultiMarkdown oder Pandoc-Metadaten
- _metadata.X_ testet auf bestimmte Metadatenschlüssel wie Autor,
  Datum, Titel usw.

Um alle Dateien abzugleichen (d. h. einen Custom Prozessor, der immer
ausgeführt wird), setzen Sie `filename` auf `contains` `*`. Das Sternchen wird
fungiert als Platzhalter und gleicht alle Dateien ab.

[Add a predicate][addpredicate]

[addpredicate]: images/custom-rules-add-predicate-800.jpg @2x width=800

Klicken Sie auf das Pluszeichen (+) in der Prädikatzeile, um ein weiteres Prädikat hinzuzufügen. Halten Sie die Wahltaste gedrückt, während Sie auf das + klicken, um eine boolesche Gruppe hinzuzufügen, die auf „Alle“ (UND) oder „Beliebig“ (ODER) eingestellt werden kann.

### Aktionen

Verwenden Sie die Schaltfläche *+ Aktion*, um der Regel Aktionen hinzuzufügen.

![Add an action][addaction]

[addaction]: images/custom-rules-add-action-800.jpg @2x width=800

Zu den verfügbaren Aktionen gehören:

Stil festlegen
: Legen Sie den Stil für die Vorschau fest. Jeder von Ihnen hinzugefügte integrierte Stil oder Custom-Stil ist verfügbar.

Befehl ausführen
: Dies erfordert einen Befehlszeilenbefehl, einschließlich aller Argumente, und übergibt den Inhalt der Datei an STDIN. Der Befehl sollte die resultierende Ausgabe auf STDOUT zurückgeben.

> **Mac App Store Sandboxing**: Die Mac App Store (MAS)-Version von Marked wird in einer Sandbox-Umgebung ausgeführt, die die Ausführung externer Binärdateien einschränkt. Wenn Sie externe Prozessoren wie Pandoc in der MAS-Version verwenden müssen, müssen Sie die Binärdatei in das App-Bundle kopieren. Gehen Sie dazu wie folgt vor:
>
> 1. Klicken Sie mit der rechten Maustaste auf Marked.app → Paketinhalt anzeigen
> 2. Navigieren Sie zu Inhalt/Ressourcen/
> 3. Erstellen Sie einen Ordner `bin`, falls dieser nicht vorhanden ist
> 4. Kopieren Sie Ihre Binärdatei (z. B. `pandoc`) hierhin
> `bin` Ordner
> 5. Machen Sie es ausführbar: `chmod +x` die Binärdatei
> 6. Verweisen Sie in der Aktion „Befehl ausführen“ wie folgt darauf:
>
> `YOUR_BINARY_NAME [arguments]`
> Oder verwenden Sie den vollständigen Pfad:
> `/Applications/Marked.app/Contents/Resources/bin/YOUR_BINARY_NAME [arguments]`
>
> **Hinweis**: Skripte mit externen Shebangs (wie Python-Skripte, die auf `/opt/homebrew/bin/python` verweisen) werden beim Kopieren in das Bundle automatisch über Systeminterpreter ausgeführt. Die MAS-Version hat möglicherweise immer noch Probleme beim Ausführen von Binärdateien, bei denen es sich tatsächlich um Python- oder Ruby-Skripte und nicht um Binärdateien handelt.
> Sie müssen die Binärdateien nach jedem App-Update erneut kopieren, da Updates das gesamte Paket ersetzen. Alternativ können Sie **Hilfe->Crossgrade** verwenden, um die Nicht-Sandbox-Version zu erhalten, für die es keine derartigen Einschränkungen gibt.

Führen Sie das eingebettete Skript aus
: Bearbeiten Sie ein vollständiges Skript im integrierten Code-Editor. Wie „Run Command“ sollte dies Eingaben auf STDIN entgegennehmen und Ausgaben auf STDOUT zurückgeben.

Metadaten festlegen
: Fügt Metadaten hinzu oder legt sie fest. Geben Sie einen Schlüssel und einen Wert an. Wenn der Schlüssel vorhanden ist, wird sein Wert aktualisiert, andernfalls wird er hinzugefügt. Der Typ der verwendeten Metadaten wird automatisch durch den Inhalt der Datei (oder das Ergebnis einer Metadatenkonvertierungsaktion) bestimmt.
: Wenn keine vorhandenen Metadaten gefunden werden, werden die Metadaten im MultiMarkdown-Format innerhalb eines HTML-Kommentars hinzugefügt. Marked kann diese Metadaten lesen, sie werden jedoch nicht in Ihrer Vorschau angezeigt, unabhängig davon, welcher Prozessor verwendet wird.

Metadaten löschen
: Metadaten basierend auf ihrem Schlüssel löschen.

Metadaten entfernen
: Alle Metadaten löschen. Betrifft YAML-, MultiMarkdown- und Pandoc-Metadaten.

Konvertieren Sie YAML Meta in MMD
: Konvertiert einen YAML-Metadatenblock am Anfang der Datei in Metadaten im MultiMarkdown-Stil.

Konvertieren Sie MMD Meta in YAML
: Konvertiert einen MultiMarkdown-Metadatenblock in YAML.

Suchen und Ersetzen
: Führen Sie eine Suche und Ersetzung im Inhalt der Datei durch.
: Wenn die Suchzeichenfolge in Schrägstriche eingeschlossen ist (z. B. `/Project \w+/`), wird sie als regulärer Ausdruck behandelt. Sie können `$1`, `$2` usw. verwenden, um Übereinstimmungsgruppen in die Ersetzungszeichenfolge aufzunehmen.
: Das Ersetzungsfeld unterstützt einige Escape-Sequenzen (einen Backslash gefolgt von): `\n` fügt eine neue Zeile ein, `\t` fügt ein Tabulatorzeichen ein, `\\` fügt einen Literal-Backslash ein, `\$` fügt ein Literal-Dollarzeichen ein (anstelle einer Übereinstimmungsgruppe)
: Jede andere `\X`-Sequenz wird nur als `X` behandelt (der Backslash wird entfernt), sodass `\e` zu `e` wird. Ein nachgestelltes \ ohne Zeichen danach wird als wörtlicher Backslash beibehalten.
: Verwenden Sie `[%key]` in der Ersetzungszeichenfolge, um einen Wert aus Dokumentmetadaten, Umgebungsvariablen oder Kontext einzufügen (z. B. `[%title]`, `[%MARKED_PATH]`). Schlüssel, die durch frühere Aktionen in derselben Regel oder durch eine vorhergehende Regel festgelegt wurden, sind verfügbar. Nicht übereinstimmende Schlüssel werden durch eine leere Zeichenfolge ersetzt.

Fügen Sie Titel H1 ein
: Fügt ein H1 in das Dokument ein. Dies kann entweder aus Metadaten oder dem Dateinamen entnommen werden.

Header verschieben
: Passen Sie die Header-Ebenen von -5 bis +5 an. Wenn Sie dies beispielsweise auf -1 festlegen, werden alle H1-Elemente zu H2-Elementen, H2-Elemente werden zu H3-Elementen usw. Legen Sie eine positive Zahl fest, um die Header-Ebenen um diesen Betrag anzuheben.

Header normalisieren
: Diese Aktion stellt nach Möglichkeit sicher, dass es nur ein H1 im Dokument gibt, und passt alle Header-Ebenen so an, dass sie in einer semantischen Reihenfolge sind und keine Ebenen überspringen, z. B. von H2 bis H4. Wenn das Originaldokument überhaupt semantisch geordnet ist, wird die Hierarchie dadurch gut verfeinert.

Inhaltsverzeichnis einfügen
: Ein Inhaltsverzeichnis einfügen. Das Inhaltsverzeichnis kann nach dem ersten H1, dem ersten H2 oder am Anfang der Datei stehen (wird nach allen Metadaten eingefügt).

Datei einfügen
: Fügt eine ausgewählte Textdatei an einer bestimmten Stelle im Dokument ein. Dies kann nach dem ersten H1, dem ersten H2, oben, unten oder nach einer Textübereinstimmung erfolgen (verwenden Sie `/pattern/`, um nach einem regulären Ausdruck zu suchen).

Text einfügen
: Stellt einen Popup-Editor bereit, mit dem Sie Text direkt in die Aktion einbetten können. Die Positionierungsoptionen sind die gleichen wie bei _Datei einfügen_.
: Verwenden Sie `[%key]` an einer beliebigen Stelle im eingefügten Text, um Werte aus Dokumentmetadaten, Umgebungsvariablen oder dem Marked-Kontext abzurufen (z. B. `[%author]`, `[%MARKED_PATH]`). Dies funktioniert unabhängig davon, welchen Prozessor Sie verwenden, sodass Sie MultiMarkdown nicht für die Metadatenersetzung benötigen. Werte aus früheren Aktionen in derselben Regel (z. B. **Metadaten festlegen**) oder aus einer vorhergehenden Regel werden einbezogen. Nicht übereinstimmende Schlüssel werden durch eine leere Zeichenfolge ersetzt.

CSS-Datei einfügen
: Fügt eine ausgewählte CSS-Datei in das Dokument ein. Diese wird nach jeder Stilauswahl geladen und kann verwendet werden, um vorhandene Stile zu überschreiben oder neue hinzuzufügen.

CSS einfügen
: Bietet einen Popup-CSS-Editor, mit dem Sie Ihr eigenes CSS direkt zur Aktion hinzufügen können. Dieses CSS wird oben im Dokument nach allen vorhandenen Stilen eingefügt. Die Reihenfolge der eingefügten Stile entspricht der Reihenfolge der Aktionen in der Regel.

Fügen Sie eine JavaScript-Datei ein
: Fügt eine ausgewählte JavaScript-Datei am Ende des Dokuments ein. Beachten Sie, dass Sie eine Aktion *JavaScript einfügen* mit einem [update hook](#updatehook) verwenden müssen, wenn Sie möchten, dass das Skript bei jedem Update neu geladen wird.

Fügen Sie JavaScript von der URL ein
: Verwenden Sie dies, um am Ende des Dokuments ein `<script>`-Tag einzufügen, das mit einem CDN oder einer anderen Remote-URL verknüpft ist. Beachten Sie, dass Sie eine Aktion *JavaScript einfügen* mit einem [update hook](#updatehook) verwenden müssen, wenn Sie möchten, dass das Skript bei jedem Update neu geladen wird.

Fügen Sie JavaScript ein
: Stellt einen Popup-JavaScript-Editor bereit, mit dem Sie benutzerdefiniertes JavaScript direkt in die Aktion einbetten können. Dies wird am Ende des Dokuments eingefügt und die Reihenfolge, in der JavaScript von der Regel ausgeführt wird, wird durch die Reihenfolge der Aktionen bestimmt, wobei die letzte Aktion zuletzt hinzugefügt wird.
: Beachten Sie, dass Sie ein [update hook](#updatehook) verwenden müssen, wenn Sie möchten, dass bei jedem Update Skripts ausgeführt werden.

Self-Link-URLs
: Konvertieren Sie alle nackten URLs in `<url>`, wodurch in jedem Prozessor ein Hyperlink generiert wird.

Verknüpfung ausführen
: Führen Sie eine Apple-Verknüpfung aus. Jede Shortcut-Ausführung sollte Eingaben von STDIN entgegennehmen und am Ende eine Ausgabe zurückgeben (Stopp- und Rückgabeausgabe). Wenn Sie Aktionen ausführen möchten, die den Text nicht ändern, legen Sie die Eingabe auf eine Variable fest, führen Sie Ihre Aktionen aus und geben Sie am Ende die ursprüngliche Textvariable aus.

Führen Sie den Systemdienst aus
: Führen Sie einen beliebigen Systemdienst in `~/Library/Services` aus. Der Dienst sollte Eingaben akzeptieren und Ausgaben zurückgeben.

Führen Sie den Automator-Workflow aus
: Führen Sie eine beliebige Automator-Datei `.workflow` aus. Die Eingabe wird auf STDIN weitergeleitet und die Ausgabe wird auf STDOUT erwartet.

Weiter
: Standardmäßig wird die Verarbeitung gestoppt, sobald eine Regel übereinstimmt (getrennt für Präprozessoren und Prozessoren, sodass ein Präprozessor und ein Prozessor übereinstimmen können). Diese Aktion erzwingt, dass der Regelabgleich fortgesetzt wird, nachdem die Regel ihre Aktionen ausgeführt hat.

### Hook aktualisieren

Marked führt nicht bei jedem Update eine vollständige Aktualisierung durch
Sie haben Skripte, die Teile des DOM rendern, die sie benötigen
um ihre Renderfunktion mit der Hook-API von Marked auszuführen.

Das folgende Beispiel verwendet Mermaid, was Sie eigentlich nie tun
Dies ist nicht erforderlich, da Mermaid jetzt standardmäßig enthalten ist. Aber
So würden Sie vorgehen, wenn Sie es manuell einbinden würden.

Fügen Sie eine Aktion **JavaScript einfügen** hinzu und klicken Sie im Bereich „JS bearbeiten“
Fenster, initialisieren Sie das Skript und fügen Sie den Hook hinzu:

„Javascript
mermaid.initialize({ startOnLoad: true });

Marked.hooks.register('update', function() {
    mermaid.run();
});
„

Dies führt dazu, dass `mermaid.run()` jedes Mal ausgeführt wird
Marked führt eine Teilaktualisierung durch.

### Testregeln

Die Schaltfläche _Testregeln_ unter der Regelliste öffnet ein
Dialog, in dem Sie eine beliebige Markdown-Datei auswählen können
anhand aller Ihrer Regeln getestet. Regeln, die übereinstimmen, werden erhalten
wird durch eine grüne Lasche auf der linken Seite hervorgehoben. Beim Matching
Gegen eine Datei erscheint eine X-Schaltfläche, die dazu verwendet werden kann
Löschen Sie den Test und heben Sie die Markierung der Zeilen auf.

## Drag-and-Drop

Das Dirigentenfenster unterstützt erweitertes Drag & Drop
Funktionen, die Dateitypen intelligent erkennen und
Bereitstellung geeigneter Aktionen basierend auf der gezogenen Datei. Die
Die Implementierung umfasst ein geteiltes Overlay-System für Text
Dateien, die es Benutzern ermöglichen, zwischen dem Testen der Datei zu wählen
gegen Regeln verstoßen oder es als Aktion hinzufügen.

![Drag and Drop in Custom Rules][drag]

[drag]: images/draganddropconductor.jpg @2x width=800

### Dateityperkennung

Das System erkennt automatisch verschiedene Dateitypen und
zeigt entsprechende Overlay-Meldungen an:

- **CSS-Dateien** (`.css`): Zeigt die Überlagerung „CSS-Datei einfügen“ an
- **JavaScript-Dateien** (`.js`, `.javascript`): Zeigt „Einfügen
  JS-Datei“-Overlay
- **Skriptdateien** (jede ausführbare Datei)): Zeigt „Ausführen
  „Befehl“-Overlay
- **Textdateien**: Zeigt geteilte Überlagerung
- **Ausführbare Dateien**: Zeigt die Überlagerung „Befehl ausführen“ an
- **Unbekannte Erweiterungen**: Standardmäßig wird der Typ „Text“ verwendet und angezeigt
  geteilte Überlagerung

## Custom Prozessorprotokoll

Wenn Sie merkwürdige Ergebnisse erhalten und sehen möchten, was vor sich geht, zeigt Ihnen das Custom-Regelprotokoll, welche Regeln in welcher Reihenfolge ausgeführt werden. Verwenden Sie **Hilfe->Regelprotokoll für Custom anzeigen**, um es zu öffnen.

![Custom Rules Log][crlog]

[crlog]: images/CustomRulesLog.jpg @2x width=809

## Mehrere Befehle ausführen

Eine Regel kann mehrere aufeinanderfolgende Befehle enthalten. Die Ausgabe von
Jeder Befehl wird an den nächsten weitergegeben. Wenn du haben willst
Ein Befehl gibt gleichzeitig mit Marked etwas aus
Wenn Sie Aktualisierungen in der Vorschau anzeigen möchten, geben Sie unbedingt den Originalinhalt zurück
an STDOUT zur Verarbeitung des nächsten Befehls oder integriert
Prozessor.

Wenn Sie beispielsweise möchten, dass ein Befehl einen PDF aktualisiert
Um ein Dokument mit Pandoc zu erstellen, übergeben Sie einfach den ursprünglichen Dateipfad
(von Umgebungsvariablen) an Pandoc mit entsprechendem
Befehlszeilenoptionen und geben Sie dann den STDIN-Inhalt zurück
auf STDOUT übertragen.

## Dynamische Umgehung benutzerdefinierter Prozessoren

Wenn ein benutzerdefinierter Prozessor „NOCUSTOM“ auf STDOUT zurückgibt, Marked
beendet den benutzerdefinierten Prozessor und greift auf den zurück
Standardmäßiger interner Prozessor. Auf diese Weise können Sie eine erstellen
benutzerdefinierter Prozessor, der entscheiden kann, ob dies erforderlich ist oder nicht
mit [environment variables](#environmentvariables) ausführen
Unten der Dateiname oder die Erweiterung des Dokuments, Inhaltsübereinstimmung
oder andere Logik.

Wenn anstelle von `NOCUSTOM` ein Custom Prozessor zurückgegeben wird
`MULTIMARKDOWN` oder `DISCOUNT` (oder `GFM`), `KRAMDOWN` oder
`COMMONMARK`, dann wird dieser interne Prozessor verwendet
nur dieses Dokument. Diese Änderung hat keine Auswirkungen auf die Standardeinstellung
Prozessor in den Einstellungen eingestellt.

## Umgebungsvariablen

Die Aktion „Befehl ausführen“ verfügt über einen Umgebungseditor, in dem Sie
Sie können Ihre eigenen Umgebungsvariablen festlegen
für den Befehl oder das Skript verfügbar. Zusätzlich zu diesen
Benutzerdefinierte Variablen, Marked enthält einige eigene.

Marked führt den benutzerdefinierten Prozessor in seiner eigenen Shell aus, d. h
Standardumgebungsvariablen werden nicht automatisch übergeben.
Sie können die Umgebungsvariablen von Marked verwenden, um Ihre zu erweitern
eigene in Ihren Skripten. Marked erstellt die folgenden Variablen
Verfügbar für die Verwendung in Ihren Shell-Skripten:

**MARKED_ORIGIN**
: Der Speicherort (Basisverzeichnis) Ihrer primären Arbeitsdatei (der Ordner des Arbeitstextes, Scrivener oder Indexdatei).

**PFAD**
: Marked legt einen Pfad fest, der standardmäßige ausführbare Ordner enthält, und hängt das Verzeichnis im `MARKED_ORIGIN` oben an. Die Standardwerte sind: `/Developer/usr/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin`. Sie können Ihre eigene hinzufügen, indem Sie die PATH-Variable nach Bedarf festlegen und den Pfad von Marked anhängen oder überschreiben (z. B. `PATH=/usr/local/yourfolder:$PATH`).

**Zuhause**
: Das Home-Verzeichnis des angemeldeten Benutzers. Python und andere Skripte, die auf das Setzen der HOME-Variablen angewiesen sind, übernehmen dies automatisch, es steht jedoch für andere Zwecke in Ihren Skripten zur Verfügung.

**MARKED_EXT**
: Die Erweiterung der primären Datei, die verarbeitet wird. Mit dieser Variable können Sie je nach Art der angezeigten Datei unterschiedliche Prozesse skripten. Wenn zum Beispiel `$MARKED_EXT == "md"` Ihren bevorzugten Markdown-Prozessor ausführt, aber wenn `$MARKED_EXT == "textile"` einen Textile-Prozessor ausführt.

**MARKED_PATH**
: Dies ist der vollständige UNIX-Pfad zur Hauptdatei, die zum Zeitpunkt des Ladens in Marked geöffnet ist.

**MARKED_INCLUDES**
: Eine in Anführungszeichen gesetzte, durch Kommas getrennte Liste der Dateien, die Marked in den Text aufgenommen hat, der mit den verschiedenen [include syntaxes](Special_Syntax.html#pagebreaks) übergeben wird.

**MARKED_PHASE**
: Dies wird entweder auf „PROCESS“ oder „PREPROCESS“ gesetzt, sodass Sie ein einziges Skript verwenden können, um beide Phasen basierend auf dieser Variablen abzuwickeln.

**MARKED_CSS_PATH**
: Der vollständige Pfad zum aktuellen Stylesheet

### Metadaten-Umgebungsvariablen

Wenn die Aktion „Befehl ausführen“ in Marked ausgeführt wird
Dirigentensystem, Dokumentmetadaten werden automatisch erstellt
extrahiert und als Umgebungsvariablen zur Verfügung gestellt
Befehl.

#### Wie es funktioniert

1. **Metadatenextraktion**: Das System extrahiert Metadaten aus dem Dokument mithilfe der vorhandenen Methode `extractMetaDataFromString:`, die Folgendes unterstützt:
   - YAML Titelseite (`---` Blöcke)
   - MultiMarkdown-Metadaten (Schlüssel: Wertezeilen)
   - Pandoc-Metadaten (`%` Schriftfelder)
   – HTML Kommentarmetadaten (`<!-- key: value -->`)

2. **Schlüsselnormalisierung**: Metadatenschlüssel werden für die Verwendung als Umgebungsvariablen normalisiert:
   - In Kleinbuchstaben umgewandelt
   - Alle nicht alphanumerischen Zeichen werden entfernt
   - Leerzeichen und Sonderzeichen werden entfernt

3. **Format der Umgebungsvariablen**: Jeder Metadatenschlüssel wird zu einer Umgebungsvariablen mit dem Präfix `MD_`:
   - `Author` → `MD_author`
   - `XHTML header` → `MD_xhtmlheader`
   - `Custom Processor` → `MD_customprocessor`

#### Beispiel

Gegeben sei ein Dokument mit diesen Metadaten:

```markdown
title: My Document
author: John Doe
date: 2024-01-15
Custom Processor: true
Marked Style: amblin
XHTML header: <meta name="viewport" content="width=device-width">
Status: Draft
Priority: High
```

Die folgenden Umgebungsvariablen stehen zur Verfügung
Befehle:

```bash
MD_title="My Document"
MD_author="John Doe"
MD_date="2024-01-15"
MD_customprocessor="true"
MD_markedstyle="amblin"
MD_xhtmlheader="<meta name=\"viewport\" content=\"width=device-width\">"
MD_status="Draft"
MD_priority="High"
```

#### Verwendung in Befehlen

Sie können diese Umgebungsvariablen jetzt in Ihrem Run verwenden
Befehlsaktionen:

„Bash
# Drucken Sie den Dokumenttitel aus
echo „Verarbeitung: $MD_title“

# Metadaten in bedingter Logik verwenden
if [ "$MD_status" = "Entwurf" ]; dann
    echo „Dokument befindet sich noch im Entwurfsstatus“
fi

# Übergeben Sie Metadaten an andere Tools
pandoc „$MARKED_PATH“ \
  --metadata title="$MD_title" \
  --metadata author="$MD_author" \
  --metadata date="$MD_date" \
  -o Ausgabe.pdf

# Verwenden Sie Metadaten für die Dateibenennung
if [ -n "$MD_title" ]; dann
    Output_file="${MD_title// /_}.html"
sonst
    Output_file="output.html"
fi
„

#### Unterstützte Aktionen

Diese Metadaten-zu-Umgebungsvariablen-Funktionalität ist
erhältlich in:

- **Befehl ausführen**-Aktionen
- Aktionen **Eingebettetes Skript ausführen**

Die Metadaten werden automatisch aus dem Dokument extrahiert
Inhalt und wird für jeden Befehl oder jedes Skript verfügbar gemacht
durchläuft diese Aktionen.

## Aktivieren und Deaktivieren

Die benutzerdefinierten Prozessoren können für aktiviert und deaktiviert werden
einzelne Dokumente mit {% kbd opt cmd C %}. Du
kann auch einen Präprozessor oder Prozessor für ein Dokument aktivieren
automatisch [using metadata](#perdocument) am Anfang
das Dokument.

Die aktuellen Status der Bearbeiter für jedes Dokument sind
werden als Kontrollleuchten angezeigt (nur sichtbar, wenn ein Prozessor vorhanden ist).
aktiviert ist) links neben den Symbolleistenelementen unten
rechte Symbolleiste der Vorschau.

### Präprozessor

Wenn Sie Präprozessorregeln einrichten, werden diese nach Marked ausgeführt.
übernimmt alle Marked-spezifischen Aufgaben, z. B. das Einbeziehen externer
Dokumente und Code, aber bevor es läuft, läuft der Prozessor
(intern oder benutzerdefiniert). Dies gibt Ihnen die Möglichkeit zum Rendern
Benutzerdefinierte Vorlagenvariablen, verarbeiten Sie Ersetzungen oder fügen Sie sie ein
Ihre eigenen Inhalte auf andere Weise.

Marked legt eine Umgebungsvariable für die Funktion fest
Verzeichnis (`MARKED_ORIGIN`) in das übergeordnete Verzeichnis des
Datei, die in der Vorschau angezeigt wird. Damit können Sie die Arbeitsweise ändern
Verzeichnis eines Skripts und Include-Dateien mit relativen Pfaden
zum Originaldokument. In Ruby ist das beispielsweise möglich
Verwendung:

Dir.chdir(ENV['MARKED_ORIGIN'])

Wenn diese Option aktiviert ist, kann der benutzerdefinierte Präprozessor aktiviert und aktiviert werden
für einzelne Dokumente ausschalten
{% kbd ctrl opt cmd C %}.

#### Pro-Dokument-Prozessor/Vorprozessor [perDokument]

Custom Prozessoren können auch pro Dokument festgelegt werden
Verwendung des Metadatenformats für [Per-Document
settings](Per-Document_Settings.html).

Sie können angeben, ob benutzerdefinierte Prozessoreinstellungen verwendet werden sollen und
Überschreiben Sie die Standardeinstellung für ein Dokument mit [Per-Document
settings](Per-Document_Settings.html) (`Custom Processor:`
und `Custom Preprocessor:`). Jede andere Einstellung als „true“
oder „Ja“ deaktiviert den benutzerdefinierten Vor-/Prozessor.

Beispielverwendung:

Custom Prozessor: wahr
    Custom Präprozessor: falsch

Wie auf der Seite [Per-Document
Settings](Per-Document_Settings.html#hidingmeta) erwähnt, Sie
kann diese Metadaten mit HTML Kommentarmarkierungen umgeben, um sie auszublenden
es von GitHub und anderen Prozessoren, die es nicht entfernen
aus der Ausgabe:

<!--
    Custom Prozessor: wahr
    Custom Präprozessor: wahr
    ->

## Verwendung eines alternativen Markdown-Prozessors

Jede Markdown-Variante, die Sie über die Befehlszeile rendern können, ist möglich
mit Marked verwendet werden. Es muss in der Lage sein, Eingaben anzunehmen
STDIN, was dasselbe ist, als würde man Ihren Markdown daran weiterleiten
Befehlszeile, d. h. `cat myfile.md | myprocessor`. Es braucht
um den resultierenden HTML auf STDOUT zurückzugeben, was jeder
Der Prozessor, mit dem ich jemals gearbeitet habe, funktioniert standardmäßig.

Verwenden Sie `which YOUR_PROCESSOR` im Terminal, um den Pfad zu bestimmen
zur ausführbaren Datei hinzufügen und diese dann in den Pfad „Befehl ausführen“ einfügen
Feld, oder ziehen Sie einfach die ausführbare Datei in das Custom-Regelfenster
mit der Regel, zu der Sie die Aktion hinzufügen möchten, ausgewählt.

Wenn Ihr Prozessor Argumente in der Befehlszeile benötigt,
Sie müssen diese ebenfalls in das Feld eingeben. Einige
Prozessoren benötigen Bindestriche, um auf STDIN und/oder STDOUT zu funktionieren.
z.B. `-o - -` signalisiert häufig die Eingabe von STDIN und die Ausgabe an
STDOUT. Weitere Informationen finden Sie in der Dokumentation Ihres Prozessors.

Ich habe die Custom-Prozessorfunktion mit Pandoc getestet.
Kramdown, markiert (Rabatt), MultiMarkdown 6, Maruku und
verschiedene andere Geschmacksrichtungen.

### Eine Anmerkung zu Pandoc und Sandboxing

Pandoc (und einige andere Befehlszeilentools) werden nicht ausgeführt
die Mac App Store-Version (Sandbox) von Marked.
Wenn Sie Pandoc ausführen müssen, verwenden Sie **Hilfe->Crossgrade**, um eine zu erhalten
kostenlose Lizenz für die direkte (Paddle-)Version. Das ist wahr
eines Prozessors, bei dem Sandboxing-Probleme auftreten: wenn Marked
kann es aufgrund von MAS-Berechtigungsproblemen nicht ausführen, wird es aber tun
Bieten Sie die Schritte zum Crossgrade an. Wenn bei Ihnen Probleme auftreten
und dies nicht der Fall ist, kontaktieren Sie mich bitte über die
[support site](https://support.markedapp.com/questions/add).

### Pandoc als Markdown Auftragsverarbeiter der Schweizer Armee

[Pandoc](https://pandoc.org/) ist bei weitem die flexibelste
Allzweck-Tool zur Verarbeitung einer Reihe von Markup-Formaten. Von
Pandoc kann ein `-f`-Argument mit einem der folgenden Elemente hinzufügen
Seien Sie Ihr Custom Auftragsverarbeiter für Folgendes:

- `commonmark`
- `docbook`
- `dokuwiki`
- `gfm`
- `markdown_phpextra`
- `mediawiki`
- `textile`
- `twiki`
- `vimwiki`

Und noch ein paar andere. Weitere Informationen finden Sie unter [Pandoc
documentation](https://pandoc.org/MANUAL.html)
Infos. Um eines davon als Eingabeformat zu verwenden, fügen Sie einfach das hinzu
Geben Sie Folgendes in Ihr Feld „Befehl ausführen“ ein:

/usr/local/bin/pandoc -f INPUT_FORMAT

Pandoc eignet sich perfekt zum Schreiben eines Skripts, das das verwendet
`$MARKED_EXT` Umgebungsvariable, um das Format zu bestimmen
um Pandoc auszuführen oder eine Reihe von Regeln mit zu verwenden
Erweiterungsübereinstimmungen. Wenn die Erweiterung `md` ist, verwenden Sie
`pandoc -f gfm` oder `pandoc -f markdown_mmd` (oder einfach zurückgeben
`NOCUSTOM` auf STDOUT, um den Standardprozessor zu verwenden). Aber wenn ja
`textile`, führen Sie `pandoc -f textile` innerhalb des Skripts aus. Und wenn
Es ist `wiki`, verwenden Sie einen der Wiki-Markup-Prozessoren. Du bekommst
die Idee.

Wie Pandoc-Fans wissen, kann Pandoc auch damit umgehen
umfangreiche Bibliographie und LaTeX-Szenarien. Die meisten Funktionen
Sie können einfach über die Befehlszeile darauf zugreifen
durch die Verwendung von Übergabeargumenten in Marked.

## Textil verwenden

Einige Leute haben gefragt, wie man Textile zum Laufen bringt
Marked. Sie benötigen einen Textilkonverter von
die Befehlszeile. Es gibt einige Optionen, darunter Pandoc
(siehe oben), aber wenn Sie Pandoc noch nicht installiert haben,
Zwei weitere Optionen sind RedCloth für Ruby und Textile für Perl
(erfordert die Installation der Entwicklertools). Installieren
das eine oder andere:

1. Installieren Sie Textile von
   <https://github.com/bradchoate/text-textile> **ODER**
   `sudo gem install RedCloth` im Terminal
2. Verwenden Sie `which textile` oder `which redcloth`, um die zu bestimmen
   Pfad, der in den Custom-Prozessorpfadeinstellungen verwendet werden soll

Jetzt ist Marked ein Textil-Previewer für Sie!

## AsciiDoc verwenden

1. Installieren Sie [AsciiDoctor](http://asciidoctor.org/).
2. Aktivieren Sie eine Custom-Regel in {% prefspane Processor %}, um Ihre AsciiDoc-Dateien abzugleichen.
3. Legen Sie die Regel als Prozessor fest und fügen Sie eine Aktion „Befehl ausführen“ hinzu
    1. Bestimmen Sie den Pfad zu `asciidoc`
       so etwas wie `/usr/bin/asciidoc` oder
       `/opt/local/bin/asciidoc`. Wenn Sie unsicher sind, verwenden Sie
       `which asciidoc` zum Suchen
    2. Geben Sie `[PATH To asciidoc] --backend html5 -o - -` als ein
       Der Befehl (das - am Ende sendet die Ausgabe als
       STDOUT)

Dadurch wird das aktuelle Dokument an STDIN gesendet und angezeigt
generiert HTML als STDOUT.

Siehe [this gist](https://gist.github.com/mojavelinux/6324279)
von [Dan Allen](https://gist.github.com/mojavelinux) für
Weitere Informationen.