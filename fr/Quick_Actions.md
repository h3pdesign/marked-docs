<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

La palette Actions rapides est un lanceur de commandes consultable pour Marqué. Il collecte les actions de la barre de menu principale et du **menu d'engrenage** d'aperçu, ainsi que les commandes clavier en aperçu uniquement qui n'apparaissent pas dans les menus (telles que **Défilement automatique**). Utilisez-le lorsque vous savez ce que vous voulez faire mais que vous ne vous souvenez plus du menu qui le contient.

## Ouverture de la palette d'actions rapides

Ouvrez la palette avec {% kbd shift cmd P %} ou depuis {% appmenu File, Quick Actions… %}. Le panneau apparaît sous la forme d'une fenêtre flottante au-dessus de votre document actuel.

Appuyez à nouveau sur le même raccourci ou appuyez sur **Échap** pour fermer la palette. Si la palette est déjà ouverte, choisir **Actions rapides…** dans le menu la ferme également.

## Personnalisation du raccourci

Le raccourci par défaut est {% kbd shift cmd P %}. Pour le modifier, ouvrez {% prefspane General %} et enregistrez une nouvelle combinaison sous **Ouvrir la palette d'actions** dans la section **Raccourcis**.

Contrairement à **Activer Marked** et **Augmenter la première fenêtre**, le raccourci Actions rapides ne fonctionne que lorsque Marked est l'application active. Il met à jour le raccourci de menu {% appmenu File, Quick Actions… %} pour qu'il corresponde à vos paramètres.

## Recherche et filtre

Tapez dans le champ de recherche en haut du panneau pour filtrer les commandes en temps réel. La correspondance est floue et indulgente :

- L'ordre des mots n'a pas d'importance (`view source` correspond à **Toggle Source View**)
- Les initiales fonctionnent bien (`sv` correspond à **Source View**)
- La correspondance réduite recherche les commandes sans espaces (`akdoc` correspond à **Ask About Document**)

Chaque résultat affiche le nom de la commande à gauche et son raccourci clavier (si disponible) à droite en gris. Certaines commandes affichent également un chemin de fil d'Ariane (par exemple `Preview › Autoscroll`) lorsque l'action provient d'un sous-menu ou du moteur de prévisualisation.

## Ce qui apparaît dans la liste

La palette comprend :

- **Commandes de menu** de la barre de menu principale, y compris des menus dynamiques tels que **Style**, **Historique** et des onglets ouverts **Fenêtre**.
- Commandes **Menu Gear** de la fenêtre d'aperçu
- **Aperçu des raccourcis** à partir de la carte du clavier en aperçu (les mêmes commandes affichées dans le HUD d'aide en aperçu), y compris la navigation, le défilement automatique, les signets, la recherche et d'autres actions en aperçu uniquement

Lorsque la même commande apparaît à plusieurs endroits, Marqué affiche le chemin de menu le plus court et fusionne les informations de raccourci des doublons.

## Navigation au clavier

Parcourez la palette Actions rapides entièrement à partir du clavier :

- **↑/↓ Touches fléchées** : Déplacez-vous dans la liste filtrée
- **Retour** : Exécutez la commande sélectionnée
- **Échap** : Fermez la palette
- **⌘-raccourcis clavier** : fermez la palette et exécutez la commande de menu correspondante (par exemple, appuyez sur {% kbd cmd U %} pour exécuter **Toggle Source View** au lieu de la sélectionner dans la liste)

La saisie simple (sans la touche Commande) filtre le champ de recherche. Des raccourcis à touche unique en aperçu uniquement, tels que `s` pour le défilement automatique, filtrent la liste ; appuyez sur **Return** pour exécuter la commande sélectionnée.

## Exécuter des commandes

La sélection d'une commande de menu la répartit de la même manière que sa sélection dans le menu, y compris les éléments de menu dynamiques et d'engrenage.

La sélection d'un **raccourci d'aperçu** exécute l'action associée dans l'aperçu actif (par exemple, activer le défilement automatique ou passer à l'en-tête suivant). Ces commandes nécessitent un document ouvert avec un aperçu ; si aucun aperçu n'est disponible, la palette s'ouvre toujours mais les actions d'aperçu uniquement n'auront aucun effet.

Pour le changement de fichier associé, voir [Ouverture rapide](Quick_Open.html). Pour la référence complète du clavier d'aperçu, voir [Raccourcis clavier](Keyboard_Shortcuts.html) ou appuyez sur {% kbd h %} dans l'aperçu pour afficher la palette d'aide.