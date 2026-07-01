# <%= @title %>

Mit Marked können bestimmte Attribute eines Dokuments im MultiMarkdown-Metadatenformat festgelegt werden (siehe unten). Sie können diese verwenden, um Merkmale und Stile zu definieren, die sich nur auf dieses Dokument auswirken, ohne die Standardeinstellungen zu ändern.

Die meisten MultiMarkdown-Header werden von der Vorschau ignoriert, die folgenden sind jedoch zulässig und wirken sich auf das Rendering aus. Sie können andere Metadaten einbeziehen, die in der endgültigen Ausgabe gerendert werden sollen. Marked ignoriert einfach Schlüssel, die unten nicht aufgeführt sind. Wenn Sie als HTML speichern und *keine* Vorlage einbinden, stellt Marked alle Metadatenschlüssel wie erwartet dar.

## Metadatenformat

Metadaten werden am Anfang der Datei Markdown oder unmittelbar im Anschluss an alle YAML-Header eingegeben. Sie bestehen aus einem Schlüssel, gefolgt von einem Doppelpunkt, optionalen Leerzeichen oder Tabulatoren und dem Wert:

Beispielmetadaten: Beispielschlüssel

Mehrere Metadateneinträge sollten in eigenen Zeilen stehen, jedoch ohne Zeilenumbrüche dazwischen. Auf den letzten Metadateneintrag muss vor Beginn des Dokumenttextes eine Leerzeile folgen.

Erstens: Dies ist der erste Metadateneintrag
	Zweitens: Dies ist der zweite Eintrag
	Drittens: der letzte Metadateneintrag

# Der Anfang des Dokumenttextes

## Marked Metadatenschlüssel

### Metadaten für andere Prozessoren ausblenden [hidingmeta]

**Hinweis:** Wenn Sie einen benutzerdefinierten Prozessor verwenden oder Ihre Markdown direkt in einer Quelle veröffentlichen, die diese Metadaten nicht verarbeitet, können Sie sie trotzdem verwenden, indem Sie vor und nach den Metadaten HTML Kommentarmarkierungen hinzufügen. Im Gegensatz zu MultiMarkdown und anderen Prozessoren lokalisiert Marked diese Tags an einer beliebigen Stelle im Dokument und verarbeitet/entfernt sie aus der Ausgabe. Daher liefert Folgendes in der Kopfzeile die gewünschten Ergebnisse in Marked, wird aber an anderer Stelle nicht angezeigt:

<!--
	Marked Stil: Mein Custom Stil
	Custom Prozessor: wahr
	->

*Stellen Sie einfach sicher, dass der Metadatenschlüssel am Anfang der Zeile ohne Leerzeichen oder Tabulatoren beginnt, und fügen Sie nach dem Wert nichts anderes in die Zeile ein.*

### Stile pro Dokument

Der Schlüssel „Marked Style:“ legt einen Vorschaustil für das Dokument fest. Der Wert kann der Name eines Standardstils oder ein Name oder Pfad für jedes [Custom Style](Custom_Styles.html) sein, das Sie in den Einstellungen definiert haben. Wenn dieser Schlüssel gefunden wird und mit einem Stil übereinstimmt, den Marked kennt, wird dieser Stil jedes Mal für die Vorschau verwendet, wenn das Dokument, das ihn enthält, geladen wird.

**Beispiel**

Marked Stil: Aufrechter Bürger

### Zitate Sprache

Standardmäßig verwendet Marked Anführungszeichen im englischen Stil. Sie können dies für jedes Dokument mit der Taste „Sprache der Zitate:“ ändern. Verfügbare Sprachen sind:

* niederländisch
* Englisch
* französisch
* deutsch
*Guillemets
* schwedisch

**Beispiel**

Zitate Sprache: Französisch

Erstellt französischsprachige «Anführungszeichen».

### Basis-Header-Ebene

Mit der Taste „Base Header Level:“ können Sie die Header-Ebene festlegen, ab der Marked zu zählen beginnt. Dies sollte eine Zahl zwischen 1 und 6 sein und ändert die Art und Weise, wie „#“-Header gerendert werden. Wenn Sie die Header-Ebene auf 3 festlegen, wird das, was normalerweise ein Header der ersten Ebene (h1) wäre, als Header der dritten Ebene (h3) gerendert, und nachfolgende Header in der Hierarchie werden um 2 nach oben verschoben.

**Beispiel**

Basis-Header-Ebene: 3

# Diese Überschrift wird als h3 gerendert

## Diese Überschrift wird ein h4 sein

Wird wie folgt gerendert:

<h3>Diese Überschrift wird als h3 gerendert</h3>

<h4>Diese Überschrift wird ein h4 sein</h4>

### Custom Prozessoren

Wie im [Custom Processor](Custom_Processor.html#preprocessor) beschrieben, können Sie einen benutzerdefinierten Prozessor und einen benutzerdefinierten Präprozessor mithilfe von Metadaten aktivieren oder deaktivieren:

Custom Prozessor: wahr
    Custom Präprozessor: falsch

„true“ oder „false“ schalten den Vor-/Prozessor ein und aus.

Der Wert „Prozessor“ kann auf „Multimarkdown“ oder „Discount“ gesetzt werden, um die Verwendung des einen oder anderen der internen Prozessoren zu erzwingen. Durch diese Einstellung pro Dokument wird die Standardeinstellung in {% prefspane Processor %} nicht geändert.

### Kopf-/Fußzeilen drucken

Sie können die Einstellungen in {% prefspane Export %} zum Drucken von Kopf- und Fußzeilen mit den folgenden Tasten überschreiben:

Kopfzeile links drucken:
	Kopfzeile Mitte drucken:
	Kopfzeile rechts drucken:
	Fußzeile links drucken:
	Fußzeile mittig drucken:
	Fußzeile rechts drucken:

Dazu können [print variables](Exporting.html#headersandfooters) wie `%title`, `%page`, `%total` usw. sowie Verweise auf andere Metadaten mit `%md_[key without spaces]` gehören.

### Druckränder

Legen Sie die Seitenränder für die gedruckte und paginierte PDF-Ausgabe mit der Taste `Margins:` fest. Die Werte sind in Punkten angegeben; Suffixe wie `px`, `pt` und `em` werden ignoriert. Geben Sie zwei Zahlen für vertikale und horizontale Ränder oder vier Zahlen für oben, rechts, unten und links an:

Ränder: 10 20
	Ränder: 10, 20, 10, 20

Metadatenränder überschreiben die {% prefspane Export %}-Einstellungen und die Randfelder im PDF-Exportbereich.

### JavaScript einfügen

Diese Methode gibt Daten an, die im Tag `<head>` des Dokuments enthalten sind. Marked ignoriert die meisten Werte für diesen Schlüssel, außer in der Ausgabe des vollständigen Dokuments, berücksichtigt aber auf diese Weise eingebundene Skripte. Hier definierte Skript-Tags befinden sich nicht im Header, werden jedoch vor dem schließenden Tag `</body>` angehängt. jQuery ist bereits geladen und Sie können dies in allen von Ihnen eingefügten Skripten nutzen.

**Beispiel**

XHTML Header: <script>(function($){$('#wrapper').fadeOut();})(jQuery);</script>

-oder-

XHTML Header: <script src="myfancyscript.js"></script>

