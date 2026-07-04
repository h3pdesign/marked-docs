<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Le Markdown Dingus est un outil de test spécialisé qui aide
vous comprenez comment les différents processeurs Markdown gèrent votre
contenu. Il fournit une interface à trois volets où vous pouvez
modifiez Markdown, affichez la source HTML générée et voyez le
aperçu rendu simultanément.

Le Dingus partage une certaine maniabilité de bas niveau avec celui de Marked
aperçu, comme un traitement spécial des blocs de code clôturés.
Il n'exécute __pas__ [Règles personnalisées](Custom_Processor.html)
(Chef d'orchestre). Il utilise la plupart des paramètres par défaut, ignorant les paramètres
comme "nouvelles lignes GitHub" et "cases à cocher GitHub", donc le
Le résultat peut différer de ce que vous voyez dans un marquage normal
aperçu.

## Les règles personnalisées ne s'appliquent pas

Le Dingus est un __processor sandbox__ : votre Markdown va
directement au processeur intégré que vous choisissez (MultiMarkdown,
CommonMark (GFM), Discount ou Kramdown). [Règles personnalisées](Custom_Processor.html)
ne jamais y exécuter — pas d'actions de prétraitement, de règles de recherche/remplacement,
commandes shell, insérer du texte/fichier ou d’autres étapes de Conductor.

Dans un aperçu normal, les règles personnalisées peuvent modifier la démarque
avant le rendu, définissez les styles, injectez du CSS ou du JavaScript, et
plus. Rien de tout cela ne se produit lorsque vous modifiez dans Dingus.
La modification des règles personnalisées pendant que le Dingus est ouvert ne change rien.
mettre à jour son aperçu.

Les Dingus __peuvent__ utiliser les mêmes [styles CSS d'aperçu](Custom_Styles.html)
comme fenêtre principale (via le menu de style dans le volet de sortie).
Ce n’est qu’une apparence ; ce n'est pas la même chose que d'exécuter Custom
Règles.

__Ouvrir dans Dingus__ à partir d'un aperçu charge le document
tampon de démarque actuel. Si les règles personnalisées étaient déjà exécutées lorsque
ce fichier a été ouvert dans Marqué, vous pouvez voir leurs effets dans
le texte (par exemple, le texte inséré par une règle), mais le
Dingus ne réappliquera pas les règles au fur et à mesure que vous tapez. Pour tester personnalisé
Règles, utilisez un aperçu marqué standard ou enregistrez à partir de Dingus
et ouvrez le fichier avec __Open in Marked__.

## Qu'est-ce qu'un « Dingus » ?

Un « dingus » est un terme emprunté au développement web qui
fait référence à un simple outil de test ou à un environnement sandbox. Le
Markdown Dingus vous permet d'expérimenter la syntaxe Markdown et
voyez immédiatement comment les différents processeurs l’interprètent.

## Accéder au Dingus

Le Markdown Dingus est accessible depuis
[{% appmenu Help, Open Markdown Dingus %}][2]. C'est particulièrement
utile lorsque vous êtes :

* Apprentissage de la nouvelle syntaxe Markdown
* Dépannage des problèmes de rendu
* Choisir entre différents processeurs
* Rédiger une documentation qui doit fonctionner sur plusieurs
  systèmes

## Disposition à trois volets

![][1]

La fenêtre Dingus est divisée en trois volets synchronisés :

### 1. Entrée Markdown (volet de gauche)

* __Syntax Highlighting__ : votre Markdown est mis en évidence avec
  des couleurs pour rendre la structure claire
* __Live Editing__ : saisissez et voyez les modifications reflétées instantanément
  dans les autres volets
* __Large Font__ : police Menlo 21 pt pour une édition confortable

__Options déroulantes__ (en haut à droite du volet de gauche) : le
Le menu **Options** vous permet de basculer :

* __Afficher les numéros de ligne__ : Affiche une gouttière à gauche avec
  un numéro de ligne par paragraphe (les lignes retournées comptent pour un
  ligne).
* __Afficher les invisibles__ : affiche les espaces sous forme de points médians (·), les tabulations sous forme de
  une flèche vers la droite (→) et des nouvelles lignes comme retour chariot
  symbole (↵) en gris clair pour que vous puissiez repérer les parasites
  espace blanc.
* __Highlight gremlins__ : met un fond rouge clair sur
  caractères non-ASCII (par exemple, guillemets bouclés, emoji) et un caractère sombre
  fond rouge sur les caractères invisibles problématiques (par ex.
  espaces de largeur nulle). Les caractères de tabulation et de nouvelle ligne normaux sont
  pas mis en valeur.

Vos choix sont enregistrés et restaurés lors de votre prochaine ouverture
les Dingus.

__Barre de recherche__ : appuyez sur **⌘F** pour afficher la barre de recherche sous le
Étiquette « Entrée Markdown ». Vous pouvez rechercher et remplacer dans le
éditeur, utilisez **⌘G** pour Rechercher suivant et **⇧⌘G** pour Rechercher
Précédent et remplacez une ou toutes les correspondances. Appuyez sur la touche de fermeture
ou **⌘F** à nouveau pour masquer la barre de recherche.

### 2. Source HTML (volet du milieu)

* __Generated HTML__ : voyez exactement quel HTML est sélectionné
  le processeur crée
* __Syntaxe mise en évidence__ : le HTML est codé par couleur pour faciliter
  lecture

### 3. Aperçu rendu (volet droit)

* __Live Preview__ : découvrez à quoi ressemblera votre Markdown lorsque
  rendu
* __Emoji Support__ : les emojis de style GitHub comme `:zzz:` sont
  converti en images
* __Auto-scrolling__ : défile automatiquement pour afficher votre
  position d'édition actuelle

## Édition dans le Dingus

Le volet de saisie Markdown comprend des fonctionnalités d'édition intelligentes pour
rendre l'écriture de Markdown plus rapide et plus naturelle.

### Nouvelle ligne intelligente (touche Retour)

Un appui sur Retour s'adapte à la ligne actuelle :

* __Lists__ : Sur une ligne de liste (`-`, `*` , `+` ou `1.` ),
  insère un nouvel élément de liste avec le marqueur correct. Numéroté
  les listes continuent avec le numéro suivant.
* __Blockquotes__ : Sur une ligne commençant par `>` , insère un
  nouvelle ligne de citation de bloc.
* __Code fences__ : sur une ligne avec trois backticks ou plus
  (par exemple ` ``` `), insère une ligne vide entre l'ouverture
  et la fermeture des clôtures.
* __Autres lignes__ : insère une nouvelle ligne normale.

### Appariement des caractères

Lorsque vous tapez un caractère d'ouverture, l'éditeur
insère le caractère de fermeture et place le curseur entre
eux. Paires prises en charge : `"` `'` `(` `[` `` ` `` `<` .

* __Avec sélection__ : Encapsule le texte sélectionné dans la paire.
* __Sans sélection__ : Insère la paire avec le curseur
  entre eux.
* __Type-over__ : Si le caractère suivant est déjà le
  délimiteur de fermeture, le taper à nouveau déplace le curseur au-delà
  au lieu d'insérer un double.
- __Espace dans une paire vide__ : Si le curseur se trouve entre une paire vide (par exemple `(|)`), taper un espace remplace le caractère de fermeture par un espace.

### Touches de raccourci

| Raccourci | Actions |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **⌘F** | Afficher ou masquer la barre de recherche dans le volet de saisie Markdown |
| **⌘G** | Rechercher suivant (lorsque la barre de recherche est visible) |
| **⇧⌘G** | Rechercher précédent (lorsque la barre de recherche est visible) |
| **⌘B** | Gras : enveloppez la sélection dans `**` ou insérez `**\|**` avec le curseur entre |
| **⌘I** | Italique : enveloppez la sélection dans `_` ou insérez `_\|_` avec le curseur entre |
| **⇧⌘L** | Marqueur de liste de cycles (non ordonné ↔ ordonné) |
| **Onglet** | Mettre en retrait une ligne ou un élément de liste |
| **Maj+Tab** | Ligne ou élément de liste sortant |
| **⌃⌘→** | Indenter une ligne ou un élément de liste (identique à Tab) |
| **⌃⌘←** | Ligne ou élément de liste retiré (identique à Shift+Tab) |
| **⌃⌘↑** | Déplacer le paragraphe vers le haut (couper le paragraphe, y compris la nouvelle ligne, coller une ligne vers le haut) |
| **⌃⌘↓** | Déplacer le paragraphe vers le bas (couper le paragraphe, y compris la nouvelle ligne, coller une ligne vers le bas) |
| **⌘K** | Insérez ou enveloppez un lien Markdown : enveloppez la sélection comme `[text]()` et placez le curseur dans l'URL, ou insérez `[]()` avec le curseur entre les crochets lorsqu'il n'y a pas de sélection |
| **⌘U** | Basculer le volet de sortie (Source/Aperçu) |
| **⌥⌘↑** | Développer la sélection : mot → délimiteurs internes/externes → phrase → paragraphe → bloc contigu (tel qu'un tableau ou un bloc de code) → liste/citation de bloc/bloc de code → document |
| **⌥⌘↓** | Sélection de contrat redescendant à travers les mêmes niveaux jusqu'à la position d'origine du curseur |

Tab/Shift+Tab (et ⌃⌘←/⌃⌘→) respectent la structure de la liste et
blockquotes : ils mettent en retrait/retrait les éléments de la liste et ajoutent ou
supprimez `>` des lignes de citation de bloc. Déplacer le paragraphe vers le haut/bas
sélectionne le paragraphe entier sous le curseur (y compris son
nouvelle ligne finale), le coupe et le colle au-dessus ou en dessous du
paragraphe adjacent afin que les paragraphes ne fusionnent pas.

### Coller une URL intelligente

Lorsque vous collez et que le presse-papier contient une URL du formulaire
`protocol://...` sans espaces :

* __Avec une sélection__ : la sélection se transforme en
  Lien de démarque : `[selected text](url)` .
* __Sans sélection__ : l'URL est insérée sous forme de
  auto-lien : `<url>` .

Cela facilite la transformation des URL copiées en liens sans
saisie manuelle.

### Sélection intelligente (⌥⌘↑ / ⌥⌘↓)

L'éditeur Dingus prend en charge __l'expansion de la sélection sémantique__ :

* __⌥⌘↑__ commence au curseur et élargit la sélection
  à travers :
	- le mot actuel
	- contenu délimité intérieur et extérieur (guillemets, parenthèses,
   parenthèses et blocs de code clôturés)
	- la phrase actuelle
	- le paragraphe actuel
	- le bloc de lignes contigu et non vide (par exemple, un
   table entière ou bloc de code multiligne sans lignes vides)
	- l'élément de liste englobant, la citation de bloc ou le bloc de code
	- l'intégralité du document
* __⌥⌘↓__ redescend à travers les mêmes niveaux jusqu'à ce qu'il
  revient à la position initiale du curseur.

Chaque pression se déplace toujours vers une direction strictement plus grande ou plus petite.
sélection, de sorte que vous n'obtiendrez jamais d'appuis sur des touches "no-op" pendant que
en expansion ou en contraction.

## Utiliser Dingus comme éditeur

Le Dingus n'est pas destiné à remplacer un texte complet
éditeur, mais cela peut être très pratique pour des modifications rapides avec un
aperçu en direct__, surtout lorsque vous voulez voir exactement comment
les changements seront rendus. Tout le comportement d'édition de texte
décrit dans [Édition dans le Dingus][3] s'applique ici.

### Ouvrir un fichier/créer un nouveau fichier

* __Créer un nouveau fichier dans le Dingus__
	- Choisissez __{% appmenu File, New, New Markdown File %}__
   (⌘N).
	- Lorsque vous y êtes invité, choisissez __Dingus__ pour démarrer un nouveau fichier non enregistré.
   Document Dingus.
	- De nouveaux documents Dingus s'ouvrent avec un exemple de contenu sélectionné ;
   commencez simplement à taper pour le remplacer.
* __Ouvrir un fichier existant dans le Dingus__
	- Utilisez __{% appmenu File, Open in Dingus... %}__ (⌥⌘O), ou
   avec la fenêtre Dingus active, cliquez sur __Open…__ dans l'état
   barre. La commande ouvre la fenêtre Dingus si besoin, puis
   affiche le panneau Ouvrir.
	- Choisissez n'importe quel fichier texte brut/Markdown pris en charge ; c'est
   le contenu remplacera le tampon Dingus actuel.
* __Ouvrez un document d'aperçu marqué dans Dingus__
	- Depuis une fenêtre d'aperçu normale, utilisez __{% appmenu Preview,
   Open in Dingus %}__ (⌥⌘E).
	- Le Markdown du document actuel est chargé dans le Dingus
   pour que vous puissiez expérimenter sans toucher au fichier original
   jusqu'à ce que vous choisissiez de sauvegarder. Les règles personnalisées ne sont pas appliquées dans
   les Dingus ; voir [Les règles personnalisées ne s'appliquent pas](#custom-rules-do-not-apply).

### Enregistrer un fichier

* __Enregistrer les modifications dans le fichier actuel__
	- Dans la fenêtre Dingus, cliquez sur __Save__ dans la barre d'état,
   ou utiliser
    __{% appmenu File, Save Dingus %}__ (⌘S).
	- Si le document Dingus n'a pas encore été enregistré, vous le serez
   vous êtes invité à indiquer un emplacement et un nom de fichier ; après ça, ⌘S
   met à jour le même fichier.
* __Enregistrer sous / dupliquer dans un nouveau fichier__
	- Utilisez __{% appmenu File, Save Dingus As... %}__ (⌥⌘S).
	- Cela ouvre toujours une boîte de dialogue __Enregistrer sous__ et écrit le
   contenu actuel de Dingus dans un nouveau fichier sans écrasement
   l'original.

### Aperçu dans Marqué

* __Ouvrez le document Dingus en tant qu'aperçu marqué complet__
	- Cliquez sur __Ouvrir dans Marqué__ dans la barre d'état de Dingus, ou utilisez

__{% appmenu File, Open Dingus in Marked %}__ (⌘P).
	- Si le document Dingus n'est pas enregistré ou comporte des modifications non enregistrées,
   vous serez d'abord invité à enregistrer ; puis Marked ouvre un
   aperçu standard pour ce fichier.

En utilisant ces commandes, vous pouvez traiter le Dingus comme un
éditeur léger pour des solutions rapides et des expériences, puis
passez à un aperçu marqué complet ou à votre éditeur habituel lorsque
vous êtes prêt pour une édition plus approfondie.

## Sélection du processeur

Utilisez le menu déroulant en haut pour basculer entre les différents
Processeurs de démarque :

* __MultiMarkdown__ : processeur complet avec tables,
  notes de bas de page et support mathématique
* __CommonMark (GFM)__ : processeur standard et rapide suivant le
  Spécification CommonMark
* __Discount__ : GitHub Flavored Markdown avec tâche
  listes et tableaux
* __Kramdown__ : processeur avancé avec fonctionnalités supplémentaires
  comme les IAL et la typographie

## Pourquoi utiliser le Dingus ?

### Comprendre les différences entre les processeurs

Différents processeurs Markdown gèrent la syntaxe différemment. Le
Dingus vous aide à :

* __Compare Output__ : découvrez exactement le rendu de chaque processeur
  la même démarque
* __Problèmes de débogage__ : identifiez pourquoi certaines syntaxes ne le sont pas
  fonctionne comme prévu
* __Apprendre la syntaxe__ : comprendre les différences subtiles
  entre les implémentations de processeur

### Tester avant d'écrire

Avant de vous engager dans un style Markdown particulier dans votre
document :

* __Validate Syntax__ : assurez-vous que votre Markdown sera rendu
  correctement
* __Choisissez les processeurs__ : décidez quel processeur fonctionne le mieux
  pour votre contenu
* __Expérimentez en toute sécurité__ : essayez une nouvelle syntaxe sans affecter
  vos documents réels

## Cas d'utilisation courants

### Différences de syntaxe des tableaux

Certains processeurs gèrent la syntaxe des tables différemment. Le Dingus
vous permet de voir quel processeur prend le mieux en charge votre table
besoins de formatage.

### Prise en charge des notes de bas de page

Tous les processeurs ne prennent pas en charge les notes de bas de page. Utilisez le Dingus pour
vérifiez que la syntaxe des notes de bas de page fonctionne avec le processeur que vous avez choisi.

### Mathématiques et caractères spéciaux

Testez comment différents processeurs gèrent les mathématiques
expressions et caractères typographiques spéciaux.

## Conseils pour une utilisation efficace

1. __Start Simple__ : commencez par le Markdown de base et progressivement
   ajouter de la complexité
2. __Test Edge Cases__ : essayez des combinaisons de syntaxe inhabituelles pour
   comprendre les limites du processeur
3. __Comparez côte à côte__ : basculez entre les processeurs pour
   voir clairement les différences
4. __Utiliser du contenu réel__ : copiez le contenu réel de votre
   des documents pour tester des scénarios du monde réel

Le Dingus est un outil puissant pour tous ceux qui souhaitent
comprendre les nuances des différentes implémentations de Markdown
et assurez-vous que leur contenu s'affiche correctement sur divers
plates-formes et processeurs.

[1]: images/dingus-interface-800.jpg @2x width=800px height=573px class=center
[2]: x-marked-3://dingus
[3]: #editing-in-the-dingus