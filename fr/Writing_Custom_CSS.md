<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked possède un éditeur de style intégré et peut appliquer des fichiers CSS personnalisés.

Vous pouvez utiliser l'éditeur pour créer de superbes styles, ou si vous connaissez juste assez de CSS pour être dangereux, vous pouvez donner à Marked l'apparence que vous souhaitez.

## Commencer

Il existe une galerie de styles personnalisés créée par le développeur et par les utilisateurs sur [markedapp.com/styles] (https://markedapp.com/styles/). La galerie vous permet de prévisualiser et d'installer les styles directement dans Marked. Tout style installé peut être révélé dans le Finder pour examen et modification. La galerie peut être ouverte à l'aide d'une visionneuse interne avec {% appmenu Style, Generate a Custom Style %}, ou cliquez sur l'icône en forme de crayon (modifier) à côté de tout style modifiable dans le gestionnaire de styles. Si vous souhaitez modifier un style intégré, vous devrez d'abord le dupliquer dans le gestionnaire.

Il existe également un [dépôt pour les styles personnalisés](https://github.com/ttscoff/MarkedCustomStyles) sur GitHub avec des exemples. N'hésitez pas à le parcourir, à l'utiliser et à y contribuer. Si vous distribuez votre thème sur la base d'un des thèmes de base, n'hésitez pas à vous ajouter au générique en tant que contributeur.

Grâce à la capacité de Marked à utiliser des fichiers CSS personnalisés, il n'y a aucune limite lors de la personnalisation de votre aperçu. Toutes les options CSS3 qui fonctionnent dans Safari fonctionneront dans Marked. Avec les fichiers Markdown par défaut dans Marked, vous ne devez gérer que quelques éléments HTML ; tout le contenu est dans un div avec l'identifiant "wrapper", tout le reste est déterminé par le balisage de votre document.

Si vous concevez pour un usage personnel, il n’y a pas de règles. Activez le suivi CSS avec la case à cocher située sous le sélecteur CSS personnalisé et lorsque vous modifiez et enregistrez votre CSS personnalisé, l'aperçu sera mis à jour.

**Un [thème squelette est disponible](https://github.com/ttscoff/MarkedCustomStyles/blob/master/Custom.css) pour commencer.**

Si vous envisagez de partager votre création CSS, vous devez aborder quelques points. Tout d’abord, certaines classes de corps nécessitent l’application de styles :

## Cours de corps

Les styles suivants doivent être inclus dans tout CSS marqué pour être partagé. Les classes body vous permettent de cibler et de modifier n'importe quel sélecteur sous différentes options de préférence.

### Inversé

 Lorsque l'utilisateur sélectionne {% appmenu Preview, Dark Mode %}, une classe « inversé » est ajoutée à la balise body. Vous pouvez l’utiliser pour cibler les styles clairs et sombres à contraste élevé.

Vous souhaitez uniquement que les styles inversés s'appliquent à l'aperçu, pas à l'impression, utilisez donc une requête multimédia (@media screen) pour le restreindre. Le code ci-dessous est assez polyvalent et dans la plupart des cas, vous pouvez simplement le déposer dans votre feuille de style pour des raisons de compatibilité, mais n'hésitez pas à le modifier.

```css
@media screen {
	.inverted, .inverted #wrapper { background:#111 !important }
	.inverted p,.inverted td,.inverted li,.inverted h1,.inverted h2,
	.inverted h3,.inverted h4, .inverted h5, .inverted h6, .inverted pre,
	.inverted code,.inverted th {
		color:#eee !important;
	}
	.inverted a { color:#fff;text-decoration:underline }
	#wrapper {
		background: transparent;
		padding:20px;
	}
}
```

### Poésie

L'utilisateur peut choisir si le texte en retrait par tabulation est de la poésie ou du code. La seule différence est que les blocs pré/code sont stylisés de manière plus poétique si le mode poésie est choisi. La classe « poésie » est appliquée à la balise body.

Soyez aussi créatif que vous le souhaitez avec le formatage, mais voici un extrait de base :

```css
.poetry pre code {
	font-family:Georgia, Garamond, serif;
	font-style:italic;
	font-size:110% !important;
	line-height:1.6em;
	display:block;
	margin-left:1em;
}
```

## Cas particuliers

Les tableaux, la figure/la légende de la figure et le cas particulier de `a.footnote` et `div.footnotes>a` doivent également être pris en compte. Il n'y a pas de règles définies sur la façon dont vous les gérez, mais jetez un œil aux styles par défaut pour avoir une idée des règles CSS dont Marked a besoin.

Le style de tableau standard dans tous les styles par défaut utilise la transparence sur les lignes alternées pour le fondre doucement avec n'importe quel arrière-plan. Vous pouvez copier ces styles ou suivre votre propre chemin, assurez-vous simplement de les avoir stylisés ! Idem pour la figure et la légende de la figure ; ajoutez une image à un document avec du texte alternatif pour voir comment le balisage apparaîtra et le stylera de manière appropriée.

Les notes de bas de page incluses dans un document afficheront un lien dans le contenu (a.footnote) et un div à la fin avec le texte référencé (div.footnotes). Encore une fois, consultez les styles par défaut pour référence. Pour éviter de modifier la hauteur des lignes contenant un numéro de référence de note de bas de page, veillez à inclure quelque chose comme :

```css
sup,sub,a.footnote {
	font-size: 1.4ex;
	height: 0;
	line-height: 1;
	vertical-align: super;
	position: relative;
}
```

Pour conserver la flèche de retour sur la même ligne, incluez :

```css
.footnotes p {display:inline}
```

C'est également une bonne idée d'inclure une règle générale pour toutes les images afin de les conserver dans la largeur de la page. Quelque chose comme :

```css
#wrapper img { max-width: 100% }
```

Si votre thème a un remplissage supplémentaire ou une largeur fixe, modifiez la largeur maximale pour l'adapter.

## Styles d'impression

Assurez-vous d'inclure des styles d'impression qui suppriment toutes les couleurs d'arrière-plan, le défilement fixe et l'interface utilisateur en aperçu uniquement. Marqué vous offre deux façons de cibler la sortie impression et PDF.

### `@media print`

Les règles d'impression CSS standard s'appliquent lors de l'impression à partir de Marqué ou lorsque l'exportation PDF utilise un support d'impression :

```css
@media print {
  .inverted, .inverted #wrapper { background: white !important; }
  #wrapper { padding: 0; }
}
```

### La classe `.mkprinting`

Lorsque Marked prépare un document pour l'**exportation PDF** ou l'**Aperçu impression/PDF** ({% kbd cmd P %}), il ajoute la classe `mkprinting` à la balise `<body>` (aux côtés des classes d'exportation telles que `bandw`, `breakAfterTOC` et la classe `mkstyle--*` de votre style). Les thèmes intégrés de Marked utilisent cette classe pour la plupart des règles spécifiques à l'impression au lieu de s'appuyer uniquement sur `@media print`.

L'exportation PDF charge souvent le rendu caché WebView avec un support **écran** (en particulier pour les styles personnalisés et les documents [Fountain](Fountain_for_Screenwriters.html)), donc les blocs `@media print` de votre feuille de style peuvent **ne pas** s'appliquer à la sortie PDF. Les règles préfixées par `.mkprinting` s'appliquent toujours lors de l'exportation car il s'agit de sélecteurs de classe ordinaires, et non de requêtes multimédias.

```css
/* Hide preview UI during print/PDF */
.mkprinting #generated-toc,
.mkprinting #criticnav,
.mkprinting .mkscrollmeter {
  display: none !important;
}

/* Print/PDF typography */
.mkprinting #wrapper {
  background: white;
  padding: 0;
}

.mkprinting #wrapper p {
  font-size: 10pt;
  line-height: 1.4;
}
```

Pour les styles qui doivent fonctionner **à la fois** pour l'impression via le navigateur et pour l'exportation au format PDF marqué, dupliquez les règles critiques ou combinez les sélecteurs :

```css
@media print {
  #wrapper img { max-width: 100%; }
}

.mkprinting #wrapper img {
  max-width: 100%;
}
```

Lors du débogage du CSS d'impression personnalisé, ouvrez l'aperçu impression/PDF ou exportez au format PDF, puis utilisez [l'inspecteur Web de Safari] (#webkitinspector) pour inspecter le document --- le `<body>` aura la classe `mkprinting` pendant que la mise en page d'impression est active.

Le masquage des liens lors de l'impression est géré en dehors du thème principal, permettant aux utilisateurs de choisir de masquer les surlignages et les soulignements des liens lors de l'impression. Tant que vous disposez d’un style de base défini pour le texte, vous n’avez pas à vous en soucier.

Alors, allez-y. Convertissez le thème de votre blog, créez un style d'impression génial pour les documents PDF ou créez l'aperçu parfait pour le style d'écriture que vous utilisez. Si vous créez quelque chose de génial, faites-le-moi savoir et je le publierai pour toute la communauté Marked.

## Paramètres CSS supplémentaires

Dans le {% prefspane Style %}, vous pouvez modifier du CSS supplémentaire. Ces styles seront ajoutés à n’importe quel thème chargé et pourront être utilisés pour apporter des modifications universelles à tous les thèmes.

En utilisant [haute spécificité] (#overridingspeciality), `@media` requêtes pour l'impression et l'écran et `.mkprinting` sélecteurs pour l'exportation PDF, vous pouvez contrôler à peu près tous les aspects de style avec un peu de connaissances CSS.

## Inspecteur WebKit

L'inspecteur Web de Safari est le moyen le plus simple de voir exactement ce que HTML et CSS Marked génèrent et d'expérimenter les styles personnalisés en direct.

### Activation du menu Développer dans Safari

1. Ouvrez Safari et choisissez {% appmenu Safari, Settings… %}.
2. Sélectionnez l'onglet **Avancé**.
3. Activez **Afficher les fonctionnalités pour les développeurs Web** (ou **Afficher le menu Développement dans la barre de menu** sur les anciennes versions de macOS).

Une fois activé, un menu **Développer** apparaîtra dans la barre de menus de Safari.

![Menu Développement Safari affichant les documents marqués][menu développement]

### Inspecter un document marqué

1. Avec une fenêtre d'aperçu ouverte dans Marked, passez à Safari.
2. Dans la barre de menu, choisissez **Développer → _\<nom de votre Mac\>_ → Marqué → _\<titre du document\>_**.
3. Safari ouvrira une fenêtre Web Inspector attachée à l'aperçu marqué sélectionné.

À partir de là, vous pouvez :

- Utilisez l'onglet **Éléments** pour inspecter le DOM à l'intérieur du div `#wrapper` et voir quelles règles CSS sont appliquées.
- Survolez les éléments dans l'arborescence DOM pour les mettre en surbrillance dans la fenêtre Marqué.
- Utilisez la barre latérale **Styles** pour modifier les règles en direct, puis recopiez les extraits de code dans un style personnalisé ou dans un **CSS supplémentaire**.
    - Après avoir modifié le CSS dans l'onglet Éléments, vous pouvez obtenir un résumé de vos modifications en sélectionnant l'onglet Modifications.

	![Modifications][changements css]
- Utilisez l'onglet **Console** pour exécuter JavaScript sur l'aperçu en direct. L'[API JavaScript marquée](https://markedapp.com/help/jsapi/) complète est disponible dans cette console.
- Explorez d'autres onglets tels que **Réseau** lors du débogage des ressources chargées par votre document.

![Inspection d'un aperçu marqué avec Safari Web Inspector][inspection]

## Partage de CSS personnalisé

Utilisez {% appmenu Style, Share a Custom Style %} pour ouvrir l'application de partage dans votre navigateur Web. Faites glisser votre CSS vers la zone de dépôt (ou cliquez pour sélectionner à partir du disque) et téléchargez le CSS pour votre style personnalisé.

Les styles partagés doivent être approuvés par le développeur avant d'apparaître dans la galerie, vous ne verrez donc pas de résultats immédiats.

## Autres conseils

### Spécificité prioritaire

Dans l'aperçu Marqué, une classe de corps basée sur le nom de fichier du style actuel est ajoutée. Si l'aperçu est défini sur "Suisse", alors il y aura une classe sur la balise `<body>` appelée `mkstyle--swiss`. Si votre CSS personnalisé s'appelle MyCustom.css, alors la classe body sera `mkstyle--mycustom`. Vous pouvez l'utiliser avant les règles définies dans les styles de base pour les remplacer. Pour obtenir une spécificité absolue dans une règle, utilisez également l'ID #wrapper du div du conteneur :

	.mkstyle--mycustom #wrapper p+p { ... }

### Style de la table des matières

Si vous utilisez le jeton `<!--toc-->` pour [insérer une table des matières](Special_Syntax.html#tableofcontents), vous pouvez remplacer les paramètres des indicateurs de niveau de table des matières dans un style personnalisé à l'aide du « #wrapper » pour augmenter la spécificité :

```css
#wrapper #mkreplaced-toc li {
 list-style-type: square;
}
```

Cela obligerait tous les éléments de la liste de la table des matières à utiliser une puce carrée au lieu de ce qui a été défini dans les paramètres lorsque votre style personnalisé est actif.

[develop-menu]: images/develop-menu-600.jpg @2x width=600px height=273px "Safari Develop menu" class=center
[inspecting]: images/inspecting-600.jpg @2x width=600px height=367px "Inspecting a Marked document in Safari" class=center

[css-changes]: images/css-changes.jpg @2x width=322px height=207px