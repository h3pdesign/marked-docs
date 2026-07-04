<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

## Qu'est-ce que le Markdown ?

Markdown est un langage de balisage léger qui vous permet d'écrire en utilisant un format de texte brut facile à lire et à écrire, puis de le convertir en HTML structurellement valide. L'objectif primordial de la conception de la syntaxe de formatage de Markdown est de la rendre aussi lisible que possible.

## Syntaxe de base

### En-têtes

Créez des en-têtes à l'aide de symboles de hachage (`#`). Le nombre de hachages détermine le niveau d'en-tête :

```markdown
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6
```

### Accentuation

**Texte en gras** utilisant des doubles astérisques ou des doubles traits de soulignement :

```markdown
**Bold text**
__Bold text__
```

*Texte en italique* utilisant des astérisques simples ou des traits de soulignement simples :

```markdown
*Italic text*
_Italic text_
```

### Listes

**Listes non ordonnées** utilisant des astérisques, des signes plus ou des traits d'union :

```markdown
* Item 1
* Item 2
* Item 3

+ Item 1
+ Item 2
+ Item 3

- Item 1
- Item 2
- Item 3
```

**Listes ordonnées** utilisant des nombres suivis de points :

```markdown
1. First item
2. Second item
3. Third item
```

### Liens

**Liens en ligne** avec le texte entre crochets et l'URL entre parenthèses :

```markdown
[Link text](http://example.com)
```

**Liens de référence** avec le texte entre crochets et une référence entre crochets :

```markdown
[Link text][reference]

[reference]: http://example.com "Optional title"
```

**Liens automatiques** en plaçant les URL entre crochets :

```markdown
<http://example.com>
<user@example.com>
```

### Images

Les images utilisent une syntaxe similaire aux liens mais avec un point d'exclamation au début :

```markdown
![Alt text](http://example.com/image.jpg)
![Alt text][image-reference]

[image-reference]: http://example.com/image.jpg "Optional title"
```

### Citations

Créez des guillemets en utilisant le symbole supérieur à (`>`) au début de chaque ligne :

```markdown
> This is a blockquote.
> It can span multiple lines.
>
> You can have multiple paragraphs in a blockquote.
```

###Code

**Code en ligne** utilisant des backticks :

```markdown
Use ⟦4⟧ in your text.
```

**Blocs de code** en indentant avec quatre espaces ou une tabulation :

```markdown
    This is a code block.
    It preserves formatting and spacing.
    Multiple lines are supported.
```

### Règles horizontales

Créez des règles horizontales en utilisant au moins trois traits d'union, astérisques ou traits de soulignement :

```markdown
---

***

___
```

### Sauts de ligne

**Sauts de ligne définitifs** en terminant une ligne par deux espaces ou plus :

```markdown
This line ends with two spaces.
This creates a hard line break.
```

**Sauts de ligne doux** en appuyant simplement sur Entrée (crée un espace en HTML) :

```markdown
This line
continues on the next line with a space.
```

### Caractères d'échappement

Échapper aux caractères spéciaux à l'aide de barres obliques inverses :

```markdown
\*This text is not italic\*
\[This is not a link\]
```

Caractères courants pouvant être échappés :
- `\` barre oblique inverse
- `` ` `` backtick
- `*` astérisque
- `_` soulignement
- `{}` accolades
- `[]` crochets
- `()` parenthèses
- `#` hachage
- `+` plus
- `-` moins
- `.` période
- `!` point d'exclamation

## meilleures pratiques

1. **Utilisez des lignes vides** pour séparer les différents éléments pour une meilleure lisibilité
2. **Soyez cohérent** avec vos choix de formatage (par exemple, utilisez `*` ou `_` pour mettre l'accent)
3. **Gardez les choses simples** - Markdown est conçu pour être lisible sous forme de texte brut
4. **Testez votre sortie** pour vous assurer qu'elle s'affiche comme prévu
5. **Utilisez un texte de lien significatif** au lieu d'expressions génériques telles que « cliquez ici »

## Modèles courants

### Listes imbriquées

```markdown
1. First item
   - Nested item
   - Another nested item
2. Second item
   - More nested content
```

### Listes avec paragraphes

```markdown
1. First item

   This is a paragraph under the first item.

2. Second item

   This is a paragraph under the second item.
```

### Blockquotes avec d'autres éléments

```markdown
> This is a blockquote with **bold text** and *italic text*.
>
> - It can contain lists
> - And other Markdown elements
>
> > Nested blockquotes are also possible.
```

## Résumé

Markdown fournit un moyen simple et lisible de formater du texte qui peut être facilement converti en HTML. La clé est de le garder simple et lisible tout en utilisant les éléments de syntaxe de base de manière cohérente. Avec de la pratique, vous constaterez que Markdown devient une seconde nature et facilite grandement la rédaction de contenu structuré.

---

*Ce didacticiel couvre la syntaxe de base de Markdown telle que définie dans la spécification originale. Pour des fonctionnalités plus avancées, consultez la documentation des processeurs Markdown spécifiques tels que CommonMark (GFM), MultiMarkdown ou GitHub Flavored Markdown.*