# <%= @title %>

Marked kann automatisch reaktionsfähige `<picture>`-Elemente für lokale Bilder erstellen, wenn begleitende **Dunkelmodus**- und **Retina**-Dateien neben dem Bild liegen, auf das Sie verweisen. Hierbei werden dieselben Namenskonventionen wie in den DocC-Dokumentationskatalogen von Apple verwendet, es funktioniert jedoch für **jedes Markdown- oder HTML-Dokument** mit normalen Bildpfaden, die eine Dateierweiterung enthalten.

Siehe auch [DocC Support](DocC_Support.html) für erweiterungslose Katalogverweise innerhalb von `.docc` Bundles.

## Bildvarianten aktivieren

Aktivieren Sie in {% prefspane Apps %} unter den DocC-Einstellungen **Dunkle und @2x-Bildvarianten auflösen** (standardmäßig aktiviert).

Diese Einstellung ist unabhängig von **DocC-Bildverweise auflösen**, die nur innerhalb von `.docc`-Katalogen gilt. Abhängig von Ihrem Projekt können Sie eines, beide oder keines von beiden verwenden.

## Namenskonvention

Platzieren Sie Variantendateien im **gleichen Ordner** wie das Primärbild. Marked sucht basierend auf dem Basisnamen nach vier Kombinationen:

| Rolle | Beispieldateiname |
|------|----|
| Licht (1x) | `icon.png` |
| Dunkel (1x) | `icon~dark.png` |
| Licht (2x) | `icon@2x.png` |
| Dunkel (2x) | `icon~dark@2x.png` |

Die Reihenfolge der Suffixe ist flexibel – `icon@2x~dark.png` und `icon~dark@2x.png` werden gleich behandelt.

Unterstützte Erweiterungen: `png`, `jpg`, `jpeg`, `gif`, `svg`, `webp` und `pdf`.

## Was wird neu geschrieben

Marked scannt Ihr Dokument **vor** der endgültigen Vorschauwiedergabe:

- **Markdown:** `![Alt text](images/icon.png)`
- **HTML:** `<img src="images/icon.png" alt="Alt text">`

Wenn mindestens **zwei** übereinstimmende Variantendateien auf der Festplatte vorhanden sind, wird die Referenz durch einen `<picture>`-Block ersetzt. Eine einzige zusätzliche Datei reicht aus – Sie benötigen nicht alle vier Varianten.

Beispielausgabe, wenn helle, dunkle und @2x-Dateien vorhanden sind:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="images/icon~dark.png 1x, images/icon~dark@2x.png 2x">
  <source srcset="images/icon.png 1x, images/icon@2x.png 2x">
  <img src="images/icon.png" alt="Alt text">
</picture>
```

Die Vorschau (und der HTML-Export) folgt dann der Systemdarstellung des Benutzers für dunkle Varianten und der Gerätepixeldichte für @2x-Assets.

## Was wird übersprungen

Marked schreibt **nicht** um:

- Remote-URLs (`http://`, `https://`, `data:`)
– Verweise, die bereits auf eine `~dark`-Datei verweisen
- `<img>`-Tags befinden sich bereits in einem vorhandenen `<picture>`-Element
- Namen ohne Erweiterung wie `![Diagram](diagram)` – verwenden Sie [DocC Support](DocC_Support.html) für Referenzen im Katalogstil

## Live-Vorschau und Dateianzeige

Wenn Varianten erkannt werden, fügt Marked **jede vorhandene Variantendatei** neben dem Hauptdokument zu seiner Beobachtungsliste hinzu. Das Speichern von `icon~dark.png` in einem externen Editor löst das gleiche Neuladen von Livebildern aus wie das Bearbeiten von `icon.png`.

## Tipps

- Verweisen Sie nach Möglichkeit auf das **light 1x**-Bild in Ihrer Quelle (`icon.png`, nicht `icon~dark.png`). Marked entdeckt Geschwister auf diesem Weg.
– Wenn Sie nur über `@2x`-Assets verfügen, fügen Sie mindestens eine weitere Variante hinzu (normalerweise `~dark`), sonst lässt Marked die Referenz unverändert.
- Bei der Variantenauflösung werden Pfade **relativ zum Dokument** (oder zum Ordner der eingebundenen Datei für verschachtelte Includes) verwendet, es gelten dieselben Basispfadregeln wie [Multi-file Documents](Multi-File_Documents.html).

## Verwandte Themen

- [DocC Support](DocC_Support.html) – erweiterungslose Bildnamen in `.docc` Katalogen
- [Settings: Apps](Settings_Apps.html) – Präferenz schaltet für DocC- und Bildvarianten um
- [Previewing](Previewing.html) – Live-Vorschau und Dateiaktualisierungen