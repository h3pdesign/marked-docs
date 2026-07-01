# <%= @title %>

Optionen im {% prefspane General %}:

![Settings: General][1]

[1]: images/screenshots/preferences-General.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Fenster

Lassen Sie oben neue Fenster
: Neue Fenster automatisch so einstellen, dass sie über anderen Anwendungen schweben.

Fenster bei Aktualisierung öffnen
: Wenn eine Änderung in einer überwachten Datei erkannt wird, wird das Vorschaufenster für dieses Dokument über andere Fenster auf Ihrem Desktop angezeigt, ohne dass Marked aktiviert wird.

Im Hintergrund durchscheinend
: Das Fenster ausblenden, wenn es nicht fokussiert ist. Verwenden Sie den Schieberegler, um die Deckkraft einzustellen.

Deaktivieren Sie speicherintensive Funktionen für große Dokumente
: Deaktivieren Sie einige prozessorintensive Funktionen, z. B. ausblendbare Überschriften, wenn Dokumente über 100 KB groß sind.

Neue Dokumente werden geöffnet
: Wählen Sie **Windows**, **Tabs** oder **Automatisch** (folgen Sie den macOS-Systemeinstellungen für Tabs). Wenn Sie Tabulatoren verwenden, navigieren Sie mit {% kbd cmd shift [/] %} und [Quick Open panel](Quick_Open.html).

Bringen Sie das aktualisierte Dokument in den Vordergrund
: Wenn eine Vorschau aktualisiert wird, wählen Sie ihre Registerkarte aus oder ordnen Sie ihr Fenster nach vorne **nur innerhalb von Marked**. Wenn sich eine andere Anwendung im Vordergrund befindet (z. B. Ihr Texteditor), bleibt Marked im Hintergrund – die richtige Registerkarte ist ausgewählt, sodass sie bereit ist, wenn Sie wieder zu Marked wechseln. Um die Vorschau über allen Anwendungen anzuzeigen, ohne Marked zu aktivieren, verwenden Sie stattdessen **Fenster bei Aktualisierung vergrößern**.

Den Fokus wieder auf die vorherige App richten
: Wenn diese Option aktiviert ist und eine Raise/Bring-on-Update-Aktion dazu führt, dass Marked den Vordergrundfokus übernimmt, wird der Tastaturfokus auf die App zurückgesetzt, die vor dem Update ganz vorne war (z. B. Ihr Texteditor). Wenn diese Option deaktiviert ist, führt Marked diese Fokusübergabe niemals durch. Wenn Marked nicht ganz vorne steht, hat diese Option keine Auswirkung.

### Statusleiste

Stilauswahl anzeigen
: Zeigt die Stilauswahl in der unteren Leiste des Vorschaufensters an.

Wortanzahl anzeigen
: Wortanzahl (und Statistikschaltfläche) in der unteren Leiste des Vorschaufensters anzeigen.

Wortanzahl ausgeschlossen
: Bei der Berechnung der Wortanzahl können alle Kombinationen von Folgendem ignoriert werden:

- **Fußnoten/Zitate**
- **Blockzitate**
- **Eingerückte Codeblöcke** (umzäunte Codeblöcke sind immer ausgeschlossen)
- **Bildunterschriften**

### Verknüpfungen

Klicken Sie auf das Verknüpfungsfeld, um eine Tastenkombination aufzuzeichnen, die ein Ereignis auslöst:

Aktivieren Sie Marked
: Wechseln Sie zu Marked, wenn dieser Hotkey in einer beliebigen Anwendung gedrückt wird.

Öffnen Sie das erste Fenster
: Bringt das vorderste (letzte aktive) Vorschaufenster Marked in den Vordergrund, ohne die aktuelle Anwendung zu verlassen.

Aktionspalette öffnen
: Öffnen Sie die Befehlspalette [Quick Actions](Quick_Actions.html), während Marked aktiv ist. Diese Verknüpfung gilt für {% appmenu File, Quick Actions… %} und funktioniert nur innerhalb von Marked (nicht aus anderen Anwendungen).

Warnungen zurücksetzen
: Stellen Sie alle Warndialoge wieder her, die Sie zuvor geschlossen haben, damit sie erneut angezeigt werden können.