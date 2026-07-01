# <%= @title %>

[vim-marked][vimrepo] ist ein Vim-Plugin, das den aktuellen Markdown-Puffer in Marked öffnet. Es fügt `:MarkedOpen`, `:MarkedQuit`, `:MarkedToggle` und `:MarkedPreview` hinzu, sodass Sie die Datei (oder einen Bereich) an Marked senden können, ohne den Editor zu verlassen.

## Aufstellen

Installieren Sie es mit Ihrem Plugin-Manager; siehe [project README][vimrepo] für `vim-plug` und andere Optionen. Der Standardwert `g:marked_filetypes` umfasst `markdown` und gängige Varianten; Erweitern Sie die Liste, wenn Sie ein benutzerdefiniertes `filetype` verwenden.

## macOS und App-Name

Marked ist nur für macOS verfügbar, daher wird das Plugin nicht auf anderen Systemen geladen. Der Standard-App-Name ist **Marked 2**; Wenn Ihre Kopie von Marked unter einem anderen Namen oder Pfad installiert ist, legen Sie `g:marked_app` entsprechend fest (z. B. einen vollständigen Pfad zum App-Bundle). Die README-Datei behandelt Beenden, automatisches Beenden und Fokusverhalten.

I> Dieses Hilfethema ist nicht Teil des mit vim markierten Projekts; Für die neuesten Befehle und Optionen verwenden Sie [GitHub repository][vimrepo].


[vimrepo]: https://github.com/itspriddle/vim-marked
