# <%= @title %>

Schauen Sie sich [Markdown Dingus](x-marked-3://dingus?processor=multimarkdown) an, um mit dem MultiMarkdown-Prozessor zu experimentieren.

## Was ist MultiMarkdown?

MultiMarkdown ist ein erweiterter Markdown-Prozessor, der für die Arbeit mit vollständigen Dokumenten und nicht nur mit Webseitenfragmenten entwickelt wurde. Es erweitert die ursprüngliche Markdown-Syntax um Funktionen, die die Konvertierung in mehrere Ausgabeformate ermöglichen, darunter HTML, LaTeX, PDF, ODF und Microsoft Word-Dokumente.

## Hauptmerkmale

- **Dokumentorientiert**: Entwickelt für vollständige Dokumente, nicht nur für Webausschnitte
- **Multiformat-Ausgabe**: Konvertiert in HTML, LaTeX, PDF, ODF, RTF und Word
- **Inhalt vor Präsentation**: Konzentriert sich auf die Struktur und Bedeutung des Dokuments
- **Plattformübergreifend**: Funktioniert auf jedem Betriebssystem mit jedem Texteditor
- **Erweiterbar**: Umfangreicher Funktionsumfang für komplexe Dokumentanforderungen
- **Version 5**: Vollständige Neufassung mit verbesserter Leistung und Zuverlässigkeit

## Philosophie und Designziele

MultiMarkdown folgt dem Prinzip, dass **Inhalt wichtiger ist als Präsentation**. Der Schwerpunkt liegt auf der Darstellung der Bedeutung von Dokumenten (das ist eine Liste, das ist eine Tabelle usw.) und nicht auf der Vorgabe von Schriftarten, Farben oder Stilen.

Ziel ist es, für 80 % der Dokumente verwendbar zu sein, die 80 % der Menschen schreiben, sodass es für Romane, Abschlussarbeiten, technische Dokumentationen und die meisten anderen schriftlichen Inhalte geeignet ist.

## Hauptfunktionen und Erweiterungen

### 1. **Metadaten-Unterstützung**

- Dokumentmetadaten oben in den Dateien
- Titel, Autor, Datum und benutzerdefinierte Variablen
- Automatische Einbindung in Ausgabe-Header

„Abschlag
Titel: Mein Dokument
Autor: John Doe
Datum: 15.01.2024
Benutzerdefiniert: Wert

<!-- Eine Leerzeile beendet die Metadaten -->
Inhalt
---

# Dokumentinhalt
„

**Metadatenvariablen**

- Verwenden Sie im gesamten Dokument Metadatenwerte
- Syntax: `[%variable_name]`
- Automatische Ersetzung während der Verarbeitung

```markdown
Title: [%title]
Author: [%author]
Date: [%date]
```

### 2. **Erweiterte Tabellen**

**Vollständige Tabellenunterstützung**

- Überschriften, Ausrichtung und komplexe Tabellenstrukturen
- Unterstützung für Tabellenüberschriften und Beschriftungen
- Querverweise auf Tabellen

„Abschlag
| Kopfzeile 1 | Kopfzeile 2 | Kopfzeile 3 |
| :------- | :------: | -------: |
| Links |  Zentrum |    Richtig |
| Ausgerichtet | Ausgerichtet |  Ausgerichtet |

Tabelle: Beispieltabelle mit Ausrichtung
„

**Tischfunktionen**

- Spaltenausrichtung mit Doppelpunkten
- Tabellenüberschriften und Beschriftungen
- Querverweise mit `[Table 1]`
- Unterstützung komplexer Tabellenstrukturen

### 3. **Fußnoten und Zitate**

**Fußnoten**

– Fußnoten im Referenzstil mit der Syntax `[^1]`
- Automatische Nummerierung und Verlinkung
- Unterstützung für Inline-Fußnoten

„Abschlag
Dies ist ein Satz mit einer Fußnote[^1].

[^1]: This is the footnote content.
„

**Zitierunterstützung**

- Formatierung wissenschaftlicher Zitate
- Erstellung von Bibliographien
- Unterstützung verschiedener Zitierstile

```
This is a statement that should be attributed to
its source[p. 23][#Doe:2006].
```

Und es folgt die Beschreibung der Referenz
in der Bibliographie verwendet.

```
[#Doe:2006]: John Doe. *Some Big Fancy Book*.  Vanity Press, 2006.
```

In der HTML-Ausgabe sind Zitate nicht von Fußnoten zu unterscheiden.

Sie sind nicht verpflichtet, einen Locator zu verwenden (z. B. S. 23), und es gibt keine besonderen Regeln dafür, was als Locator verwendet werden kann, wenn Sie sich für die Verwendung eines Locators entscheiden. Wenn Sie den Locator lieber weglassen möchten, verwenden Sie einfach einen leeren Satz eckiger Klammern vor dem Zitat:

```
This is a statement that should be attributed to its
source[][#Doe:2006].
```

Es gibt keine Regeln für das von Ihnen verwendete Zitierschlüsselformat (z. B. Doe:2006), ihm muss jedoch ein `#` vorangestellt werden, genau wie Fußnoten `^` verwenden.

### 4. **Querverweise**

**Automatische Querverweise**

- Link zu Überschriften, Tabellen, Abbildungen und Gleichungen
- Automatische Etikettengenerierung
- Unterstützung für benutzerdefinierte Etiketten

„Abschlag
Einzelheiten finden Sie in [Tabelle 1].
Weitere Informationen finden Sie in [Abschnitt 2.1].

## Abschnitt 2.1 [Abschnitt-2-1]
„

**Referenztypen**

- Überschriften: `[Section 1]`, `[Heading Title]`
- Tabellen: `[Table 1]`, `[Table: Caption]`
- Zahlen: `[Figure 1]`, `[Figure: Caption]`
- Gleichungen: `[Equation 1]`

### 5. **Definitionslisten**

**Begriffsdefinitionspaare**

- Unterstützung für Definitionslisten
- Mehrere Definitionen pro Begriff
– Korrekte HTML `<dl>` Ausgabe

„Abschlag
Begriff 1
: Definition 1

Begriff 2
: Definition 2a
: Definition 2b
„

### 6. **Eingezäunte Codeblöcke**

**Sprachspezifische Codeblöcke**

- Dreifache Backticks mit Sprachangabe
- Unterstützung für Syntaxhervorhebung
- Automatische Spracherkennung

```markdown
```python
def hello():
    print("Hello, World!")
```
„

**Codeblockfunktionen**

- Sprachspezifikation für Syntaxhervorhebung
- Unterstützung für viele Programmiersprachen
– Korrekte HTML `<pre><code>` Ausgabe

### 7. **Mathe-Unterstützung**

**Mathematische Ausdrücke**

- LaTeX-kompatible mathematische Syntax
- Sowohl Inline- als auch Block-Mathe-Unterstützung
- Integration mit LaTeX-Ausgabe

„Abschlag
Inline-Mathematik: $E = mc^2$

Blockmathematik:

$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
„

### 8. **Bild- und Linkattribute**

**Erweiterte Links und Bilder**

– Unterstützung für HTML-Attribute
- Breite, Höhe, Alternativtext und mehr
- Bessere Integration mit Ausgabeformaten

```markdown
[Link text]: url.html title="Link title" class="external"
```

### 9. **Transklusion**

**Dateieinbindung**

- Fügen Sie andere Dateien in Dokumente ein
- Unterstützung für verschachtelte Includes
- Automatische Pfadauflösung

```markdown
{{chapter1.md}}
{{../shared/intro.md}}
```

**Transklusion-Funktionen**

- Dateieinbindung mit `<!--MKPH0-->`
- Unterstützung für relative und absolute Pfade
- Unterstützung für verschachtelte Transklusion
- Manifestgenerierung für enthaltene Dateien

### 10. **CriticMarkup Integration**

**Änderungsverfolgung**

- Unterstützung für die CriticMarkup-Syntax
- Verfolgen Sie Hinzufügungen, Löschungen und Kommentare
- Funktionen zur kollaborativen Bearbeitung

„Abschlag
Dies ist {>>gelöschter Text<<} und dies ist {++hinzugefügter Text++}.

Dies ist ein {~~Löschung~>Ersatz~~}.
„

### 11. **Inhaltsverzeichnis**

**Automatische TOC-Generierung**

- `<!--MKPH0-->` Platzhalter für Inhaltsverzeichnis
- Hierarchische Struktur basierend auf Überschriften
- Customisierbare TOC-Generierung

„Abschlag
# Dokumenttitel

{{TOC}}

## Abschnitt 1
Inhalt hier...

## Abschnitt 2
Mehr Inhalt...
„

### 12. **Abkürzungen**

**HTML-Stil-Abkürzungen**

- Definieren Sie Abkürzungen für die automatische Erweiterung
- Unterstützung für Tooltips und Erklärungen
– Korrekte HTML `<abbr>` Ausgabe

„Abschlag
*[HTML]: HyperText Markup Language
*[CSS]: Cascading Style Sheets

Dies verwendet HTML und CSS.
„

## MultiMarkdown v5 im Vergleich zu anderen Markdown-Varianten

| Funktion | MultiMarkdown v5 | CommonMark (GFM) | Rabatt | Kramdown | Standard |
| ---------------- | ---------------- | ---------- | ------------ | -------- | -------- |
| Tabellen | Ja | Nein | Ja | Ja | Nein |
| Durchgestrichen | Ja | Nein | Ja | Nein | Nein |
| Aufgabenlisten | Ja | Nein | Ja | Nein | Nein |
| Eingezäunter Code | Ja | Ja | Ja | Ja | Nein |
| Mathematik | Ja | Nein | Nein | Ja | Nein |
| Fußnoten | Ja | Nein | Ja | Ja | Nein |
| Definitionslisten | Ja | Nein | Nein | Ja | Nein |
| Abkürzungen | Ja | Nein | Nein | Ja | Nein |
| Attributlisten | Ja | Nein | Nein | Ja | Nein |
| Erweiterungen | Ja | Nein | Begrenzt | Ja | Nein |
| Typografie | Ja | Nein | Grundlegend | Ja | Nein |
| Autolinks | Ja | Nein | Ja | Nein | Nein |
| Querverweise | Ja | Nein | Nein | Nein | Nein |
| Zitate | Ja | Nein | Nein | Nein | Nein |
| Transklusion | Ja | Nein | Nein | Nein | Nein |
| Metadaten | Ja | Nein | Nein | Nein | Nein |

## Hauptvorteile von MultiMarkdown v5

1. **Dokumentorientiert**: Entwickelt für vollständige Dokumente, nicht nur für Webausschnitte
2. **Multiformat-Ausgabe**: Konvertieren in HTML, LaTeX, PDF, ODF, RTF und Word
3. **Akademische Unterstützung**: Zitate, Fußnoten und Querverweise
4. **Professionelle Funktionen**: Metadaten, Transklusion und erweiterte Formatierung
5. **Plattformübergreifend**: Funktioniert auf jedem Betriebssystem
6. **Zukunftssicher**: Das reine Textformat gewährleistet langfristige Kompatibilität
7. **Erweiterbar**: Umfangreicher Funktionsumfang für komplexe Dokumentanforderungen

## Häufige Anwendungsfälle

**Akademisches Schreiben**

- Abschlussarbeiten, Dissertationen und Forschungsarbeiten
- Zitierverwaltung und Erstellung von Bibliographien
- Querverweise und Fußnoten

**Technische Dokumentation**

- API-Dokumentation und Benutzerhandbücher
- Technische Spezifikationen und Handbücher
- Codedokumentation mit Syntaxhervorhebung

**Veröffentlichung**

- Bücher, Artikel und Berichte
- Multiformat-Ausgabe für verschiedene Plattformen
- Professionelle Dokumentformatierung

**Content-Management**

- Dokumentationswebsites
- Wissensdatenbanken und Wikis
- Gemeinsame Schreibprojekte

## Best Practices

1. **Metadaten verwenden**: Nutzen Sie die Titelseite von YAML für Dokumentinformationen
2. **Struktur mit Überschriften**: Verwenden Sie die richtige Überschriftenhierarchie für die Inhaltsverzeichnisgenerierung
3. **Querverweise nutzen**: Verwenden Sie automatische Verlinkungen für eine bessere Navigation
4. **Organisieren mit Transclusion**: Teilen Sie große Dokumente in überschaubare Dateien auf
5. **Testausgabe**: Überprüfen Sie die Formatierung in verschiedenen Ausgabeformaten
6. **Zitate verwenden**: Implementieren Sie ordnungsgemäße akademische Zitierpraktiken

## Migration von anderen Markdown-Varianten

Die meisten Standard-Markdown funktionieren ohne Änderungen mit MultiMarkdown. So nutzen Sie die Funktionen von MMD:

1. **Metadaten hinzufügen**: Fügen Sie YAML Titelblatt für Dokumentinformationen hinzu
2. **Querverweise verwenden**: Ersetzen Sie manuelle Links durch automatische Verweise
3. **Zitate implementieren**: Fügen Sie die richtige Formatierung für akademische Zitate hinzu
4. **Struktur mit Transklusion**: Teilen Sie große Dokumente in kleinere Dateien auf
5. **Nutzung von Tabellen**: Nutzen Sie erweiterte Tabellenfunktionen für die Datenpräsentation

## Ressourcen

- [MultiMarkdown User's Guide](https://fletcher.github.io/MultiMarkdown-5/MMD_Users_Guide.html)
- [MultiMarkdown Syntax Guide](https://fletcher.github.io/MultiMarkdown-5/MMD_Users_Guide.html#syntax)
- [MultiMarkdown GitHub Repository](https://github.com/fletcher/MultiMarkdown-5)
- [MultiMarkdown Documentation](https://fletcher.github.io/MultiMarkdown-5/)

---

*Diese Dokumentation gilt für MultiMarkdown v5.1.0. Aktuelle Informationen finden Sie immer in der offiziellen MultiMarkdown-Dokumentation unter [fletcher.github.io/MultiMarkdown-5](https://fletcher.github.io/MultiMarkdown-5/).*