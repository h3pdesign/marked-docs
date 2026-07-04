<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Options dans le {% prefspane Processor %} :

![Paramètres : Processeur][1]

[1]: images/screenshots/preferences-Processor.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Processus de démarque avec

Processeur Markdown par défaut. Le processeur CommonMark est préféré pour les utilisateurs de GitHub, MultiMarkdown est idéal pour les rédacteurs et Discount et Kramdown ont des objectifs spécialisés. Marked compense certaines différences entre la syntaxe. Voir __Aide->Markdown Reference__ pour plus d'informations.

Règles personnalisées
: cliquez sur le bouton Règles personnalisées pour ouvrir l'éditeur de règles, dans lequel vous pouvez spécifier différents processeurs et transformations de documents à exécuter en fonction de critères de correspondance. Voir [Processeur personnalisé](Custom_Processor.html) pour plus de détails.

Les nouveaux documents utilisent des
 : lorsque cette case est cochée, les nouveaux documents utilisent automatiquement votre **préprocesseur** et/ou **processeur** enregistré à partir des règles personnalisées sans nécessiter de configuration par document.

Accès complet au disque
 : cliquez sur **Accorder** pour accorder à Marked l'autorisation de lire des fichiers en dehors de son bac à sable lors de l'utilisation de processeurs personnalisés ou d'autres fonctionnalités nécessitant un accès plus large aux fichiers.

Pour explorer les différences entre les processeurs, consultez le [Markdown Dingus](Markdown_Dingus.html).

### HTML

Générer des identifiants sur les titres
 : Génère des ID d'en-tête basés sur le contenu de la balise h1-h6.

Utiliser des identifiants de notes de bas de page aléatoires
: Générez des ID de note de bas de page aléatoires pour éviter les conflits lorsque plusieurs documents sont affichés sur une seule page.

Traiter le Markdown à l'intérieur du HTML
: Par défaut, le Markdown à l'intérieur des balises HTML est généralement ignoré. Cette option force Marked à poursuivre le traitement dans les éléments de bloc. Notez que certains balisages peuvent causer des problèmes.

### Rendu

Conserver les sauts de ligne dans les paragraphes
 : Respecter les sauts de ligne dans le texte du paragraphe, en les remplaçant par des sauts nets au lieu de les concaténer avec la ligne précédente.

Rendre les cases à cocher GitHub
: Rendu `- [ ]` et `- [x]` pour créer des cases à cocher dans les listes. Les cases à cocher sont affichées pour l'aperçu mais ne fonctionnent pas dans Marked.

Afficher GitHub : emoji :
: Rendu `:name:` shortcodes sous forme d'emoji de style GitHub dans l'aperçu.

\#Le texte est une balise
: permet aux hashtags (`#` immédiatement suivis d'un texte sans espace) d'être interprétés comme des balises, et non comme des titres. Cette fonctionnalité est par défaut pour les utilisateurs de Bear.

Balises de style
 : Lorsque **#Text is tag** est activé, affiche les balises reconnues avec un style de capsule. Les balises peuvent être affichées ou masquées depuis {% appmenu {{gear}}, Proofing, Show Comments %}.

![#Le texte est activé par la balise][textistag]

[textistag]: images/textistag.jpg @2x width=896px height=274px class=center

Rendu `==highlight==` et `~~delete~~`
: Si cette option est activée, alors le texte `==highlight==` sera rendu sous la forme d'une balise HTML `<mark>`, qui apparaîtra sous forme de surbrillance jaune, sauf modification contraire par un style. De plus, la syntaxe `~~delete~~` sera rendue avec une balise `<del>`.

: Si __Render as CriticMarkup__ est activé, alors les syntaxes `==highlight==` et `~~delete~~` seront converties en CriticMarkup, qui pourra ensuite être affichée dans les vues originales, de balisage et modifiées.

Afficher `~text~` sous forme de trait de soulignement
: Si cette option est activée, `~text~` entouré de tildes simples sera rendu souligné. Cela entre en conflit avec la syntaxe MultiMarkdown pour l'indice et est désactivé par défaut.