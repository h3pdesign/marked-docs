# <%= @title %>

## Was ist Markdown?

Markdown ist eine leichte Auszeichnungssprache, die es Ihnen ermöglicht, in einem leicht lesbaren, einfach zu schreibenden Klartextformat zu schreiben und es dann in strukturell gültiges HTML zu konvertieren. Das übergeordnete Designziel für die Formatierungssyntax von Markdown besteht darin, sie so lesbar wie möglich zu machen.

## Grundlegende Syntax

### Kopfzeilen

Erstellen Sie Header mit Hash-Symbolen (`#`). Die Anzahl der Hashes bestimmt die Header-Ebene:

```markdown
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6
```

### Schwerpunkt

**Fettgedruckter Text** mit doppelten Sternchen oder doppelten Unterstrichen:

```markdown
**Bold text**
__Bold text__
```

*Kursiver Text* mit einzelnen Sternchen oder einzelnen Unterstrichen:

```markdown
*Italic text*
_Italic text_
```

### Listen

**Ungeordnete Listen** mit Sternchen, Pluszeichen oder Bindestrichen:

„Abschlag
* Punkt 1
* Punkt 2
* Punkt 3

+ Punkt 1
+ Punkt 2
+ Punkt 3

- Punkt 1
- Punkt 2
- Punkt 3
„

**Geordnete Listen** mit Zahlen gefolgt von Punkten:

```markdown
1. First item
2. Second item
3. Third item
```

### Links

**Inline-Links** mit dem Text in eckigen Klammern und der URL in Klammern:

```markdown
[Link text](http://example.com)
```

**Referenzlinks** mit dem Text in eckigen Klammern und einem Verweis in eckigen Klammern:

„Abschlag
[Link text][reference]

[reference]: http://example.com "Optional title"
„

**Automatische Links** durch Umschließen von URLs in spitze Klammern:

```markdown
<http://example.com>
<user@example.com>
```

### Bilder

Bilder verwenden eine ähnliche Syntax wie Links, jedoch mit einem Ausrufezeichen am Anfang:

„Abschlag
![Alt text](http://example.com/image.jpg)
![Alt text][image-reference]

[image-reference]: http://example.com/image.jpg "Optional title"
„

### Blockzitate

Erstellen Sie Blockzitate mit dem Größer-als-Symbol (`>`) am Anfang jeder Zeile:

```markdown
> This is a blockquote.
> It can span multiple lines.
>
> You can have multiple paragraphs in a blockquote.
```

### Code

**Inline-Code** mit Backticks:

```markdown
Use `code` in your text.
```

**Codeblöcke** durch Einrücken mit vier Leerzeichen oder einem Tabulator:

```markdown
    This is a code block.
    It preserves formatting and spacing.
    Multiple lines are supported.
```

### Horizontale Regeln

Erstellen Sie horizontale Regeln mit drei oder mehr Bindestrichen, Sternchen oder Unterstrichen:

„Abschlag
---

***

___
„

### Zeilenumbrüche

**Harte Zeilenumbrüche**, indem eine Zeile mit zwei oder mehr Leerzeichen endet:

```markdown
This line ends with two spaces.
This creates a hard line break.
```

**Weiche Zeilenumbrüche** durch einfaches Drücken der Eingabetaste (erstellt ein Leerzeichen in HTML):

```markdown
This line
continues on the next line with a space.
```

### Escape-Zeichen

Sonderzeichen mit Backslashes maskieren:

```markdown
\*This text is not italic\*
\[This is not a link\]
```

Häufige Zeichen, die maskiert werden können:
- `\` Backslash
- `` ` `` Backtick
- `*` Sternchen
- `_` Unterstrich
- `{}` geschweifte Klammern
- `[]` eckige Klammern
- `()` Klammern
- `#` Hash
- `+` plus
- `-` minus
- `.` Punkt
- `!` Ausrufezeichen

## Best Practices

1. **Verwenden Sie Leerzeilen**, um verschiedene Elemente zur besseren Lesbarkeit zu trennen
2. **Seien Sie konsistent** bei Ihren Formatierungsoptionen (verwenden Sie z. B. entweder `*` oder `_` zur Hervorhebung).
3. **Halten Sie es einfach** – Markdown ist so konzipiert, dass es als einfacher Text lesbar ist
4. **Testen Sie Ihre Ausgabe**, um sicherzustellen, dass sie wie erwartet gerendert wird
5. **Verwenden Sie aussagekräftigen Linktext** anstelle allgemeiner Phrasen wie „hier klicken“

## Gemeinsame Muster

### Verschachtelte Listen

```markdown
1. First item
   - Nested item
   - Another nested item
2. Second item
   - More nested content
```

### Listen mit Absätzen

„Abschlag
1. Erster Punkt

Dies ist ein Absatz unter dem ersten Punkt.

2. Zweiter Punkt

Dies ist ein Absatz unter dem zweiten Punkt.
„

### Blockzitate mit anderen Elementen

```markdown
> This is a blockquote with **bold text** and *italic text*.
>
> - It can contain lists
> - And other Markdown elements
>
> > Nested blockquotes are also possible.
```

## Zusammenfassung

Markdown bietet eine einfache, lesbare Möglichkeit, Text zu formatieren, der problemlos in HTML konvertiert werden kann. Der Schlüssel liegt darin, es einfach und lesbar zu halten und gleichzeitig die grundlegenden Syntaxelemente konsequent zu verwenden. Mit etwas Übung werden Sie feststellen, dass Markdown zur zweiten Natur wird und das Schreiben strukturierter Inhalte viel einfacher macht.

---

*Dieses Tutorial behandelt die Kernsyntax Markdown, wie sie in der Originalspezifikation definiert ist. Weitere erweiterte Funktionen finden Sie in der Dokumentation zu bestimmten Markdown-Prozessoren wie CommonMark (GFM), MultiMarkdown oder GitHub Flavored Markdown.*