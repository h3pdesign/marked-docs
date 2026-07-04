<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked has special handling for comments and annotations.

## Annotation sources

Marked recognizes comments coming from:

- Markdown Footnotes
- CriticMarkup comments
- Commentaires et modifications Microsoft Word

## The Comments sidebar

Toutes les annotations sont affichées dans une barre latérale et masquées dans l'aperçu du document. To show the annotations sidebar, use the **Gear Menu -> Proofing -> Show Comments**, or press {% kbd ctrl cmd C %}.

![Une note de bas de page dans la barre latérale des commentaires][barre latérale]

  [barre latérale] : images/comment-sidebar-800.jpg @2x width=800

Passer la souris sur un commentaire dans la barre latérale tracera une ligne vers son emplacement dans le document. Dans le cas des notes de bas de page, cela indiquera l'endroit où la note de bas de page apparaît dans le texte. In the case of comments, it will point to the original location of the comment, which may be blank space in the preview.

Clicking a comment in the sidebar will draw a highlighted animation pointing to its location.

La police et le style de la barre latérale dépendent du style actuel, ils peuvent donc être différents selon les styles.