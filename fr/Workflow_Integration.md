<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

##AppleScript

Marked comprend un [dictionnaire AppleScript](AppleScript_Support.html) complet pour ouvrir des fichiers, contrôler l'aperçu (rechargement, défilement, surlignages, défilement automatique, lecture rapide), lire les statistiques, configurer les processeurs, copier HTML ou RTF, modifier les styles d'aperçu et exporter vers Markdown, HTML, PDF, EPUB, DOCX, ODT, TextBundle, RTF et OPML. **L'aperçu des titres/table des matières** via AppleScript est [documenté comme travail en cours](AppleScript_Support.html#table-of-contents-work-in-progress) et n'est pas encore fiable.

Vous pouvez cibler l'application, une fenêtre spécifique ou un document. Les commandes d'application incluent **ouvrir l'aperçu du streaming**, **prévisualiser le presse-papiers** et **fermer tout**. Les commandes de document incluent **obtenir des statistiques** et **imprimer avec un profil**. Les commandes d'exportation acceptent un **profil** d'exportation facultatif ou un enregistrement **`with`** pour des options telles que l'aperçu **style**, **pageSize** et **marges**. Par exemple :

```applescript
tell application "Marked"
	tell document 1
		export paginated pdf to "/path/to/output.pdf" with {style:"Amblin", pageSize:"A4", margins:"1in"}
	end tell
end tell
```

Voir [Prise en charge AppleScript](AppleScript_Support.html) pour la liste des commandes, le raccourci de marge, les notes du bac à sable et les conseils de débogage.

L'intégration AppleScript permet également à des applications telles que Tags.app de fonctionner directement dans Marked.

{% note %}
## Raccourcis

Marqué inclut les [Actions de raccourcis](Shortcuts_Integration.html) natives sur macOS 13 ou version ultérieure. Utilisez **Ouvrir et exporter un fichier** pour les flux de travail Finder vers PDF, **Exporter un document** pour tout ce qui est déjà ouvert dans Marqué ou **Définir le style d'aperçu** pour modifier les thèmes avant l'exportation. Les actions d'exportation acceptent les **profils**, les **styles** d'aperçu et des options telles que la **taille de page**, les **marges** et la **taille de police** (même sémantique que les enregistrements AppleScript `with`).

[shortcuts]: Shortcuts_Integration.html
{% endnote %}

## Gestionnaire d'URL

Le [Marked URL handler][urlhandler] permet une intégration étendue simplement en appelant des URL, soit à partir d'AppleScript, soit avec une commande de base `open` dans un script shell.

## Pack bonus marqué

Le Marked Bonus Pack est une collection de scripts, de commandes et de services. Certains fonctionnent avec plusieurs éditeurs, d'autres sont spécifiques à certains éditeurs. Les Services fonctionneront généralement avec tout éditeur disposant des capacités nécessaires. Les autres sont organisés dans des dossiers en fonction de l'application avec laquelle ils travaillent.

Vous pouvez télécharger le Bonus Pack et trouver des instructions pour l'installer et l'utiliser dans cet [article de la base de connaissances](http://support.markedapp.com/kb/how-to-tips-and-tricks/marked-bonus-pack-scripts-commands-and-bundles).

[urlhandler]: URL_Handler.html
[applescript]: AppleScript_Support.html