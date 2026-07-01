# <%= @title %>

Sie können Ihr eigenes JavaScript aus CDNs einbinden oder Rohcode einfügen.

## Eine Anmerkung zum Marked Dirigenten

Der einfachste Weg, benutzerdefiniertes JavaScript zu implementieren, das je nach Dokumenttyp und Speicherort variiert, ist mit [Marked Conductor][conductor]. Sie können eine YAML-Konfiguration verwenden, um Skripte mithilfe von „Filtern“ anzuhängen. Weitere Informationen finden Sie unter [Conductor page][conductor] und Beispiele unter [sample config][sample config].

[conductor]: https://brettterpstra.com/projects/conductor/
[sample config]: https://github.com/ttscoff/conductor-config/

## JavaScripts von CDNs hinzufügen [cdns]

![][1]

   [1]: images/screenshots/AdditionalJavascript.jpg @2x width=592px height=576px class=center

Sie können JavaScript-CDN-URLs im Fenster „Zusätzliche Skripte“ hinzufügen, auf das Sie über {% prefspane Style %} zugreifen können. Geben Sie CDN-URLs ein, eine pro Zeile. Fügen Sie keine `<script>`-Tags ein, sondern nur die URL:

```
https://cdn.jsdelivr.net/gh/user/repo@version/file
https://cdn.jsdelivr.net/npm/micromark-extension-gfm-strikethrough@2.1.0/lib/html.min.js
```

> Beachten Sie, dass jQuery bereits im Vorschaufenster enthalten ist.

Diese Skripte werden am Ende der Vorschau vor dem Dokument-Tag eingefügt. Wenn Sie bei jeder Vorschau eine Init-Funktion aufrufen oder aktualisieren müssen, lesen Sie [Including Raw JavaScript](#rawjs). Um das DOM zu untersuchen und diese Skripte in einer Live-Vorschau von Marked zu debuggen, können Sie den Web Inspector von Safari anhängen, wie in [WebKit Inspector](Writing_Custom_CSS.html#webkitinspector) beschrieben.


### Einschließlich rohem JavaScript [rawjs]

Im unteren Textfeld des Fensters „Zusätzliche Skripte“ können Sie rohes JavaScript einfügen. Dies wird in ein `<script></script>`-Paar eingefügt, also schließen Sie es nicht in die Eingabe ein. Dieses Feld kann jeden JavaScript-Befehl enthalten, den Sie benötigen, um eine enthaltene Bibliothek zu initialisieren, DOM-Änderungen durchzuführen oder alles, was Sie in einer WebKit-Ansicht tun möchten. Zur Vereinfachung der DOM-Manipulation ist jQuery bereits enthalten.

Diese Skripte werden nur ausgeführt, wenn das Fenster zum ersten Mal geladen wird. Wenn die Vorschau aktualisiert wird, geschieht dies direkt durch Ersetzen von Teilen des DOM. Skripts, die auf den aktualisierten Inhalt reagieren müssen, sollten dies daher mit [Hooks](Embedding_Scripts.html#hooks) tun.

Fügen Sie in das Roh-JavaScript-Feld einen Aufruf wie diesen ein:

```javascript
Marked.hooks.register('update', function() { myCustomFunction(); });
```