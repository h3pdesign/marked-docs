<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Options dans le {% prefspane Apps %} :

(Voir [Prise en charge supplémentaire des applications](Additional_Application_Support.html))

![Paramètres : Applications][1]

[1]: images/screenshots/preferences-Apps.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Paramètres généraux

Éditeur de texte
: Sélectionnez un éditeur de texte pour recevoir le document actuel lorsque vous tapez {% kbd cmd E %}.

Modifier automatiquement les nouveaux fichiers
: Lorsque vous utilisez la commande "Nouveau fichier", cette option ouvrira automatiquement le fichier créé dans l'éditeur externe de votre choix.

Les liens vers les fichiers texte doivent s'ouvrir dans :
: Détermine le comportement de Marked lorsqu'un lien cliqué dans une fenêtre d'aperçu mène à un fichier texte local.

Éditeur d'images
: Sélectionnez une application à ouvrir lorsqu'un clic droit sur une image locale est effectué et que "Modifier l'image" est sélectionné.

Éditeur d'annotations/balisages d'images
: Sélectionnez une application à ouvrir lorsqu'un clic droit sur une image locale est effectué et que "Annoter l'image" est sélectionné.

Si aucun éditeur n'est choisi, Marked présente un menu des applications installées lorsque vous modifiez ou annotez. Le menu comprend des outils Markdown, d'image et d'annotation courants trouvés sur votre Mac, une option **Autre…** pour choisir n'importe quelle application parmi `/Applications` et **Toujours utiliser cette application** (activée par défaut) pour enregistrer votre choix par défaut. Utilisez le bouton Effacer (encercler avec un X) à côté de chaque contrôle Choisir dans {% prefspane Apps %} pour supprimer une sélection et revenir au sélecteur.

### Paramètres spécifiques à l'application

Afficher les commentaires et annotations par défaut
: Si cette case est cochée, les annotations faites dans les documents Scrivener, Fountain, Word et CriticMarkup apparaîtront en surbrillance dans l'aperçu. Décochez pour masquer complètement. Ceux-ci peuvent également être activés lors de la lecture d'un document à partir du menu {% appmenu Gear, Proofing ({{ctrl}}{{cmd}}C)%}.
: Lorsque les commentaires sont activés, les commentaires et les notes de bas de page apparaîtront dans une barre latérale. Le survol d'un commentaire indiquera son emplacement dans le document.

#### DocC

[(Infos sur le support DocC)](DocC_Support.html)

Résoudre les références d'images DocC
: Dans un catalogue de documentation `.docc`, résolvez les références `![](ImageName)` sans extension aux images du dossier `Resources` du catalogue, y compris les variantes `~dark` et `@2x`.

Résoudre les variantes d'image sombres et @2x
: Pour les images locales avec une extension de fichier (`images/icon.png`), détectez les fichiers compagnons `~dark` et `@2x` dans le même dossier et émettez un balisage réactif `<picture>`. Fonctionne dans n'importe quel document Markdown ou HTML, pas seulement dans les catalogues DocC. Voir [Variantes d'images](Image_Variants.html).

#### Crochet

Résoudre les URL hook:// dans les images et les liens
: Marked peut lire les URL créées par Hookmark, en les résolvant selon leur chemin sur le disque.

#### Leanpub/GitBook

Activer la prise en charge de Leanpub
: Interprète les fichiers nommés `Book.txt` comme fichiers d'index et gère la syntaxe Leanpub spéciale.

Activer la prise en charge de GitBook
: Interprétez les fichiers nommés `SUMMARY.md` comme fichiers d'index pour la documentation GitBook.

#### Markdownifier

Utiliser des liens en ligne
: Les documents Markdown créés par Markdownifier utiliseront des liens en ligne au lieu de liens de référence.

#### Mars

Inclure le titre du message comme en-tête Markdown (h1)
: Utilisez le titre de la publication sélectionnée comme en-tête Markdown.

Afficher les métadonnées sous forme de tableau
: Lorsqu'elles sont activées, les métadonnées telles que les catégories et les titres seront affichées sous forme de tableau Markdown dans l'aperçu.

#### Dossiers

Prévisualisez uniquement ces extensions
: Lors de l'ouverture d'un dossier, Marked recherchera le document modifié le plus récemment, par défaut avec des extensions telles que `md`, `mmd` et `html`. La liste ici remplace la liste par défaut.

#### Scriveneur

[(Informations sur le support Scrivener)](Scrivener_Support.html)

Inclure les titres des documents comme en-têtes Markdown
 : analysez le titre des pages et des pages imbriquées pour créer des en-têtes Markdown hiérarchiques.

Ajouter des métadonnées de compilation (titre, auteur) en cas d'absence
: Lorsqu'un projet Scrivener n'a pas de document `metadata` ou d'en-tête MultiMarkdown existant, ajoutez Titre et Auteur à partir des paramètres de compilation du projet (`Settings/compile.xml`).

Ouvrez les fichiers .scriv dans Scrivener lorsqu'ils sont ouverts dans Marked
: Lorsqu'un document Scrivener est ouvert dans Marqué, ouvrez-le également automatiquement dans Scrivener.

#### Mot

Convertir le suivi des modifications <-> CriticMarkup
: Si activé, le suivi des modifications dans les documents Word sera converti en CriticMarkup lors de l'importation, et CriticMarkup sera converti en suivi des modifications Word lors de l'exportation de fichiers DOCX.

#### Cartes mentales/Contours {#MindMapsOutlines}

Intégrer en tant que cartes mentales de sirène
: Chaque case à cocher contrôle un format inclus. Lorsqu'il est **activé**, le fichier inclus est converti en un diagramme de carte mentale Sirène (disposition en arbre bien rangé). Lorsqu'il est **désactivé**, Marked utilise l'alternative pour ce format.
: **Cartes mentales** — iThoughts X (.itmz), MindManager (.mmap), FreeMind (.mm). Si activé : carte mentale de la sirène. Si cette option est désactivée : iThoughts intègre son image d'aperçu ; MindManager et FreeMind se convertissent en listes Markdown imbriquées.
: **Fichiers OPML** (.opml). Si activé : carte mentale de la sirène. Si désactivé : liste Markdown imbriquée.
: **Contours OmniOutliner** (.ooutline). Si activé : carte mentale de la sirène. Si désactivé : liste Markdown imbriquée (ou liste de contrôle le cas échéant).
: **Contours de vélo**. Si activé : carte mentale de la sirène. Si désactivé : liste Markdown imbriquée.