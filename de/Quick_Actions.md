# <%= @title %>

Die Schnellaktionspalette ist ein durchsuchbarer Befehlsstarter für Marked. Es sammelt Aktionen aus der Hauptmenüleiste und dem Vorschau-**Zahnradmenü** sowie Tastaturbefehle, die nur in der Vorschau verfügbar sind und nicht in Menüs angezeigt werden (z. B. **Autoscroll**). Verwenden Sie es, wenn Sie wissen, was Sie tun möchten, sich aber nicht erinnern können, in welchem ​​Menü es enthalten ist.

## Öffnen der Schnellaktionspalette

Öffnen Sie die Palette mit {% kbd shift cmd P %} oder von {% appmenu File, Quick Actions… %}. Das Bedienfeld erscheint als schwebendes Fenster über Ihrem aktuellen Dokument.

Drücken Sie dieselbe Tastenkombination erneut oder drücken Sie **Escape**, um die Palette zu schließen. Wenn die Palette bereits geöffnet ist, wird sie auch durch Auswahl von **Schnellaktionen…** aus dem Menü geschlossen.

## Customisieren der Verknüpfung

Die Standardverknüpfung ist {% kbd shift cmd P %}. Um es zu ändern, öffnen Sie {% prefspane General %} und zeichnen Sie eine neue Kombination unter **Aktionspalette öffnen** im Abschnitt **Verknüpfungen** auf.

Im Gegensatz zu **Aktivieren Sie Marked** und **Erstes Fenster öffnen** funktioniert die Schnellaktionsverknüpfung nur, wenn Marked die aktive Anwendung ist. Dadurch wird die Menüverknüpfung {% appmenu File, Quick Actions… %} entsprechend Ihrer Einstellung aktualisiert.

## Suchen und Filtern

Geben Sie oben im Bedienfeld das Suchfeld ein, um Befehle in Echtzeit zu filtern. Matching ist unscharf und nachsichtig:

- Wortreihenfolge spielt keine Rolle (`view source` entspricht **Quellenansicht umschalten**)
- Initialen funktionieren gut (`sv` entspricht **Quellansicht**)
- Reduzierter Abgleich findet Befehle ohne Leerzeichen (`akdoc` entspricht **Ask About Document**)

Bei jedem Ergebnis wird links der Befehlsname und rechts die entsprechende Tastenkombination (sofern verfügbar) in Grau angezeigt. Einige Befehle zeigen auch einen Breadcrumb-Pfad an (z. B. `Preview › Autoscroll`), wenn die Aktion aus einem Untermenü oder der Vorschau-Engine stammt.

## Was in der Liste erscheint

Die Palette umfasst:

- **Menübefehle** aus der Hauptmenüleiste, einschließlich dynamischer Menüs wie **Stil**, **Verlauf** und offene **Fenster**-Registerkarten
- **Zahnradmenü**-Befehle aus dem Vorschaufenster
- **Vorschau-Verknüpfungen** aus der Tastaturbelegung in der Vorschau (dieselben Befehle, die im Vorschau-Hilfe-HUD angezeigt werden), einschließlich Navigation, Autoscroll, Lesezeichen, Suche und anderen Nur-Vorschau-Aktionen

Wenn derselbe Befehl an mehr als einer Stelle erscheint, zeigt Marked den kürzesten Menüpfad an und führt Verknüpfungsinformationen aus Duplikaten zusammen.

## Tastaturnavigation

Navigieren Sie in der Schnellaktionspalette vollständig über die Tastatur:

- **Pfeiltasten ↑/↓**: Durch die gefilterte Liste navigieren
- **Zurück**: Den ausgewählten Befehl ausführen
- **Escape**: Schließen Sie die Palette
- **⌘-Tastenkombinationen**: Schließen Sie die Palette und führen Sie den entsprechenden Menübefehl aus (drücken Sie beispielsweise {% kbd cmd U %}, um **Quellansicht umschalten** auszuführen, anstatt ihn in der Liste auszuwählen).

Durch einfache Eingabe (ohne Befehlstaste) wird das Suchfeld gefiltert. Nur in der Vorschau verfügbare Einzeltastenkürzel wie `s` für Autoscroll filtern die Liste; Drücken Sie **Return**, um den ausgewählten Befehl auszuführen.

## Befehle ausführen

Durch die Auswahl eines Menübefehls wird dieser auf die gleiche Weise ausgelöst wie durch die Auswahl aus dem Menü, einschließlich dynamischer und Zahnradmenüelemente.

Wenn Sie eine **Vorschauverknüpfung** auswählen, wird die zugehörige Aktion in der aktiven Vorschau ausgeführt (z. B. das Umschalten des automatischen Bildlaufs oder das Springen zur nächsten Kopfzeile). Für diese Befehle ist ein geöffnetes Dokument mit Vorschau erforderlich. Wenn keine Vorschau verfügbar ist, wird die Palette weiterhin geöffnet, Aktionen, die nur in der Vorschau erfolgen, haben jedoch keine Auswirkung.

Informationen zum entsprechenden Dateiwechsel finden Sie unter [Quick Open](Quick_Open.html). Die vollständige Tastaturreferenz für die Vorschau finden Sie unter [Keyboard Shortcuts](Keyboard_Shortcuts.html) oder drücken Sie in der Vorschau {% kbd h %}, um das Hilfe-HUD anzuzeigen.