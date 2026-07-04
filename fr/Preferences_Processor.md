<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Options dans le {% prefspane Processor %} :

![Paramètres : Processeur][1]

[1]: images/screenshots/preferences-Processor.jpg @2x width=689px height=1031px class=preferencepane


### Processus de démarque avec

Processeur Markdown par défaut. Le processeur Discount est préféré pour les utilisateurs de GitHub, MultiMarkdown est idéal pour les rédacteurs. Marked compense certaines différences entre la syntaxe. Voir __Aide->Markdown Reference__ pour plus d'informations.

Règles personnalisées
: utilisez le bouton Règles personnalisées pour ouvrir l'éditeur de règles personnalisées, vous permettant de déterminer les options de traitement et les transformations de documents en fonction de critères. Consultez la [Documentation du processeur personnalisé](Custom_Processor.html) pour plus de détails.

Les nouveaux documents utilisent des
: Sélectionnez le préprocesseur et/ou le processeur pour activer automatiquement le traitement des règles sur les nouveaux documents. Si vous utilisez des règles personnalisées, vous souhaiterez probablement que ces deux fonctions soient activées.

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

\#Le texte est une balise
: permet aux hashtags (`#` immédiatement suivis d'un texte sans espace) d'être interprétés comme des balises, et non comme des titres. Cette fonctionnalité est par défaut pour les utilisateurs de Bear.
: __Style tags__ provoque l'affichage des balises avec un formatage "capsule" pour les distinguer du texte. Lorsque ceci est activé, les balises peuvent être affichées/masquées en utilisant {% appmenu {{gear}}, Proofing, Show Comments %}.

![#Le texte est activé par la balise][textistag]

[textistag]: images/textistag.jpg @2x width=896px height=274px class=center

Rendu `==highlight==` et `~~delete~~`
: Si cette option est activée, alors le texte `==highlight==` sera rendu sous la forme d'une balise HTML `<mark>`, qui apparaîtra sous forme de surbrillance jaune, sauf modification contraire par un style. De plus, la syntaxe `~~delete~~` sera rendue avec une balise `<del>`.

: Si __Render as CriticMarkup__ est activé, alors les syntaxes `==highlight==` et `~~delete~~` seront converties en CriticMarkup, qui pourra ensuite être affichée dans les vues originales, de balisage et modifiées.

Afficher `~text~` sous forme de trait de soulignement
: Si cette option est activée, `~text~` entouré de tildes simples sera rendu souligné. Cela entre en conflit avec la syntaxe MultiMarkdown pour l'indice et est désactivé par défaut.