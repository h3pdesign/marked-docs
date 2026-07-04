<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

[vim-marked][vimrepo] est un plugin Vim qui ouvre le tampon Markdown actuel dans Marked. Il ajoute `:MarkedOpen`, `:MarkedQuit`, `:MarkedToggle` et `:MarkedPreview` afin que vous puissiez envoyer le fichier (ou une plage) vers Marked sans quitter l'éditeur.

## Configuration

Installez avec votre gestionnaire de plugins ; voir le [projet README][vimrepo] pour `vim-plug` et d'autres options. Le `g:marked_filetypes` par défaut inclut `markdown` et des variantes courantes ; étendez la liste si vous utilisez un `filetype` personnalisé.

## macOS et nom de l'application

Marqué est uniquement macOS, le plugin ne se charge donc pas sur d'autres systèmes. Le nom de l'application par défaut est **Marqué 2** ; si votre copie de Marked est installée sous un nom ou un chemin différent, définissez `g:marked_app` pour qu'il corresponde (par exemple un chemin complet vers l'ensemble d'applications). Le README couvre les arrêts, l'arrêt automatique et le comportement de focus.

I> Cette rubrique d'aide ne fait pas partie du projet marqué vim ; pour les dernières commandes et options, utilisez le [dépôt GitHub][vimrepo].


[vimrepo]: https://github.com/itspriddle/vim-marked