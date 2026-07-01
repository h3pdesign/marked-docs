# <%= @title %>

Optionen im {% prefspane Style %}:

![Settings: Style][1]

[1]: images/screenshots/preferences-Style.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Layout und Typografie

Begrenzen Sie die Textbreite in der Vorschau
: Legen Sie mithilfe des Schiebereglers eine maximale Breite für den Hauptteil der Vorschau fest (in Pixel).

Automatische Silbentrennung in Absätzen
: Wörter automatisch durch Silbentrennung umbrechen lassen.

Verhindern Sie Witwen in Überschriften und Absätzen
: Erzwingt ein geschütztes Leerzeichen zwischen den letzten beiden Wörtern von Überschriften und Absätzen, um zu verhindern, dass einzelne Wörter in eine neue Zeile umgebrochen werden.

Generieren Sie typografisch korrekte Anführungszeichen und Zeichensetzung
: Verwenden Sie SmartyPants für intelligente Anführungszeichen, die Konvertierung von Ellipsen und andere Typografiefunktionen (MultiMarkdown).

Umgeben Sie Fußnotenmarkierungen mit eckigen Klammern
: Wenn aktiviert, verwenden Sie die Standardformatierung MultiMarkdown für Fußnotenmarkierungen ([1]). Deaktivieren Sie die Option, um eckige Klammern zu entfernen.

Aktivieren Sie Outline für Erweiterungen
: Den Gliederungsmodus für Dateien mit aufgelisteten Erweiterungen automatisch aktivieren.

Verwenden Sie den APA-Stil
: Verwenden Sie Umrisse im APA-Stil anstelle des standardmäßigen Dezimalformats.

Stilisieren Sie wörtliche (Code-)Blöcke als Poesie
: Wenn diese Option aktiviert ist, wird mit Tabulatoren eingerückter, umzäunter oder eingeschlossener Code als Poesie statt als Codeblock angezeigt (keine Syntaxhervorhebung und spezielles Styling je nach Thema).

Erlauben Sie Themes, Text innerhalb von Codeblöcken einzuschließen
: Wenn diese Option aktiviert ist, dürfen Themen einen Umbruch innerhalb von `pre>code`-Blöcken verursachen. Wenn diese Option deaktiviert ist, wird beim horizontalen Überlauf immer gescrollt.

Code immer umbrechen
: Erzwingen Sie das Umbrechen von Codeblöcken unabhängig von den Designeinstellungen (überschreibt das Umbruchverhalten des Themas).

Erkennen und formatieren Sie RTL-Text
: Sprache pro Element im Dokument erkennen und „Rechts nach links“ entsprechend formatieren.

### Thema

Stile verwalten
: Öffnet das Fenster [Style Manager](Style_Manager.html). Fügen Sie CSS-Dateien von Ihrem Laufwerk hinzu, damit sie in den Stilauswahlmenüs angezeigt werden. Verwenden Sie die Schaltfläche `Add New Style` oder ziehen Sie CSS-Dateien in dieses Fenster. Ziehen Sie, um die Reihenfolge neu anzuordnen, und verwenden Sie die Kontrollkästchen, um Stile zu aktivieren oder zu deaktivieren.

Weitere Themen
: Öffnen Sie die Online-Themengalerie, um zusätzliche Stile zu durchsuchen und zu installieren.

Standardstil
: Der hier ausgewählte Stil wird für alle neuen Fenster geladen, es sei denn, ein [document-specific style is indicated in metadata](Per-Document_Settings.html) (z. B. „Marked Stil: Grump“).

Verfolgen Sie CSS-Änderungen
: Wenn dies aktiviert ist, überwacht Marked den aktuellen Stil auf Festplattenänderungen und hilft so bei der Bearbeitung benutzerdefinierter Stile und der Webentwicklung.

Zusätzliches CSS
: Das hier hinzugefügte CSS wird nach dem normalen Stylesheet in alle Themes eingefügt. Unter anderem können Sie damit Einstellungen flächendeckend überschreiben, ohne interne Stile zu bearbeiten.
: Dies gilt für alle Dokumente und alle Stile. Wenn Sie benutzerdefiniertes CSS auf Dokumente basierend auf Bedingungen anwenden möchten, verwenden Sie Custom Rules unter {% prefspane Processor %}.

### Skripte einschließen

Syntaxhervorhebung
: Highlight.js [syntax highlighting](Syntax_Highlighting.html) für Codeblöcke aktivieren. Wählen Sie ein Thema aus der Dropdown-Liste aus.
: Wenn **Nur wenn die Sprache angegeben ist** aktiviert ist, wird die Syntaxhervorhebung nur auf eingezäunte Codeblöcke mit einer angegebenen Sprache angewendet.

Aktivieren Sie MathJax
: Lädt [MathJax](MathJax.html) zur Anzeige von MathML-Gleichungen. Wählen Sie im Dropdown-Menü **Lokal** (gebündelt) oder **CDN** aus.
: **Zusätzliche Pakete** öffnet ein Blatt, um zusätzliche MathJax-Pakete aufzunehmen (z. B. Physik und Chemie).
: **Erweiterte Konfiguration** öffnet ein Blatt für die benutzerdefinierte MathJax-Konfiguration.

KaTeX aktivieren
: Lädt [KaTeX](Mathjax.html#katex) als Alternative zu MathJax. Es kann nur das eine oder das andere ausgewählt werden.

Zahlengleichungen
: Gegebenenfalls fügt Marked Abbildungsnummern zu gerenderten Gleichungen hinzu. Wählen Sie für die Nummerierung **Linke Seite** oder **Rechte Seite**. Wenn Sie MathJax verwenden, können Sie **Nur AMS** wählen, um nur AMS-Gleichungen zu nummerieren.

Meerjungfrau
: Lädt [mermaid.js](https://mermaid.js) von einem CDN, um Diagramme im Markdown-Stil zu ermöglichen. Der zum Rendern von Mermaid-Diagrammen bei jeder Dokumentaktualisierung erforderliche Hook ist automatisch enthalten.

Schwenk- und Zoomdiagramme
: Wenn Meerjungfrau-Diagramme vorhanden sind, aktivieren Sie den Zoom mit {% kbd cmd %}-scrollen und schwenken Sie durch Klicken und Ziehen.