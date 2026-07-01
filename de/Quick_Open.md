# <%= @title %>

Quick Open bietet schnellen Zugriff auf Ihre geöffneten Dokumente und zuletzt verwendeten Dateien.

## Öffnen Schnell öffnen

Greifen Sie mit {% kbd shift cmd O %} oder über das Menü {% appmenu File, Quick Open %} auf das Schnellöffnungsfeld zu. Das Bedienfeld erscheint als schwebendes Fenster über Ihrem aktuellen Dokument, sodass Sie schnell zwischen geöffneten Dokumenten wechseln oder zuletzt verwendete Dateien öffnen können.

![Quick Open Panel][qo]

[qo]: images/quick-open-800.jpg @2x width=800

## Dokumentabschnitte

Das Schnellöffnungsfenster organisiert Dokumente in übersichtliche Abschnitte:

### Dokumente öffnen

Oben in der Liste sehen Sie alle aktuell geöffneten Dokumente. Dokumente werden visuell nach ihrem Fenster gruppiert:

- **Fenster mit Registerkarten**: Dokumente in Fenstern mit Registerkarten zeigen als Untertitel „Fenster mit X-Registerkarten“, was angibt, wie viele Registerkarten sich in dieser Fenstergruppe befinden
- **Eigenständiges Fenster**: Dokumente in einzelnen Fenstern zeigen „Fenster“ als Untertitel

Für jedes geöffnete Dokument wird Folgendes angezeigt:
- Der Dateiname des Dokuments als Haupttitel
– Die Fenstergruppierungsinformationen als Untertitel
- Ein Dokumentsymbol

### Aktuelle Dokumente

Unterhalb der geöffneten Dokumente unterteilt ein Trennzeichen „Zuletzt verwendete Dokumente“ die Liste. Im Abschnitt „Zuletzt verwendete Dokumente“ werden bis zu 10 Ihrer zuletzt geöffneten Dateien angezeigt, die derzeit nicht geöffnet sind. Für jedes aktuelle Dokument wird Folgendes angezeigt:

- Der Dateiname des Dokuments als Haupttitel
- „Neueste“ als Untertitel
- Ein Dokumentsymbol

### Andere öffnen

Unten in der Liste können Sie mit der Option „Andere öffnen…“ die Standard-Dateiauswahl von macOS öffnen, um eine beliebige Datei auszuwählen. Diese Option zeigt Folgendes an:

- „Open Other…“ als Haupttitel
- „Öffne eine Datei oder einen Ordner“ als Untertitel
- Ein Ordnersymbol

## Suchen und Filtern

Geben Sie oben im Bedienfeld das Suchfeld ein, um die Liste in Echtzeit zu filtern. Die Suche entspricht:

- Dokumentdateinamen
- Vollständige Dateipfade

Während Sie tippen, wird die Liste sofort aktualisiert und zeigt nur passende Dokumente an. Die Option „Andere öffnen…“ bleibt immer unten in den gefilterten Ergebnissen sichtbar.

## Tastaturnavigation

Navigieren Sie im Quick Open-Bereich vollständig mit Ihrer Tastatur:

- **Pfeiltasten ↑/↓**: Durch die Liste nach oben und unten bewegen
- **Zurück**: Öffnet das ausgewählte Dokument oder die ausgewählte Option
- **Escape**: Schließen Sie das Schnellöffnungsfeld
- **Befehl (⌘)**: Halten Sie gedrückt, um Dateipfade anzuzeigen (siehe unten)

## Dateipfade anzeigen

Halten Sie die **Befehlstaste (⌘)** gedrückt, während das Schnellöffnungsfenster geöffnet ist, um den vollständigen Dateipfad für jedes Dokument im Untertitelbereich anzuzeigen. Pfade in Ihrem Home-Verzeichnis werden mit der Abkürzung `~` angezeigt (z. B. `~/Documents/file.md`). Lassen Sie die Befehlstaste los, um zur normalen Ansicht mit Fenstergruppierung oder „Zuletzt“-Informationen zurückzukehren.

Dies ist besonders nützlich, wenn Sie mehrere Dateien mit demselben Namen geöffnet haben oder wenn Sie den genauen Speicherort eines Dokuments überprüfen müssen.

## Dokumente öffnen

- **Offene Dokumente**: Wenn Sie ein geöffnetes Dokument auswählen, wird dessen Fenster in den Vordergrund gebracht und zur Registerkarte dieses Dokuments gewechselt, wenn es sich in einem Fenster mit Registerkarten befindet
- **Zuletzt verwendete Dokumente**: Wenn Sie ein aktuelles Dokument auswählen, wird es in einem neuen Fenster geöffnet oder als Registerkarte hinzugefügt (abhängig von Ihrer Einstellung „Dokumente in Registerkarten öffnen“ in {% prefspane General %}).
- **Andere öffnen...**: Wenn Sie diese Option auswählen, wird das Standarddialogfeld für die Dateiauswahl von macOS geöffnet

