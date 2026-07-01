# <%= @title %>

Sehen Sie sich Ihre Dokumente auf Ihre Art an.

## Benutzerdefinierte Stile verwenden

![][img1]

  [img1]: images/custom_styles.jpg @2x width=544px height=196px class=center

Der einfachste Weg, Custom-Stile zu erkunden, ist über die
[Custom Style Gallery][2]. Von dort aus können Sie die durchsuchen
Verfügbare Stile in Aktion, installieren Sie sie mit einem Klick
Taste und sogar [submit your own creations][6] für
Inklusion.

Um benutzerdefinierte Stylesheets von Ihrem lokalen Laufwerk zu Marked hinzuzufügen,
Verwenden Sie {% prefspane Style %}. Neue Stile werden hinzugefügt
die Dropdown-Menüs in den Fenstereinstellungen und in jedem Fenster,
und wird basierend auf dem Basisdateinamen der CSS-Datei benannt
hinzugefügt. Speichern Sie Ihre benutzerdefinierten CSS-Dateien an einem sicheren Ort auf Ihrem
fahren. Wenn sie sich auf Ihrem Laufwerk bewegen, werden sie entfernt
Marked, bis Sie sie vom neuen Speicherort erneut hinzufügen. Es ist
Es empfiehlt sich, geöffnete Dokumente zu schließen und den Stil zu entfernen
in den Einstellungen, bevor Sie eine von verwendeten CSS-Datei löschen oder umbenennen
Marked. Es wird nichts kaputt gehen, wenn Sie es nicht tun, aber es spart
etwas Verwirrung.

Fügen Sie Custom-Stile hinzu, indem Sie den Stil-Manager mit der Schaltfläche „Hinzufügen“ verwenden oder indem Sie eine oder mehrere CSS-Dateien in die Einstellungen ziehen
Scheibe.

## Stile mit dem Style Manager verwalten

Wenn Sie den Style Manager starten, haben Sie einen einzigen Ort, an dem Sie alle integrierten Elemente kuratieren können
und benutzerdefiniertes Thema. Klicken Sie im {% prefspane Style %} auf die Schaltfläche **Stile verwalten…**
Scheibe,
oder legen Sie einfach CSS-Dateien im Einstellungsfenster ab --- Marked importiert sie,
Öffnen Sie den Stil-Manager und wählen Sie die neu hinzugefügte Zeile aus. CSS ziehen
Dateien direkt im Style-Manager-Fenster funktionieren ebenfalls; wenn mehrere Dateien
Wenn Sie die Elemente ziehen, wird das Overlay auf „N Custom Stile hinzufügen“ aktualisiert, damit es klar ist
Sie importieren einen Stapel.

![][img-style-manager]

Im Style Manager finden Sie eine sortierbare Tabelle, die integrierte und kombiniert
benutzerdefinierte Stile. Jede Zeile bietet:

- Ein Kontrollkästchen **Aktiviert**, das den Stil sofort zum Stil hinzufügt/entfernt
  Menü, Standardstil-Popup und Tastaturkürzel. Deaktivieren der aktuellen
  Der aktive Stil wechselt automatisch zum nächsten verfügbaren Eintrag.
- Eine Spalte **Name**, die Sie inline bearbeiten können; Änderungen bleiben bestehen und breiten sich auf alle aus
  Menü. Klicken Sie auf den Namen des Stils, um ihn direkt zu bearbeiten.
– Eine **Quelle**-Spalte, die „Built-in“, „Custom“ oder „Duplicated“ aufruft.
- Ein **Aktionsstapel** mit Schaltflächen zum **Bearbeiten** (öffnet die CSS-Datei in Ihrem
  Editor), **Duplicate** (erstellt eine Kopie und eine neue CSS-Datei auf der Festplatte), **Reveal**
  (zeigt die Datei im Finder) und **Löschen** (mit Optionen zum Entfernen der Referenz oder
  Verschieben Sie die CSS-Datei in den Papierkorb.

Die Reihenfolge der Zeilen kann per Drag-and-Drop geändert werden, und die Reihenfolge bestimmt auch das Menü „Stil“.
die `⌘/#` Shortcut-Zuweisungen, sodass Sie Stile buchstäblich in die Slots ziehen können
du willst. Sie können externe CSS-Dateien auch an bestimmte Positionen ziehen; der Tropfen
Der Indikator bestimmt, wo der neue Stil eingefügt wird.

### Live-Vorschau

Im rechten Bereich wird eine Vorschau angezeigt, die den ausgewählten Stil darstellt
innerhalb eines vollständigen HTML-Dokuments mit einem umfassenden Satz von Überschriften, Listen, Tabellen, Codeblöcken usw. Die
Die Vorschau verwendet das tatsächliche CSS auf der Festplatte, sodass Änderungen, die Sie in Ihrem externen Editor vornehmen, sofort aktualisiert werden. Ein Kontrollkästchen schaltet die Vorschau im Dunkelmodus um.

Sie können zusätzliche Stile zur Verwendung (oder als Beispiele dafür) finden
eigene erstellen) [on GitHub][1] (siehe [examples][2] für
ein kurzer Blick auf das, was da ist). Siehe [Creating Custom CSS][3]
für Details und Tipps.

## Zusätzliches CSS

Unter {% prefspane Style %} finden Sie eine Option
mit dem Titel „Zusätzliches CSS“ mit einer Schaltfläche mit der Bezeichnung „CSS bearbeiten“.
Wenn Sie auf diese Schaltfläche klicken, öffnet sich ein Fenster, in dem Sie etwas hinzufügen können
Universelle CSS-Regeln, die auf alle Stile angewendet werden. Hinweis
Diese Spezifität der Regeln kann wichtig sein, wenn
Überschreiben einiger Standardformate von Marked. Der Hauptteil
des Dokuments wird in ein Div mit der ID „#wrapper“ eingeschlossen.
Wenn Sie dies einem Selektor voranstellen, kann dies einfacher sein
Überschreibungen, z. B.:

#wrapper img { width: 100%; Höhe: automatisch; }

CSS in diesem Feld wird auf jedes Dokument angewendet, nein
Egal welchen Stil es verwendet. Wenn Sie benutzerdefinierte anwenden möchten
CSS basiert auf bedingten Übereinstimmungen. Verwenden Sie „Stil festlegen“ und „Einfügen“.
CSS-Datei oder CSS-Aktionen in {% prefspane Processor %} einfügen
Custom Regeln.

## Drucken und PDF Export

Marked fügt bei jedem einen integrierten `@media print`-Block (`mkprintstyles`) ein
Vorschau. Es legt Standardwerte wie eine **10pt**-Basis auf `html`, `body` und fest
`#wrapper` (oder die Größe aus **Custom Schriftgröße für Export/Druck** in
{% prefspane Export %}, wenn diese Option aktiviert ist) und normalisiert den Absatz
Text mit `p { font-size: 1em; }` und `li p { font-size: 1em; }` also
Nur-Bildschirm-Regeln wie `p { font-size: 1.1429em; }` vergrößern den Textkörper nicht
in PDFs und gedruckte Ausgabe.

Der PDF-Export verwendet Druckmedien auf dem versteckten WebView, das für die Generierung verwendet wird
`@media print { ... }`-Regeln in Ihrem Stylesheet gelten auf die gleiche Weise wie für
Drucken.

Um Größen festzulegen, die von den Druckstandards von Marked abweichen, fügen Sie explizite Regeln hinzu
innerhalb von `@media print` in Ihrem benutzerdefinierten CSS (oder in zusätzlichem CSS). Benutzen
`!important` wenn Sie die in Marked eingefügten Druckstile überschreiben müssen --- für
Beispiel:

„css
@media print {
  #wrapper p,
  Körper p,
  p {
    Schriftgröße: 9pt !important;
    Zeilenhöhe: 1,4 !important;
  }

h1 {
    Schriftgröße: 16pt !important;
  }
}
„

Regeln ohne `!important` verlieren möglicherweise gegen spätere Regeln in `mkprintstyles` oder gegen
andere unqualifizierte Selektoren in Ihrem Blatt, die noch im Druck gelten. Putten
Nur-Druck-Optimierungen in `@media print` (und nicht nur in Bildschirmregeln) bleiben erhalten
Das Vorschau- und Exportverhalten lässt sich leichter nachvollziehen.

## Beobachten Sie CSS-Änderungen

Sie können ein Kontrollkästchen im Abschnitt „Custom Styles“ von {% prefspane Style %} aktivieren
damit Marked die aktive CSS-Datei überwacht
zusätzlich zur Markdown-Datei, die Sie bearbeiten. Wann
Wenn in einer der Dateien Änderungen festgestellt werden, wird dies auch in der Vorschau der Fall sein
aktualisieren. Dies ist nützlich, um benutzerdefinierte Stile ohne zu bearbeiten
ständig aktualisiert und kann auch für einfaches Web verwendet werden
Entwicklungsaufgaben.

Dies ist auch für einige grundlegende Webdesign-Arbeiten und CSS nützlich
Experimentieren (z. B. Erstellen benutzerdefinierter Stile). Laden Sie a
Markdown-Datei, die das gesamte Markup enthält, das Sie formatieren möchten
Erstellen Sie dazu einen benutzerdefinierten Stil und sehen Sie sich die Vorschau live an
ändert sich, wenn Sie es bearbeiten.

## Benutzerdefiniertes CSS schreiben

Wenn Sie mit CSS vertraut sind, können Sie Ihren eigenen Stil erstellen
Blätter zur Verwendung in Marked. Siehe [Writing Custom CSS][3] für
Details. Denken Sie jedes Mal darüber nach, wenn Sie etwas Neues erstellen
[submitting it][6] zum [gallery][2] zum Teilen mit anderen
Benutzer. Stellen Sie sicher, dass Sie die im Leitfaden aufgeführten Grundlagen abdecken
Fügen Sie oben den Kommentar zu den Metadaten ein.

### Automatische Custom Styles mit StyleStealer

Sie können sogar automatisch einen Stil basierend auf einem generieren
bestehende Website mit [Style Stealer][4]. Auf diese Weise können Sie eine Webseite laden, die berechneten Stile für alle in Markdown gefundenen Hauptelemente abrufen und sie dann in einem benutzerdefinierten Stil speichern.

![Style Stealer][stylestealer]

  [stylestealer]: images/style-stealer-800.jpg @2x width=800


Verwalten Sie Custom-Stile (umbenennen, neu anordnen, duplizieren und löschen) über [Style Manager](Style_Manager.html).

[1]: https://github.com/ttscoff/MarkedCustomStyles
[2]: https://markedapp.com/styles/
[3]: Writing_Custom_CSS.html
[4]: Style_Stealer.html
[6]: https://markedapp.com/styleshare/
[img-style-manager]: images/screenshots/style-manager.jpg @2x width=1009px height=517px class=center

