<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked can preview the same file with several built-in Markdown processors. Each one makes different tradeoffs between **writing workflow** (books, blogs, GitHub READMEs) and **output control** (IDs, classes, metadata). Vous choisissez la valeur par défaut dans {% prefspane Processor %} ; you can also override the processor per document.

This page summarizes how the four main processors differ. For full syntax details, see the reference pages under **Help → Markdown Reference** (e.g. [MultiMarkdown v5 Specification](MultiMarkdown_v5_Spec.html), [Kramdown Specification](Kramdown_Spec.html), [CommonMark Specification](CommonMark_Spec.html), [Discount GFM Specification](Discount_GFM_Spec.html)).

---

## MultiMarkdown (v5)

**Idéal pour :** la prose longue, la rédaction académique ou technique, et tout ce qui repose sur des **métadonnées**, des **citations** et des fonctionnalités **spécifiques à MultiMarkdown**.

Marked ships with **MultiMarkdown 5** (see the [MultiMarkdown User's Guide](https://fletcher.github.io/MultiMarkdown-5/) for the upstream documentation).

### Strengths

- **Narrative and reference-heavy documents:** Footnotes, bibliography/citations, and tables are first-class.
- **Métadonnées :** Blocs de métadonnées MultiMarkdown standard (`Key: Value` en-têtes) plus **transclusion** et autres commodités MMD décrites dans le guide v5.
- **Metadata substitution:** Keys from metadata can be inserted in the body with `[%key]`-style replacement so titles, author strings, and similar values stay in sync with the header.
- **Tables, images, and cross-references:** Aligned with the features documented for MultiMarkdown 5.

### IDs and manual headings

- Heading IDs are **normalized** in a way that tends to produce **lowercase, concatenated** slugs (no spaces — words run together).
- For **manual header IDs**, MultiMarkdown uses the form: `## Headline Text [my-id]` (the bracketed identifier after the heading text).

### When to pick something else

If you need **GitHub-flavored** task lists and the exact behavior of GitHub’s current parser, prefer **CommonMark (GFM)**. If you need **fine-grained HTML classes/IDs** on arbitrary elements, consider **Kramdown**.

---

## Kramdown

**Idéal pour :** Documents pour lesquels vous souhaitez **un contrôle précis sur la sortie HTML** : **classes**, **ID** et attributs personnalisés, afin que votre CSS puisse cibler des blocs et des étendues spécifiques.

The [kramdown syntax reference](https://kramdown.gettalong.org/syntax.html) is the authoritative guide.

### Strengths

- **Mostly compatible** with MultiMarkdown-style habits for everyday Markdown, while adding its own extensions.
- **Inline and block attribute lists (IALs):** Attach `{: #id .class key="value"}` to paragraphs, headers, code blocks, links, images, and more --- ideal for Jekyll-style sites and custom stylesheets.
- **Header IDs:** kramdown normalizes auto-generated header IDs to **lowercase, hyphen-separated** words (e.g. `my-section-title`). For **manual IDs**, use the `{#id}` form after the headline text — e.g. Setext: `My Section {#my-section}` then the underline, or ATX: `# My Section {#my-section}` (see kramdown’s [headers](https://kramdown.gettalong.org/syntax.html#headers) for exact placement and IAL rules).
- **Listes de définitions, notes de bas de page, typographie intelligente, blocs mathématiques :** Riche ensemble de fonctionnalités pour les pipelines de publication qui nécessitent plus qu'un simple Markdown.

### When to pick something else

If you rely on **MultiMarkdown-only** metadata substitution (`[%key]`) or MMD-specific citation workflows, **MultiMarkdown** may be a better fit. For **README and repo docs** that must match GitHub online, **CommonMark (GFM)** is usually closer.

---

## CommonMark (GitHub Flavored Markdown / cmark-gfm)

**Idéal pour :** **Fichiers README**, **descriptions de problèmes/RP** et **documentation de projet** qui doivent correspondre le plus étroitement possible au **comportement Markdown actuel de GitHub**.

Marked uses a **GFM**-oriented engine (cmark-gfm). La spécification formelle est la [GitHub Flavored Markdown Spec](https://github.github.com/gfm/), construite sur [CommonMark](https://commonmark.org/).

### Strengths

- **Correspondance la plus proche de GitHub :** Les tableaux, les barrés, les éléments de la liste de tâches, les blocs de code clôturés avec des balises de langue et les liens automatiques se comportent comme le rendu GitHub moderne.
- **Unambiguous parsing:** CommonMark defines block/inline precedence and list rules precisely — stricter in some edge cases than "classic" Markdown.pl behavior, but **more predictable** once you learn the rules.
- **Practical for wrapped text:** Paragraph and list rules are designed to behave well with hard-wrapped prose (see the spec's sections on lazy continuations and lists).

### Header IDs

Les ancres de titre générées automatiquement sont généralement **en minuscules et séparées par des traits d'union**, conformément aux slugging courants de style GitHub.

### Quand choisir autre chose

GFM ne réplique pas les flux de travail **métadonnées MultiMarkdown**, **kramdown IAL** ou **MMD citation**. For books, theses, or heavy metadata, use **MultiMarkdown** or **Kramdown** as appropriate.

---

## Discount

**Idéal pour :** Un processeur **rapide basé sur C** qui suit le **Markdown classique** et un ensemble de fonctionnalités **plus anciennes à saveur GitHub** — utile lorsque vous souhaitez un comportement plus proche du **Markdown original** plus des tableaux, des notes de bas de page et des extensions associées sans le livre de règles complet de CommonMark.

Accueil du projet : [Remise](https://www.pell.portland.or.us/~orc/Code/discount/).

### Strengths

- **PHP Markdown Extra-style tables** and many extensions (footnotes, fenced code when enabled, etc. --- see Marked's [Discount GFM Specification](Discount_GFM_Spec.html) for what Marked enables).
- **Optional "GitHub" extras** in upstream Discount (e.g. checkbox lists when built with the right flags); Marqué documente la combinaison qu'il expédie dans la page des spécifications de remise.
- **Typographie de style SmartyPants** et autres commodités décrites sur le site Discount (bien que tous les processeurs inclus offrent en fait des fonctionnalités de typographie).
- Philosophically close to **John Gruber's Markdown** plus practical extensions, rather than the full CommonMark test suite.

### Quand choisir autre chose

Pour une **parité parfaite au pixel près avec le github.com** d'aujourd'hui, préférez **CommonMark (GFM)**. Pour les **métadonnées et citations MultiMarkdown**, utilisez **MultiMarkdown**.

---

## Quick comparison

| Concern | MultiMarkdown | Kramdown | CommonMark (GFM) | Discount |
|--------|---------------|--------|-----------------------|--------------|
| **Primary use** | Prose, papers, books | HTML stylisé, sites de type Jekyll | READMEs, GitHub-like docs | Classic MD + extensions |
| **Citations / MMD metadata** | Fort | Via different syntax | No | No |
| **Manual heading ID style** | `## Title [id]` | `## Title {: #id }` (IAL) | Spec / GitHub slug rules | None |
| **Auto heading IDs** | Lowercase concatenated | Lowercase hyphenated | Lowercase hyphenated | Lowercase-hyphenated |
| **Attributs supplémentaires (classes/identifiants)** | Limited MMD mechanisms | **IALs** — very strong | Limited | Limited |

---

## See also

- [Paramètres : Processeur](Settings_Processor.html) — processeur par défaut et options associées
- [Markdown Dingus](Markdown_Dingus.html) — essayez les processeurs côte à côte dans Marked
- [Custom Processor](Custom_Processor.html) — plug in your own toolchain when needed