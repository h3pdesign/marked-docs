<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Entrez en mode relecture à partir du menu d’engrenage. Il s'agit d'une fonctionnalité expérimentale conçue principalement pour les éditeurs qui reçoivent du texte d'autres personnes et ont besoin de faire des commentaires et de fournir des commentaires.

Le mode de relecture gèle les mises à jour du document, empêchant ainsi la perte des annotations et des notes lors de l'actualisation du document. Un indicateur rouge apparaît dans la barre supérieure pour vous rappeler que le mode relecture est actif.

Navigation au clavier, mise en favoris et mot-clé mettant en évidence toutes les fonctions lors de la vérification.

##Annotations

En mode relecture, la sélection de texte dans le document générera une fenêtre contextuelle qui vous permettra de choisir parmi plusieurs types de surbrillance différents. Cliquez sur le type de surbrillance que vous souhaitez ajouter au texte, ou annulez en cliquant sur le bouton "Annuler" ou en cliquant simplement en dehors de la fenêtre contextuelle.

## Remarques

![Annotations][1]

[1]: images/Annotating.jpg class=center

Une fois qu'un surlignage est ajouté, vous pouvez y ajouter de courtes notes en cliquant sur le surlignage. La fenêtre contextuelle contiendra désormais un champ de texte dans lequel vous pourrez saisir toutes les notes pouvant être pertinentes par rapport au texte en surbrillance. Les notes peuvent être supprimées et modifiées en cliquant sur un point surligné contenant déjà une note.

Les notes sont **uniquement** exportées lors de l'enregistrement au format HTML. Les faits saillants restent dans la plupart des formats d'exportation, notamment RTF et PDF.

## Vérification orthographique

En mode relecture, vous pouvez accéder au correcteur orthographique à l'échelle du système à partir du menu d'engrenage : {% appmenu {{gear}}, Proofing, Show Spelling Errors %}. Cela sera lent sur les documents volumineux et un avertissement s'affichera vous informant si le processus prend environ 30 secondes. Étant donné que le correcteur orthographique ne fonctionne pas dans l'aperçu Web de Marked, un « hack » est implémenté pour que cela fonctionne, et ce n'est pas rapide.

Une fois la vérification orthographique exécutée, vous pouvez ouvrir le panneau Corrections orthographiques pour activer la vérification grammaticale ainsi que voir les suggestions pour corriger les erreurs. Marqué *ne peut pas* les modifier sur place, vous devez revenir à votre document d'origine pour utiliser les résultats.

*Raccourcis :* {% kbd ctrl opt cmd S %} exécutera le correcteur orthographique. {% kbd ctrl opt cmd N %} passera à l'erreur suivante dans le document et {% kbd ctrl opt cmd G %} affichera le panneau des suppositions.