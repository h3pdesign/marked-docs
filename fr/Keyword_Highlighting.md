<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Attraper le verbiage gênant et mettre en évidence les phrases importantes.

## Mise en surbrillance des mots clés

La mise en surbrillance des mots clés dans Marqué vous permet de détecter des expressions courantes que vous souhaiterez peut-être éviter, de trouver des termes alternatifs ou simplement de les mettre en surbrillance à des fins générales. La liste des mots-clés utilisés pour correspondre à chaque catégorie peut être modifiée dans le {% prefspane Proofing %}.

Activez la mise en surbrillance avec {% kbd shift cmd H %}, depuis le menu d'engrenage ({% appmenu {{gear}}, Highlight Keywords %}), ou ouvrez le tiroir de mots-clés à l'aide de l'icône de surligneur en bas à gauche (près du menu d'engrenage). Le tiroir peut également être ouvert avec le raccourci clavier {% kbd shift cmd K %}. La mise en surbrillance est automatiquement activée lorsque le tiroir est ouvert et peut être activée et désactivée avec l'interrupteur situé sur le côté gauche du tiroir.

## Le tiroir de mots clés

![Tiroir de mots-clés][kwd]

[kwd]: images/screenshots/mainwindow-feature-keywords-crop.jpg @2x width=1089px height=503px class=center

Le tiroir de mots clés qui s'affiche lors de l'activation de la surbrillance offre un accès rapide aux options de surbrillance, y compris la possibilité d'activer et de désactiver des types de surbrillance individuels. La rangée verticale d'étiquettes colorées sur le côté gauche correspond aux surlignages du texte. Cliquer sur une étiquette fait basculer les surbrillance pour ce type de mot-clé.

À gauche de chaque étiquette se trouve une icône de cible. En cliquant dessus, le document fera défiler le document jusqu'à l'instance suivante de la surbrillance dans l'ordre du document. À droite de l’étiquette se trouve un décompte indiquant le nombre total de surbrillance pour ce type.

Vous pouvez naviguer rapidement parmi les points forts à l'aide du clavier. Taper `[` et `]` avancera et reculera initialement dans toutes les surbrillance. Si vous cliquez sur une icône cible, `[` et `]` passeront à la navigation uniquement sur ce type de surbrillance. `{` (Shift-[) et `}` (Shift-]) parcourront toujours toutes les surbrillance, quelle que soit la dernière cible cliquée.

Si un mot ou une phrase en surbrillance est cliqué, ce type deviendra la cible de la navigation et l'utilisation de `[` ou `]` naviguera à partir de ce point dans le document.

## Modification des mots clés

![Paramètres de relecture][proofprefs]

  [proofprefs] : images/screenshots/preferences-Proofing.jpg @2x width=689px height=1031px class=preferencepane

Par défaut, Marked utilise la liste [Plain English Campaign's](http://www.plainenglish.co.uk) de mots et d'expressions surutilisés. Vous pouvez les ajouter ou les remplacer facilement en les modifiant dans le {% prefspane Proofing %}. Chaque champ est un texte de forme libre et chaque ligne est interprétée comme une expression de recherche. Utilisez `*` au début d'une phrase ou d'un mot pour faire correspondre n'importe quel texte précédent, et `?` pour faire correspondre un seul caractère comme caractère générique.

Les expressions régulières peuvent être utilisées en entourant l'expression de barres obliques :

    /\\S*?ly/

Ce qui précède correspondra à tous les mots se terminant par « ly » pour les mettre en surbrillance. La syntaxe des expressions régulières dans la mise en surbrillance des mots clés de Marked est la [identique à JavaScript](http://www.regular-expressions.info/javascript.html).

## Mots clés temporaires

Vous pouvez également ajouter des mots-clés temporaires dans le tiroir de mots-clés en modifiant le bloc-notes. Tout comme dans les champs {% prefspane Proofing %}, vous ajoutez un mot-clé ou une phrase par ligne, expressions régulières autorisées (entourées de barres obliques). Après avoir modifié les mots-clés temporaires, assurez-vous de cliquer sur le bouton « Mettre à jour » (ou appuyez sur {% kbd cmd return  %}) pour enregistrer les modifications et les voir mises en surbrillance dans votre document.

Les expressions régulières fonctionnent également dans le champ de mot-clé temporaire, entourez simplement le texte de barres obliques (`/my expression\b/`).

Les mots-clés temporaires sont destinés aux situations où la densité des mots-clés est importante et vous permettent de voir rapidement combien de fois vous avez utilisé les mots cibles, en mettant en évidence leurs emplacements dans le document. Un nombre de correspondances pour les mots-clés temporaires est affiché bien en évidence dans le tiroir.

Consultez également la commande ["Visualize Word Repetition"][wordrep] pour rechercher les mots surutilisés dans votre texte.

[wordrep]: Document_Statistics.html#visualizewordrepetition

## Voix passive

Marqué soulignera l'utilisation de « voix passive » dans le texte anglais. Comme [défini par Wikipédia] [passif] :

> le sujet grammatical exprime le thème ou le patient du verbe principal – c'est-à-dire la personne ou la chose qui subit l'action ou dont l'état change.

La voix passive n'est pas mauvaise, comme vous pouvez le lire [dans les articles du linguiste Geoffrey K. Pullum][gkp]. Les passages marqués sont soulignés à la voix passive, mais la décision quant à leur validité vous appartient.

[passive]: https://en.wikipedia.org/wiki/Passive_voice
[gkp]: http://languagelog.ldc.upenn.edu/nll/?cat=54

## Mots doublés

Les mots doubles (par exemple « le le ») sont automatiquement surlignés en orange lorsque la mise en surbrillance des mots clés est activée. Ceci n'est actuellement pas configurable, mais devrait s'avérer pratique pour la relecture.