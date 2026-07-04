<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Speed Read est un mode de lecture de style RSVP qui affiche un mot à la fois dans une superposition ciblée.

## Comment fonctionne la lecture rapide

Speed Read utilise une méthode appelée **Rapid Serial Visual Présentation** (RSVP). Au lieu de déplacer vos yeux sur les lignes de texte, les mots apparaissent dans une position fixe. Cela réduit les mouvements oculaires, les changements de ligne et les retours en arrière qui se produisent normalement pendant la lecture, ce qui peut le rendre utile pour survoler, réviser des documents familiers ou se déplacer rapidement dans un texte sans perdre votre place.

La méthode n’est pas magique, et elle ne garantit pas une meilleure compréhension à très grande vitesse. La compréhension écrite dépend toujours de la complexité de l'écriture, de votre familiarité avec le sujet et du paramètre WPM. Pour les matériaux denses ou inconnus, une vitesse modérée est généralement plus efficace que de pousser la vitesse aussi haut que possible.

La lettre rouge marque le point d'ancrage visuel du mot, parfois appelé **point de reconnaissance optimal**. En d’autres termes, les lecteurs identifient le mot plus efficacement lorsque leur regard se pose légèrement à gauche du centre plutôt que sur la première lettre. En gardant ce point d'ancrage au même endroit et en le mettant en évidence, Speed ​​Read donne à votre œil une cible cohérente. Il en résulte moins de recentrage entre les mots et un rythme plus régulier au fur et à mesure que le texte avance.

## Lecture de la vitesse d'ouverture

Utilisez **Aperçu > Lecture rapide**, l'élément **Lecture rapide** dans le menu Gear de la fenêtre d'aperçu, ou appuyez sur {% kbd ctrl opt S %}. L'élément de menu est disponible lorsqu'une fenêtre d'aperçu du document Markdown est active (il est désactivé pour les aperçus HTML bruts et lorsqu'aucun document n'est ouvert).

Lorsque Speed ​​Read s'ouvre, il démarre dans un état de pause afin que vous puissiez vous orienter avant le début de la lecture.

<contrôles vidéo preload="metadata" poster="images/speedread-poster.png">
  <source src="images/speedread.webm" type="video/webm">
  <source src="images/speedread.mp4" type="video/mp4">
  Votre navigateur ne prend pas en charge la vidéo de démonstration Speed Read.
</vidéo>
<p><em>Superposition de lecture rapide affichant les commandes de lecture, l'option de synchronisation et l'accès à l'aide.</em></p>

## Contrôles de superposition

Une fois la superposition visible, ces clés sont disponibles :

| Raccourci | Fonction |
| :-- | :-- |
| {% kbd space %} | Lecture/Pause |
| {% kbd [ %} | Aller au début du paragraphe (appuyer à nouveau pour le paragraphe précédent) |
| {% kbd ] %} | Aller au début du paragraphe suivant |
| {% kbd left %} | Diminuer la vitesse de lecture (WPM) |
| {% kbd right %} | Augmenter la vitesse de lecture (WPM) |
| {% kbd esc %} | Vitesse de sortie Lecture |

Les crochets sont capturés pour la navigation dans les paragraphes et les flèches gauche/droite sont capturées pour les changements de vitesse, de sorte que ces touches ne déclenchent pas la navigation dans l'aperçu lorsque la lecture rapide est ouverte. Vous pouvez également cliquer sur le bouton circulaire **X** dans le coin supérieur gauche de la superposition pour la faire disparaître.

D'autres raccourcis de navigation d'aperçu normaux fonctionnent toujours lorsque la lecture rapide est active, notamment `t`/`gg` (en haut), `G`/`b` (en bas) et `,`/`.` (navigation dans l'en-tête). Voir [Aperçu de la navigation](Keyboard_Shortcuts#preview-navigation) pour la liste complète.

La table des matières peut également être utilisée lors de la lecture rapide. Appuyez sur {% kbd cmd t %} pour l'ouvrir et naviguer, ou appuyez sur {% kbd f %} pour concentrer immédiatement la recherche rapide sur la navigation dans les en-têtes du document.

## Partir d'une sélection

Si du texte est sélectionné dans l'aperçu lorsque vous démarrez Speed Read, la lecture utilise le texte sélectionné. Si aucune sélection n'est active, Speed ​​Read utilise le texte complet du document.

## Synchronisation avec la position de défilement

Activez **Synchroniser la lecture rapide avec la position de défilement** dans {% prefspane Preview %}, ou utilisez la case à cocher dans la superposition de lecture rapide, pour conserver l'aperçu et la position de lecture rapide ensemble.

Lorsque cette option est activée, la lecture rapide commence au contenu actuellement visible en haut de l'aperçu au lieu du début du document. Au fur et à mesure que la lecture avance, l'aperçu défile avec les mots affichés.

Si vous fermez Speed ​​Read, faites défiler l'aperçu et rouvrez la superposition, la lecture démarre à partir de la nouvelle position visible. Si vous cochez la case de superposition alors que Speed ​​Read est déjà ouvert, la lecture se réinitialise à la position de défilement actuelle et continue à partir de là.

## Vitesse mémorisée

La valeur WPM est enregistrée automatiquement lorsque vous la modifiez avec {% kbd ← %} et {% kbd → %}. La vitesse que vous avez choisie sera restaurée la prochaine fois que vous utiliserez Speed ​​Read.