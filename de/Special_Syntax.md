# <%= @title %>

## Hinweistexte

## Bär/Obsidian ##

Marked unterstützt Callouts mit der von Obsidian und Bear verwendeten Syntax, bei der es sich um ein speziell formatiertes Blockzitat handelt:

> [!NOTE] Notiztitel
	> Zusätzlicher Text

Beim „NOTE“ in `[!NOTE]` wird die Groß-/Kleinschreibung nicht beachtet. Es kann eines von Folgendem sein:

- HINWEIS
- ZUSAMMENFASSUNG, ZUSAMMENFASSUNG, TLDR
- INFO
- TODO
- TIPP, HINWEIS, WICHTIG
- ERFOLGREICH, PRÜFEN, FERTIG
- FRAGE, HILFE, FAQ
- WARNUNG, VORSICHT, ACHTUNG
- FEHLER, FEHLER, FEHLT
- GEFAHR, FEHLER
- FEHLER
- BEISPIEL
- ZITIEREN, ZITIEREN

Dadurch werden speziell formatierte Blöcke erstellt.

Sie können `+` oder `-` verwenden, um die Beschriftung einblendbar zu machen. Ein Pluszeichen (`+`) bedeutet, dass die Beschriftung ausklappbar ist, aber standardmäßig geöffnet ist. Ein Minuszeichen (`-`) bedeutet, dass die Beschriftung ausklappbar ist, standardmäßig aber geschlossen ist.

![Callouts in Marked][callouts]

[callouts]: images/callouts-800.jpg @2x width=800

### Xcode-Spielplatz ###

Bei der Vorschau von Xcode Playground-Dateien unterstützt Marked die native Xcode Playground-Callout-Syntax:

- Achtung: Optionaler Titel
	Callout-Inhalte kommen hierher.

Beim Callout-Typ (z. B. „Achtung“) wird die Groß-/Kleinschreibung nicht beachtet und es kann sich um einen der folgenden Xcode Playground-Callout-Typen handeln:

- **Achtung** – Als Info-Callout gestaltet
- **Autor** – Metadaten-Callout
– **Autoren** – Metadaten-Callout
- **Bug** – Fehler-/Gefahrenhinweis
- **Komplexität** – Hinweis im Notizstil
- **Urheberrecht** – Hinweis auf Metadaten
- **Custom Callout** – Callout im Beispielstil
- **Datum** – Metadaten-Callout
- **Beispiel** – Beispiel-Callout
- **Experiment** – Hinweis im Tipp-Stil
- **Wichtig** – Hinweis im Info-Stil
- **Invariant** – Beschriftung im Notizstil
- **Hinweis** – Hinweishinweis
- **Voraussetzung** – Hinweis im Notizstil
- **Nachbedingung** – Hinweis im Notizstil
- **Anmerkung** – Hinweis im Notizstil
- **Erfordert** – Beschriftung im Notizstil
- **Siehe auch** – Hinweis im Info-Stil
– **Seit** – Metadaten-Callout
– **Version** – Metadaten-Callout
- **Warnung** – Warnhinweis

Der optionale Titel nach dem Doppelpunkt wird als Callout-Titel verwendet. Wenn kein Titel angegeben wird, wird der Name des Callout-Typs als Titel verwendet.

Der Callout-Inhalt folgt unmittelbar in der nächsten Zeile (keine Leerzeile erforderlich). Der Inhalt wird bis zu einer Leerzeile, der nächsten Beschriftung, einem abgegrenzten Codeblock oder dem Ende des Dokuments fortgesetzt.

Beispiel:

````Abschlag
- Wichtig: Leistungshinweis
Dieser Algorithmus hat eine Komplexität von O(n log n).

- Beispiel: Schnellsortierung
So implementieren Sie es:

```swift
func quickSort(_ array: [Int]) -> [Int] {
   // implementation
}
```
````

Sie können den Titel auch ganz weglassen:

- Warnung
	Dies ist eine Warnung ohne benutzerdefinierten Titel.

Diese Callouts werden automatisch in das Callout-Format von Marked konvertiert und entsprechend gestaltet. Der ursprüngliche Callout-Typ bleibt im Attribut `data-callout` erhalten und ermöglicht bei Bedarf einen benutzerdefinierten CSS-Stil.

> Diese Funktion funktioniert nur bei der Vorschau von Xcode Playground-Dateien (`.playground`). Normale Markdown-Dateien verarbeiten diese Syntax nicht.


## Inhaltsverzeichnis

Mit `<!--TOC-->` können Sie angeben, wo im Dokument das Inhaltsverzeichnis erscheinen soll. Wenn dies festgelegt ist, überschreibt es die Option in den Einstellungen und wird immer im Vorschaufenster sowie beim Speichern und Drucken angezeigt. Das Inhaltsverzeichnis wird nur einmal angezeigt, auch wenn der Inhalt mehrere `<!--TOC-->`-Bezeichner enthält.

Wenn Sie `max#` zum obigen Tag hinzufügen (wobei # eine Ziffer von 1 bis 5 ist), wird die Tiefe des angezeigten Inhaltsverzeichnisses gesteuert. Beispielsweise zeigt `<!--TOC max2-->` nur Header der ersten und zweiten Ebene in der Liste an. Sie können mit `<!--TOC min2-->` auch eine minimale Headerebene angeben. Höchst- und Mindestwerte basieren auf den tatsächlichen Überschriftenebenen, nicht auf der Verschachtelungsebene. Maximum und Minimum können zusammen verwendet werden.

Marked erkennt auch den MultiMarkdown-Stil `<!--MKPH0-->` und den Pandoc-Stil `<!--MKPH1-->`, wobei `2-6` der Bereich der minimalen und maximalen Ebenen der einzubeziehenden Header ist.

Standardmäßig wird das Inhaltsverzeichnis auf der ersten Seite des Dokuments gedruckt, wenn „Inhaltsverzeichnis drucken“ unter {% prefspane Export %} aktiviert ist. Wenn im Dokument eine Markierung vorhanden ist, wird diese stattdessen an dieser Stelle platziert.

I> Sie können die Art der Nummerierung oder Beschriftung jeder Ebene einer verschachtelten Inhaltsverzeichnishierarchie im {% prefspane Export %} angeben.

## Seitenumbrüche

Sie können einen Seitenumbruch für die Ausgabe von print/PDF erzwingen, indem Sie die folgende Syntax verwenden:

```html
<!--BREAK-->
```

Platzieren Sie das Token in einer eigenen Zeile und es wird ein Markup generiert, das an dieser Stelle eine neue Seite erzwingt. Marked versteht auch das Leanpub-Format:

{::pagebreak /}

## Autoscroll pausiert [pauses]

Marked kann mit der Funktion [Autoscroll](Autoscroll.html) als Teleprompter fungieren (Sie sollten [Teleprompter style](https://markedapp.com/styles/preview?style=teleprompter) hinzufügen). Dabei kann es sinnvoll sein, Pausen in das Dokument einzubauen. Tun Sie dies mit:

```html
<!--PAUSE:X-->
```

Dabei ist `X` die Anzahl der Sekunden, die Marked pausieren soll. Wenn Sie also `<!--PAUSE:15-->` einfügen, erhalten Sie eine 15-sekündige Pause, wenn dieser Punkt im Dokument die Mitte des Bildschirms erreicht.

## Datei enthält

Der Inhalt zusätzlicher Dateien kann mit der folgenden Syntax eingefügt werden:

<<[Ordner/Dateiname]

Der Pfad zur Datei kann relativ zur Indexdatei oder absolut sein. Includes können verschachtelt werden; Sie können dieselbe Syntax in einer eingebundenen Datei verwenden. Wenn Sie relative Pfade verwenden, sollten Einbindungen in verschachtelte Dateien relativ zu dieser Datei sein. ***Jedoch*** verarbeitet MultiMarkdown alles basierend auf dem Speicherort der ersten geöffneten Datei, daher sollten alle Bildpfade oder andere Einbettungen relativ zur ersten übergeordneten Datei sein, auch wenn sie in untergeordneten Dokumenten vorhanden sind.

MultiMarkdown-Metadaten und YAML-Header werden vor dem Rendern automatisch aus den enthaltenen Dateien entfernt. Dadurch wird verhindert, dass die Kopfzeilen im Dokument angezeigt werden. Beachten Sie jedoch, dass Metadaten wie „Basis-Kopfzeilenebene“ in den enthaltenen Dokumenten ignoriert werden.

T> Beachten Sie, dass Sie beim Anzeigen von Dokumenten mit eingebundenen Dateien „I“ (Umschalt-i) eingeben können, um zu sehen, welche eingebundene Datei sich im sichtbaren Bereich befindet.

Weitere Informationen finden Sie unter ["Multi-File Documents"][ext].

[ext]: Multi-File_Documents.html

## Einschließlich Code

Marked kann externe Dateien als Code einschließen, wobei eine Syntax verwendet wird, die den oben genannten Datei-Includes ähnelt:

<<(Ordner/Dateiname)

Beachten Sie die Klammern anstelle der eckigen Klammern. Aus Kompatibilitätsgründen mit der Leanpub-Syntax erkennt Marked auch einen vorangehenden Satz eckiger Klammern, die einen Titel enthalten, aber derzeit wird in Marked nichts damit gemacht:

<<[Code title](folder/filename)

Der Inhalt der angegebenen Datei wird in einen Vorcodeblock in Ihrem Dokument eingefügt und steht für die automatische Syntaxhervorhebung zur Verfügung, sofern diese aktiviert ist. Codeblöcke können nicht verschachtelt werden und werden nicht mit MultiMarkdown verarbeitet. Custom-Prozessoren werden weiterhin über den erstellten Vorcodeblock ausgeführt.

## Einschließlich unverarbeitetem Text oder HTML

E> **Hinweis:** Diese Funktion ist für fortgeschrittene Benutzer.

Wenn Sie rohen HTML oder anderen Text einschließen möchten, der nicht von MultiMarkdown (oder Ihrem benutzerdefinierten Prozessor) verarbeitet werden soll, können Sie geschweifte Klammern (`{}`) verwenden, um eine Datei *nach* der Verarbeitung des Rests des Dokuments einzuschließen:

<<{folder/raw_file.html}

In diesen Dateien wird keine Include-Syntax erkannt (keine Verschachtelung) und der **Rohinhalt** der Datei wird in die endgültige HTML-Ausgabe eingefügt. Dies eignet sich hervorragend zum Einfügen von HTML, ohne den Textprozessor zu verlangsamen oder Dinge zu konvertieren/zu maskieren, wenn Sie dies nicht möchten. Seien Sie jedoch vorsichtig, da es nur wenige Sicherheitsvorkehrungen gibt, um sicherzustellen, dass die Formatierung des Dokuments rund um das, was Sie einfügen, erhalten bleibt.