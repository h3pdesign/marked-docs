# <%= @title %>

Optionen im {% prefspane Advanced %}:

![Settings: Advanced][1]

[1]: images/screenshots/preferences-Advanced.jpg @2x width=689px height=1031px class=preferencepane-scroll

YAML und Pandoc-Metadaten
: - __Ignore:__ Belässt es genau so, wie es im Dokument vorhanden ist. Dies ist nützlich, wenn Ihr Prozessor oder Präprozessor tatsächlich den YAML verwendet.
: - __Entfernen vor dem Rendern__: Der YAML-Block wird entfernt
: - __Treat as MMD metadata:__ Konvertiert den YAML- oder Pandoc-Metadatenblock in das MultiMarkdown-Format.

Entfernen Sie MultiMarkdown-Metadaten-Header
: Wenn dies aktiviert ist, werden die MultiMarkdown-Metadaten oben im Dokument vor dem Rendern entfernt.
: Dies kann nützlich sein, wenn Sie einen Nicht-MultiMarkdown-Prozessor verwenden, der andernfalls die Metadaten im gerenderten Dokument anzeigen würde. Die Metadaten werden vor dem Entfernen noch gelesen, sodass die Marked-spezifische Syntax weiterhin erkannt wird.

Gehostete Bilder zwischenspeichern
: Marked speichert Bilder in der Vorschau standardmäßig nicht zwischen, da diese Bilder auf Änderungen überwacht und sie sofort aktualisiert werden. Wenn Sie Bilder verwenden, auf die über eine Web-URL verwiesen wird, können Sie die Zwischenspeicherung dieser Bilder aktivieren, um das Rendern bei langsameren Verbindungen zu beschleunigen.

Analysieren Sie Lesbarkeitsstatistiken
: Wenn Sie [statistics](Document_Statistics.html) lieber nicht berechnen lassen möchten, wird diese Verarbeitung dadurch deaktiviert. Dies kann bei sehr großen Dokumenten zu einigen Leistungsverbesserungen führen. Die Zeichen-, Wort- und Satzzählung funktioniert weiterhin.

Verwenden Sie die systemweite Find-Pasteboard-Funktion
: Mit dieser Option kann Marked den Suchbegriff übernehmen, den Sie zuletzt in einem anderen Editor verwendet haben, und alles, was in Marked gesucht wird, wird auch in anderen Anwendungen zur Suche. Durch Deaktivieren wird die Suchfunktion von Marked unabhängig.

Verwenden Sie {% kbd cmd E %} für „Mit Auswahl suchen“.
: Standardmäßig öffnet {% kbd cmd E %} den Standardeditor. Wenn diese Option aktiviert ist, funktioniert {% kbd cmd E %} wie in den meisten Textbearbeitungsanwendungen und verwendet den ausgewählten Text für die Suche. Das Öffnen im Editor kann mit {% kbd opt cmd E %} ausgelöst werden.

Debug-Modus
: Aktiviert die Debug-Protokollierung. Verwenden Sie dies für Ihre eigene Fehlerbehebung und wenn Sie ein Problem melden. Wählen Sie __Hilfe->Debug-Protokoll öffnen__, um die Aktivität anzuzeigen.
: Bei der Einstellung _Alle_ werden Informationsmeldungen, Warnungen und Fehlermeldungen angezeigt. Sie können auch festlegen, dass nur Fehler oder Fehler und Warnungen angezeigt werden.

Sicherung der Einstellungen
: Sie können Ihre Einstellungen in einer JSON-Datei sichern, mit der Sie Einstellungen wiederherstellen oder auf einen neuen Computer portieren können.