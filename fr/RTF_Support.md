<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marqué peut ouvrir directement les documents Rich Text Format (`.rtf`) et RTFD (`.rtfd`). Faites glisser un fichier vers Marqué ou utilisez {% appmenu File, Open... ({{cmd}}O) %}. Le document est converti en Markdown pour prévisualisation et exportation.

Cela fonctionne bien avec les documents de **Pages**, **TextEdit**, **Word** et d'autres applications qui enregistrent RTF ou RTFD. Marked est toujours un outil **d'aperçu** : vous modifiez dans l'application d'origine et les mises à jour marquées lorsque vous enregistrez.

## Comment fonctionne la conversion

Marked convertit RTF en HTML à l'aide du moteur de texte du système, puis en Markdown. Le convertisseur :

- Mappe les **grandes tailles de police de paragraphe** aux niveaux de titre (par rapport à la taille de corps la plus courante dans le document)
- Préserve les **gras**, *italique* et les liens lorsque cela est possible
- Extrait les **images** des bundles RTFD et des pièces jointes intégrées
- Ne traite **pas** les noms de fichiers RTF comme légendes d'images (voir images ci-dessous)

Le même pipeline de conversion est utilisé pour la compilation Scrivener RTF et pour les fichiers RTF inclus dans d'autres documents.

## Aperçu en direct

Lorsque vous enregistrez le fichier RTF ou RTFD dans une autre application, Marked détecte la modification et actualise automatiquement l'aperçu.

## Images

RTF ne définit pas de champ "légende" distinct comme Cocoa l'exporte au format HTML. Ce qui ressemble à une légende dans votre mise en page est généralement du **texte normal** dans le paragraphe suivant, et Marked le conserve comme corps de texte.

Les images intégrées et les images dans les bundles RTFD (par exemple `pastedGraphic.png` dans une exportation Pages) sont copiées dans un dossier de cache sous `~/Library/Caches/Marked/Watchers/`. Les chemins d’accès aux images d’aperçu pointent vers ces fichiers mis en cache jusqu’à ce que vous les exportiez.

Marked n'utilise **pas** le nom de fichier image comme texte alternatif ou légende de figure MultiMarkdown. Vous ne devriez pas voir `pastedGraphic.png` sous l'image à moins que vous n'ayez tapé ce texte dans le document.

## Exportation et autres fonctionnalités

Après la conversion, Marked traite le document comme les autres sources compilées (similaires à [Scrivener](Scrivener_Support.html) et [DOCX](Working_with_DOCX.html)) : l'exportation, les statistiques et la plupart des fonctionnalités d'aperçu s'exécutent sur le Markdown généré stocké dans le cache Watchers.

## Limites

La qualité de la conversion dépend de l'application source. En général :

- Les **titres** sont déduits de la taille de la police, et non des styles de contour Word/Pages.
- **Mise en page complexe** (tableaux à plusieurs colonnes utilisés uniquement pour le positionnement, zones de texte) peut ne pas correspondre correctement à Markdown
- **Les équations** en RTF ne sont pas prises en charge dans l'aperçu (voir [MathJax](MathJax.html) pour les mathématiques Markdown)
- **Legacy `.doc`** (Word binaire) n'est pas pris en charge ; enregistrer d'abord au format DOCX ou RTF

Pour un collage unique sans enregistrer de fichier, utilisez plutôt [Aperçu du presse-papiers](Opening_Files.html#from-the-clipboard).

## Sujets connexes

- [Support PDF](PDF_Support.html) -- ouvrir des documents PDF en tant que sources Markdown
-[Travailler avec DOCX](Working_with_DOCX.html) -- Documents Word avec suivi des modifications et commentaires
- [Ouverture de fichiers](Opening_Files.html) -- glisser-déposer, ouvrir récent, presse-papiers
- [Exportation](Exporting.html) -- Copiez le texte enrichi et enregistrez RTFD (exportation), distinct de l'ouverture de RTF en tant que fichier source