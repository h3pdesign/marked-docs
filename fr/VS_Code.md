<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

[Visual Studio Code][vscode] n'inclut pas Marked prêt à l'emploi, mais vous pouvez utiliser une extension de communauté pour l'**aperçu Markdown en direct** dans Marked --- aperçu, exportation et vérification pendant que vous continuez à écrire dans VS Code.

## Démarrage rapide

1. Installez une extension VS Code **Ouvrir dans l'extension marquée** (voir [Ouvrir dans l'extension marquée][ext] ci-dessous).
2. Ouvrez votre fichier Markdown dans VS Code.
3. Envoyez le fichier à Marked --- l'aperçu est mis à jour lorsque vous enregistrez.

## Ouvrir dans l'extension marquée

L'[extension Ouvrir dans Marked][ext] (Visual Studio Marketplace) ajoute une action **Ouvrir dans Marked** : bouton de titre de l'éditeur, **{% kbd shift cmd m %}**, menus contextuels dans l'éditeur et l'explorateur de fichiers, **ouvrir le dossier** en option pour le navigateur de fichiers de Marked, un indicateur de barre d'état et une sauvegarde automatique facultative avant l'ouverture. Les paramètres vous permettent de définir le chemin d'accès à l'application marquée si elle ne se trouve pas à l'emplacement par défaut.

I> L'extension a été initialement publiée pour Marked 2. Marked 3 utilise le même style de transfert de fichier et d'URL, donc cette intégration continue de fonctionner ; si quelque chose change, vérifiez la [page d'extension][ext] ou le référentiel de l'auteur pour les mises à jour.

## Exigences

Marqué fonctionne uniquement sur macOS. Installez [Marked 3][marked] et l'extension, puis pointez **chemin de l'application** vers votre application marquée si nécessaire.

[ext]: https://marketplace.visualstudio.com/items?itemName=vikgamov.vscode-open-in-marked2
[marked]: https://markedapp.com/
[vscode]: https://code.visualstudio.com/