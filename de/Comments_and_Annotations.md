# <%= @title %>

Marked verfügt über eine spezielle Behandlung für Kommentare und Anmerkungen.

## Anmerkungsquellen

Marked erkennt Kommentare von:

- Markdown Fußnoten
- CriticMarkup Kommentare
- Kommentare und Änderungen zu Microsoft Word

## Die Kommentar-Seitenleiste

Alle Anmerkungen werden in einer Seitenleiste angezeigt und in der Dokumentvorschau ausgeblendet. Um die Anmerkungsseitenleiste anzuzeigen, verwenden Sie das **Zahnradmenü -> Prüfung -> Kommentare anzeigen** oder drücken Sie {% kbd ctrl cmd C %}.

![A footnote in the Comments  Sidebar][sidebar]

  [sidebar]: images/comment-sidebar-800.jpg @2x width=800

Wenn Sie mit der Maus über einen Kommentar in der Seitenleiste fahren, wird eine Linie zu seiner Position im Dokument gezeichnet. Bei Fußnoten zeigt dies an, wo die Fußnote im Text vorkommt. Bei Kommentaren wird auf die ursprüngliche Position des Kommentars verwiesen, bei der es sich möglicherweise um eine Leerstelle in der Vorschau handelt.

Wenn Sie in der Seitenleiste auf einen Kommentar klicken, wird eine hervorgehobene Animation angezeigt, die auf seine Position verweist.

Die Schriftart und der Stil der Seitenleiste hängen vom aktuellen Stil ab und können daher je nach Stil unterschiedlich aussehen.