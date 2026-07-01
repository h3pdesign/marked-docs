# <%= @title %>

[Drafts][drafts] auf dem Mac kann den aktiven Entwurf mithilfe der **Marked Streaming-Vorschau** in Marked spiegeln – dem gleichen auf der Zwischenablage basierenden Kanal, der in [Streaming Preview](Streaming_Preview.html) beschrieben wird. Sie können den aktuellen Entwurf auch einmal mit einer Community-**Aktion** senden (keine Live-Updates, bis Sie ihn erneut ausführen).

## Streaming-Vorschau (Entwürfe für Mac)

1. Wählen Sie in Marked {% appmenu File, New, Streaming Preview %} aus, damit ein Streaming-Vorschaufenster bereit ist.
2. Öffnen Sie in **Entwürfe für Mac** die **Einstellungen** und aktivieren Sie **Unterstützung für App-Streaming-Vorschau für Marked aktivieren**.
3. Verwenden Sie **Open Marked**, wenn Drafts es anbietet, um Marked vorzuziehen, und bearbeiten Sie es dann in Drafts; Die Vorschau wird aktualisiert, wenn sich Ihr Entwurf ändert.

![][draftsprefs]

Wenn diese Option aktiviert ist, verschiebt Drafts Markdown über die Integration, die Marked für Streaming-Vorschauen bereitstellt, an Marked (anstatt sich auf die Anzeige einer Datei auf der Festplatte zu verlassen).

### Holen Sie sich Marked

Wenn **Get Marked App** im Einstellungsblatt von Drafts angezeigt wird, verwenden Sie es, wenn Marked noch nicht installiert ist.

## Vorschau in Aktion Marked (manuelle Aktualisierung)

Installieren Sie die Community-Aktion [**Preview in Marked**](https://actions.getdrafts.com/a/11f) aus dem Drafts-Verzeichnis. Es sendet den **aktuellen Entwurfstext** unter Verwendung einer `x-marked://preview?text=…`-URL an Marked (Entwürfe ersetzen Ihren Entwurfsinhalt). **Inhalte werden nicht live aktualisiert**: Führen Sie die Aktion immer dann erneut aus, wenn Sie möchten, dass Marked mit dem Entwurf übereinstimmt.

Dieser Ansatz ist praktisch für gelegentliche Überprüfungen, während die **Streaming-Vorschau** für kontinuierliche Schreibsitzungen geeignet ist.

Drafts läuft auch auf iPhone und iPad; Die hier dokumentierte Streaming-Vorschau-Integration gilt für **Drafts für Mac** mit Marked auf demselben Mac.

[draftsprefs]: images/Drafts_streaming_preview_preference.png width=842px height=182px class=center

[drafts]: https://getdrafts.com/
