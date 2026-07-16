# <%= @title %>

Schauen Sie sich [Markdown Dingus](x-marked-3://dingus?processor=kramdown) an, um mit dem Kramdown-Prozessor zu experimentieren.

## Was ist Kramdown? [what-is-kramdown]

Kramdown ist ein schneller, reiner Ruby-Markdown-Superset-Konverter, der die ursprüngliche Markdown-Syntax um Funktionen erweitert, die in anderen Implementierungen wie Maruku, PHP Markdown Extra und Pandoc zu finden sind. Es bietet eine strenge Syntax mit eindeutigen Regeln und gewährleistet gleichzeitig die Kompatibilität mit den meisten Markdown-Dokumenten.

## Hauptmerkmale [key-characteristics]

- **Schnelles und reines Ruby**: Aus Gründen der Leistung und Portabilität vollständig in Ruby geschrieben
- **Strenge Syntax**: Bietet eindeutige Regeln und klare Spezifikationen
- **Erweiterte Funktionen**: Enthält viele Erweiterungen, die nicht im Standard-Markdown enthalten sind
- **Jekyll-Integration**: Standardprozessor Markdown für den statischen Site-Generator von Jekyll
- **Umfassend**: Unterstützt sowohl Elemente auf Blockebene als auch auf Span-Ebene mit umfassender Anpassung

## Wesentliche Unterschiede zum Standard Markdown [major-differences-from-standard-markdown]

### 1. **Erweiterte Elemente auf Blockebene** [1-enhanced-block-level-elements]

**Definitionslisten**

- Kramdown unterstützt Definitionslisten (nicht im Standard Markdown)
– Verwendet `:`, um Begriffe von Definitionen zu trennen

„Abschlag
Begriff 1
: Definition 1

Begriff 2
: Definition 2a
: Definition 2b
„

**Tabellen**

- Vollständige Tabellenunterstützung mit Kopfzeilen, Ausrichtung und Formatierung
- Umfassender als die grundlegende Markdown-Tabellensyntax

```markdown
| Header 1 | Header 2 | Header 3 |
| :------- | :------: | -------: |
| Left     |  Center  |    Right |
| Aligned  | Aligned  |  Aligned |
```

**Matheblöcke**

- Unterstützung für mathematische Ausdrücke mit LaTeX-Syntax
- Sowohl Inline- als auch Block-Mathe-Unterstützung

„Abschlag
Inline-Mathematik: $E = mc^2$

Blockmathematik:
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
„

### 2. **Erweiterte Textmarkierung** [2-advanced-text-markup]

**Fußnoten**

- Vollständige Fußnotenunterstützung mit automatischer Nummerierung
– Fußnoten im Referenzstil mit der Syntax `[^1]`

„Abschlag
Dies ist ein Satz mit einer Fußnote[^1].

[^1]: This is the footnote content.
„

**Abkürzungen**

- Unterstützung für Abkürzungen im HTML-Stil
- Automatische Erweiterung definierter Abkürzungen

„Abschlag
*[HTML]: HyperText Markup Language
*[CSS]: Cascading Style Sheets

Dies verwendet HTML und CSS.
„

**Typografische Symbole**

- Automatische Konvertierung gängiger typografischer Zeichen
- Intelligente Anführungszeichen, Gedankenstriche, Ellipsen usw.

```markdown
"Smart quotes" and -- em dashes -- and ... ellipses
Even << guillemets >>
```

### 3. **Attributlisten und Erweiterungen** [3-attribute-lists-and-extensions]

**Attributlistendefinitionen (ALDs)**

- Definieren Sie wiederverwendbare Attributsätze
- Unterstützung für IDs, Klassen und benutzerdefinierte Attribute

„Abschlag
{:ref-name: #myid .my-class title="Mein Titel"}

Ein Absatz mit Attributen.
{: #para-one .highlight}
„

**Inline-Attributlisten (IALs)**

- Attribute an bestimmte Elemente anhängen
- Unterstützung sowohl auf Block- als auch auf Span-Ebene

```markdown
This *is*{:.underline} some `code`{:#id}{:.class}.
A [link](test.html){:rel='something'} and some **tools**{:.tools}.
```

**Erweiterungen**

- Custom Erweiterungssystem für zusätzliche Funktionalität
- Integrierte Erweiterungen für Kommentare und Optionen

„Abschlag
{::Kommentar}
Dieser Text wird von Kramdown komplett ignoriert.
{:/Kommentar}

{::options key="val" /}
„

### 4. **Erweiterte Codeblock-Unterstützung** [4-enhanced-code-block-support]

**Sprachspezifikation**

- Automatische Syntaxhervorhebung für eingezäunte Codeblöcke
- Unterstützung für viele Programmiersprachen

    ```ruby
    def hello
      puts "Hello, World!"
    end
    ```

**Standard-Codeblöcke**

- Verbesserte Handhabung eingerückter Codeblöcke
- Bessere Integration mit anderen Blockelementen

### 5. **Strengere Parsing-Regeln** [5-stricter-parsing-rules]

**Zeilenumbruch**

- Unterstützung für fest umschlossene Inhalte (lazy syntax)
- Klare Regeln dafür, wann Zeilenumbruch zulässig ist
– Aus Gründen der Lesbarkeit nicht empfohlen, aber aus Kompatibilitätsgründen unterstützt

**Tab-Handhabung**

- Setzt Tabulatorstopps bei Vielfachen von vier voraus
- Tabulatoren sind zum Einrücken nur am Zeilenanfang zulässig
- Es dürfen keine Leerzeichen vorangestellt werden

**Blockgrenzen**

- Klare Regeln dafür, wann Elemente an Blockgrenzen beginnen/enden müssen
- Konsistentes Verhalten über verschiedene Elementtypen hinweg

### 6. **Erweiterte Link- und Bildunterstützung** [6-advanced-link-and-image-support]

**Automatische Links**

- Verbesserte automatische Linkerkennung
- Besserer Umgang mit URLs und E-Mail-Adressen

**Referenzlinks**

- Verbesserte Verarbeitung von Referenzlinks
- Bessere Konfliktlösung für mehrere Definitionen

**Bildattribute**

- Unterstützung für Bildattribute durch IALs
– Breite, Höhe, Alternativtext und andere HTML-Attribute

```markdown
![Alt text](image.jpg){:width="300" height="200" class="responsive"}
```

### 7. **HTML Integration** [7-html-integration]

**HTML Blöcke**

- Bessere Handhabung von HTML innerhalb von Markdown
- Unterstützung für HTML-Attribute und -Verarbeitung
- Flexibler als die standardmäßige Handhabung von Markdown HTML

**HTML Spannen**

– Inline HTML mit Attributunterstützung
- Bessere Integration mit der Markdown-Syntax

### 8. **Mathematische Ausdrücke** [8-mathematical-expressions]

**Inline-Mathematik**

- `$...$` Syntax für eingebettete mathematische Ausdrücke
- LaTeX-kompatible Syntax

**Mathe blockieren**

- `$$...$$` Syntax für blockmathematische Ausdrücke
- Unterstützung für komplexe Gleichungen und Formeln

## Kramdown vs. andere Markdown Geschmacksrichtungen [kramdown-vs-other-markdown-flavors]

| Funktion | Kramdown | CommonMark (GFM) | GitHub Aromatisiert | MultiMarkdown | Standard |
| ---------------- | -------- | ---------- | --------------- | ------------- | -------- |
| Durchgestrichen | Nein | Ja | Nein | Nein | Nein |
| Aufgabenlisten | Nein | Nein | Ja | Ja | Nein |
| Eingezäunter Code | Ja | Ja | Ja | Ja | Nein |
| Mathematik | Ja | Nein | Ja | Ja | Nein |
| Fußnoten | Ja | Ja | Ja | Ja | Nein |
| Definitionslisten | Ja | Nein | Nein | Ja | Nein |
| Abkürzungen | Ja | Nein | Nein | Nein | Nein |
| Attributlisten | Ja | Nein | Nein | Nein | Nein |
| Typografie | Ja | Nein | Nein | Ja | Nein |

## Hauptvorteile von Kramdown [key-advantages-of-kramdown]

1. **Umfassender Funktionsumfang**: Enthält viele Erweiterungen, die in anderen Implementierungen nicht zu finden sind
2. **Jekyll-Integration**: Nahtlose Integration mit dem statischen Site-Generator von Jekyll
3. **Ruby-Ökosystem**: Reine Ruby-Implementierung mit guter Ruby-Tooling-Unterstützung
4. **Erweiterbarkeit**: Custom Erweiterungssystem für zusätzliche Funktionalität
5. **Attributunterstützung**: Umfangreiches Attributsystem für die HTML-Ausgabeanpassung
6. **Mathematische Unterstützung**: Integrierte Unterstützung für mathematische LaTeX-Ausdrücke
7. **Strenges Parsing**: Klare, eindeutige Parsing-Regeln

## Häufige Anwendungsfälle [common-use-cases]

**Jekyll-Sites**

- Standardprozessor für die statische Jekyll-Site-Generierung
- Hervorragend geeignet für Dokumentationen und Blogseiten

**Technische Dokumentation**

- Mathe-Unterstützung für wissenschaftliches und technisches Schreiben
– Attributlisten für erweiterte HTML-Anpassung

**Akademisches Schreiben**

- Fußnotenunterstützung für Zitate und Referenzen
- Mathematische Ausdrücke für Formeln und Gleichungen

**Content-Management**

- Erweiterungen für benutzerdefinierte Funktionen
- Attributlisten für Metadaten und Stil

## Ressourcen [resources]

- [Kramdown Syntax Documentation](https://kramdown.gettalong.org/syntax.html)
- [Kramdown Converter Documentation](https://kramdown.gettalong.org/converter.html)
- [Jekyll Integration Guide](https://jekyllrb.com/docs/configuration/markdown/)
- [Kramdown GitHub Repository](https://github.com/gettalong/kramdown)

## Migration vom Standard Markdown [migration-from-standard-markdown]

Die meisten Standard-Markdown-Dokumente funktionieren mit Kramdown ohne Änderungen. So nutzen Sie die Funktionen von Kramdown:

1. **Definitionslisten hinzufügen**: Glossare und Begriffslisten konvertieren
2. **Attributlisten verwenden**: Fügen Sie IDs, Klassen und benutzerdefinierte Attribute hinzu
3. **Fußnoten implementieren**: Verweise in Klammern umwandeln

## Best Practices [best-practices]

1. **Lazy Syntax vermeiden**: Verlassen Sie sich für die Lesbarkeit nicht auf Hard-Wrapping
2. **Attributlisten verwenden**: Nutzen Sie IALs für Styling und Metadaten
3. **Konsistente Einrückung**: Verwenden Sie nach Möglichkeit Leerzeichen anstelle von Tabulatoren

---

*Diese Dokumentation deckt Kramdown 2.5.1 ab. Aktuelle Informationen finden Sie immer in der offiziellen Dokumentation unter [kramdown.gettalong.org](https://kramdown.gettalong.org/).*