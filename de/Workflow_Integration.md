# <%= @title %>

## AppleScript

Marked enthält ein vollständiges [AppleScript dictionary](AppleScript_Support.html) zum Öffnen von Dateien, zum Steuern der Vorschau (Neuladen, Scrollen, Hervorheben, Autoscrollen, Schnelllesen), zum Lesen von Statistiken, zum Festlegen von Prozessoren, zum Kopieren von HTML oder RTF, zum Ändern von Vorschaustilen und zum Exportieren nach Markdown, HTML, PDF, EPUB, DOCX, ODT, TextBundle, RTF und OPML. **Vorschauüberschriften/Inhaltsverzeichnis** über AppleScript ist [documented as work in progress](AppleScript_Support.html#table-of-contents-work-in-progress) und noch nicht zuverlässig.

Sie können auf die Anwendung, ein bestimmtes Fenster oder ein Dokument abzielen. Zu den Anwendungsbefehlen gehören **Streaming-Vorschau öffnen**, **Vorschau der Zwischenablage** und **Alle schließen**. Zu den Dokumentbefehlen gehören **Statistiken abrufen** und **Mit Profil drucken**. Exportbefehle akzeptieren ein optionales Export-**Profil** oder einen **`with`**-Datensatz für Optionen wie Vorschau **Stil**, **Seitengröße** und **Ränder**. Zum Beispiel:

```applescript
tell application "Marked"
	tell document 1
		export paginated pdf to "/path/to/output.pdf" with {style:"Amblin", pageSize:"A4", margins:"1in"}
	end tell
end tell
```

Unter [AppleScript Support](AppleScript_Support.html) finden Sie die Befehlsliste, Randkurzschrift, Sandbox-Hinweise und Debugging-Tipps.

Durch die AppleScript-Integration können Anwendungen wie Tags.app auch direkt in Marked ausgeführt werden.

{% note %}
## Verknüpfungen

Marked enthält natives [Shortcuts actions](Shortcuts_Integration.html) auf macOS 13 oder höher. Verwenden Sie **Datei öffnen und exportieren** für Workflows vom Finder nach PDF, **Dokument exportieren** für alles, was bereits in Marked geöffnet ist, oder **Vorschaustil festlegen**, um Designs vor dem Export zu ändern. Exportaktionen akzeptieren **Profile**, Vorschau-**Stile** und Optionen wie **Seitengröße**, **Ränder** und **Schriftgröße** (gleiche Semantik wie AppleScript `with`-Datensätze).

[shortcuts]: Shortcuts_Integration.html
{% endnote %}

## URL-Handler

Der [Marked URL handler][urlhandler] ermöglicht eine umfassende Integration durch einfaches Aufrufen von URLs, entweder über AppleScript oder mit einem einfachen `open`-Befehl in einem Shell-Skript.

## Marked Bonuspaket

Das Marked Bonus Pack ist eine Sammlung von Skripten, Befehlen und Diensten. Einige funktionieren mit mehreren Editoren, andere sind spezifisch für bestimmte Editoren. Die Dienste funktionieren im Allgemeinen mit jedem Editor, der über die erforderlichen Fähigkeiten verfügt. Der Rest ist in Ordnern organisiert, die auf der Anwendung basieren, mit der sie arbeiten.

Sie können das Bonuspaket herunterladen und Anweisungen zur Installation und Verwendung finden Sie in diesem [knowledge base article](http://support.markedapp.com/kb/how-to-tips-and-tricks/marked-bonus-pack-scripts-commands-and-bundles).

[urlhandler]: URL_Handler.html
[applescript]: AppleScript_Support.html

