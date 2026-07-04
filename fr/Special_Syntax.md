<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

## appels

## Ours/Obsidienne ##

Marked prend en charge les légendes avec la syntaxe utilisée par Obsidian et Bear, qui est une citation en bloc spécialement formatée :

	> [!NOTE] Titre de la note
	> Texte supplémentaire

La « REMARQUE » dans `[!NOTE]` n'est pas sensible à la casse. Il peut s'agir de :

- REMARQUE
- RÉSUMÉ, RÉSUMÉ, TLDR
- INFOS
- À FAIRE
- CONSEIL, ASTUCE, IMPORTANT
- SUCCÈS, VÉRIFIER, FAIT
- QUESTION, AIDE, FAQ
- AVERTISSEMENT, ATTENTION, ATTENTION
- ÉCHEC, ÉCHEC, MANQUANT
- DANGER, ERREUR
- BOGUE
- EXEMPLE
- CITATION, CITE

Ceux-ci créeront des blocs spécialement formatés.

Vous pouvez utiliser un `+` ou un `-` pour rendre la légende pliable. Un signe plus (`+`) signifie que la légende est pliable mais qu'elle s'ouvre par défaut. Un signe moins (`-`) signifie que la légende est pliable mais qu'elle est fermée par défaut.

  ![Callouts dans Marqué][callouts]

[callouts]: images/callouts-800.jpg @2x width=800

### Terrain de jeu Xcode ###

Lors de la prévisualisation des fichiers Xcode Playground, Marked prend en charge la syntaxe native de légende Xcode Playground :

	- Attention : Titre facultatif
	Le contenu de l'accroche est placé ici.

Le type de légende (par exemple, « Attention ») ne respecte pas la casse et peut être l'un des types de légende Xcode Playground suivants :

- **Attention** – Conçu comme une légende d'information
- **Auteur** – Légende des métadonnées
- **Auteurs** – Légende des métadonnées
- **Bug** - Légende d'erreur/danger
- **Complexité** – Légende de style note
- **Copyright** - Légende des métadonnées
- **Légende personnalisée** – Légende de style exemple
- **Date** – Légende des métadonnées
- **Exemple** - Exemple de légende
- **Expérience** – Légende de style astuce
- **Important** – Légende de style info
- **Invariant** - Légende de style note
- **Remarque** - Légende de note
- ** Précondition ** – Légende de style note
- **Postcondition** – Légende de style note
- **Remarque** - Légende de style note
- **Nécessite** – Légende de style note
- **Voir aussi** - Légende de style info
- **Depuis** – Légende des métadonnées
- **Version** – Légende des métadonnées
- **Avertissement** - Légende d'avertissement

Le titre facultatif après les deux-points sera utilisé comme titre de l'accroche. Si aucun titre n’est fourni, le nom du type d’accroche sera utilisé comme titre.

Le contenu de la légende suit immédiatement la ligne suivante (aucune ligne vide n'est requise). Le contenu continue jusqu'à une ligne vide, la légende suivante, un bloc de code isolé ou la fin du document.

Exemple :

```` démarque
- Important : Note sur les performances
Cet algorithme a une complexité O(n log n).

- Exemple : Tri rapide
Voici comment le mettre en œuvre :

```swift
func quickSort(_ array: [Int]) -> [Int] {
   // implementation
}
```
````

Vous pouvez également omettre complètement le titre :

	- Attention
	Il s'agit d'un avertissement sans titre personnalisé.

Ces légendes sont automatiquement converties au format de légende de Marked et stylées de manière appropriée. Le type de légende d'origine est conservé dans l'attribut `data-callout`, permettant un style CSS personnalisé si vous le souhaitez.

> Cette fonctionnalité ne fonctionne que lors de la prévisualisation des fichiers Xcode Playground (`.playground`). Les fichiers de démarques classiques ne traiteront pas cette syntaxe.


## Table des matières

Vous pouvez spécifier où dans le document la table des matières doit apparaître en utilisant `<!--TOC-->`. Si cette option est définie, elle remplace l'option dans les Préférences et s'affichera toujours dans la fenêtre d'aperçu ainsi que lors de l'enregistrement et de l'impression. La table des matières ne s'affichera qu'une seule fois, même s'il y a plusieurs spécificateurs `<!--TOC-->` dans le contenu.

Si vous ajoutez `max#` à la balise ci-dessus (où # est un chiffre de 1 à 5), cela contrôlera la profondeur de la table des matières affichée. Par exemple, `<!--TOC max2-->` affichera uniquement les en-têtes de premier et de deuxième niveaux dans la liste. Vous pouvez également spécifier un niveau d'en-tête minimum avec `<!--TOC min2-->`. Les maximums et les minimums sont basés sur les niveaux réels et non sur les niveaux d'imbrication. Le maximum et le minimum peuvent être utilisés ensemble.

Marked reconnaît également le style MultiMarkdown `{{TOC}}` et le style Pandoc `{{TOC:2-6}}`, où `2-6` est la plage de niveaux minimum et maximum d'en-têtes à inclure.

Par défaut, la table des matières s'imprimera sur la première page du document si « Imprimer la table des matières » est activé sous le {% prefspane Export %}. Si un marqueur existe dans le document, il sera placé à cet endroit.

I> Vous pouvez spécifier le type de numérotation ou de lettrage de chaque niveau d'une hiérarchie de table des matières imbriquée dans le {% prefspane Export %}.

## Sauts de page

Vous pouvez forcer un saut de page pour la sortie impression/PDF en utilisant la syntaxe :

```html
<!--BREAK-->
```

Placez le jeton sur une ligne seul et il générera un balisage qui forcera une nouvelle page à ce stade. Marked comprend également le format Leanpub :

	{::saut de page /}

## Le défilement automatique met en pause [pause]

Marked peut fonctionner comme un téléprompteur en utilisant la fonction [Défilement automatique](Autoscroll.html) (vous devez ajouter le [Style de téléprompteur](https://markedapp.com/styles/preview?style=teleprompter)). Ce faisant, il peut être utile d’inclure des pauses dans le document. Faites cela en utilisant :

```html
<!--PAUSE:X-->
```

Où `X` est le nombre de secondes pendant lesquelles Marked doit faire une pause. Ainsi, insérer `<!--PAUSE:15-->` vous donnerait une pause de 15 secondes lorsque ce point du document atteint le milieu de l'écran.

## Le fichier comprend

Le contenu de fichiers supplémentaires peut être inséré en utilisant la syntaxe :

	<<[dossier/nom de fichier]

Le chemin d'accès au fichier peut être relatif au fichier d'index ou absolu. Les inclusions peuvent être imbriquées ; vous pouvez utiliser cette même syntaxe dans un fichier inclus. Si vous utilisez des chemins relatifs, les inclusions dans les fichiers imbriqués doivent être relatives à ce fichier. ***Cependant*** MultiMarkdown traitera tout en fonction de l'emplacement du premier fichier ouvert, de sorte que tous les chemins d'image ou autres intégrations doivent être relatifs au premier fichier parent, même s'ils existent dans des documents enfants.

Les métadonnées MultiMarkdown et les en-têtes YAML sont automatiquement supprimés des fichiers inclus avant le rendu. Cela empêchera les en-têtes d'apparaître dans le document, mais sachez que les métadonnées telles que le « niveau d'en-tête de base » seront ignorées dans les documents inclus.

T> Notez que lors de la visualisation de documents contenant des fichiers inclus, vous pouvez taper « I » (shift-i) pour voir quel fichier inclus se trouve dans la zone visible.

Voir ["Documents multi-fichiers"][ext] pour plus d'informations.

[ext]: Multi-File_Documents.html

## Y compris le code

Marked peut inclure des fichiers externes sous forme de code en utilisant une syntaxe similaire à celle des fichiers inclus ci-dessus :

	<<(dossier/nom de fichier)

Notez les parenthèses au lieu des crochets. Pour des raisons de compatibilité avec la syntaxe Leanpub, Marked reconnaîtra également un ensemble précédent de crochets contenant un titre, mais pour l'instant, rien n'est fait avec celui-ci dans Marked :

	<<[Titre du code](dossier/nom de fichier)

Le contenu du fichier spécifié sera inséré dans un bloc pré>code de votre document et sera disponible pour la coloration syntaxique automatique si elle est activée. Les blocs de code ne peuvent pas être imbriqués et ne seront pas traités avec MultiMarkdown. Les processeurs personnalisés seront toujours exécutés sur le bloc pré>code créé.

## Y compris le texte ou le HTML non traité

E> **Remarque :** Cette fonctionnalité est destinée aux utilisateurs avancés.

Si vous souhaitez inclure du HTML brut ou un autre texte qui ne doit pas être traité par MultiMarkdown (ou votre processeur personnalisé), vous pouvez utiliser des accolades (`{}`) pour inclure un fichier *après* avoir traité le reste du document :

	<<{dossier/raw_file.html}

Aucune syntaxe d'inclusion ne sera reconnue dans ces fichiers (pas d'imbrication) et le contenu **brut** du fichier sera inséré dans la sortie HTML finale. C'est idéal pour insérer du HTML sans enliser le traitement de texte ou sans convertir/échapper des éléments lorsque vous ne le souhaitez pas, mais soyez prudent car il existe peu de garanties pour garantir que le formatage du document est préservé autour de ce que vous insérez.