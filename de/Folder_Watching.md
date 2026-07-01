# <%= @title %>

Legen Sie einen **Ordner** mit Klartextnotizen auf Marked ab. Marked öffnet ein Vorschaufenster, das immer die **zuletzt bearbeitete** geeignete Datei in diesem Ordner verfolgt (.md, .txt, .markdown usw., entsprechend den Dateitypfiltern von Marked).

Updates werden immer dann ausgeführt, wenn eine überwachte Datei gespeichert wird: Wenn die neueste Datei mit der vorherigen übereinstimmt, scrollt Marked in Richtung des erkannten Bearbeitungsbereichs; Wenn Sie zwischen Dokumenten wechseln, wechselt die gesamte Vorschau zur aktiven Datei.

## Funktioniert gut mit nvUltra, nvALT und ähnlichen Tools

Notebook-Apps, die einzelne Dateien auf der Festplatte belassen (klassische Bibliotheken im **nvALT**-, **nvUltra**-, **Notational Velocity**-Stil, synchronisierte Git-Ordner, Dropbox-Scratch-Ordner usw.) lassen sich auf natürliche Weise mit der Ordnerüberwachung kombinieren – Sie schreiben in ein Fenster und lassen Marked daneben angeheftet, ohne die Vorschau manuell erneut zu öffnen.

**nvUltra** bietet in seinem Kontextmenü auch **[Preview File(s) in Marked](nvUltra.html)** an, wenn Sie bestimmte Notizen in Marked direkt öffnen möchten, anstatt Marked an den oben beschriebenen Überwachungsablauf für den gesamten Ordner anzuhängen.

Marked zeigt das gleiche Beobachterverhalten auch unter anderen Menünamen, wenn Sie viele kleine Kapitel zu einem Leseerlebnis zusammenfassen; siehe auch [Multi-File Documents](Multi-File_Documents.html) für Manuskripte, die absichtlich mehrere Markdown-Quellen zusammenführen.