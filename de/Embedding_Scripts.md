# <%= @title %>

Es gibt mehrere Möglichkeiten, zusätzliche JavaScripts in Marked einzubetten.

## Einschließlich JavaScript pro Dokument [including-javascript-per-document]

Sie können Skripte in ein einzelnes Dokument einfügen, indem Sie `<script>`-Tags im Inhalt selbst verwenden. Dies kann für Bibliotheken wie [D3](https://d3js.org/) für Datenvisualisierungen nützlich sein, die Sie nur in bestimmten Dokumenten benötigen:

```html
<script src="https://cdn.jsdelivr.net/npm/d3@7/dist/d3.min.js"></script>
```

Wenn Sie MultiMarkdown als Prozessor verwenden, können Sie Skripte in die Metadaten einschließen und diese werden in das Dokument eingefügt. Da Marked nur „Snippet“ ausgibt, ist der Schlüssel `XHTML Header` nicht ideal. Verwenden Sie stattdessen `CSS Header` und die Skripte werden am Ende des Dokuments eingefügt.

CSS-Header: <script src="file.js"></script>

Informationen dazu, wie die enthaltenen Skripte aktualisiert werden, wenn sich der Inhalt ändert, finden Sie unter [Hooks](#hooks).

## Einschließlich JavaScript [including-javascript]

Sie können Ihr eigenes JavaScript aus lokalen Dateien, CDNs oder durch Einfügen von Rohcode einbinden. Um darauf zuzugreifen, öffnen Sie {% prefspane Style %} und klicken Sie auf die Schaltfläche *Custom Regeln*.

Richten Sie eine neue Custom-Regel ein oder fügen Sie Skripts zu einer vorhandenen hinzu. Um Skripte zu jeder Datei hinzuzufügen, setzen Sie das Prädikat auf „Dateiname enthält *“.

Der Aktionseditor für eine Custom-Regel bietet drei Optionen zum Einbinden von Skripten:

Fügen Sie eine JavaScript-Datei ein
: Ermöglicht die Auswahl einer lokalen Datei, die am Ende des Dokuments eingefügt werden soll

Fügen Sie JavaScript von der URL ein
: Ermöglicht das Einfügen eines CDN oder einer anderen Remote-URL, wodurch am Ende des Dokuments ein `<script>`-Tag mit der verknüpften URL erstellt wird

Fügen Sie JavaScript ein
: Öffnet einen Code-Editor, in dem Sie Ihren eigenen JavaScript-Code schreiben/einfügen können

Diese Skripte werden am Ende der Vorschau vor dem Dokument-Tag eingefügt. Wenn Sie bei jeder Aktualisierung der Vorschau eine Init-Funktion aufrufen oder aktualisieren müssen, lesen Sie [Including Raw JavaScript](Additional_Javascript.html#rawjs) und machen Sie sich mit [hooks](#hooks) von Marked vertraut.

## Meerjungfrau und andere Skripte [mermaid]

jQuery ist standardmäßig enthalten und Sie können es in allen Skripten verwenden, die Sie mit einer der folgenden Methoden zu Marked hinzufügen.

[Mermaid](https://mermaid.js.org/intro/) für Markdown-ähnliche Diagramme ist jetzt standardmäßig in jedem Dokument enthalten. Jeder eingezäunte Codeblock mit der Sprache `mermaid` wird automatisch als Diagramm gerendert.

Unten im {% prefspane Style %} ist ein Kontrollkästchen für „Schwenk- und Zoomdiagramme“ verfügbar, wenn Mermaid-Inhalte vorhanden sind. Wenn Sie dieses Kontrollkästchen aktivieren, werden Diagramme mit {% kbd cmd %}-scroll gezoomt und durch Klicken und Ziehen verschoben. Das Skript für diese Funktion ist über ein CDN enthalten und erfordert eine Internetverbindung.

Wenn Sie eine bestimmte Bibliothek standardmäßig enthalten sehen möchten, teilen Sie mir dies bitte unter [BrettTerpstra.com forum](https://forum.brettterpstra.com/) oder über [the support site](https://support.markedapp.com/questions/add) mit.

## Haken [hooks]

Ab neueren Versionen führt Marked beim Aktualisieren von Inhalten keine vollständige Seitenaktualisierung mehr durch, sondern fügt den neuen Inhalt stattdessen in das DOM ein, ohne dass ein Seitenladen erforderlich ist. Dies bedeutet, dass eingebundene Skripts, die beim Laden der Seite ausgelöst werden, nicht erneut ausgelöst werden, wenn der Inhalt aktualisiert wird. Marked bietet eine „Hooks“-Funktion, um dies zu berücksichtigen. Um einen Hook zu registrieren, müssen Sie einen zweiten Skriptblock einschließen, der [<!--MKPH0--> function](https://markedapp.com/jsapi/Marked.hooks.html#.register__anchor) aufruft und einen Auslöser, in diesem Fall „Update“, und eine auszuführende Funktion akzeptiert.

```html
<script src="https://cdn.jsdelivr.net/npm/d3@7/dist/d3.min.js"></script>
<script>
	Marked.hooks.register('update', function() {
		// Re-run your D3 visualization when content updates
		d3.selectAll('.chart').each(function() {
			// your D3 render logic here
		});
	});
</script>
```

Alle [API functionality](https://markedapp.com/jsapi/) von Marked können in diesem Feld verwendet werden. (Sie können die API auch in allen geladenen Skripten verwenden.) Informationen zum interaktiven Debuggen und Experimentieren mit der API in einer Live-Vorschau finden Sie im Abschnitt [WebKit Inspector](Writing_Custom_CSS.html#webkitinspector) für Details zur Verwendung des Safari-Menüs „Entwickeln“ mit Marked.

Jetzt wird die übergebene Funktion immer dann ausgeführt, wenn eine Aktualisierung durchgeführt wird (immer wenn die überwachte Quelldatei gespeichert wird). Solange das von Ihnen ausgeführte Skript über eine Art Init- oder Render-Funktion verfügt, können Sie es mit einem Hook aufrufen und jedes Mal rendern lassen, wenn Ihr Dokument gespeichert und eine Aktualisierung ausgelöst wird.



*[CDN]: Content Distribution Network