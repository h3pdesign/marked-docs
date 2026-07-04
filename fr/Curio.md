<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

[Curio][curio] est une application de brainstorming visuel et de prise de notes qui peut diffuser l'élément que vous modifiez dans le canal **aperçu en streaming** de Marked.

## Flux sélectionné comme marqué

1. Dans Marqué, choisissez {% appmenu File, New, Streaming Preview %} pour qu'une fenêtre d'aperçu en streaming soit prête.
2. Dans Curio, activez **Affichage → Flux sélectionné sur marqué**.

Lorsque vous double-cliquez pour modifier une figure, une note, une liste ou un autre élément dans Curio, son Markdown est transmis à l'aperçu en streaming et se met à jour au fur et à mesure que vous écrivez.

Mises à jour marquées en temps quasi réel, suivant le même contrat de presse-papiers `mkStreamingPreview` que les autres applications intégrées : voir [Détails techniques](Streaming_Preview.html#developers) sous [Aperçu en streaming](Streaming_Preview.html).

Si les aperçus cessent de se mettre à jour, vérifiez qu'une fenêtre d'aperçu en continu est ouverte dans Marqué et basculez **Flux sélectionné sur Marqué** une fois dans Curio.

[curio]: https://www.zengobi.com/products/curio/