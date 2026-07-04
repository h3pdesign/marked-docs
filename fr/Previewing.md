<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

I> Cette page couvre l'aperçu *apparence* --- les styles, le zoom, le mode sombre et la barre d'état. Pour configurer l'aperçu en direct à partir de votre éditeur, voir [Aperçu Live Markdown sur Mac](Live_Markdown_Preview_on_Mac.html).

Changer votre façon de voir les choses.

## Choisir un style

![][1]

   [1] : images/StylePicker.jpg @2x width=896px height=195px class=center

Vous pouvez définir un style par défaut pour les nouveaux documents dans le {% prefspane Style %}. Si le menu de style dans la barre d'outils est activé dans les paramètres de la fenêtre, vous pouvez ajuster le style pour chaque document directement à partir de la fenêtre d'aperçu. Votre sélection de style sera mémorisée et constituera le premier choix pour les options d’exportation et d’impression.

Les styles personnalisés ajoutés dans les paramètres de style seront disponibles dans les deux menus.

Les styles peuvent être sélectionnés avec des raccourcis clavier. Ouvrez le menu des styles pour voir le raccourci clavier de chaque style. Les raccourcis clavier sont attribués dans l'ordre des styles : les 9 premiers styles de la liste sont accessibles avec {% kbd cmd 1 %} -- {% kbd cmd 9 %}, les 10 styles suivants avec {% kbd cmd opt 1 %} -- {% kbd cmd opt 0 %}, etc.

## Mode Plan

Si votre document est une liste hiérarchique, telle qu'une liste générée à partir d'une carte mentale ou d'une application de plan, vous pouvez activer le mode Plan dans le menu Gear pour appliquer une mise en forme spéciale dans le style de plan APA ou décimal.

Le mode plan automatique peut être activé pour des extensions de fichiers spécifiques dans le {% prefspane Style %}.

## Zoom sur le texte

![][2]

   [2] : images/textzoom.jpg @2x width=800px height=414px class=center

Vous pouvez modifier la taille du texte en utilisant {% kbd cmd shift + %} et {% kbd cmd shift - %}, ou utiliser le menu Zoom sous Aperçu dans la barre de menus ou dans le menu d'engrenage de la fenêtre du document. Marqué se souviendra de toutes les modifications que vous apporterez pour la prochaine fois (et à chaque fois). Réinitialisez le zoom à 100 % avec {% kbd cmd 0 %} (ou accédez à **Zoom Reset** depuis le menu Zoom).

## Mode sombre/Contraste élevé

Si vous préférez un texte clair sur un fond sombre, Marked est ce qu'il vous faut. Dans le menu __Preview__, vous pouvez utiliser {% appmenu Preview, Dark Mode ({{opt}}{{cmd}}I) %} pour inverser les couleurs de l'un des schémas par défaut pour un résultat clair sur sombre, et si un thème personnalisé est [construit correctement](Writing_Custom_CSS.html), il fonctionnera également là-bas.

## Afficher/Masquer la barre d'état

La barre d'état en bas de la fenêtre d'aperçu peut être basculée avec l'élément de menu {% appmenu Preview, Show Status Bar ({{ctrl}}/) %}. Lorsqu'il est masqué, il peut être visualisé et utilisé en survolant l'espace en bas de l'aperçu.