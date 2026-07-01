# <%= @title %>

Marked kann eine Vorschau derselben Datei mit mehreren integrierten Markdown-Prozessoren anzeigen. Jeder geht unterschiedliche Kompromisse zwischen **Schreibworkflow** (Bücher, Blogs, GitHub READMEs) und **Ausgabekontrolle** (IDs, Klassen, Metadaten) ein. Sie wählen die Standardeinstellung in {% prefspane Processor %}; Sie können den Prozessor auch pro Dokument überschreiben.

Diese Seite fasst zusammen, wie sich die vier Hauptprozessoren unterscheiden. Ausführliche Syntaxdetails finden Sie auf den Referenzseiten unter **Hilfe → Markdown-Referenz** (z. B. [MultiMarkdown v5 Specification](MultiMarkdown_v5_Spec.html), [Kramdown Specification](Kramdown_Spec.html), [CommonMark Specification](CommonMark_Spec.html), [Discount GFM Specification](Discount_GFM_Spec.html)).

---

## MultiMarkdown (v5)

**Am besten geeignet für:** Lange Prosa, akademisches oder technisches Schreiben und alles, was auf **Metadaten**, **Zitate** und **MultiMarkdown-spezifische** Funktionen basiert.

Marked wird mit **MultiMarkdown 5** geliefert (siehe [MultiMarkdown User's Guide](https://fletcher.github.io/MultiMarkdown-5/) für die Originaldokumentation).

### Stärken

- **Erzählungs- und referenzlastige Dokumente:** Fußnoten, Bibliographie/Zitate und Tabellen sind erstklassig.
- **Metadaten:** Standard-MultiMarkdown-Metadatenblöcke (`Key: Value` Header) plus **Transklusion** und andere MMD-Annehmlichkeiten, die im v5-Handbuch beschrieben werden.
- **Metadaten-Ersetzung:** Schlüssel aus Metadaten können mit einer Ersetzung im `[%key]`-Stil in den Textkörper eingefügt werden, sodass Titel, Autorenzeichenfolgen und ähnliche Werte mit dem Header synchron bleiben.
- **Tabellen, Bilder und Querverweise:** Abgestimmt auf die für MultiMarkdown 5 dokumentierten Funktionen.

### IDs und manuelle Überschriften

- Überschriften-IDs werden so **normalisiert**, dass tendenziell **verkettete Kleinbuchstaben** Slugs entstehen (keine Leerzeichen – Wörter laufen zusammen).
- Für **manuelle Header-IDs** verwendet MultiMarkdown die Form: `## Headline Text [my-id]` (die in Klammern gesetzte Kennung nach dem Überschriftentext).

### Wann sollte man sich für etwas anderes entscheiden?

Wenn Sie Aufgabenlisten mit **GitHub-Geschmack** und das genaue Verhalten des aktuellen Parsers von GitHub benötigen, bevorzugen Sie **CommonMark (GFM)**. Wenn Sie **feinkörnige HTML-Klassen/IDs** für beliebige Elemente benötigen, ziehen Sie **Kramdown** in Betracht.

---

## Kramdown

**Am besten geeignet für:** Dokumente, bei denen Sie **präzise Kontrolle über die HTML-Ausgabe** wünschen – benutzerdefinierte **Klassen**, **IDs** und Attribute, damit Ihr CSS auf bestimmte Blöcke und Bereiche abzielen kann.

Der [kramdown syntax reference](https://kramdown.gettalong.org/syntax.html) ist der maßgebliche Leitfaden.

### Stärken

- **Größtenteils kompatibel** mit Gewohnheiten im MultiMarkdown-Stil für alltägliche Markdown, mit eigenen Erweiterungen.
- **Inline- und Blockattributlisten (IALs):** Hängen Sie `{: #id .class key="value"}` an Absätze, Überschriften, Codeblöcke, Links, Bilder und mehr an – ideal für Websites im Jekyll-Stil und benutzerdefinierte Stylesheets.
- **Header-IDs:** Kramdown normalisiert automatisch generierte Header-IDs auf **kleingeschriebene, durch Bindestriche getrennte** Wörter (z. B. `my-section-title`). Für **manuelle IDs** verwenden Sie die Form `{#id}` nach dem Überschriftentext – z. B. Setext: `My Section {#my-section}`, dann die Unterstreichung, oder ATX: `# My Section {#my-section}` (genaue Platzierung und IAL-Regeln finden Sie in Kramdowns [headers](https://kramdown.gettalong.org/syntax.html#headers)).
- **Definitionslisten, Fußnoten, intelligente Typografie, Mathematikblöcke:** Umfangreicher Funktionsumfang für die Veröffentlichung von Pipelines, die mehr als „einfaches“ Markdown benötigen.

### Wann sollte man sich für etwas anderes entscheiden?

Wenn Sie sich auf **Nur MultiMarkdown**-Metadatensubstitution (`[%key]`) oder MMD-spezifische Zitierworkflows verlassen, ist **MultiMarkdown** möglicherweise besser geeignet. Für **README- und Repo-Dokumente**, die online mit GitHub übereinstimmen müssen, liegt **CommonMark (GFM)** normalerweise näher.

---

## CommonMark (GitHub Aromatisiert Markdown / cmark-gfm)

**Am besten geeignet für:** **README-Dateien**, **Problem-/PR-Beschreibungen** und **Projektdokumentation**, die so genau wie möglich dem aktuellen Markdown-Verhalten von **GitHub entsprechen sollten.

Marked verwendet eine **GFM**-orientierte Engine (cmark-gfm). Die formale Spezifikation ist [GitHub Flavored Markdown Spec](https://github.github.com/gfm/), die auf [CommonMark](https://commonmark.org/) aufbaut.

### Stärken

- **Höchste Übereinstimmung mit GitHub:** Tabellen, Durchstreichungen, Aufgabenlistenelemente, eingezäunte Codeblöcke mit Sprach-Tags und Autolinks verhalten sich wie modernes GitHub-Rendering.
- **Eindeutiges Parsen:** CommonMark definiert Block-/Inline-Vorrang- und Listenregeln präzise – in einigen Randfällen strenger als das „klassische“ Markdown.pl-Verhalten, aber **vorhersehbarer**, sobald Sie die Regeln gelernt haben.
- **Praktisch für umbrochenen Text:** Absatz- und Listenregeln sind so konzipiert, dass sie sich gut mit fest umbrochenem Text verhalten (siehe Abschnitte der Spezifikation zu Lazy Continuations und Listen).

### Header-IDs

Automatisch generierte Überschriftenanker werden in der Regel **durch Kleinbuchstaben und Bindestriche getrennt**, was dem üblichen Slugging-Stil im GitHub-Stil entspricht.

### Wann sollte man sich für etwas anderes entscheiden?

GFM repliziert keine **MultiMarkdown-Metadaten**, **Kramdown-IALs** oder **MMD-Zitat-Workflows**. Für Bücher, Dissertationen oder umfangreiche Metadaten verwenden Sie je nach Bedarf **MultiMarkdown** oder **Kramdown**.

---

## Rabatt

**Best für:** Ein **schneller, C-basierter** Prozessor, der **klassisches Markdown** und einen **älteren GitHub-basierten** Funktionssatz verfolgt – nützlich, wenn Sie ein Verhalten näher am **original Markdown** plus Tabellen, Fußnoten und zugehörige Erweiterungen ohne das vollständige CommonMark-Regelwerk wünschen.

Projektheim: [Discount](https://www.pell.portland.or.us/~orc/Code/discount/).

### Stärken

- **PHP Markdown Extra-Style-Tabellen** und viele Erweiterungen (Fußnoten, abgeschirmter Code, wenn aktiviert usw. --- siehe [Discount GFM Specification](Discount_GFM_Spec.html) von Marked für die Möglichkeiten von Marked).
- **Optionale „GitHub“-Extras** im Upstream-Rabatt (z. B. Kontrollkästchenlisten, wenn sie mit den richtigen Flags erstellt werden); Marked dokumentiert die gelieferte Kombination auf der Seite „Rabattspezifikation“.
- **Typografie im SmartyPants-Stil** und andere auf der Discount-Website beschriebene Annehmlichkeiten (obwohl alle enthaltenen Prozessoren tatsächlich Typografiefunktionen bieten).
- Philosophisch nahe an **John Grubers Markdown** plus praktischen Erweiterungen, statt der vollständigen CommonMark-Testsuite.

### Wann sollte man sich für etwas anderes entscheiden?

Für **pixelgenaue Parität mit dem heutigen github.com** bevorzugen Sie **CommonMark (GFM)**. Für **MultiMarkdown-Metadaten und Zitate** verwenden Sie **MultiMarkdown**.

---

## Schneller Vergleich

| Sorge | MultiMarkdown | Kramdown | CommonMark (GFM) | Rabatt |
|--------|---------------|--------|------------------|----------|
| **Hauptverwendung** | Prosa, Aufsätze, Bücher | Stilisierte HTML, Jekyll-ähnliche Websites | READMEs, GitHub-ähnliche Dokumente | Klassische MD + Erweiterungen |
| **Zitate / MMD Metadaten** | Stark | Über unterschiedliche Syntax | Nein | Nein |
| **Manueller Überschriften-ID-Stil** | `## Title [id]` | `## Title {: #id }` (IAL) | Spec / GitHub Slug-Regeln | Keine |
| **Auto-Überschriften-IDs** | Kleinbuchstaben verkettet | Kleinbuchstaben mit Bindestrich | Kleinbuchstaben mit Bindestrich | Kleinbuchstaben mit Bindestrich |
| **Zusätzliche Attribute (Klassen/IDs)** | Eingeschränkte MMD-Mechanismen | **IALs** – sehr stark | Begrenzt | Begrenzt |

---

## Siehe auch

- [Settings: Processor](Settings_Processor.html) – Standardprozessor und zugehörige Optionen
- [Markdown Dingus](Markdown_Dingus.html) – Prozessoren nebeneinander in Marked ausprobieren
- [Custom Processor](Custom_Processor.html) – Schließen Sie bei Bedarf Ihre eigene Toolchain an