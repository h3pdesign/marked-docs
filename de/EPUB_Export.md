# <%= @title %>

Marked exportiert vollständig kompatible EPUB-Dateien aus Ihrer Markdown-Vorschau – gestaltet mit denselben integrierten und benutzerdefinierten Designs, die Sie auf dem Bildschirm verwenden, und lesbar in **Apple Books**, **Kobo** und anderen Standard-EPUB-Readern.

Der typische Arbeitsablauf ist **zuerst Vorschau, dann EPUB exportieren**: Öffnen oder kompilieren Sie Ihr Dokument in Marked, wählen Sie ein Thema, lesen Sie es in der Live-Vorschau Korrektur und exportieren Sie es dann, wenn das Buch fertig ist.

## Exportieren eines EPUB

Öffnen Sie [Export Panel](Exporting.html#drawer) ({% kbd shift cmd e %}) oder verwenden Sie **Speichern unter** aus dem Zahnradmenü und wählen Sie **EPUB**.

Im Dialog zum Speichern von EPUB können Sie Folgendes festlegen:

* **Titel** --- Standardmäßig werden MultiMarkdown-Metadaten oder der Dateiname verwendet
* **Autor** --- Standardmäßig ist Ihr macOS-Benutzername; Der zuletzt eingegebene Autor wird für den nächsten Export gespeichert
* **Datum** --- ISO-Format; zum Speichern bearbeitbar
* **Titelbild** --- optional PNG oder JPG; Marked generiert eine Standard-Cover-Vorschau, wenn keine festgelegt ist

Marked bettet lokale Bilder in EPUB ein und kann Remote-Bilder herunterladen, sodass die fertige Datei in sich geschlossen ist. Exportierte EPUBs werden vor dem Speichern als wohlgeformte XHTML validiert. Dadurch werden Dateien erstellt, die den EPUB-Standards für Verteilung und Zugänglichkeit entsprechen.

Siehe [Export Profiles](Exporting.html#export-profiles) zum Speichern von EPUB-Metadaten und Exporteinstellungen für die wiederholte Verwendung.

## Styling mit integrierten Themen

Der für Ihr Dokument ausgewählte **Vorschaustil** bestimmt das Erscheinungsbild. Jedes integrierte Marked-Theme – Swiss, GitHub, Manuscript und der Rest – kann auf den EPUB-Export angewendet werden.

1. Wählen Sie einen Stil aus dem Stilmenü des Vorschaufensters (oder legen Sie einen Standard in {% prefspane Style %} fest).
2. Überprüfen Sie Typografie, Überschriften, Codeblöcke und Bilder in der Live-Vorschau.
3. Export nach EPUB --- Marked bündelt das CSS des Themes im Paket EPUB.

Marked wendet außerdem exportspezifisches CSS zusätzlich zu Ihrem Vorschaudesign an, sodass Elemente wie Fußnoten, Tabellen und syntaxhervorgehobene Codeblöcke in E-Readern korrekt dargestellt werden. Dokumente im Gliederungsmodus verwenden gliederungsoptimierte Exportstile. [Leanpub](Multi-File_Documents.html) `Book.txt` Indizes verwenden automatisch den Leanpub-orientierten Exportstil.

I> EPUB-Leser ignorieren einige Nur-Web-CSS (feste Positionierung, Ansichtsfenster-Tricks usw.). Was Sie in der Vorschau von Marked sehen, ist das Ziel, aber E-Reader-Layout-Engines können Abstände und Schriftarten vereinfachen. Testen Sie es vor der Veröffentlichung in Apple Books oder Ihrem Zielleser.

## Styling mit benutzerdefinierten Themen

[Custom Styles](Custom_Styles.html) funktioniert für EPUB genauso wie für Vorschau und PDF:

* Fügen Sie CSS-Dateien in {% prefspane Style %} oder [Style Manager](Custom_Styles.html) hinzu.
* Wählen Sie vor dem Exportieren das benutzerdefinierte Design aus.
* Marked bettet Ihr Stylesheet in das exportierte EPUB ein.

Tipps für EPUB-freundliches benutzerdefiniertes CSS:

* Halten Sie die Layouts flüssig – verwenden Sie relative Einheiten und `max-width: 100%` für Bilder (`#wrapper img { max-width: 100%; }` ist eine gute Basislinie).
* Vermeiden Sie `@media print`-Regeln für das E-Book-Styling; EPUB verwendet die Hauptbildschirmstile sowie das Export-Stylesheet von Marked.
* [Dark Mode](Previewing.html) Invertierung in der Vorschau verwendet `@media screen` Abfragen; Die meisten EPUB-Reader verwenden das helle Stylesheet, es sei denn, die Reader-App wendet ihr eigenes dunkles Design an.
* Verwenden Sie [Additional CSS](Custom_Styles.html) in den Stileinstellungen, um alle Designs gleichzeitig zu optimieren (z. B. eine einheitliche Schriftgröße für alle Exporte).

Hinweise zur Erstellung finden Sie unter [Creating Custom CSS](Writing_Custom_CSS.html).

## Syntaxhervorhebung und Mathematik

Wenn **Syntaxhervorhebung beim Export einbeziehen** in {% prefspane Export %} aktiviert ist, werden Codeblöcke mit denselben Syntaxfarben wie in Ihrer Vorschau exportiert. Mit [MathJax](MathJax.html) gerenderte Mathematik ist im EPUB enthalten, sofern dies für die E-Reader-Unterstützung erforderlich ist.

## Metadaten in Ihrer Quelldatei

Sie können EPUB-Metadaten im Dokument anstelle des Speicherdialogs festlegen. Verwenden Sie am Anfang einer Markdown-Datei (oder auf einer Scrivener-Metadatenseite) Schlüssel im MultiMarkdown-Stil:

```yaml
title: Your Document Title
author: Your Name
cover image: path/to/image.jpg
```

`cover image` akzeptiert einen Pfad relativ zum Dokument oder einen absoluten Pfad. PNG und JPG werden unterstützt. Dialogwerte überschreiben oder ergänzen fehlende Metadaten beim Export.

## Bücher mit mehreren Dateien

Kompilieren Sie für lange Werke Kapitel mit [Multi-File Documents](Multi-File_Documents.html) --- Indexdateien, Scrivener-Exporten, Leanpub `Book.txt` oder Indizes im GitBook-Stil. Marked überwacht die enthaltenen Dateien, zeigt eine Vorschau des gesamten Buchs an und exportiert einen EPUB aus dem kompilierten HTML.

Überschriften im kompilierten Dokument werden zum EPUB [table of contents](Document_Navigation.html) für die Navigation in Apple Books und anderen Readern.

## Lesen und Veröffentlichen

Exportierte EPUBs werden direkt in **Apple Books** geöffnet (doppelklicken Sie auf die Datei oder verwenden Sie **Datei → Zur Bibliothek hinzufügen**). Sie funktionieren auch in Kobo, Thorium, Calibre und den meisten EPUB 3-kompatiblen Apps.

### Apple Books

Ziehen Sie ein exportiertes `.epub` in die Bücher-App oder fügen Sie es über **Datei → Importieren** hinzu. Custom Typografie und Cover-Art aus Ihrem Marked-Thema. Verwenden Sie Apple Books auf Mac, iPad oder iPhone, um das Layout vor der Freigabe zu überprüfen.

### Kindle Direct Publishing (KDP)

EPUB ist ein akzeptiertes Upload-Format für [Kindle Direct Publishing](https://kdp.amazon.com/). Aus Marked exportieren und die Datei `.epub` hochladen; Amazon konvertiert es für die Kindle-Lieferung. KDP akzeptiert auch [DOCX](Working_with_DOCX.html). Aktuelle Anforderungen finden Sie im [supported eBook formats](https://kdp.amazon.com/en_US/help/topic/G200634390) von Amazon.

**MOBI ist nicht erforderlich** für neue KDP-Titel. Marked exportiert kein MOBI.

Optional: Sehen Sie sich vor dem Hochladen eine Vorschau des Kindle-Layouts mit dem kostenlosen [Kindle Previewer](https://kdp.amazon.com/help/topic/G202131170) von Amazon an.

## Verwandt

* [HTML Export](HTML_Export.html) --- eigenständiger HTML mit eingebetteten Stilen und Bildern
* [Exporting](Exporting.html) --- Panel, Profile und andere Formate exportieren
* [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html) --- Vorschau des Workflows vor dem Export
* [Custom Styles](Custom_Styles.html) und [Custom Style Generator](Custom_Style_Generator.html)
* [Multi-File Documents](Multi-File_Documents.html) --- Bücher und Kapitelindizes
* [AppleScript export](AppleScript_Support.html) --- EPUB-Export automatisieren