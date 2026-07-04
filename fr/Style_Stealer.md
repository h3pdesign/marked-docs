<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Extrayez et volez des styles de n’importe quel site Web.

## Qu'est-ce que le voleur de style ?

Le Style Stealer est un outil qui vous permet d'extraire les styles CSS de n'importe quel site Web et de les appliquer à vos documents Markdown en tant que [Styles personnalisés](Custom_Styles.html). C'est parfait pour :

- **Blogueurs** qui souhaitent correspondre au style de leurs sites Web préférés
- **Écrivains** qui ont besoin de créer des documents correspondant à une marque ou une publication spécifique
- **Développeurs** qui souhaitent créer rapidement des prototypes avec des systèmes de conception existants
- **Toute personne** souhaitant capturer l'apparence et la convivialité d'un site Web bien conçu

> Le Style Stealer dépend d'un site relativement bien présenté avec des divisions de balisage claires. Cela ne fonctionnera pas sur tous les sites, mais cela devrait faire du bon travail sur la plupart.

> Pour de meilleurs résultats, entrez une page contenant autant de contenu textuel que possible. Par exemple, pour extraire des styles d'un blog, ouvrez-le directement sur un article ou une publication, et non sur la page d'index principale.

## Comment utiliser le voleur de style

### Étape 1 : Ouvrez le Style Stealer

Accédez à Style Stealer via **Aide** → **Style Stealer**.

### Étape 2 : Saisissez une URL

Dans le champ URL, saisissez l'adresse du site Web dont vous souhaitez extraire les styles. Le Style Stealer fonctionne avec n’importe quel site Web accessible au public. Si le site est derrière un paywall, vous devrez peut-être vous connecter pour pouvoir extraire le contenu.

![Aperçu de Style Stealer][Aperçu]

  [aperçu] : images/style-stealer-preview.jpg @2x width=800

### Étape 3 : Charger et naviguer

Cliquez sur **Extraire** ou appuyez sur {% kbd return  %} pour charger le site Web. Une fois chargé, vous pouvez :

- **Naviguer** sur le site en utilisant Commande+Clic sur les liens
- **Survolez** les zones de contenu pour les voir mises en surbrillance
- **Cliquez** sur la zone de contenu principale dont vous souhaitez extraire les styles

La zone de contenu principale que vous sélectionnez ne doit contenir que des titres, des paragraphes, des listes, etc. Ne sélectionnez pas une zone de contenu contenant des menus, des barres latérales ou tout autre contenu superflu. Souvent, un titre se trouve dans un conteneur distinct du contenu normal du paragraphe. Dans ces cas-là, essayez d’abord de sélectionner le plus petit conteneur contenant encore les deux. Si les résultats sont médiocres, cliquez à nouveau sur **Extraire** et resélectionnez uniquement le conteneur contenant les paragraphes.

### Étape 4 : Extraire les styles

Lorsque vous cliquez sur la zone de contenu, les styles qui s'appliquent à cette zone seront extraits. L'aperçu se rechargera avec une page générique qui présente tous les éléments HTML courants et comment les styles extraits s'y appliqueront.

Vous pouvez ensuite enregistrer ce style personnalisé dans votre dossier CSS personnalisé pour l'utiliser dans n'importe quel document. Cliquez sur le bouton **Enregistrer** ou appuyez sur {% kbd cmd S %} pour enregistrer. Le style sera nommé en fonction du domaine de l'URL que vous avez saisie.

![][img3]

  [img3] : images/style-stealer-stolen-800.jpg @2x width=800px height=637px class=center

## Ce qui est extrait

Le Style Stealer capture un ensemble complet de styles, notamment :

### Typographie

- **Familles de polices** et tailles pour tous les niveaux de titres (H1-H6)
- Style **Paragraphe** incluant la hauteur et l'espacement des lignes
- **Couleurs du texte** et couleurs d'arrière-plan
- **Poids de police** et styles (gras, italique, etc.)

### Disposition et espacement

- **Marges et remplissage** pour tous les éléments
- Styles et couleurs **Bordure**
- **Couleurs d'arrière-plan**, y compris les arrière-plans du corps pour les thèmes sombres

### Éléments interactifs

- **Styles de liens**, y compris les états de survol et visités
- **Bouton** et style des éléments de formulaire
- Style **Liste** (puces, chiffres, indentation)

### Fonctionnalités spéciales

- Style **Premier paragraphe**
- Formatage **Blockquote**
- **Code** et style de texte préformaté
- Style **Table**
- **Faces de police personnalisées** et polices Web

## Fonctionnalités avancées

### Blocage des médias

Le Style Stealer bloque automatiquement le contenu multimédia (vidéos, images, audio) pour éviter les plantages et se concentrer sur le style du texte. Cela garantit un processus d’extraction fluide, même sur les sites Web riches en médias.

### Prise en charge des pseudo-sélecteurs

L'outil capture les pseudo-sélecteurs CSS tels que :

- `:hover` états pour les liens et les boutons
- `:visited` états des liens
- `:first-child` style de paragraphe
- `::first-letter` pour les lettrines

### Filtrage intelligent

Le Style Stealer filtre intelligemment :

- Styles de navigateur par défaut
- Préfixes de fournisseur inutiles
- Règles contradictoires ou redondantes
- Des styles qui rendraient le texte illisible

### Mode débogage

Activez le mode débogage dans Style Stealer pour voir la journalisation détaillée du processus d’extraction. Ceci est utile pour dépanner ou comprendre quels styles sont capturés.

## Conseils pour de meilleurs résultats

### Choisissez la bonne zone de contenu

- Cliquez sur la **zone de contenu principale** de la page, et non sur les en-têtes, les barres latérales ou les pieds de page.
- Recherchez la zone qui contient le texte de l'article, l'article de blog ou le contenu principal
- Évitez les zones avec du JavaScript lourd ou du contenu dynamique

### Gérer les thèmes sombres

Le Style Stealer capture automatiquement les couleurs d’arrière-plan du corps, ce qui le rend parfait pour extraire les styles de thèmes sombres. L'aperçu montrera à quoi ressemble votre contenu avec le style sombre extrait.

### Considérations sur les polices

- Les **polices Web** sont capturées et incluses dans les styles extraits
  - Les polices chargées à partir d'une URL distante (par exemple Google Fonts) conserveront cette URL. Les polices chargées à partir des URL de données seront dupliquées dans la feuille de style générée.
- Les **polices système** s'adapteront gracieusement aux différents systèmes.
- Le **chargement des polices** peut prendre un moment dans l'aperçu

### Tester vos styles

Après avoir enregistré les styles extraits :

1. Appliquez-les à un document de test
2. Vérifiez à quoi ils ressemblent avec votre contenu réel
3. Effectuez des ajustements en :
   1. Ouvrez le {% prefspane Style %}
   2. Sélectionnez le nouveau style dans le tableau Styles personnalisés
   3. Cliquez sur Révéler pour afficher le fichier dans le Finder
   4. Ouvrez le fichier dans n'importe quel éditeur de texte brut (TextEdit fonctionnera en mode texte brut) et effectuez les ajustements nécessaires

## Dépannage

### Le site Web ne se charge pas

- Vérifiez que l'URL est correcte et accessible au public
- Certains sites peuvent bloquer l'accès automatisé
- Essayez une autre page sur le même site

### Les styles sont différents

- Les styles extraits sont basés sur le contenu spécifique que vous avez sélectionné
- Certains sites utilisent des CSS complexes qui peuvent ne pas se traduire parfaitement
- Utilisez du CSS supplémentaire ou modifiez la feuille de style pour effectuer des ajustements précis

### Styles manquants

- Assurez-vous d'avoir sélectionné la zone de contenu principale, et non une barre latérale ou un en-tête.
- Certains styles peuvent être appliqués via JavaScript et ne seront pas capturés
- Consultez la console de débogage pour des informations détaillées sur l'extraction

## Raccourcis clavier

- {% kbd return  %} - Charger l'URL pour l'extraction
- {% kbd cmd S %} - Enregistrez le style extrait dans un fichier CSS de style personnalisé
- {% kbd cmd  %}-Clic - Naviguer dans les liens lors de la prévisualisation

## Intégration avec des styles personnalisés

Les styles extraits sont enregistrés dans votre dossier CSS personnalisé et peuvent être :

- **Appliqué** à n'importe quel document via le menu Style
- **Modifié** à l'aide de n'importe quel éditeur de texte
- **Partagé** avec d'autres en copiant le fichier CSS
- **Combiné** avec d'autres styles personnalisés

Le Style Stealer facilite la création d’une bibliothèque de styles magnifiques inspirés des sites Web les mieux conçus sur Internet.