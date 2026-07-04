<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked dispose d'une prise en charge étendue pour travailler avec des fichiers Microsoft Word. Le flux de travail typique est **prévisualiser d'abord, exporter DOCX ensuite** : ouvrez ou regardez votre Markdown dans Marked, affinez les styles et la relecture dans l'aperçu en direct, puis exportez vers Word lorsque le document est prêt.

## Ouverture des fichiers DOCX

Marqué peut lire un fichier DOCX et le convertir en fichier propre
Démarquage. Les éléments de style valides tels que les titres et les listes
être convertis en leur équivalent Markdown.

Le suivi des modifications et les commentaires seront convertis en
CritiqueMarkup. Les faits saillants seront convertis en `<mark>` balises,
avec des couleurs le cas échéant.

## Exportation de fichiers DOCX

Utilisez la palette Exporter pour générer un fichier DOCX à partir de votre
Démarquage. Dans la boîte de dialogue d'enregistrement, vous pouvez spécifier un
styles --- ce style peut facilement être modifié dans Word simplement en
ouvrir le sélecteur de thème et sélectionner un nouveau thème.

### En-têtes et pieds de page

Si vous configurez les en-têtes et pieds de page en {% prefspane Export %}, ils sont inclus dans le DOCX exporté. Les espaces réservés standard tels que `%title`, `%date`, `%page` et `%total` sont remplacés au moment de l'exportation. `%logo` et `%image` intègrent le logo des préférences En-tête/Pied de page. `%md_*` Les variables de métadonnées sont résolues à partir des métadonnées MultiMarkdown du document. `%h1`--`%h6` deviennent des champs Word **STYLEREF** liés aux styles de titre exportés ; Word les remplit lorsque vous ouvrez le document. Voir [Exportation](Exporting.html#headers-and-footers) pour la liste complète des variables et les différences entre le comportement DOCX et l'impression/PDF.

## Suivi des modifications

La syntaxe CriticMarkup dans un document Markdown sera convertie
au suivi des modifications Word lors de l'exportation vers DOCX. Commentaires
les insertions, suppressions et substitutions suivantes seront
apparaître dans la colonne de droite dans Word lors du suivi des modifications
est activé.

Lors de l'importation d'un fichier DOCX dans Marked, le suivi des modifications sera
être converti en balises CriticMarkup et `<mark>` comme
approprié.

## Mathématiques

Les équations MathJax et Katex affichées dans le document seront converties en MathML pour être affichées dans Word. Cette conversion n'est pas parfaite, mais dans la plupart des cas, elle restituera un bloc mathématique valide dans le document Word. Cela s'applique uniquement à l'exportation : les blocs mathématiques des documents Word ne seront pas convertis lors de l'importation.

## Ajout de styles d'exportation personnalisés

Vous pouvez ajouter vos propres styles d'exportation en incluant un modèle et un fichier styles.xml dans `~/Library/Application Support/Marked/Custom Word Styles/`. Pour les créer :

1. Ouvrez un fichier DOCX généré par Marked dans Word
2. Modifiez les styles dans l'éditeur de styles pour chaque élément, en sélectionnant "Ajouter au modèle" pour chacun.
3. Enregistrez le fichier DOCX.
4. Générez un modèle en accédant à **Conception** dans la barre supérieure, et dans la liste déroulante *Modèle* sur la gauche, cliquez sur **Enregistrer le modèle actuel**. Nommez-le comme vous souhaitez qu'il apparaisse dans le menu Style marqué et enregistrez-le sous `~/Library/Application Support/Marked/Custom Word Styles/STYLENAME.thmx`, où `STYLENAME` est le nom de votre style.
5. Accédez au Finder et localisez le fichier DOCX que vous avez enregistré à partir de Word. Dupliquez-le et renommez la copie en `FILENAME.zip` et double-cliquez dessus pour la décompresser.
6. Dans le document décompressé, vous verrez un dossier « word » contenant un fichier styles.xml. Copiez ce fichier styles.xml dans le même dossier que ci-dessus et nommez-le `STYLENAME.xml` (où `STYLENAME` est le nom de votre style). Les fichiers `.thmx` et `.xml` doivent avoir le même nom de base (juste des extensions différentes).

La prochaine fois que vous exporterez un DOCX depuis Marked, vous verrez votre nouveau style dans le menu Style de la boîte de dialogue Enregistrer.