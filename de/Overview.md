# <%= @title %>

{% apponly div %}
*Die neueste Version dieser Dokumentation finden Sie unter [online version][help].*
{% endapponly %}

**Sehen Sie sich unbedingt die wachsende Sammlung von [Marked tutorial videos](https://www.youtube.com/playlist?list=PLNoOPRHOBV0ptk_ka386xltm3VyVw6QgZ) an.**

## Was ist Markdown?

[daringfireball]: http://daringfireball.net/projects/markdown/basics
[mmd5]: https://fletcher.github.io/MultiMarkdown-5/
[mdguide]: https://www.markdownguide.org/
[help]: http://markedapp.com/help/

Markdown ist eine grundlegende Auszeichnungssprache mit einfachen Symbolen, die es Ihnen ermöglicht, HTML mit einfacher Syntax wie `*italics*` und `**bold**` zu schreiben (und in andere Formate zu exportieren). Markdown wurde von John Gruber entwickelt und entwickelt sich schnell zum De-facto-Standard für Web-Publishing, Notizen und sogar Buchveröffentlichung. Damit können Sie ohne viele Symbolleisten und Formatierungen schreiben, indem Sie einfach Wörter auf die Seite bringen und Ihre Prozessoren (wie Marked) mit Stil und Formatierung befassen.

Marked funktioniert mit GitHub Flavored Markdown, CommonMark (GFM), Kramdown und MultiMarkdown und kann Syntax aus mehreren Varianten für die Vorschau konvertieren (es kann auch erweitert werden, um mit nahezu jedem Prozessor zu arbeiten, den Sie benötigen, einschließlich Textile, reStructuredText, Wikitext und mehr). Ich gehe davon aus, dass Sie – da Sie hier sind – mindestens eine dieser Auszeichnungssprachen kennen. Wenn nicht, sollten Sie mit [Markdown Basics][daringfireball] von John Gruber beginnen und sich [MarkdownGuide.org][mdguide] ansehen. Marked enthält im Hilfemenü eine vollständige Markdown-Syntaxanleitung.

Sie können [Markdown Dingus](x-marked-3://dingus) verwenden, um mit den verschiedenen Varianten von Markdown zu experimentieren, die Marked unterstützt.

## Was ist Marked?

Marked ist eine Live-Vorschau-App für Markdown für macOS – eine editorunabhängige (Multi)Markdown-Vorschauanwendung, die eine Datei auf Änderungen überwacht und die Vorschau bei jedem Speichern aktualisiert. Durch die Trennung und Automatisierung der Formatierungsdetails können Sie sich mehr auf das Schreiben und weniger auf die Präsentation konzentrieren und behalten gleichzeitig Ihr Endprodukt im Auge.

Informationen zu Setup-Workflows und editorspezifischen Schnellstarts finden Sie unter [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html). Eine kürzere Produktübersicht finden Sie unter [markedapp.com/markdown-preview](https://markedapp.com/markdown-preview/).

Marked funktioniert mit jeder Datei, auf die lokal zugegriffen werden kann, einschließlich iCloud-Dokumenten. Ziehen Sie einfach ein Textdokument aus der Symbolleiste eines beliebigen Editors auf Marked und es wird als HTML-Vorschau gerendert und beginnt mit der Verfolgung von Änderungen, wobei die Vorschau während des Schreibens aktualisiert wird. Es kann sogar [multi-file documents](Multi-File_Documents.html) mit einer einfachen „include“-Syntax oder aus den Indexformaten Scrivener, Leanpub und mmd_merge kompilieren.

Marked verfügt über zusätzliche Funktionen, darunter Wortanzahl und andere Dokumentstatistiken, die Möglichkeit, über anderen Anwendungen zu schweben oder im Hintergrund zu verschwinden, und es kann Ihre Arbeit in einer Vielzahl gut gestalteter Stile anzeigen. Es kann mit einem Tastendruck die Ausgabe zum Ausdrucken oder PDF, Word-Dokumente, vollständige HTML-Dokumente (einschließlich Stile und Bilder) oder HTML-Quell- oder RTF-Daten in die Zwischenablage kopieren. Marked verfügt außerdem über ein grundlegendes AppleScript-Wörterbuch und ein [URL handler](URL_Handler.html), was die Integration in Ihren Workflow erleichtert.

Oh ja, und es funktioniert mit einer Menge Ihrer Lieblings-Apps: Texteditoren von Vim und Emacs bis hin zu Sublime Text und TextMate, Markdown-Editoren wie MultiMarkdown Composer, Byword und iA Writer, sogar Apps, die Sie vielleicht nicht erwarten, wie Ulysses, Scrivener, VoodooPad, MarsEdit und mehr.

## Beispielanwendungen

Marked verwandelt jeden Texteditor in einen Markdown-fähigen Editor. Ihre Vorschau ist immer verfügbar und wird während Ihrer Arbeit aktualisiert.

* Wenn Ihr Lieblingseditor keine Live-Vorschau für Markdown bietet, öffnen Sie das Dokument, an dem Sie gerade arbeiten, in Marked und verschieben Sie das Fenster zur Seite, um ein Markdown-Schreiberlebnis mit vollem Funktionsumfang zu erhalten.
* Schreiben oder bloggen Sie gerne in MacVim oder einem anderen terminalbasierten Editor? Jetzt haben Sie während der Arbeit eine synchronisierte Markdown-Vorschau.
* Marked bietet außerdem Anzeigefunktionen, die über jede vorhandene Markdown-Vorschau hinausgehen, und kann stattdessen verwendet werden, um vollständige Wortzahl- und Dokumentstatistiken bereitzustellen, Schreibvorschläge zu machen und sogar Fehler in Ihrer Markdown-Formatierung hervorzuheben.
* Sie können Marked auch ohne Editor verwenden. Ziehen Sie einfach Markdown-Dateien auf das Symbol, um eine Vorschau anzuzeigen, sie auszudrucken und in den Quellcode PDF, DOC, RTF oder HTML zu exportieren. Marked kann auch `.rtf`- und `.rtfd`-Dateien** als Quelldokumente öffnen ([RTF and RTFD Support](RTF_Support.html)).
* In Apps mit automatischer Speicherung hält die Vorschau ohne Hilfe mit Ihrem Schreiben Schritt. Verwenden Sie es mit jedem Editor ... oder *allen* Ihrer Editoren.
* Ein Buch schreiben? Marked kann mehrere Dateien kompilieren, um eine vollständige Vorschau Ihrer Arbeit zu erhalten, und sogar die enthaltenen Dateien auf Änderungen überprüfen, wobei das Hauptdokument bei jedem Speichern aktualisiert wird. Es kann sogar einen ganzen Ordner auf Änderungen überwachen und die Vorschau automatisch auf die Datei umschalten, die Sie gerade aktualisieren. Wenn Sie bereit sind, können Sie in den Formaten EPUB, DOCX oder TextBundle veröffentlichen.
* Arbeiten Sie mit einer KI-Codierungsplattform? Öffnen Sie einen Plan- oder Dokumentationsordner in Marked und wann immer sich eine Markdown-Datei in diesem Ordner ändert, zeigt Marked sie an und scrollt automatisch zum Punkt der letzten Änderung. Marked zeigt Mermaid-Diagramme an und kann alle Arten erweiterter Syntax verarbeiten. Behalten Sie während der Arbeit den Überblick über Pläne und Dokumentation, ohne zwischen Dateien wechseln zu müssen.