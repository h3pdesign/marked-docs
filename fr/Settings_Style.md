<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Options dans le {% prefspane Style %} :

![Paramètres : Style][1]

[1]: images/screenshots/preferences-Style.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Mise en page et typographie

Limiter la largeur du texte dans l'aperçu
: Définissez une largeur maximale pour le corps de l'aperçu à l'aide du curseur (en pixels).

Césure automatique dans les paragraphes
: Autoriser les mots à rompre automatiquement avec la césure.

Empêcher les veuves dans les titres et les paragraphes
 : force un espace insécable entre les deux derniers mots des titres et des paragraphes pour empêcher que des mots simples ne soient renvoyés sur une nouvelle ligne.

Générez des guillemets et des signes de ponctuation typographiquement corrects
: Utilisez SmartyPants pour les guillemets intelligents, la conversion d'ellipses et d'autres fonctionnalités typographiques (MultiMarkdown).

Entourez les marqueurs de notes de bas de page de crochets
: Si cette case est cochée, utilisez le formatage MultiMarkdown par défaut pour les marqueurs de notes de bas de page ([1]). Décochez pour supprimer les crochets.

Activer le plan pour les extensions
: active automatiquement le mode Plan pour les fichiers avec les extensions répertoriées.

Utiliser le style APA
: utilisez les contours de style APA au lieu du format décimal par défaut.

Styliser les blocs verbatim (code) comme de la poésie
: Si coché, le code en retrait, clôturé ou inclus est affiché sous forme de poésie au lieu d'un bloc de code (pas de coloration syntaxique et style spécial selon le thème).

Autoriser les thèmes à envelopper le texte dans des blocs de code
: Si cette case est cochée, les thèmes peuvent provoquer un enroulement dans `pre>code` blocs. Si cette case n'est pas cochée, le débordement horizontal défilera toujours.

Toujours envelopper le code
 : Forcer l'habillage des blocs de code quels que soient les paramètres du thème (remplace le comportement d'habillage du thème).

Détecter et styliser le texte RTL
: Détectez la langue par élément dans le document et stylisez de droite à gauche en conséquence.

### Thème

Gérer les styles
: Ouvre la fenêtre [Style Manager](Style_Manager.html). Ajoutez des fichiers CSS depuis votre lecteur pour les faire apparaître dans les menus du sélecteur de styles. Utilisez le bouton `Add New Style` ou faites glisser les fichiers CSS vers cette fenêtre. Faites glisser pour réorganiser et utilisez les cases à cocher pour activer ou désactiver les styles.

Plus de thèmes
: ouvrez la galerie de thèmes en ligne pour parcourir et installer des styles supplémentaires.

Style par défaut
: Le style sélectionné ici sera chargé pour toutes les nouvelles fenêtres, à moins qu'un [style spécifique au document soit indiqué dans les métadonnées](Per-Document_Settings.html) (par exemple "Style marqué : Grump").

Suivre les modifications CSS
: Lorsque cette option est activée, Marked surveillera le style actuel pour les modifications du disque, facilitant ainsi l'édition de style personnalisé et le développement Web.

CSS supplémentaire
: Le CSS ajouté ici sera inclus après la feuille de style normale avec tous les thèmes. Entre autres choses, vous pouvez l'utiliser pour remplacer les paramètres à tous les niveaux sans modifier les styles internes.
: Ceci s'applique à tous les documents et à tous les styles. Si vous souhaitez appliquer du CSS personnalisé aux documents en fonction de conditions, utilisez les règles personnalisées sous {% prefspane Processor %}.

### Inclure les scripts

Mise en évidence de la syntaxe
: Activez highlight.js [surbrillance de la syntaxe](Syntax_Highlighting.html) pour les blocs de code. Sélectionnez un thème dans la liste déroulante.
: Si **Seulement si la langue spécifiée** est cochée, la coloration syntaxique ne sera appliquée qu'aux blocs de code isolés avec une langue spécifiée.

Activer MathJax
: Charge [MathJax](MathJax.html) pour afficher les équations MathML. Choisissez **Local** (groupé) ou **CDN** dans la liste déroulante.
: **Paquets supplémentaires** ouvre une feuille pour inclure des packages MathJax supplémentaires (par exemple Physique et Chimie).
: **Configuration avancée** ouvre une feuille pour la configuration MathJax personnalisée.

Activer KaTeX
: Charge [KaTeX](Mathjax.html#katex) comme alternative à MathJax. Seul l'un ou l'autre peut être sélectionné.

Équations numériques
: Le cas échéant, Marked ajoutera des numéros de figures aux équations rendues. Choisissez **Côté gauche** ou **Côté droit** pour la numérotation. Si vous utilisez MathJax, vous pouvez choisir **AMS uniquement** pour numéroter uniquement les équations AMS.

Sirène
: Charge [mermaid.js](https://mermaid.js) à partir d'un CDN pour activer la création de diagrammes de style Markdown. Le hook requis pour afficher les diagrammes Mermaid à chaque mise à jour de document est inclus automatiquement.

Diagrammes de panoramique et de zoom
: Lorsque des diagrammes Sirène sont présents, activez le zoom avec le défilement {% kbd cmd %} et le panoramique en cliquant et en faisant glisser.