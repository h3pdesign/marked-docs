# <%= @title %>

Marked funktioniert mit [Obsidian][obsidian-app]-Notizen auf zwei Arten: Öffnen Sie einen **Tresorordner** für automatisches Verfolgen oder verwenden Sie das **Community-Plugin** für eine engere Synchronisierung.

Die integrierte Vorschau von Obsidian ist ideal, wenn Sie die App nie verlassen. Wählen Sie Marked, wenn Sie einen Export in Veröffentlichungsqualität, erweitertes Korrekturlesen, benutzerdefinierte CSS-Designs oder denselben Live-Vorschau-Workflow für mehrere Editoren wünschen. Einen vollständigen Vergleich finden Sie unter [Marked vs Obsidian Preview](Marked_vs_Obsidian_Preview.html).

## Öffnen Sie einen gesamten Tresor

Ziehen Sie den **Tresorordner** (das Verzeichnis, das den versteckten Konfigurationsordner von Obsidian im Tresorstammverzeichnis enthält) auf Marked im Dock. Marked überwacht diesen Baum, behält die **zuletzt bearbeitete** Notiz in der Vorschau und aktualisiert sie, während Sie in Obsidian speichern.

Fügen Sie für Tresor-spezifische Standardeinstellungen (Stil, Prozessor, Basis-URL für Bilder usw.) ein [Custom Rule](http://support.markedapp.com) hinzu, das den Pfaden unter diesem Tresor entspricht.

## Obsidian-Callout-Syntax

Wenn der MultiMarkdown-Prozessor ausgeführt wird, konvertiert Marked gängige **Callouts im Obsidian-Stil** (das `> [!note]`-Muster) in stilisierte Blockmarkierungen, sodass sie mit dem Rest Ihrer Vorschau übereinstimmen.

## Marked 3 Obsidian-Plugin

Der [Marked 3 Obsidian plugin][plugin] kann die aktuelle Notiz oder den gesamten Tresor mit Befehlen oder Hotkeys öffnen, sodass das Fenster Marked verfolgt, was Sie bearbeiten. Verwenden Sie die Befehlspalette (**⌘P**) und suchen Sie nach **Marked** oder weisen Sie Hotkeys in den **Hotkeys**-Einstellungen von Obsidian zu.

### Installation über Community-Plugins

Öffnen Sie in Obsidian **Einstellungen → Community-Plugins**, durchsuchen oder suchen Sie nach **markiert** und installieren Sie **In Marked öffnen**.

### Manuelle Installation des Plugins

Wenn Sie lieber ab GitHub installieren möchten:

1. Laden Sie `main.js` und `manifest.json` vom [latest release][plugin-releases] auf GitHub herunter (oder erstellen Sie sie aus dem [Marked3-obsidian][plugin] Repository).
2. Erstellen Sie in Ihrem Tresor den Plugin-Ordner unter `plugins/` im Konfigurationsverzeichnis von Obsidian im Stammverzeichnis des Tresors. Der Ordnername muss mit dem Plugin `id` in `manifest.json` übereinstimmen (den vollständigen Pfad finden Sie unter [plugin README][plugin]).
3. Kopieren Sie `main.js` und `manifest.json` in diesen Ordner.
4. Öffnen Sie in Obsidian **Einstellungen → Community-Plugins**, deaktivieren Sie bei Bedarf den **Eingeschränkten Modus** und aktivieren Sie **In Marked öffnen**.

[obsidian-app]: https://obsidian.md/
[plugin]: https://github.com/ttscoff/Marked3-obsidian
[plugin-releases]: https://github.com/ttscoff/Marked3-obsidian/releases/latest