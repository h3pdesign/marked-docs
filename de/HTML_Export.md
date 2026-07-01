# <%= @title %>

Marked exportiert HTML aus Ihrer **Live-Vorschau** --- die gleiche gerenderte Ausgabe, die Sie auf dem Bildschirm sehen. Verwenden Sie den HTML-Export, wenn Sie ein Snippet zum Einfügen in ein Blog oder CMS oder eine eigenständige `.html`-Datei mit eingebetteten Stilen und Bildern benötigen, die Sie in jedem Browser oder Host überall öffnen können.

Der typische Arbeitsablauf ist **zuerst Vorschau, dann HTML exportieren**: Öffnen oder kompilieren Sie Ihr Dokument in Marked, wählen Sie ein Thema, lesen Sie es in der Live-Vorschau Korrektur und exportieren Sie es dann, wenn das Markup richtig aussieht.

## Zwei Möglichkeiten, HTML zu erhalten

### Kopieren HTML (Ausschnitt)

**Kopieren Sie HTML** und legen Sie die HTML-Quelle der Vorschau in der Zwischenablage ab – bereit zum Einfügen in WordPress, Ghost, Squarespace, ein Forum, eine E-Mail-Vorlage oder eine andere App, die HTML-Fragmente akzeptiert.

* Zahnradmenü → **Kopieren HTML** oder {% kbd shift cmd C %} mit fokussierter Vorschau
* Kopiert den **gerenderten Textkörper HTML** (kein vollständiges Dokument mit `<html>` Wrapper)
* Optional: Aktivieren Sie **Bilder beim Kopieren von HTML** in {% prefspane Export %} einbetten, um lokale Bilder als `data:`-URLs in der eingefügten Quelle mit Base64 zu kodieren

Das Kopieren von HTML ist ideal, wenn Ihr Ziel bereits über ein eigenes Stylesheet verfügt und Sie nur das Inhalts-Markup benötigen.

### Speichern HTML (Datei)

**Save HTML** schreibt eine vollständige `.html`-Datei auf die Festplatte.

* Exportieren → **Speichern Sie HTML**, {% kbd cmd S %} oder **HTML** aus dem [Export Panel](Exporting.html#drawer) ({% kbd shift cmd e %})
* Wählen Sie im Speicherdialog Dateinamen und Speicherort aus
* Exportoptionen im Dialogzubehör konfigurieren (siehe unten)

Save HTML ist ideal zum Archivieren, zum Teilen einer eigenständigen Datei oder zum direkten Öffnen des Ergebnisses in einem Browser.

## HTML Optionen speichern

Das Dialogfeld „Speichern HTML“ enthält eine Exportprofilauswahl und die folgenden Optionen:

![Save HTML options][savehtml]

**Stil in Ausgabe einbeziehen**

Wenn diese Option aktiviert ist, bettet Marked das CSS des ausgewählten Vorschauthemas in einen `<style>`-Block in der exportierten Datei ein. Wählen Sie ein beliebiges integriertes Design oder [Custom Style](Custom_Styles.html) aus dem Stilmenü neben dem Kontrollkästchen aus. Die Ausgabe ist ein vollständiges HTML-Dokument mit `<!DOCTYPE html>`, `<head>` und einem `#wrapper` div um Ihren Inhalt – passend zu dem, was Sie in der Vorschau angezeigt haben.

Wenn diese Option deaktiviert ist, speichert Marked ein minimales HTML-Dokument nur mit Ihrem gerenderten Inhalt (kein Marked-Design-CSS). Verwenden Sie dies, wenn Sie möchten, dass rohes HTML in ein anderes System eingefügt oder importiert wird, das seinen eigenen Stil bereitstellt.

**Lokale Bilder für Standalone einbetten HTML**

Wenn **Stil in Ausgabe einschließen** aktiviert ist, können Sie lokale Bilder auch als Base64-`data:`-URLs in die Datei HTML einbetten. Das Ergebnis ist eine einzelne Datei, die Sie ohne separaten `images/`-Ordner per E-Mail versenden, hochladen oder hosten können.

* Funktioniert mit Bildern, auf die durch **relative oder absolute Pfade** auf Ihrem lokalen Laufwerk verwiesen wird
* Vermeiden Sie `file:///` URLs – diese können nicht zuverlässig eingebettet werden
* Remote-Bilder (http/https) bleiben als externe URLs, es sei denn, Sie laden sie zuerst herunter
* Durch die Base64-Einbettung können große Dateien entstehen. Verwenden Sie es, wenn die Portabilität wichtiger ist als die Dateigröße

**JavaScript mit Syntaxhervorhebung einbinden**

Wenn die Syntaxhervorhebung in {% prefspane Preview %} aktiviert ist, fügt diese Option Highlight.js CSS und JavaScript von einem CDN hinzu, sodass Codeblöcke ihre Farben in der exportierten Datei behalten. Der exportierte HTML benötigt eine Internetverbindung, damit die CDN-Ressourcen geladen werden können.

**CDN-Link MathJax oder KaTeX einschließen**

Wenn [MathJax](MathJax.html) oder KaTeX für die Vorschau aktiviert ist, können Sie die passenden CDN-Skripte in das gespeicherte HTML einschließen, damit Gleichungen in einem Browser gerendert werden. Wie bei der Syntaxhervorhebung ist hierfür beim Anzeigen der Datei Netzwerkzugriff erforderlich, es sei denn, Sie hosten die Skripts selbst.

**CriticMarkup Exporttyp**

Dokumente mit [CriticMarkup](CriticMarkup.html) können wählen, ob beim Export bearbeiteter Text, Originaltext oder vollständiges Markup angezeigt wird.

**Profil exportieren**

Wählen Sie ein gespeichertes [Export Profile](Exporting.html#export-profiles) aus, um Ihre bevorzugten HTML-Exporteinstellungen (eingebettete Stile, Bilder, Syntaxhervorhebung, Mathematik) in einem Schritt wiederherzustellen.

## Styling mit integrierten und benutzerdefinierten Designs

Der **Vorschaustil** steuert das Erscheinungsbild von HTML, wenn **Stil in Ausgabe einbeziehen** aktiviert ist:

1. Wählen Sie einen Stil aus dem Stilmenü des Vorschaufensters (oder legen Sie einen Standard in {% prefspane Style %} fest).
2. Überprüfen Sie Typografie, Überschriften, Codeblöcke und Bilder in der Live-Vorschau.
3. Speichern Sie HTML mit demselben Stil, der im Exportdialog ausgewählt wurde.

Jedes integrierte Marked-Theme – Swiss, GitHub, Manuscript und der Rest – kann eingebettet werden. [Custom Styles](Custom_Styles.html) und Stile aus [Style Manager](Custom_Styles.html) funktionieren auf die gleiche Weise.

I> Einige Nur-Vorschau-CSS (feste Positionierung, Ansichtsfenster-Tricks, Dark Mode `@media screen`-Inversion) werden außerhalb von Marked möglicherweise nicht eins zu eins übersetzt. Öffnen Sie die gespeicherte Datei in einem Browser, um sie vor der Veröffentlichung zu überprüfen.

Hinweise zur Erstellung finden Sie unter [Creating Custom CSS](Writing_Custom_CSS.html).

## Metadaten und MultiMarkdown-Header

MultiMarkdown-Metadaten oben in Ihrer Quelldatei können sich auf den HTML-Export auswirken:

* **`Title:`** --- wird für das Element `<title>` beim Speichern eines vollständigen HTML-Dokuments verwendet
* **`XHTML Header:`** / **`HTML Header:`** --- fügt zusätzliche Tags in das exportierte `<head>` ein (Skripte, Link-Tags, Meta-Tags)
* Andere Metadatenschlüssel werden gemäß Ihrem [Markdown processor](Choosing_a_Processor.html) verarbeitet

Wenn Sie Metadaten für Exporteinstellungen verwenden, aber nicht möchten, dass Schlüssel in anderen Ausgaben sichtbar sind, schließen Sie sie in HTML-Kommentare ein. --- Marked findet und verarbeitet kommentierte Metadaten an einer beliebigen Stelle im Dokument. Siehe [Per-Document Settings](Per-Document_Settings.html).

## Dokumente mit mehreren Dateien

Für Bücher und Kapitelzusammenstellungen verwenden Sie [Multi-File Documents](Multi-File_Documents.html). Marked zeigt eine Vorschau des zusammengeführten Dokuments an und exportiert eine HTML-Datei aus dem kompilierten Ergebnis. Eingeschlossene Dateien sind mit HTML-Kommentaren markiert, die ihre Quellpfade anzeigen – nützlich bei der Prüfung, welches Kapitel zu welchem ​​Abschnitt beigetragen hat.

## Einfügen in andere Anwendungen

| Ziel | Vorgeschlagener Ansatz |
| :-- | :-- |
| Blog / CMS mit eigenem Theme | **Kopieren Sie HTML** (Snippet, kein eingebettetes Marked CSS) |
| Statische Site oder Archiv | **Speichern Sie HTML** mit **Stil in Ausgabe einbeziehen** |
| E-Mail oder Dateifreigabe (ein Anhang) | **Speichern Sie HTML** mit **Lokale Bilder einbetten** |
| WordPress, Ghost, Notion usw. | **Kopieren HTML**; Aktivieren Sie **Bilder beim Kopieren von HTML einbetten**, wenn der Editor lokale Pfade nicht auflöst |
| Weitere Bearbeitung in einem Code-Editor | **Speichern Sie HTML** ohne eingebetteten Stil oder kopieren Sie das Snippet und umbrechen Sie es manuell |

[Copy Rich Text](Exporting.html#rtfexportoptions) (Zahnradmenü) ist eine Alternative, wenn die Ziel-App formatierten Text anstelle der HTML-Quelle akzeptiert.

## Verwandte Themen

* [Exporting](Exporting.html) --- Panel, Profile und andere Formate exportieren
* [EPUB Export](EPUB_Export.html) --- E-Book-Ausgabe mit eingebettetem CSS
* [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html) --- Vorschau des Workflows vor dem Export
* [Custom Styles](Custom_Styles.html) und [Settings: Export](Settings_Export.html)
* [HTML Specific Settings](HTML_Specific_Settings.html) --- Prozessoroptionen für die HTML-Ausgabe
* [AppleScript export](AppleScript_Support.html) --- HTML Kopieren und Speichern automatisieren

[savehtml]: images/SaveHTML.png @2x width=740px height=229px 
r