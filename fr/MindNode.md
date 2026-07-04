<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Faites glisser un document [MindNode][mn] sur Marked (ou utilisez la commande **Ouvrir dans Marked**/aperçu de MindNode, selon la version de MindNode). Marked traite le fichier comme l'exportation Markdown de MindNode, de sorte que la hiérarchie de votre carte devient des en-têtes et des listes dans l'aperçu.

## Aperçu en streaming (MindNode 2026.3+)

I> **MindNode 2026.3** et plus récent ajoute Marked [aperçu en streaming](Streaming_Preview.html). Dans MindNode, choisissez **Affichage → Aperçu dans Marqué** pour l'ouvrir ; l'aperçu est mis à jour en direct à mesure que vous modifiez la carte.

## MindNode Classique contre MindNode 7+

W> L'intégration actuelle cible les bundles **MindNode Classic**. Les versions plus récentes de MindNode utilisent un format de package différent ; si l'ouverture d'une carte échoue ou si Marqué affiche une feuille **"Veuillez ouvrir depuis MindNode"**, préparez la carte à partir du menu **Avancé** de MindNode (souvent **Ouvrir dans une autre application** / Marqué), ou exportez un bundle compatible, plutôt que de faire glisser un package `.mindnode` brut qui n'a pas été préparé pour l'aperçu.

Étant donné que le fichier est préparé par MindNode avant que Marked ne le lise, enregistrez-le toujours dans MindNode avant d'attendre une mise à jour dans Marked.

[mn]: https://mindnode.com/
[mn-beta]: https://testflight.apple.com/join/jSvVBpnt