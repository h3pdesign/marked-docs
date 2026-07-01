# <%= @title %>

[Bear][bear] kann eine Live-Vorschau direkt an Marked senden.

## Senden von Bear

Wählen Sie in Bear im Menü **Ansicht** die Option **Vorschau in Marked** (der Wortlaut kann je nach Bear-Version leicht variieren). Marked erhält einen TextBundle, sodass eingebettete Bilder und Assets im Allgemeinen mit dem Text übertragen werden.

Bilder, auf die mit absoluten Pfaden oder `https`-URLs verwiesen wird, werden ebenfalls aufgelöst, solange Marked sie erreichen kann.

## Hinweis zum Mac App Store

Wenn Sie den **Mac App Store**-Build von Marked verwenden und macOS bei der Vorschau von Bear ständig um Erlaubnis zum Öffnen von Verzeichnissen fragt, [contact Marked support](http://support.markedapp.com) für ein kostenloses Crossgrade auf die Direkt-Download-Edition, wodurch diese besondere Sandbox-Reibung vermieden wird.

## Tags

Tags im Bärenstil können als solche gerendert werden, indem unter {% prefspane Processor %} **#Text ist Tag** und **Stil-Tags** aktiviert werden.

W> Diese Einstellung kann Marked verwirren, wenn Sie normale Überschriften ohne Leerzeichen nach dem `#` schreiben.

## Dateinamen und Export

Wenn Sie **Erstes H1 als Fallback-Titel verwenden** in {% prefspane Export %} aktivieren, kann dieser Titel den Dateinamen und den Platzhalter `%title` steuern, wenn Sie PDFs aus Marked drucken oder exportieren.

I> Ein Vorschaustil, der Bears eigenem Aussehen nahekommt [is available on markedapp.com/styles](https://markedapp.com/styles/preview?style=bear).

Die Streaming-Vorschau von Bear ist auf der Seite [Streaming Preview](Streaming_Preview.html) und in [Additional app integrations](Additional_Application_Support.html) zusammengefasst.

[bear]: https://bear.app/
