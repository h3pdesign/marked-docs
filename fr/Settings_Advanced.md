<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Options dans le {% prefspane Advanced %} :

![Paramètres : Avancé][1]

[1]: images/screenshots/preferences-Advanced.jpg @2x width=689px height=1031px class=preferencepane-scroll

Métadonnées YAML et Pandoc
: - __Ignore:__ Le laisse exactement tel qu'il existe dans le document, utile si votre processeur ou préprocesseur utilise réellement le YAML.
: - __Supprimer avant le rendu__ : Le bloc YAML est supprimé
: - __Traiter comme des métadonnées MMD :__ Convertit le bloc de métadonnées YAML ou Pandoc au format MultiMarkdown.

Supprimer les en-têtes de métadonnées MultiMarkdown
: Si cette option est activée, les métadonnées MultiMarkdown en haut du document seront supprimées avant le rendu.
: Cela peut être utile si vous utilisez un processeur non MultiMarkdown qui autrement afficherait les métadonnées dans le document rendu. Les métadonnées sont toujours lues avant leur suppression, de sorte que la syntaxe spécifique à Marked sera toujours reconnue.

Images hébergées en cache
: Marked ne met pas en cache les images dans l'aperçu par défaut, car il surveille les modifications apportées à ces images et les met à jour instantanément. Si vous utilisez des images référencées via une URL Web, vous pouvez activer la mise en cache de ces images pour accélérer le rendu sur les connexions plus lentes.

Analyser les statistiques de lisibilité
: Si vous préférez ne pas calculer les [statistiques](Document_Statistics.html), cela désactivera ce traitement. Cela peut apporter certaines améliorations de performances sur des documents très volumineux. Le décompte des caractères, des mots et des phrases continuera de fonctionner.

Utiliser la table de recherche à l'échelle du système
: Cette option permettra à Marked de récupérer le terme de recherche que vous avez utilisé le plus récemment dans un autre éditeur, et tout ce qui est recherché dans Marked deviendra également la recherche dans d'autres applications. Le désactiver rend la fonction de recherche de Marked indépendante.

Utilisez {% kbd cmd E %} pour Rechercher avec sélection
: Par défaut, {% kbd cmd E %} ouvre l'éditeur par défaut. Si cette option est activée, alors {% kbd cmd E %} fonctionnera comme dans la plupart des applications d'édition de texte, en utilisant le texte sélectionné pour Rechercher, et Ouvrir dans l'éditeur peut être déclenché avec {% kbd opt cmd E %}.

Mode débogage
: Active la journalisation du débogage. Utilisez-le pour votre propre dépannage et lorsque vous signalez un problème. Sélectionnez __Aide->Ouvrir le journal de débogage__ pour afficher l'activité.
: Le réglage sur _All_ affichera des messages d'information, des avertissements et des messages d'erreur. Vous pouvez également le configurer pour qu'il affiche uniquement les erreurs, ou les erreurs et les avertissements.

Sauvegarde des paramètres
: Vous pouvez sauvegarder vos paramètres dans un fichier JSON qui peut être utilisé pour restaurer les paramètres ou les porter sur une nouvelle machine.