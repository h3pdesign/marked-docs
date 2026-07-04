<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Quick Open offre un accès rapide à vos documents ouverts et fichiers récents.

## Ouverture Ouverture rapide

Accédez au panneau d'ouverture rapide en utilisant {% kbd shift cmd O %} ou depuis le menu {% appmenu File, Quick Open %}. Le panneau apparaît comme une fenêtre flottante au-dessus de votre document actuel, vous permettant de basculer rapidement entre les documents ouverts ou d'ouvrir des fichiers récents.

![Panneau d'ouverture rapide][qo]

[qo]: images/quick-open-800.jpg @2x width=800

## Sections du document

Le panneau Ouverture rapide organise les documents en sections claires :

### Ouvrir des documents

En haut de la liste, vous verrez tous les documents actuellement ouverts. Les documents sont visuellement regroupés par leur fenêtre :

- **Fenêtres à onglets** : les documents dans les fenêtres à onglets affichent "Fenêtre avec X onglets" comme sous-titre, indiquant le nombre d'onglets dans ce groupe de fenêtres.
- **Fenêtres autonomes** : les documents dans des fenêtres individuelles affichent « Fenêtre » comme sous-titre

Chaque document ouvert affiche :
- Le nom de fichier du document comme titre principal
- La fenêtre regroupant les informations comme le sous-titre
- Une icône de document

### Documents récents

Sous les documents ouverts, un séparateur « Documents récents » divise la liste. La section Documents récents affiche jusqu'à 10 de vos fichiers les plus récemment ouverts qui ne sont pas actuellement ouverts. Chaque document récent affiche :

- Le nom de fichier du document comme titre principal
- "Récent" comme sous-titre
- Une icône de document

### Ouvrir Autre

Au bas de la liste, l'option "Ouvrir autre..." vous permet d'ouvrir le sélecteur de fichiers standard macOS pour sélectionner n'importe quel fichier. Cette option affiche :

- "Ouvrir Autre…" comme titre principal
- "Ouvrir un fichier ou un dossier" comme sous-titre
- Une icône de dossier

## Recherche et filtre

Tapez dans le champ de recherche en haut du panneau pour filtrer la liste en temps réel. La recherche correspond à :

- Noms de fichiers de documents
- Chemins de fichiers complets

Au fur et à mesure que vous tapez, la liste est immédiatement mise à jour pour afficher uniquement les documents correspondants. L'option "Ouvrir autre..." reste toujours visible en bas des résultats filtrés.

## Navigation au clavier

Naviguez entièrement dans le panneau Quick Open avec votre clavier :

- **↑/↓ Touches fléchées** : Déplacez-vous de haut en bas dans la liste
- **Retour** : ouvrez le document ou l'option sélectionné
- **Échap** : fermez le panneau d'ouverture rapide
- **Commande (⌘)** : Maintenez enfoncé pour révéler les chemins des fichiers (voir ci-dessous)

## Affichage des chemins de fichiers

Maintenez la touche **Commande (⌘)** enfoncée pendant que le panneau d'ouverture rapide est ouvert pour voir le chemin complet du fichier pour chaque document dans la zone des sous-titres. Les chemins de votre répertoire personnel sont affichés à l'aide du raccourci `~` (par exemple, `~/Documents/file.md`). Relâchez la touche Commande pour revenir à la vue normale affichant le regroupement des fenêtres ou les informations « Récentes ».

Ceci est particulièrement utile lorsque plusieurs fichiers portant le même nom sont ouverts ou lorsque vous devez vérifier l'emplacement exact d'un document.

## Ouverture des documents

- **Documents ouverts** : la sélection d'un document ouvert amène sa fenêtre au premier plan et passe à l'onglet de ce document s'il se trouve dans une fenêtre à onglets
- **Documents récents** : La sélection d'un document récent l'ouvre dans une nouvelle fenêtre ou l'ajoute sous forme d'onglet (selon votre préférence "Ouvrir les documents dans les onglets" dans {% prefspane General %})
- **Ouvrir Autre...** : La sélection de cette option ouvre la boîte de dialogue de sélection de fichiers macOS standard.