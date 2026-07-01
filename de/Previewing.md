# <%= @title %>

I> Auf dieser Seite geht es um die *Darstellung* der Vorschau --- Stile, Zoom, Dunkelmodus und die Statusleiste. Informationen zum Einrichten der Live-Vorschau in Ihrem Editor finden Sie unter [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html).

Ändern Sie die Art und Weise, wie Sie Dinge sehen.

## Einen Stil auswählen

![][1]

   [1]: images/StylePicker.jpg @2x width=896px height=195px class=center

Sie können im {% prefspane Style %} einen Standardstil für neue Dokumente festlegen. Wenn Sie das Stilmenü in der Symbolleiste in den Fenstereinstellungen aktiviert haben, können Sie den Stil direkt im Vorschaufenster für jedes Dokument anpassen. Ihre Stilauswahl wird gespeichert und ist die erste Wahl für Export- und Druckoptionen.

Custom Stile, die in den Stileinstellungen hinzugefügt wurden, sind in beiden Menüs verfügbar.

Stile können mit Tastaturkürzeln ausgewählt werden. Öffnen Sie das Stilmenü, um die Tastenkombination für jeden Stil anzuzeigen. Tastaturkürzel werden in der Reihenfolge der Stile zugewiesen: Auf die ersten 9 Stile in der Liste kann mit {% kbd cmd 1 %} -- {% kbd cmd 9 %} zugegriffen werden, auf die nächsten 10 Stile mit {% kbd cmd opt 1 %} -- {% kbd cmd opt 0 %} usw.

## Gliederungsmodus

Wenn es sich bei Ihrem Dokument um eine hierarchische Liste handelt, die beispielsweise aus einer Mindmap oder einer Gliederungsanwendung generiert wurde, können Sie den Gliederungsmodus im Zahnradmenü aktivieren, um eine spezielle Formatierung im APA- oder Dezimal-Gliederungsstil anzuwenden.

Der automatische Gliederungsmodus kann für bestimmte Dateierweiterungen im {% prefspane Style %} aktiviert werden.

## Textzoom

![][2]

   [2]: images/textzoom.jpg @2x width=800px height=414px class=center

Sie können die Textgröße mit {% kbd cmd shift + %} und {% kbd cmd shift - %} ändern oder das Zoom-Menü unter Vorschau in der Menüleiste oder im Zahnradmenü im Dokumentfenster verwenden. Marked merkt sich alle von Ihnen vorgenommenen Änderungen für das nächste Mal (und jedes Mal). Setzen Sie den Zoom mit {% kbd cmd 0 %} auf 100 % zurück (oder greifen Sie im Zoom-Menü auf **Zoom Reset** zu).

## Dunkler Modus/Hoher Kontrast

Wenn Sie hellen Text auf dunklem Hintergrund bevorzugen, ist Marked genau das Richtige für Sie. Im Menü „__Vorschau__“ können Sie mit {% appmenu Preview, Dark Mode ({{opt}}{{cmd}}I) %} die Farben eines der Standardschemata umkehren, um ein Hell-auf-Dunkel-Ergebnis zu erzielen, und wenn ein benutzerdefiniertes Design [built properly](Writing_Custom_CSS.html) ist, funktioniert es auch dort.

## Statusleiste ein-/ausblenden

Die Statusleiste am unteren Rand des Vorschaufensters kann mit dem Menüpunkt {% appmenu Preview, Show Status Bar ({{ctrl}}/) %} umgeschaltet werden. Wenn es ausgeblendet ist, können Sie es anzeigen und mit ihm interagieren, indem Sie mit der Maus über den Bereich unten in der Vorschau fahren.