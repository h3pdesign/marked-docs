# <%= @title %>

Schauen Sie sich [Markdown Dingus](x-marked-3://dingus?processor=commonmark) an, um mit dem CommonMark-Prozessor (GFM) zu experimentieren.


## Was ist CommonMark? [what-is-commonmark]

CommonMark ist eine stark spezifizierte, hochkompatible Implementierung von Markdown. Es wurde erstellt, um die Unklarheiten und Inkonsistenzen in John Grubers ursprünglicher Markdown-Spezifikation zu beheben, die zu unterschiedlichen Implementierungen auf verschiedenen Plattformen und Tools führten.

## Warum CommonMark existiert [why-commonmark-exists]

Die ursprüngliche Markdown-Spezifikation von John Gruber war in vielen Bereichen absichtlich mehrdeutig, was zu unterschiedlichen Interpretationen durch verschiedene Implementierungen führte. Dies führte zu Problemen, da dasselbe Markdown-Dokument auf verschiedenen Plattformen (GitHub, StackOverflow, Reddit usw.) unterschiedlich gerendert wurde.

CommonMark bietet:

- **Eindeutige Angaben** für die gesamte Markdown-Syntax
- **Umfassende Testsuite** zur Gewährleistung eines konsistenten Verhaltens
- **Klare Vorrangregeln** für widersprüchliche Syntax
- **Detaillierter Parsing-Algorithmus**, der konsistent implementiert werden kann

## Hauptunterschiede zum Standard Markdown [key-differences-from-standard-markdown]

### 1. **Strengere Parsing-Regeln** [1-stricter-parsing-rules]

CommonMark erzwingt ein konsistenteres Parsing-Verhalten:

**Leerzeilen vor Blockelementen**

- CommonMark erfordert Leerzeilen vor Überschriften, Anführungszeichen und Listen
- Der Standard Markdown erlaubt diese häufig ohne Leerzeilen

```markdown
Text
# Heading [heading]
```

*CommonMark: Erfordert eine Leerzeile vor der Überschrift*

*Standard Markdown: Oft ohne Leerzeile erlaubt*

### 2. **Analyse von Listenelementen** [2-list-item-parsing]

**Einrückungsanforderungen**

- CommonMark hat spezielle Regeln für das Einrücken von Listenelementen
- Unterlisten müssen konsistent eingerückt werden (normalerweise 4 Leerzeichen).
- Standardmäßige Markdown-Implementierungen weichen hiervon ab

```markdown
1. First item
   - Sublist item (4 spaces required in CommonMark)
2. Second item
```

**Fortsetzung der Liste**

- CommonMark hat klare Regeln dafür, wann Listenelemente „locker“ oder „fest“ sind.
- Lose Listen umschließen Elemente in `<p>`-Tags, enge Listen nicht

### 3. **Codeblock-Handhabung** [3-code-block-handling]

**Eingezäunte Codeblöcke**

– CommonMark standardisiert die Syntax von abgeschirmten Codeblöcken mit Backticks oder Tilden
- Erfordert konsistente Einrückungs- und Schlussmarkierungen


    ```language
    code here
    ```


**Eingerückte Codeblöcke**

– CommonMark erfordert Leerzeilen vor eingerückten Codeblöcken
- Der Standard Markdown erlaubt sie oft ohne Leerzeilen

### 4. **Link- und Bildverarbeitung** [4-link-and-image-processing]

**Vorrang des Referenzlinks**

- CommonMark hat klare Regeln, nach denen die Referenzdefinition Vorrang hat
- Mehrere Definitionen für dieselbe Referenz werden konsistent behandelt

```markdown
[link1]: /url1
[link1]: /url2
[link1]  <!-- Uses /url2 in CommonMark -->
```

**Link-Parsing-Reihenfolge**

- CommonMark verarbeitet Links vor der Hervorhebung
– Dies wirkt sich darauf aus, wie verschachtelte Syntax interpretiert wird

### 5. **Betonung und starke Betonung** [5-emphasis-and-strong-emphasis]

**Verschachtelte Hervorhebungsregeln**

– CommonMark verfügt über spezielle Algorithmen für die Verarbeitung verschachtelter `*`- und `_`-Markierungen
- Verhindert mehrdeutiges Parsen komplexer Hervorhebungsmuster

```markdown
*foo *bar* baz*  <!-- Clear precedence rules in CommonMark -->
```

**Trennzeichenverarbeitung**

- CommonMark verwendet einen „Trennzeichen-Stack“-Algorithmus für eine konsistente Hervorhebungsanalyse
- Standardimplementierungen von Markdown unterscheiden sich in ihrem Ansatz

### 6. **HTML Blockverarbeitung** [6-html-block-processing]

**HTML Blockerkennung**

- CommonMark verfügt über 7 verschiedene Arten von HTML-Blöcken mit spezifischen Regeln
- Jeder Typ hat unterschiedliche Anforderungen an die Start-/Endbedingungen

```html
<div>
This is an HTML block in CommonMark
</div>
```

### 7. **Behandlung von Zeilenumbrüchen** [7-line-break-handling]

**Harte Zeilenumbrüche**

- CommonMark erfordert zwei Leerzeichen am Zeilenende für harte Umbrüche
- Einzelne Zeilenumbrüche werden zu weichen Umbrüchen (in HTML ignoriert)

```markdown
Line one
Line two  <!-- Two spaces before line break -->
```

### 8. **Entitäts- und Zeichenreferenzen** [8-entity-and-character-references]

**Numerische Zeichenreferenzen**

- CommonMark unterstützt sowohl dezimale als auch hexadezimale numerische Referenzen
– Die Standardunterstützung für Markdown variiert

```html
&#8212;  <!-- Decimal -->
&#x2014; <!-- Hexadecimal -->
```

## CommonMark-Parsing-Algorithmus [commonmark-parsing-algorithm]

CommonMark verwendet einen zweiphasigen Parsing-Ansatz:

### Phase 1: Blockstruktur [phase-1-block-structure]

1. **Zeilenverarbeitung**: Jede Zeile wird auf Blockebenenmarkierungen analysiert
2. **Containerblöcke**: Blockzitate, Listen und andere Container werden identifiziert
3. **Blattblöcke**: Überschriften, Codeblöcke, Absätze werden verarbeitet
4. **Referenzlinks**: Linkdefinitionen werden zur späteren Verwendung gesammelt

### Phase 2: Inline-Struktur [phase-2-inline-structure]

1. **Inline-Verarbeitung**: Text innerhalb von Blöcken wird auf Inline-Elemente analysiert
2. **Hervorhebungsanalyse**: Verwendet den Trennstapelalgorithmus für eine konsistente Hervorhebung
3. **Linkauflösung**: Referenzlinks werden anhand gesammelter Definitionen aufgelöst
4. **Entitätsverarbeitung**: Zeichenreferenzen werden in tatsächliche Zeichen umgewandelt

## Vorteile von CommonMark [benefits-of-commonmark]

1. **Vorhersehbares Verhalten**: Die gleiche Eingabe erzeugt immer die gleiche Ausgabe
2. **Plattformübergreifende Kompatibilität**: Funktioniert konsistent mit verschiedenen Tools
3. **Umfassende Tests**: Umfangreiche Testsuite sorgt für Zuverlässigkeit
4. **Klare Dokumentation**: Detaillierte Spezifikationen machen Rätselraten überflüssig
5. **Zukunftssicher**: Klar definierte Erweiterungspunkte für neue Funktionen

## Implementierungshinweise [implementation-notes]

CommonMark ist wie folgt konzipiert:

- **Spezifikationskonform**: Entspricht genau der offiziellen CommonMark-Spezifikation
- **Testgesteuert**: Besteht die offizielle CommonMark-Testsuite
- **Erweiterbar**: Kann unter Beibehaltung der Kompatibilität um zusätzliche Funktionen erweitert werden
- **Schnell**: Optimierte Parsing-Algorithmen für Leistung

## Ressourcen [resources]

- [CommonMark Specification](https://spec.commonmark.org/0.31.2/)
- [CommonMark Test Suite](https://github.com/commonmark/commonmark-spec)
- [CommonMark Dingus](https://spec.commonmark.org/dingus/) – Online-Testtool
- [CommonMark Discussion Forum](https://talk.commonmark.org/)

---

*Diese Dokumentation deckt CommonMark 0.31.2 (28.01.2024) ab. Die aktuellsten Informationen finden Sie immer in der offiziellen Spezifikation.*