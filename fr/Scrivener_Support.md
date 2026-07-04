<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Utilisez ensemble vos deux outils d’écriture préférés.

> Marked peut toujours lire les fichiers Scrivener 2.0, mais le développement se concentrera sur la version 3 après Marked 2.5.11.

## Principes de base de Scrivener 3.0

Faites glisser un projet Scrivener (.scriv) vers Marqué et il sera compilé et prévisualisé. Si vous choisissez l'option d'ouvrir les fichiers .scriv dans Scrivener (ci-dessus), Marked lancera également Scrivener lorsque vous faites glisser le fichier vers Marked.

Comme pour les autres documents, les modifications apportées aux fichiers Scrivener sont mises à jour en direct lors de l'enregistrement. De plus, lorsqu'un document Scrivener est au premier plan dans Marqué, {% kbd cmd E %} l'ouvrira dans Scrivener pour vous.

## Filtrage des documents de reliure

Lorsque vous ouvrez un projet Scrivener dans Marked, le contenu de l'aperçu est créé uniquement à partir des documents de reliure que vous sélectionnez. Le filtrage est toujours actif pour `.scriv` fichiers ; le panneau de filtre n'est qu'un moyen pratique de modifier ce qui est inclus.

Ouvrez le panneau depuis **Vérification > Filtrer les documents Scrivener** ({% kbd opt-cmd-f %}). L'élément de menu affiche une coche lorsque le panneau est visible. La fermeture du panneau ne désactive pas le filtrage ni ne réinitialise vos sélections.

Le panneau de filtrage répertorie les sections de classeur de votre projet (Brouillon, Recherche et autres classeurs de niveau supérieur, à l'exception de la Corbeille). Chaque section est réduite par défaut. Développez une section pour voir ses documents et dossiers dans un plan :

- Cochez ou décochez n'importe quel **document texte** pour l'inclure ou l'exclure de l'aperçu.
- Cliquez sur une ligne **dossier** pour sélectionner ou désélectionner tous ses descendants. Un tiret dans la case à cocher signifie que seuls certains descendants sont sélectionnés.
- Les lignes avec **Inclure dans la compilation** désactivées dans Scrivener apparaissent grisées, mais vous pouvez toujours les vérifier pour les prévisualiser dans Marqué.
- **Les images, PDF et autres éléments de classeur non textuels** apparaissent dans la liste mais ne peuvent pas être sélectionnés.
- Les fichiers **RTF** manquants apparaissent toujours ; si vous ajoutez du contenu dans Scrivener alors que Marked est ouvert, l'aperçu est mis à jour lors de l'enregistrement comme toute autre modification Scrivener.

Utilisez **Sélectionner tout** et **Désélectionner tout** en haut du panneau pour l'ensemble du projet. Chaque en-tête de section comporte des boutons **Tous** et **Aucun** pour cette section uniquement. **Désélectionner tout** signifie qu'aucun document n'est vérifié.

Si rien n'est sélectionné, l'aperçu affiche un court message avec un lien pour ouvrir le panneau de filtrage (`x-marked://scrivenerfilter`). Vous pouvez utiliser cette URL dans des scripts ou d'autres applications pour élever le panneau du document Scrivener avant dans Marked.

Vos sélections de cases à cocher sont enregistrées par projet Scrivener (par l'identifiant du projet dans le fichier `.scrivx`) et restaurées la prochaine fois que vous ouvrirez ce projet dans Marqué. La première fois que vous ouvrez un projet, Marked sélectionne uniquement les documents de reliure **Brouillon** dont l'indicateur **Inclure dans la compilation** est Oui (ou non défini, ce que Scrivener traite comme Oui). Les recherches et autres classeurs ne démarrent pas ; Les éléments de brouillon exclus de la compilation ne sont pas cochés mais restent sélectionnables dans la liste.

Les projets Scrivener 2 affichent uniquement le classeur **Draft** dans le panneau de filtrage. Les projets Scrivener 3 incluent tous les classeurs à l'exception de la Corbeille.

Le panneau de filtrage peut rester ouvert aux côtés d'autres outils tels que **Visualiser la répétition de mots**. La modification d'une case à cocher recompile l'aperçu après un court délai ; si un gros projet est toujours en cours de compilation, Marked annule l'importation en cours et recommence avec votre nouvelle sélection.

## En-têtes Markdown des titres Scrivener

Marked peut également créer pour vous des en-têtes Markdown hiérarchiques en fonction des pages de votre fichier Scrivener. Pour activer cela, cochez simplement l’option indiquée ci-dessus.

## Métadonnées MultiMarkdown

Si le premier document de votre dossier Draft est nommé « métadonnées », il sera traité comme des métadonnées MultiMarkdown au début du document d'aperçu. Aucun en-tête ne sera inséré pour cette section, quel que soit le paramètre « En-têtes Markdown des titres Scrivener » (décrit ci-dessus), permettant au processeur MultiMarkdown de le lire en tant que métadonnées et d'autoriser les remplacements et les options d'exportation en conséquence.

Vous pouvez rendre ce fichier au format YAML si votre processeur gère YAML.

Si vous n'utilisez pas de document `metadata`, Marked peut également ajouter les métadonnées MultiMarkdown à partir des paramètres de compilation de votre projet (`Settings/compile.xml`), en utilisant les mêmes champs **Titre** et **Auteur** que Scrivener exporterait vers MultiMarkdown. Ceci est activé par défaut (touche de préférence `scrivenerCompileMetadata`). Les champs de métadonnées personnalisés ne sont inclus que lorsqu'ils apparaissent dans les paramètres de compilation ** Métadonnées MMD ** du projet, et non dans les champs personnalisés par document.

## Liens

Pour les liens externes (HTTP), vous pouvez utiliser soit la syntaxe Markdown, soit le formatage de lien Scrivener. Marked convertira le format Scrivener en Markdown avant le traitement.

## Commentaires

Marqué peut traiter les commentaires et les notes de bas de page créés en ligne dans le document.

## Tableaux

Marked peut convertir les tables Scrivener de base. Cependant, si vous souhaitez inclure un tableau dans votre sortie, il est préférable de le faire au [format de tableau MultiMarkdown](https://github.com/fletcher/MultiMarkdown/wiki/MultiMarkdown-Syntax-Guide#tables). (Une application appelée [TableFlip](http://tableflipapp.com/) peut simplifier leur génération.)

## Fonctionnalités supplémentaires de Scrivener

En plus des fonctionnalités de base de compilation et de prévisualisation, Marked prend également en charge certaines conventions spécifiques à Scrivener. Tout d'abord, dans votre document Scrivener, vous pouvez utiliser « Conserver le formatage » en ligne ou sur un bloc de texte autonome et il sera converti en blocs de code dans l'aperçu.

Marked lit également les notes de bas de page _inline_ de Scrivener. Si vous saisissez une note de bas de page dans ou à la fin d'un paragraphe, elle sera convertie en note de bas de page MultiMarkdown dans l'aperçu.

## Utiliser des images dans votre document Scrivener

Les images peuvent être intégrées dans le document Scrivener ou référencées avec la syntaxe d'image Markdown. La version Markdown d'une balise d'image est `![alt text](path/to/image.ext "optional title/description")`. Le format de référence peut également être utilisé :

    ![texte alternatif][img1]

    [img1] : /path/to/image.ext "description facultative"

Le chemin de base de la sortie HTML dans l'aperçu sera défini sur le dossier contenant le document Scrivener. Ainsi, placer les images dans le même dossier que le document de travail permettra d'y accéder directement. Si votre document Scrivener est en `~/Desktop/TestDoc.scriv` et que vous avez une image appelée "testimage.png" en `~/Desktop/testimage.png`, vous pouvez ajouter l'image à votre document en utilisant :

    ![Image test](imagetest.png)

Les chemins relatifs basés sur le dossier parent du document fonctionneront et les chemins absolus permettront d'accéder aux images n'importe où mais pourraient ne pas être aussi portables pour la sortie HTML.

## Note de sécurité

Un dossier cache sera créé dans ~/Bibliothèque/Application Support/Marked lorsque vous ouvrirez votre fichier .scriv dans Marked. Il ne s'agit pas d'un dossier protégé, donc si votre document original se trouve sur un disque crypté ou autrement protégé, notez que son contenu ne sera pas crypté dans le cache. Pour une protection limitée, vous pouvez vous assurer que ce cache n'apparaît pas dans Spotlight en ajoutant ~/Library/Application Support/Marked à vos paramètres de confidentialité dans Spotlight.

Voir [Intégrations d'applications supplémentaires](Additional_Application_Support.html) pour l'aperçu du presse-papiers, les liens wiki, les scripts et la liste complète des guides par application.