# <%= @title %>

Zahlen sind genauso wichtig wie Worte.

## Vorschau von Formeln mit MathJax

![][1]

   [1]: images/mathjax.jpg @2x width=713px height=512px class=center

Durch Aktivieren von MathJax im {% prefspane Style %} werden die erforderlichen Skripte und CSS in die Vorschau einbezogen. Dann kann die MultiMarkdown-Mathe-Syntax in Ihrem Markdown-Dokument verwendet werden und die Ergebnisse werden angezeigt.

Beispiel-Syntax MMD MathJax:

\\\\[ {e}^{i\pi } 1=0 \\\\]

Wenn Sie sich dafür entscheiden, MathJax in eine exportierte HTML-Datei aufzunehmen, wird anstelle des eingebetteten MathJax-Codes ein CDN-Link verwendet. Dies erfordert eine Internetverbindung, um das gerenderte MathML anzuzeigen.

## MathJax Quelle: Lokal vs. CDN

Wenn MathJax aktiviert ist, kann Marked es von einem der folgenden Orte laden:

- **Lokal**: eine in der App gebündelte Kopie von MathJax v3 (schneller zu laden, funktioniert offline).
- **CDN**: das offizielle MathJax v3 CDN (immer aktuell, keine Auswirkungen auf das App-Bundle).

Im Popup **MathJax Quelle** in {% prefspane Style %} können Sie Folgendes auswählen:

- **Lokal** – verwendet die ES5-Komponente `tex-chtml.js` aus dem App-Bundle.
- **CDN** – lädt die gleiche Komponente vom CDN. Hierzu ist eine Internetverbindung erforderlich.

Exportierte HTML-Dateien verweisen immer auf MathJax von einem CDN, unabhängig von der Vorschauquelle, sodass sie in sich geschlossen und klein bleiben.

## Gleichungsnummerierung

Sie können die Gleichungsnummerierung in {% prefspane Style %} aktivieren. Dies funktioniert sowohl mit MathJax als auch mit KaTeX, wird intern jedoch unterschiedlich implementiert. Für MathJax v3 ordnet Marked Ihre Einstellungen der entsprechenden MathJax-Konfiguration zu, sodass:

- „Zahlengleichungen“ steuert, ob Zahlen angezeigt werden.
- Die Option „Seite“ steuert, ob Zahlen links oder rechts angezeigt werden.
- Die Option „Nur AMS“ beschränkt die Nummerierung auf Gleichungen im AMS-Stil.

Diese Optionen entsprechen den Einstellungen `tex.tags` und `tex.tagSide` von MathJax unter der Haube.

## Zusätzliche Pakete

MathJax v3 ist modular. Marked aktiviert immer die TeX/AMS-Kernpakete, und Sie können optional zusätzliche Pakete in {% prefspane Style %} aktivieren:

- **Physik** (`physics`) – physikalische Notation und Annehmlichkeiten.
- **Chemie** (`mhchem`) – Chemiegleichungen.
- **Bremse** (`braket`) – Dirac-Bremsennotation.
- **Fette Symbole** (`boldsymbol`) – fette mathematische Symbole.

Klicken Sie auf **Zusätzliche Pakete…**, um eine kleine Checkliste zu öffnen, in der Sie diese Pakete aktivieren oder deaktivieren können. Änderungen werden wirksam, wenn Marked das nächste Mal Mathematik in der Vorschau rendert.

## MathJax erweiterte Konfiguration

Sie können zusätzliche benutzerdefinierte Konfigurationen zusätzlich zu den Standardeinstellungen von Marked anwenden, indem Sie ein gültiges JSON-Objekt im Feld **Erweiterte Konfiguration** hinzufügen. Dieses Feld wird in das Konfigurationsobjekt MathJax v3 (`window.MathJax`) eingefügt, bevor MathJax geladen wird. Es kann [any options supported by MathJax v3](https://docs.mathjax.org/en/latest/options/) enthalten, zum Beispiel:

{
        "tex": {
            "inlineMath": [["$","$"],["\\\\(","\\\\)"]],
            "displayMath": [["$$","$$"],["\\\\[","\\\\]"]],
            "Makros": {
                "tr": "{\\\\scriptscriptstyle\\\\mathrm{T}}"
            },
            "packages": { "[+]": ["physics"] }
        }
    }

In diesem Beispiel werden TeX-Trennzeichen angepasst, ein `\tr`-Makro hinzugefügt und das `physics`-Paket zusätzlich zum Standardsatz aktiviert. Mit diesen Einstellungen werden alle folgenden Elemente ordnungsgemäß gerendert:

Inline-Formel mit Klammern, \\\\({x}^{2} {y}^{2}=1\\\\) oder mit Dollarzeichen, ${x}^{2} {y}^{2}=1$.

Anzeige mit maskierten Klammern:

\\\\[ {e}^{i\pi } 333=0 \label{testme} \\\\]

Oder mit doppelten Dollarzeichen:

$${x}_{1,2}=\\frac{-b\pm \sqrt{{b}^{2}-4ac}}{2a}$$

![][2]

   [2]: images/mathjax2.jpg @2x width=837px height=260px class=center

Die zusätzliche Konfiguration erweitert das vorhandene Objekt, sodass nur die angegebenen Eigenschaften überschrieben werden. Nicht angegebene Optionen bleiben für die aktuelle Voreinstellung auf der Standardeinstellung.

Beachten Sie, dass bei Verwendung des MultiMarkdown-Prozessors mit nicht standardmäßigen Trennzeichen Zeichen innerhalb des Ausdrucks analysiert werden, sodass Symbole wie `*` und `^` typografische Änderungen verursachen, die den MathJax-Prozessor beschädigen. Die beste Lösung in diesen Fällen ist die Verwendung des Discount-Prozessors in [Processor settings](x-marked-3://pref/processor).

Marked führt ein wenig Magie aus, wenn entweder MathJax oder KaTeX aktiviert sind, und konvertiert die mathematische Syntax, um sicherzustellen, dass sie mit dem aktuellen Prozessor (MultiMarkdown oder Discount) so kompatibel wie möglich ist. Das sollte unter allen Umständen großartig sein, aber wenn Sie feststellen, dass es Probleme verursacht, [contact support](https://support.markedapp.com/questions/add)!


## KaTeX

[katex]: https://katex.org/

[KaTeX][] ist als Alternative zu MathJax verfügbar. Es ist leichter und daher schneller zu laden, was bei Dokumenten mit einer großen Anzahl von Formeln von Vorteil sein kann. Es verfügt jedoch nicht über so viele Funktionen und einige Gleichungen, die mit MathJax (oder LaTeX) funktionieren, werden möglicherweise nicht unterstützt.

## Automatische Gleichungsnummerierung [Nummerierung]

Sie können die Gleichungsnummerierung in {% prefspane Style %} aktivieren. Dies funktioniert sowohl mit MathJax als auch mit KaTeX. Sie können auswählen, ob Zahlen auf der linken oder rechten Seite der Gleichung erscheinen sollen.

### In MathJax

In MathJax verwendet dies die Einstellung:

{
      TeX: { equalNumbers: { autoNumber: "all" } }
    }

Wenn Sie nur AMS-Gleichungen nummerieren möchten, wählen Sie „Nur AMS“ rechts neben dem Dropdown-Menü „Seite“ aus.

### In KaTeX

KaTeX bietet keine Gleichungsnummerierung. Um dies in Marked zu simulieren, wird CSS verwendet und alle Anzeigegleichungen sind nummeriert.

## Exportprobleme

Rich-Text-Formate verarbeiten keine Gleichungen (weder nach MathJax noch nach KaTeX). Sie werden im Ausgabedokument ausgeblendet, da der Versuch, die speziellen Schriftarten einzubeziehen, zu einem größeren Durcheinander führt, als Sie sich vorstellen können ... Dies ist etwas, das ich hoffentlich irgendwann beheben kann, aber im Moment ein Manko ist.

