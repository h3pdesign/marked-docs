# <%= @title %>

Marked enthält ein Wiki-Navigationssystem, mit dem Sie mithilfe einfacher `[[wiki]]`-Links schnell zwischen verwandten Textdateien wechseln können. Dieses System ist für eine nahtlose Navigation konzipiert und funktioniert am besten, wenn es so konfiguriert ist, dass Links im aktuellen Fenster geöffnet werden.

## Optimale Einstellungen

Um die Wiki-Verknüpfung zu verwenden, aktivieren Sie **Konvertieren `[[wiki links]]`** in {% prefspane Preview %} und legen Sie die Standarderweiterung fest, die Marked bei der Suche nach passenden Dateien verwendet.

Um das beste Erlebnis zu erzielen, setzen Sie **"Links zu Textdateien sollten geöffnet werden in:"** auf *"das aktuelle Fenster"* in {% prefspane Apps %}. Dadurch wird sichergestellt, dass sich die Navigation natürlich anfühlt und die Geschichte erhalten bleibt.

Wenn **Hervorheben von Markdown-Syntaxfehlern** in {% prefspane Proofing %} aktiviert ist, wird die `[[wiki link]]`-Syntax, die nicht mit einem Dateinamen im aktuellen Verzeichnis übereinstimmt, rot hervorgehoben, um anzuzeigen, dass eine referenzierte Datei nicht vorhanden ist. Diese Hervorhebungen werden aktualisiert, wenn Dateien hinzugefügt werden, jedoch erst, nachdem die aktuelle Datei gespeichert oder neu geladen wurde. Wenn Sie auf einen hervorgehobenen Link zu einer fehlenden Datei klicken, wird Ihnen angeboten, eine neue Datei für Sie zu erstellen und bei Bedarf die Standarderweiterung anzuhängen. Die neue leere Datei wird in Marked geöffnet, und wenn „Neue Dokumente bearbeiten“ aktiviert ist, wird Ihr Editor mit der neuen Datei geöffnet.

## Wie Wiki-Links funktionieren

- **Wiki-Links** verwenden das Format: `[[wiki link]]`.
- Wenn Sie auf einen Wiki-Link klicken, sucht Marked nach einer passenden Datei im **gleichen Verzeichnis** wie das aktuelle Dokument.
- Die Datei muss die in den Einstellungen von Marked angegebene Erweiterung haben (z. B. `.md`), es sei denn, Sie geben im Link einen vollständigen Dateinamen mit Erweiterung an (z. B. `[[notes.txt]]`).
- Wenn Sie für den Link einen vom Dateinamen abweichenden Text verwenden möchten, fügen Sie ihn nach einem Pipe (`|`) im Link ein, z. B. `[[wiki linking|A note about linking]]`, das als `[A note about linking](wiki-link.md)` angezeigt wird.
- Wenn ein Wiki-Link mit einem `#` beginnt, wird er als Ankerlink auf derselben Seite angezeigt. Ankernamen werden durch Kleinschreibung normalisiert und alle Leerzeichen werden durch Bindestriche ersetzt. Für Prozessoren, die Header-IDs ohne Bindestriche erstellen (wie MultiMarkdown), z.B. `## wiki links` erhält die ID `wikilinks`, diese Navigation könnte kaputt gehen. Geben Sie in diesen Fällen die richtige Link-ID an, bei Bedarf mit einem Pipe- und Titel, z. B. `[[#wikilinks|#wiki links]]`.

### Passende Dateinamen

Wenn Sie einen Link wie `[[wiki link]]` verwenden, sucht Marked nach einer Datei mit einem der folgenden Namen (vorausgesetzt, Ihre Standarderweiterung ist `.md`):

- `wiki link.md`
- `WikiLink.md`
- `wiki-link.md`
- `Wiki-Link.md`
- `wiki_link.md`
- `Wiki_Link.md`
- `wikilink.md`
- `WikiLink.md`
- (und andere Kombinationen aus Leerzeichen, Bindestrichen, Unterstrichen und Großbuchstaben)

**Bei allen Übereinstimmungen wird die Groß-/Kleinschreibung nicht beachtet und sie sind mit Trennzeichen flexibel.**
Wenn Sie im Link eine Erweiterung angeben (z. B. `[[notes.txt]]`), sucht Marked genau nach dieser Datei.

## Backlinks

Wenn eine Textdatei geöffnet wird und die Wiki-Navigation aktiviert ist, werden die restlichen Dateien im Verzeichnis nach `[[links]]` für die aktuelle Datei durchsucht. Dies geschieht im Hintergrund und das geöffnete Dokument wird mit einer Liste der Backlinks aktualisiert, sofern welche gefunden werden. Um die Backlinks anzuzeigen, muss die Kommentarseitenleiste geöffnet sein. Wenn es geschlossen ist, verwenden Sie das Zahnradmenü („Korrekturprüfung->Kommentare anzeigen**) oder drücken Sie {% kbd ^@c %}, um es zu öffnen.


## Navigationsverlauf

Marked verfolgt Ihre Navigation über Wiki-Links und ermöglicht Ihnen, sich **vor- und zurück** durch Ihren Dateiverlauf zu bewegen – genau wie ein Webbrowser.

- **Zurück:** {% kbd @[ %}
- **Weiterleiten:** {% kbd @] %}

Sie können auch das Menü **Verlauf** verwenden, um zu einer zuvor besuchten Datei zu springen.