# <%= @title %>

Marked verwendet viel JavaScript, um die in der Vorschau angebotenen Funktionen bereitzustellen. Aus diesem Grund können einige Komplikationen auftreten, wenn Skripte in den Hauptteil des Dokuments eingefügt werden.

## Externe Skripte

Sie können einige externe Skripte mithilfe der Metadatenzeile „CSS Header:“ oben in Ihrem Dokument einbinden. Diese Skripte werden jedoch nicht in der Kopfzeile, sondern in der Fußzeile eingefügt, nachdem die Skripte von jQuery und Marked bereits geladen wurden. Dies ist in den meisten Fällen ideal. Es kann dennoch zu unerwartetem Verhalten kommen, da Marked nicht alle möglichen Skriptkonflikte kompensieren kann. DOM-Änderungen können besonders problematisch sein.

CSS-Header: <script src="file.js"></script>

## Inline-Includes

Es gibt viele Anwendungen, mit denen JavaScript im Hauptteil eines Dokuments angezeigt werden kann, beispielsweise Diagrammgeneratoren oder andere Canvas-Tools. Abhängig von den Konfigurationseinstellungen und dem verwendeten Prozessor sind diese häufig fehlerhaft. Die Lösung besteht darin, Ihr Skript und zusätzliche DOM-Elemente in einer externen Datei abzulegen und die Syntax von Marked für ["raw" include files][syntax] zu verwenden. Diese Dateien werden in keiner Weise verarbeitet; Ihr Inhalt wird der Datei hinzugefügt, nachdem die restliche Verarbeitung abgeschlossen ist.

Markdown Text.

<<{file.html}

Mehr Markdown Text...

Zum Experimentieren und Debuggen des JavaScript, das in der Vorschau von Marked ausgeführt wird, können Sie den Web Inspector von Safari mit den Schritten in [WebKit Inspector](Writing_Custom_CSS.html#webkitinspector) an das Vorschaufenster anhängen.

[syntax]: Special_Syntax.html#includingunprocessedtextorhtml
