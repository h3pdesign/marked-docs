<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

La fonctionnalité « faire défiler pour modifier » dans Marked assure le suivi des différences entre la dernière mise à jour et la dernière, en essayant de trouver le point où vous avez effectué vos modifications les plus récentes. Marked suit toujours cela et une petite ligne rouge apparaît dans l'aperçu pour vous montrer l'emplacement du premier changement détecté. Dans le panneau de préférences Comportement, vous pouvez activer « Faire défiler jusqu'à la première modification » et lorsqu'un aperçu est mis à jour, il fera défiler doucement la vue jusqu'à cet emplacement.

Avec « Faire défiler jusqu'à la première modification » désactivé, vous pouvez toujours appuyer sur la touche « e » à tout moment dans l'aperçu pour accéder au dernier point de modification stocké.


### Remarques sur "Faites défiler pour modifier"

C’est une fonctionnalité intéressante lorsqu’elle fonctionne, mais elle entraîne de nombreuses complications. En particulier lors des premières mises à jour du document, il peut y avoir des saccades dans le défilement. Si vos modifications se situent toutes à l'intérieur d'un élément très volumineux (un paragraphe trop long par exemple), celui-ci ne pourra que se rapprocher du marqueur. De même, si vous ajoutez un ou deux mots à la fin du document, le marqueur de changement sera positionné dans l'élément situé au-dessus jusqu'à ce qu'il y ait suffisamment de contenu à ancrer dans le nouvel élément.