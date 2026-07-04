<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked utilise beaucoup de JavaScript pour fournir les fonctionnalités qu'il propose dans l'aperçu. Pour cette raison, de nombreuses complications peuvent survenir lorsque des scripts sont inclus dans le corps du document.

## Scripts externes

Vous pouvez inclure des scripts externes à l'aide d'une ligne de métadonnées « En-tête CSS : » en haut de votre document. Ces scripts ne seront cependant pas insérés dans l'en-tête, mais dans le pied de page une fois que les scripts de jQuery et Marked auront déjà été chargés. C’est idéal dans la plupart des cas. Vous pouvez toujours rencontrer un comportement inattendu, car Marked ne peut pas compenser tous les conflits de script possibles. Les modifications du DOM peuvent être particulièrement problématiques.

    En-tête CSS : <script src="file.js"></script>

## Inline inclut

Il existe de nombreuses applications permettant de faire apparaître JavaScript dans le corps d'un document, telles que des générateurs de graphiques ou d'autres outils Canvas. En fonction des paramètres de configuration et du processeur que vous utilisez, ceux-ci sont souvent mutilés. La solution consiste à placer votre script et vos éléments DOM supplémentaires dans un fichier externe et à utiliser la syntaxe de Marked pour les [fichiers d'inclusion "bruts"] [syntaxe]. Ces fichiers ne font l'objet d'aucun traitement ; leur contenu est ajouté au fichier une fois le reste du traitement terminé.

    Texte de démarque.

    <<{fichier.html}

    Plus de texte Markdown...

Pour expérimenter et déboguer le JavaScript qui s'exécute dans l'aperçu de Marked, vous pouvez attacher l'inspecteur Web de Safari à la fenêtre d'aperçu en suivant les étapes de [WebKit Inspector](Writing_Custom_CSS.html#webkitinspector).

[syntax]: Special_Syntax.html#includingunprocessedtextorhtml