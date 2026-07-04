<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

[VoodooPad][vp] regroupe chaque page dans un seul fichier de base de données. Faites glisser le `.vpdoc` sur Marqué pour prévisualiser la page actuellement au premier plan dans VoodooPad ; utilisez {% kbd cmd S %} dans VoodooPad chaque fois que vous avez besoin de Marked pour recharger à partir du disque.

Marked surveille le document sur le disque et échange l'aperçu lorsque vous changez de page dans VoodooPad.

## Images intégrées

Lorsque vous référencez des images avec Markdown ou HTML et que le binaire réside **à l'intérieur** de la base de données VoodooPad, Marked peut l'extraire pour l'aperçu. Les images qui ne sont que des **alias** (fichiers glissés par référence) ne sont pas stockées dans le bundle : pointez vers celles avec des chemins absolus ou des chemins relatifs au `.vpdoc` sur le disque afin que Marked puisse les résoudre.

[vp]: https://www.voodoopad.com/