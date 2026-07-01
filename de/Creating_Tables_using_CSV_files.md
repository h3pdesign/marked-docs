# <%= @title %>

Wenn eine über [Marked's include syntax or IA Writer block syntax][include] eingebundene Datei eine CSV- oder TSV-Erweiterung hat, versucht Marked, sie zu analysieren und in eine MultiMarkdown-Tabelle zu konvertieren. Dies funktioniert mit den meisten Standardformaten, einschließlich durch Kommas und Tabulatoren getrennter Formate sowie mit zusätzlichen Trennzeichen und Anführungszeichenformaten, die automatisch erkannt werden.

Ein Vorteil der Verwendung von CSV-Dateien anstelle des Schreibens von Markdown-Tabellen besteht darin, dass Zeilenumbrüche innerhalb von Zellen automatisch in `<br>`-Tags umgewandelt werden. Dies muss manuell durchgeführt werden, um beim Schreiben von MultiMarkdown-Tabellen Zeilenumbrüche einzuschließen, was eine zusätzliche Zeitersparnis darstellt.

Nebenbei bemerkt gibt es eine hervorragende App namens [TableFlip][], die das Bearbeiten von Tabellen in Ihrem Dokument erheblich vereinfacht. Es lohnt sich, einen Blick darauf zu werfen, wenn Sie häufig mit Tabellendaten arbeiten.

Enthaltene CSV-Dateien werden auf Änderungen überwacht, sodass zusätzliche Bearbeitungen in der ursprünglichen CSV-Datei vorgenommen werden können und Marked die Vorschau beim Speichern automatisch aktualisiert.

Konvertierte Tabellen werden in den Markdown-Export einbezogen, sodass Marked zum Kompilieren von Dokumenten mit strukturierten Daten und zum Exportieren einer einzelnen Datei verwendet werden kann.

[include]: Multi-File_Documents.html
[TableFlip]: http://tableflipapp.com/