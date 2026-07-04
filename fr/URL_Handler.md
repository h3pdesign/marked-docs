<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Le gestionnaire d'URL de Marked fournit des fonctionnalités de script et de flux de travail supplémentaires. Vous pouvez inclure une URL dans les notes d'une autre application, par exemple, qui ouvrira un fichier dans Marqué lorsque vous cliquerez dessus. Vous pouvez effectuer plusieurs actions, répertoriées ci-dessous.

## Le schéma d'URL

Le schéma d'URL de Marked est `x-marked`, appelé avec des options telles que `x-marked://open?file=/Users/username/Desktop/report.md`.

Vous pouvez cibler spécifiquement Marked 3 en utilisant `x-marked-3` au lieu de `x-marked`. Les méthodes et paramètres sont exactement les mêmes que pour `x-marked`, mais seul Marked 3 répondra à `x-marked-3`.

## Appel depuis la ligne de commande/les scripts

L'appel du gestionnaire d'URL à partir de la ligne de commande ou d'un script peut être effectué à l'aide de macOS [`open` command](http://brettterpstra.com/2014/08/06/shell-tricks-the-os-x-open-command/) :

	ouvrez 'x-marked://open?file=filename.md'
	ouvrez 'x-marked://refresh?file=filename.md'

### Appel en arrière-plan

Vous pouvez appeler la commande `open` avec l'indicateur `-g` pour exécuter le résultat en arrière-plan sans changer de focus. Pour exécuter la commande en arrière-plan et élever la fenêtre vers le haut sans voler le focus :

	open -g 'x-marked://open?file=filename.md&raise=true'

## Paramètres facultatifs

### x-succès

N'importe quelle commande peut fournir un paramètre de requête **x-success**. Définissez ceci sur une URL à appeler après avoir exécuté la commande. Par exemple : `x-marked://open/?file=filename.md&x-success=ithoughts:`. Vous pouvez également fournir un identifiant de bundle (tel que `com.googlecode.iterm`) pour ouvrir une application qui n'a pas de schéma d'URL.

### augmenter

Un paramètre **raise** peut être passé avec n'importe quelle commande qui accepte un paramètre `file` ou affecte toutes les fenêtres. Une fois l'action effectuée, la ou les fenêtres concernées s'élèveront au-dessus de toutes les autres fenêtres (toutes les applications) avant de renvoyer ou d'exécuter un rappel.

	"marqué x://refresh?file=filename.md&raise=true"

### lecture rapide

Un paramètre **speedread** peut être transmis avec les commandes du gestionnaire d'URL qui ouvrent un document d'aperçu (`open`, `paste`, `preview` et `stream`). Définissez `speedread=1` pour démarrer automatiquement Speed ​​Read dès que l'aperçu cible est prêt.

Exemples :

	x-marked://open?file=/Users/username/Desktop/report.md&speedread=1

	x-marked://preview?text=Some%20text&speedread=1

	marqué d'un x://paste?speedread=1

# Commandes disponibles

Les commandes suivantes sont disponibles pour le gestionnaire d'URL `x-marked`.

## ajouter un style

Ajoutez un nouveau style personnalisé à Marqué.

##### Paramètres :

**css** : texte CSS codé en URL à écrire dans un style personnalisé. Obligatoire sauf si vous transmettez un paramètre **file**.

**fichier** : chemin complet (POSIX) vers un fichier CSS à ajouter à Marked. Obligatoire sauf si vous passez un paramètre **css**.

**name** : Le nom du style à générer.

Avec le paramètre **css**, celui-ci sera utilisé à la fois comme nom de fichier lors de l'écriture sur le disque, avec ".css" ajouté, et comme nom d'élément de menu. Il est obligatoire pour le paramètre **css** et facultatif pour **file** (le nom du fichier sera utilisé comme si le paramètre name était vide).

	x-marked://addstyle?name=Mon+nouveau+style&css=...

	x-marked://addstyle?file=/Users/myuser/Custom+Styles/Unicorn.css

Si vous incluez un nom avec le paramètre file, l'élément de menu obtiendra ce nom au lieu du nom de fichier. Si vous utilisez à nouveau le même nom avec un chemin différent, l'élément de menu sera mis à jour avec le nouveau chemin plutôt que d'ajouter un deuxième élément portant le même nom.

## valeurs par défaut

Définir les paramètres utilisateur. Accepte une liste de clés et de valeurs comme paramètres de requête. Seules les clés existantes seront définies. Si le changement de préférence nécessite une actualisation, toutes les fenêtres s'actualiseront automatiquement à moins que `refresh=0` ne soit transmis.

Utilisez 1 pour vrai et 0 pour faux sur les valeurs booléennes.

##### Paramètres :

**rafraîchir** _(facultatif)_ : si défini sur 0, l'actualisation automatique des fenêtres d'aperçu ouvertes est désactivée

* Par défaut : 1 (vrai)

##### Exemple :

marqué x://defaults?syntaxHighlight=1&includeMathJax=0

La méthode `defaults` est principalement conçue pour que le développeur puisse ajouter des liens vers des fonctionnalités ésotériques qui autrement ne seraient pas disponibles dans les paramètres. Cependant, vous souhaiterez peut-être activer certaines options standard lors de l'automatisation. Certains paramètres courants que vous souhaiterez peut-être contrôler pendant l'automatisation :

syntaxeHighlight
: activer ou désactiver la coloration syntaxique

inclureMathJax
: activer ou désactiver la gestion interne de MathJax

processeur
: réglé sur `multimarkdown` ou `mmd` pour changer le processeur en MultiMarkdown, `discount` ou `gfm` pour utiliser le processeur Discount

h1IsPageBreak, h1IsPageBreak, breakBeforeFootnotes
: Sauts de page automatiques à l'export avant les niveaux d'en-tête 1 et 2 et les notes de bas de page.


## dingus

Ouvrez le Markdown Dingus pour tester différents processeurs Markdown.

	X-marqué://dingus

##### Paramètres :

**processeur** (facultatif) : spécifiez le processeur à sélectionner par défaut. Valeurs valides :

- `multimarkdown` - Processeur MultiMarkdown
- `commonmark` - Processeur CommonMark (GFM)
- `discount` ou `discount (gfm)` - Processeur de remise
- `kramdown` - Processeur Kramdown

Exemples :

- `x-marked://dingus?processor=kramdown` - S'ouvre avec Kramdown sélectionné
- `x-marked://dingus?processor=commonmark` - S'ouvre avec CommonMark (GFM) sélectionné

*Remarque :* Cela ouvre la fenêtre Markdown Dingus, qui vous permet de tester et de comparer différents processeurs Markdown (MultiMarkdown, CommonMark (GFM), Discount et Kramdown) côte à côte. Parfait pour expérimenter la syntaxe Markdown et comprendre les différences entre les processeurs.

## stylestealer / voler

Ouvrez le HUD du voleur de style. Utile lorsque vous souhaitez capturer du CSS à partir d'une page en direct ou exécuter une session d'extraction de contenu manuelle sans la lancer via l'interface utilisateur.

	Synonymes : x-marked://stylestealer… , x-marked://steal…

##### Paramètres :

**url** _(facultatif)_ : une URL à pré-remplir dans la fenêtre Style Stealer. En cas d'omission, le HUD s'ouvre vide.

Exemples :

- `x-marked://stylestealer?url=https%3A%2F%2Fmarkedapp.com`
- `x-marked://steal/https:%2F%2Fexample.com`

## importurl / markdownify

Ouvrez la fenêtre « Importer l'URL » (Content Extractor) pour pouvoir exécuter le pipeline Markdownifier manuellement. Cela n'effectue **pas** l'extraction automatiquement - qui est gérée par la commande `extract` ci-dessous.

	Synonymes : x-marked://importurl… , x-marked://markdownify…

##### Paramètres :

**url** _(facultatif)_ : préremplit le champ URL d'importation. En cas d'omission, la fenêtre s'ouvre avec un champ vide attendant que vous colliez un lien.
**html** _(facultatif, markdownify uniquement)_ : lorsqu'il est fourni le `x-marked://markdownify`, il doit s'agir de HTML brut codé en URL. Marked convertira le HTML en Markdown en utilisant les mêmes règles que l'aperçu du Presse-papiers et l'ouvrira dans un document transitoire, comme si vous aviez collé ce HTML dans une fenêtre d'aperçu du Presse-papiers.

Exemples :

- `x-marked://importurl?url=https%3A%2F%2Fexample.com%2Farticle`
- `x-marked://markdownify/https:%2F%2Fnews.ycombinator.com`

## faire

Exécutez une commande JavaScript dans une fenêtre de document. L'intégralité de l'API JavaScript de Marked est [documentée ici](https://markedapp.com/help/jsapi/).

##### Paramètres :

**js** _(obligatoire)_ : chaîne de requête contenant une commande JavaScript

* Accepte les paramètres de chemin faisant référence aux noms de fichiers, ou "tous"
* Les chemins divisés par / rechercheront plusieurs fichiers
* Les noms de fichiers partiels complèteront la meilleure correspondance

		x-marked://do/filename1/filename2?js=...
		marqué x://do/all?js=...

**file** : paramètre de requête contenant des chemins/noms de fichiers séparés par des virgules

	x-marked://do?file=filename1,filename2&js=...

Fonctionnera sur la fenêtre la plus en avant si un nom de fichier n'est pas donné (ou si "tout" n'est pas transmis)

## aide

Ouvrez le système d'aide interne Marked, en spécifiant éventuellement une rubrique. Ceci est principalement destiné à une utilisation interne, mais accessible via une URL. Une URL vers une section donnée peut être copiée en cliquant avec le bouton droit sur l'icône de signet à droite d'un titre et en sélectionnant __Copier le lien__. **Marked 3** L'aide et la recherche dans l'application utilisent le schéma `x-marked-3` pour ces liens afin que macOS les ouvre dans Marked 3 lorsque Marked 2 est également installé ; les exemples ci-dessous utilisent ce formulaire.

##### dingue

Ouvrez le Markdown Dingus pour tester différents processeurs Markdown.

	X-marqué://dingus

######## Paramètres :

**processeur** (facultatif) : spécifiez le processeur à sélectionner par défaut. Valeurs valides :

- `multimarkdown` - Processeur MultiMarkdown
- `commonmark` - Processeur CommonMark (GFM)
- `discount` ou `discount (gfm)` - Processeur de remise
- `kramdown` - Processeur Kramdown

Exemples :

- `x-marked://dingus?processor=kramdown` - S'ouvre avec Kramdown sélectionné
- `x-marked://dingus?processor=commonmark` - S'ouvre avec CommonMark (GFM) sélectionné

*Remarque :* Cela ouvre la fenêtre Markdown Dingus, qui vous permet de tester et de comparer différents processeurs Markdown (MultiMarkdown, CommonMark (GFM), Discount et Kramdown) côte à côte. Parfait pour expérimenter la syntaxe Markdown et comprendre les différences entre les processeurs.

##### Paramètres :

**page** _(facultatif)_ : le titre exact d'une page existante, avec un hachage d'ancrage facultatif

	x-marked-3://help?page=Document_Statistics

Les espaces sont remplacés par des traits de soulignement, conformément à la convention de dénomination des fichiers d'aide marqués. Un deux-points (:) peut être utilisé à la place d'un hachage (#) lors de la spécification d'une ancre.

La cible peut être spécifiée par chemin uniquement (sans chaîne de requête) :

	x-marked-3://help/Keyword_Highlighting:editingkeywords


## extrait

Extrayez le contenu d'une URL Web et ouvrez-le en tant que nouveau document dans Marqué.

	marqué d'un x://extract?url=https://example.com

##### Paramètres :

**url** _(obligatoire)_ : L'URL Web à partir de laquelle extraire le contenu. Doit commencer par `http://` ou `https://`

**window** _(facultatif)_ : Nom de la fenêtre

**id** _(facultatif)_ : identifiant de l'espace de noms

**base** _(facultatif)_ : URL de base pour les liens relatifs

**raise** _(facultatif)_ : réglé sur `true` pour relever la fenêtre après l'ouverture

**manuel** _(facultatif)_ : définissez sur `true` pour ouvrir la fenêtre d'extraction manuelle de Style Stealer au lieu d'effectuer une extraction automatique.

- Lorsque `manual=true`, Marqué ouvre le Style Stealer, pré-remplit le champ URL (si fourni), supprime toute boîte de dialogue d'ouverture automatique et vous permet de sélectionner et d'extraire de manière interactive les styles/contenus avant de les enregistrer.
- En cas d'omission ou de `false`, Marked exécute l'extracteur automatique (Markdownifier) ​​et ouvre directement le résultat en tant que nouveau document temporaire.

##### Exemples :

	marqué d'un x://extract?url=https://news.ycombinator.com

	marqué d'un x://extract?url=https://github.com&window=GitHub&raise=true

	marqué d'un x://extract?url=https://example.com/article&manual=true

	marqué d'un x://extract?url=https://blog.example.com/post-title

*Remarque :* Cette commande utilise le service d'extraction de contenu de Marked pour récupérer des pages Web, extraire du contenu propre à l'aide de Readability, le convertir au format Markdown et ouvrir le résultat dans un nouveau document temporaire. Le contenu extrait comprend des métadonnées (titre, URL source, date) et est formaté en Markdown propre. Parfait pour capturer et éditer rapidement du contenu Web.

## ouvert

Ouvre le document spécifié dans Marqué.

	x-marked://open?file=/Users/username/Desktop/report.md

##### Paramètres :

**fichier** *(obligatoire)* : le chemin POSIX complet du document à ouvrir, ou une liste de chemins séparés par des virgules

**speedread** *(facultatif)* : définissez sur `1` pour démarrer automatiquement Speed Read après l'ouverture.

`open` accepte également un chemin dont les composants seront combinés en une seule url

	marqué x://open/~/nvALT2.2

Si le chemin du fichier fourni n'existe pas ou ne peut pas être ouvert, Marqué sera toujours au premier plan. L'exécution sans le paramètre *file* ou avec une valeur vide ouvrira simplement Marked.

Marqué ouvrira également les fichiers si seul le chemin d'un fichier est appelé sur le gestionnaire d'URL, par ex. `x-marked:///Users/username/Desktop/report.md`.

## coller

Créez un nouveau document à partir du contenu actuel du presse-papiers.

	marqué d'un X://coller

##### Paramètres :

**speedread** *(facultatif)* : définissez sur `1` pour démarrer automatiquement Speed Read après avoir ouvert l'aperçu du presse-papiers.

*Remarque :* Cela crée un document temporaire à l'aide de la commande "Aperçu du Presse-papiers". Tout texte présent dans votre presse-papiers est ajouté à un nouveau document vierge, qui est ensuite ouvert dans Marqué. S'il est fermé sans enregistrer, il est supprimé.

## aperçu

Prévisualisez le texte spécifié dans un nouveau document.

	x-marked://preview?text=Some%20text%20to%20%2A%2Apreview%2A%2A%0A

##### Paramètres :

**text** *(obligatoire)* : Le texte à insérer dans l'aperçu. Le texte codé en pourcentage sera non codé avant la visualisation du document.

**speedread** *(facultatif)* : définissez sur `1` pour démarrer automatiquement Speed ​​Read après avoir ouvert le texte d'aperçu.

## flux

Ouvrez une fenêtre d'aperçu du presse-papiers en streaming.

	marqué x://stream

##### Paramètres :

**speedread** *(facultatif)* : définissez sur `1` pour démarrer automatiquement Speed Read après avoir ouvert l'aperçu en streaming.

*Remarque :* Cela crée un document temporaire à l'aide de la commande "Aperçu du Presse-papiers". Le texte transmis est ajouté à un nouveau document vierge, qui est ensuite ouvert dans Marqué. S'il est fermé sans enregistrer, il est supprimé.

## actualiser

Actualisez un aperçu de document ou tous les aperçus ouverts.

##### Paramètres :

**fichier** : paramètre de requête contenant des chemins/noms de fichiers séparés par des virgules (les fichiers doivent être actuellement ouverts dans Marked). Appeler sans paramètre `file` ou `?file=all` actualisera toutes les fenêtres ouvertes.

Le paramètre *file* peut être partiel, Marked actualisera toutes les fenêtres ouvertes avec une correspondance partielle dans le *filename* (pas le chemin complet). Passer « tout » actualisera toutes les fenêtres.

	marqué x://rafraîchir

	x-marked://refresh?file=/Users/username/Desktop/report.md

	marqué x://refresh?file=report.md

S'il est appelé sans le paramètre `file` mais avec les chemins de document spécifiés dans l'URL, les chemins divisés par / rechercheront plusieurs fichiers et les noms de fichiers partiels complèteront la meilleure correspondance.

	marqué x://refresh/filename1/filename2

##style

Définissez le style d'aperçu (CSS) pour un ou plusieurs documents.

##### Paramètres :

**css** _(obligatoire)_ : chaîne de requête contenant le nom ou le chemin d'un style. Les styles doivent être présents dans le menu de styles de Marked en tant que styles personnalisés par défaut ou ajoutés manuellement.

* Accepte les paramètres de chemin faisant référence aux noms de fichiers, ou "tous"
* Les chemins divisés par / rechercheront plusieurs fichiers
* Les noms de fichiers partiels complèteront la meilleure correspondance

		x-marked://style/filename1/filename2?css=...
		marqué x://style/all?css=...

**file** : paramètre de requête contenant des chemins/noms de fichiers séparés par des virgules

	x-marked://style?file=filename1,filename2&css=...

Cette méthode fonctionnera sur la fenêtre la plus en avant si aucun nom de fichier n'est donné (ou si "tout" n'est pas transmis).