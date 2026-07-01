# <%= @title %>

Das Befehlszeilentool `mk` bietet einfachen Zugriff auf die Funktionen von Marked vom Terminal aus und ermöglicht so die Automatisierung von Arbeitsabläufen und die Integration mit Shell-Skripten und anderen Befehlszeilentools.

## Installation

Die empfohlene Methode zur Installation von `mk` ist mit Homebrew:

```bash
brew tap ttscoff/thelab
brew install ttscoff/thelab/mk
```

Wenn Sie Homebrew nicht verwenden, laden Sie das signierte Paket herunter und installieren Sie es:

{% download "https://github.com/ttscoff/mk/releases/latest/download/mk.pkg" "Signed PKG installer for mk. Double-click to launch Installer and follow the prompts." %}

Nachdem Sie `mk.pkg` heruntergeladen haben, doppelklicken Sie darauf und befolgen Sie die Anweisungen des Installationsprogramms.

## Grundlegende Verwendung

### Dateien öffnen

Öffnen Sie eine Markdown-Datei in Marked über die Befehlszeile:

```bash
mk file.md
mk ~/Documents/notes.md
mk --raise document.md  # Open and raise window above all others
```

### Inhalte von STDIN streamen

Streamen Sie Inhalte direkt in die Streaming-Vorschau von Marked:

```bash
echo "# Hello World" | mk
cat notes.md | mk
mk -  # Explicitly use STDIN
```

Das Fenster „Streaming-Vorschau“ wird geöffnet und zeigt den Inhalt in Echtzeit an, während er von anderen Befehlen weitergeleitet wird.

## Befehlsreferenz

### Dateioperationen

**`mk [file]`** – Öffnen Sie eine Markdown-Datei in Marked

**`mk [file] --raise`** – Datei öffnen und das Fenster über alle anderen heben

### STDIN und Streaming

**`mk`** oder **`mk -`** – Von STDIN lesen und Streaming-Vorschau öffnen

**`mk --stream`** – Streaming-Vorschaufenster öffnen, ohne STDIN zu lesen

### Vorschauverwaltung

**`mk --refresh`** – Aktualisieren Sie das vorderste Vorschaufenster

**`mk --refresh all`** – Alle geöffneten Vorschaufenster aktualisieren

**`mk --refresh file.md`** – Vorschau für eine bestimmte Datei aktualisieren (falls geöffnet)

### Präferenzen

**`mk --pref`** – Marked-Einstellungen öffnen (Seite „Allgemein“)

**`mk --pref Advanced`** – Einstellungen für eine bestimmte Seite öffnen

**`mk --defaults KEY=VALUE [KEY=VALUE...]`** – Benutzereinstellungen festlegen (mehrere Paare zulässig)

```bash
mk --defaults syntaxHighlight=1 includeMathJax=0 processor=multimarkdown
```

### Stilmanagement

**`mk --style NAME`** – Vorschaustil für geöffnete Fenster festlegen

**`mk --add-style FILE`** – Fügen Sie eine CSS-Datei als benutzerdefinierten Stil zu Marked hinzu.

```bash
mk --add-style ~/Styles/custom.css
```

### JavaScript-Ausführung

**`mk --dojs "JAVASCRIPT_COMMAND"`** – Führen Sie JavaScript im vordersten Fenster aus

**`mk --dojs "SCRIPT" all`** – Führen Sie JavaScript in allen Fenstern aus

**`mk --dojs "SCRIPT" file.md`** – Führen Sie JavaScript in bestimmten Dateien aus.

```bash
mk --dojs "window.scrollTo(0,0)"
mk --dojs "alert('Hello')" all
```

### Inhaltsextraktion und -import

**`mk --extract URL`** – Inhalte aus der URL extrahieren und in Marked öffnen

```bash
mk --extract https://example.com/article
```

**`mk --importurl [URL]`** – Fenster „URL importieren“ öffnen (optional mit URL)

**`mk --stylestealer [URL]`** – Open Style Stealer HUD (optional mit URL)

### Dienstprogrammbefehle

**`mk --paste`** – Neues Dokument aus der Zwischenablage erstellen

**`mk --preview TEXT`** – Sehen Sie sich den Text direkt in einem neuen Dokument in der Vorschau an

**`mk --dingus`** – Öffnen Sie Markdown Dingus zum Testen von Prozessoren

**`mk --help`** oder **`mk -h`** – Nutzungsinformationen anzeigen

**`mk --version`** oder **`mk -v`** – Versionsinformationen anzeigen

## Beispiele

„Bash
# Öffnen Sie eine Datei
mk document.md

# Markdown aus einer Datei streamen
Katzennotizen.md | mk

# Prozess und Vorschau
grep -i "important" NOTES.md | mk

# Alle Vorschauen aktualisieren
mk --refresh all

# Fügen Sie einen benutzerdefinierten Stil hinzu
mk --add-style ~/Documents/MyTheme.css

# Einstellungen festlegen
mk --defaults syntaxHighlight=1 Prozessor=Multimarkdown

# Führen Sie JavaScript in allen Fenstern aus
mk --dojs "window.scrollTo(0,0)" alle

# Inhalte von einer Webseite extrahieren
mk --extract https://blog.example.com/article

# Direkte Textvorschau
mk --preview "## Hallo\n\nDies ist **Markdown**-Text!"
„

## Integration

### Shell-Aliase

Fügen Sie zu Ihrem `~/.zshrc` oder `~/.bash_profile` hinzu:

```bash
alias mko='mk --raise'      # Open with raise
alias mkr='mk --refresh all' # Refresh all
```

### Skripte

Verwenden Sie `mk` in Shell-Skripten zur Automatisierung:

```bash
#!/bin/bash
# Watch a file and stream changes to Marked
fswatch -o document.md | while read; do
  cat document.md | mk
done
```

### Arbeitsabläufe

Kombinieren Sie es mit anderen Tools:

„Bash
# Zwischenablage in Markdown umwandeln und Vorschau anzeigen
pbpaste | Abschlag | mk

# Suchen und Vorschau
grep -r "TODO" . | Kopf -20 | mk
„

## Open Source

Das Befehlszeilentool `mk` ist Open Source und unter GitHub verfügbar:

**https://github.com/ttscoff/mk**

Sie können:
- Sehen Sie sich den Quellcode an
- Tragen Sie zu Verbesserungen bei
- Probleme melden
- Bei Bedarf aus dem Quellcode erstellen

Das Tool ist in Swift geschrieben und kann mit Xcode kompiliert werden. Anweisungen zum Erstellen finden Sie unter [README](https://github.com/ttscoff/mk).

## Version

Überprüfen Sie Ihre installierte `mk` Version mit:

```bash
mk --version
```

## Verwandte Funktionen

– Weitere Informationen zum URL-Schema von Marked finden Sie unter [URL Handler](URL_Handler)
– Weitere Informationen zur Streaming-Vorschaufunktion finden Sie unter [Streaming Preview](Streaming_Preview)
- Siehe [Workflow Integration](Workflow_Integration) für Automatisierungsbeispiele