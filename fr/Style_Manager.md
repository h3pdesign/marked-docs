<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Le Style Manager fournit une interface centralisée pour gérer tous vos
Styles intégrés et personnalisés. Il vous donne un contrôle total sur lequel
Les styles apparaissent dans les menus, leur ordre, les raccourcis clavier, etc.

## Ouverture du gestionnaire de styles

Pour ouvrir le gestionnaire de styles, cliquez sur le bouton **Gérer les styles…** dans le {% prefspane Style %}
volet, ou utilisez {% appmenu Style, Manage Styles (~@$m) %}. Vous pouvez également faire glisser les fichiers CSS directement sur la fenêtre des préférences --- Marqué
les importera, ouvrira le gestionnaire de styles et sélectionnera la ligne nouvellement ajoutée pour
vous.

![Gestionnaire de styles][img-style-manager]

  [img-style-manager] : images/screenshots/style-manager.jpg @2x width=1009px height=517px class=center

## La table des styles

Le gestionnaire de styles affiche tous vos styles dans un tableau triable qui mélange
styles intégrés et personnalisés de manière transparente. Chaque ligne du tableau contient plusieurs
colonnes :

### Case à cocher activée

La case **Activé** ajoute ou supprime immédiatement le style du style
menu, fenêtre contextuelle Style par défaut et raccourcis clavier. Lorsque vous désactivez un style,
il est masqué dans les menus mais reste dans le gestionnaire de styles pour une réactivation facile.

Si vous désactivez le style actuellement actif, Marqué passe automatiquement au style
prochain style activé disponible.

### Nom de la colonne

La colonne **Nom** affiche le nom d'affichage du style. Vous pouvez modifier ce nom
inline en cliquant directement dessus ; les changements persistent et se propagent à chaque menu
où le style apparaît. Ceci est particulièrement utile pour les styles personnalisés dans lesquels vous
vous souhaiterez peut-être un nom plus descriptif que le nom du fichier.

Les styles intégrés ont des noms verrouillés qui ne peuvent pas être modifiés. Pour personnaliser un
Nom du style intégré, dupliquez-le d'abord pour créer une copie modifiable.

### Colonne source

La colonne **Source** indique d'où vient le style :

- **Intégré** : styles fournis avec Marked et stockés dans l'application
  paquet
- **Personnalisé** : styles que vous avez ajoutés à partir de fichiers CSS sur votre lecteur
- **Dupliqué** : styles créés en dupliquant un autre style (soit intégré
  ou personnalisé)

### Colonne Actions

Chaque ligne comprend une pile **Actions** avec des boutons permettant de gérer ce style :

**Modifier** : ouvre le fichier CSS dans votre éditeur par défaut. Les styles intégrés ne peuvent pas être
édités directement - vous devrez d'abord les dupliquer pour créer une copie modifiable.

**Dupliquer** : crée une copie du style et un nouveau fichier CSS sur le disque. Le
le doublon apparaît immédiatement sous le style d'origine dans le tableau. C'est
la méthode recommandée pour personnaliser les styles intégrés.

**Révéler** : affiche le fichier CSS dans le Finder, ce qui facilite sa localisation.
votre lecteur. Ce bouton est uniquement disponible pour les styles personnalisés avec un chemin de fichier.

**Supprimer** : supprime le style de Marqué. Pour les styles personnalisés, vous recevrez
la possibilité de supprimer uniquement la référence (en conservant le fichier CSS) ou de déplacer
le fichier CSS dans la Corbeille. Les styles intégrés ne peuvent pas être supprimés, mais ils peuvent être
désactivé.

**Restaurer** : pour les styles intégrés, ce bouton restaure le style à son état initial.
état par défaut s'il a été modifié. Ce bouton n'est visible que pour
styles intégrés.

## Réorganisation des styles

Les lignes peuvent être réorganisées par glisser-déposer. Faites simplement glisser une ligne de style vers une nouvelle
position dans le tableau. L'ordre que vous définissez ici entraîne :

- L'ordre du menu Style dans les menus de Marked
- Affectations de raccourcis clavier (`⌘1`–`⌘9` pour les neuf premiers styles activés,
  `⌥⌘1`–`⌥⌘0` pour les dix prochains, et ainsi de suite)

Faites glisser les styles dans les emplacements de raccourci clavier souhaités.
occuper.

## Ajout de styles

Il existe plusieurs manières d'ajouter de nouveaux styles personnalisés au gestionnaire de styles :

### Ajouter un bouton

Cliquez sur le bouton **Ajouter un nouveau style** pour ouvrir un sélecteur de fichiers.
où vous pouvez sélectionner un ou plusieurs fichiers CSS à importer. Les fichiers sélectionnés seront
ajouté au gestionnaire de styles et activé par défaut.

### Glisser-déposer

Vous pouvez faire glisser les fichiers CSS directement sur la fenêtre Style Manager. Quand tu traînes
fichiers sur la fenêtre, une superposition apparaîtra indiquant "Ajouter un style personnalisé" (ou
"Ajouter N styles personnalisés" pour plusieurs fichiers). Déposez les fichiers pour les importer.

Vous pouvez également faire glisser des fichiers CSS vers des positions spécifiques dans le tableau : le drop
L'indicateur indique où le nouveau style sera inséré, vous permettant de contrôler
à la fois l'importation et le positionnement en une seule action.

Faire glisser les fichiers CSS sur le volet des préférences {% prefspane Style %}
importez-les et ouvrez automatiquement le gestionnaire de styles.

## Aperçu en direct

Le volet droit du gestionnaire de styles affiche un aperçu en direct du style sélectionné.
style. L'aperçu affiche un exemple de document complet avec des titres,
listes, tableaux, blocs de code, blockquotes et autres éléments Markdown courants,
tous stylisés avec le CSS réel du style sélectionné.

L'aperçu utilise le fichier CSS directement à partir du disque, donc toutes les modifications que vous apportez dans votre
l'éditeur externe sera mis à jour instantanément dans l'aperçu. Cela facilite
visualisez vos modifications en temps réel à mesure que vous développez des styles personnalisés.

### Aperçu du mode sombre

Une case à cocher au-dessus de l'aperçu vous permet de basculer entre les modes clair et sombre
aperçus. Ceci est utile pour tester l'apparence des styles dans les deux modes d'apparence,
surtout si vous créez des styles qui s'adaptent à l'apparence du système.

## Raccourcis clavier

Le gestionnaire de styles affiche une légende sous le tableau montrant comment le clavier
des raccourcis sont attribués. Les neuf premiers styles activés reçoivent {% kbd cmd 1 %} via
{% kbd cmd 9 %} ({% kbd cmd 0 %} est réservé), les dix suivants reçoivent de {% kbd opt cmd 1 %} à {% kbd opt cmd 0 %}, et ainsi de suite. Vous pouvez voir les raccourcis clavier attribués dans le menu contextuel Style de n'importe quel aperçu.

## Filtrage des styles désactivés

Une case à cocher en bas de la fenêtre permet d'afficher ou de masquer les personnes handicapées
styles. Lorsque cette case n'est pas cochée, seuls les styles activés sont affichés, ce qui facilite
concentrez-vous sur et réorganisez vos styles actifs. Lorsque cette case est cochée, tous les styles (activés et désactivés)
sont affichés, vous permettant de gérer votre collection de styles complète.

## Restauration des styles intégrés

Le bouton **Restaurer tous les styles intégrés** en bas de la fenêtre
restaure tous les styles intégrés à leur état par défaut. Ceci est utile si vous avez
styles intégrés désactivés et souhaitez les réactiver, ou si vous souhaitez réinitialiser
toute modification apportée aux styles intégrés.

## Conseils

- **Organiser par fréquence** : faites glisser vos styles les plus utilisés vers le haut pour donner
  leur les raccourcis clavier les plus simples ({% kbd cmd 1 %}, {% kbd cmd 2 %}, etc.)

- **Désactiver au lieu de supprimer** : plutôt que de supprimer les styles que vous n'utilisez pas,
  désactivez-les. Ils resteront à l'écart mais resteront disponibles si vous en avez besoin
  eux plus tard.

- **Utiliser la copie pour l'expérimentation** : dupliquer un style avant de le rendre majeur
  changements afin que vous puissiez toujours revenir à l’original.

- **Aperçu lors de l'édition** : gardez le gestionnaire de styles ouvert lors de l'édition du CSS
  fichiers pour voir vos modifications mises à jour en temps réel dans le volet d’aperçu.

- **Importation par lots** : vous pouvez sélectionner plusieurs fichiers CSS à la fois lorsque vous utilisez le
  Bouton Ajouter ou faites glisser plusieurs fichiers pour les importer tous en une seule action.