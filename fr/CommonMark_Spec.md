<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Consultez le [Markdown Dingus](x-marked-3://dingus?processor=commonmark) pour expérimenter le processeur CommonMark (GFM).


## What is CommonMark?

CommonMark is a strongly specified, highly compatible implementation of Markdown. Il a été créé pour résoudre les ambiguïtés et les incohérences de la spécification Markdown originale de John Gruber, qui ont conduit à des implémentations divergentes sur différentes plates-formes et outils.

## Why CommonMark Exists

La spécification Markdown originale de John Gruber était intentionnellement ambiguë dans de nombreux domaines, conduisant à des interprétations différentes selon diverses implémentations. This created problems where the same Markdown document would render differently on different platforms (GitHub, StackOverflow, Reddit, etc.).

CommonMark provides:

- **Unambiguous specifications** for all Markdown syntax
- **Suite de tests complète** pour garantir un comportement cohérent
- **Règles de priorité claires** en cas de syntaxe conflictuelle
- **Algorithme d'analyse détaillé** qui peut être implémenté de manière cohérente

## Différences clés par rapport à la démarque standard

### 1. **Règles d'analyse plus strictes**

CommonMark applique un comportement d'analyse plus cohérent :

**Blank Lines Before Block Elements**

- CommonMark requires blank lines before headings, blockquotes, and lists
- Standard Markdown les autorise souvent sans lignes vides

```markdown
Text
# Heading
```

*CommonMark : nécessite une ligne vierge avant le titre*

*Standard Markdown : permet souvent sans ligne vierge*

### 2. **Analyse des éléments de liste**

**Indentation Requirements**

- CommonMark has specific rules for list item indentation
- Les sous-listes doivent être indentées de manière cohérente (généralement 4 espaces)
- Standard Markdown implementations vary on this

```markdown
1. First item
   - Sublist item (4 spaces required in CommonMark)
2. Second item
```

**List Continuation**

- CommonMark a des règles claires pour savoir quand les éléments de la liste sont « lâches » ou « serrés ».
- Loose lists wrap items in `<p>` tags, tight lists don't

### 3. **Gestion des blocs de code**

**Fenced Code Blocks**

- CommonMark standardise la syntaxe des blocs de code clôturés avec des backticks ou des tildes
- Requires consistent indentation and closing markers


    ```language
    code here
    ```


**Indented Code Blocks**

- CommonMark requires blank lines before indented code blocks
- Standard Markdown les autorise souvent sans lignes vides

### 4. **Traitement des liens et des images**

**Reference Link Precedence**

- CommonMark a des règles claires pour lesquelles la définition de référence est prioritaire
- Plusieurs définitions pour la même référence sont traitées de manière cohérente

```markdown
[link1]: /url1
[link1]: /url2
[link1]  <!-- Uses /url2 in CommonMark -->
```

**Link Parsing Order**

- CommonMark processes links before emphasis
- Cela affecte la façon dont la syntaxe imbriquée est interprétée

### 5. **Emphase et forte emphase**

**Règles d'accentuation imbriquées**

- CommonMark dispose d'algorithmes spécifiques pour gérer les marqueurs imbriqués `*` et `_`
- Prevents ambiguous parsing of complex emphasis patterns

```markdown
*foo *bar* baz*  <!-- Clear precedence rules in CommonMark -->
```

**Delimiter Processing**

- CommonMark uses a "delimiter stack" algorithm for consistent emphasis parsing
- Les implémentations standard de Markdown varient dans leur approche

### 6. **Traitement des blocs HTML**

**HTML Block Detection**

- CommonMark dispose de 7 types différents de blocs HTML avec des règles spécifiques
- Chaque type a des exigences différentes pour les conditions de début/fin

```html
<div>
This is an HTML block in CommonMark
</div>
```

### 7. **Gestion des sauts de ligne**

**Hard Line Breaks**

- CommonMark nécessite deux espaces en fin de ligne pour les coupures brutales
- Single line breaks become soft breaks (ignored in HTML)

```markdown
Line one
Line two  <!-- Two spaces before line break -->
```

### 8. **Références d'entités et de personnages**

**Références de caractères numériques**

- CommonMark prend en charge les références numériques décimales et hexadécimales
- Standard Markdown support varies

```html
&#8212;  <!-- Decimal -->
&#x2014; <!-- Hexadecimal -->
```

## Algorithme d'analyse CommonMark

CommonMark utilise une approche d'analyse en deux phases :

### Phase 1: Block Structure

1. **Traitement des lignes** : chaque ligne est analysée pour les marqueurs au niveau du bloc
2. **Blocs de conteneurs** : les blockquotes, les listes et autres conteneurs sont identifiés
3. **Leaf Blocks**: Headings, code blocks, paragraphs are processed
4. **Reference Links**: Link definitions are collected for later use

### Phase 2 : Structure en ligne

1. **Traitement en ligne** : le texte dans les blocs est analysé pour les éléments en ligne
2. **Emphasis Parsing**: Uses delimiter stack algorithm for consistent emphasis
3. **Link Resolution**: Reference links are resolved using collected definitions
4. **Traitement d'entité** : les références de caractères sont converties en caractères réels

## Avantages de CommonMark

1. **Comportement prévisible** : la même entrée produit toujours la même sortie
2. **Compatibilité multiplateforme** : fonctionne de manière cohérente sur différents outils
3. **Tests complets** : une suite de tests complète garantit la fiabilité
4. **Documentation claire** : les spécifications détaillées éliminent les conjectures
5. **À l'épreuve du temps** : points d'extension bien définis pour les nouvelles fonctionnalités

## Implementation Notes

CommonMark est conçu pour être :

- **Specification-compliant**: Follows the official CommonMark spec exactly
- **Test-driven** : réussit la suite de tests officielle CommonMark
- **Extensible** : peut être étendu avec des fonctionnalités supplémentaires tout en conservant la compatibilité
- **Rapide** : algorithmes d'analyse optimisés pour les performances

## Resources

- [Spécification CommonMark](https://spec.commonmark.org/0.31.2/)
- [CommonMark Test Suite](https://github.com/commonmark/commonmark-spec)
- [CommonMark Dingus](https://spec.commonmark.org/dingus/) - Outil de test en ligne
- [Forum de discussion CommonMark](https://talk.commonmark.org/)

---

*Cette documentation couvre CommonMark 0.31.2 (2024-01-28). Pour les informations les plus récentes, reportez-vous toujours à la spécification officielle.*