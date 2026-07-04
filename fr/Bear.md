<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

[Bear][bear] can send a live preview straight to Marked.

## Sending from Bear

Dans Bear, choisissez **Aperçu dans Marqué** dans le menu **Affichage** (le libellé peut varier légèrement selon la version Bear). Marked reçoit un TextBundle, donc les images et les ressources intégrées voyagent généralement avec le texte.

Images referenced with absolute paths or `https` URLs also resolve as long as Marked can reach them.

## Mac App Store note

Si vous utilisez la version **Mac App Store** de Marked et que macOS continue de demander l'autorisation d'ouvrir des répertoires lors de la prévisualisation à partir de Bear, [contactez l'assistance Marked](http://support.markedapp.com) pour une mise à niveau gratuite vers l'édition à téléchargement direct, ce qui évite cette friction particulière du bac à sable.

## Tags

Bear-style tags can be rendered as such by turning on **#Text is tag** and **Style tags** under {% prefspane Processor %}.

W> This setting can confuse Marked if you write regular headlines without spaces after the `#`.

## Filenames and export

If you turn on **Use first H1 as fallback title** in {% prefspane Export %}, that title can drive the filename and the `%title` placeholder when you print or export PDFs from Marked.

I> A preview style that approximates Bear's own look [is available on markedapp.com/styles](https://markedapp.com/styles/preview?style=bear).

L'aperçu en streaming de Bear est résumé sur la page [Aperçu en streaming](Streaming_Preview.html) et dans [Intégrations d'applications supplémentaires](Additional_Application_Support.html).

[bear]: https://bear.app/