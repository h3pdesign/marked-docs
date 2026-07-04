<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

### Mode débogage

Vous pouvez activer la journalisation du débogage en ouvrant {% prefspane Advanced %} et en cochant la case **Mode de débogage** en bas du volet. Cela affichera un menu déroulant dans lequel vous pourrez définir le niveau de journalisation que vous souhaitez voir :

- **Erreurs uniquement** : seules les erreurs graves seront enregistrées
- **Erreurs et avertissements** : affiche en outre des avertissements moins urgents
- **Tous** : affiche les erreurs, les avertissements et les messages de débogage au niveau des informations. Il s'agit du paramètre recommandé pour le dépannage.

{% note %}
À FAIRE : Est-ce que cela fonctionne toujours ?
Vous pouvez également accéder à ces options en maintenant la touche {% kbd opt  %} enfoncée lors de l'ouverture de {% appmenu Help %} dans la barre de menu.
{% endnote %}

### Affichage du journal

Avec le **Mode débogage** activé, vous pouvez ouvrir le menu {% appmenu Help %} et sélectionner Ouvrir le journal de débogage. Cela ouvrira le journal de Marked dans Console.app, qui sera mis à jour en direct au fur et à mesure que des messages de journal seront ajoutés lors de l'utilisation de Marked.

### Dépannage des règles personnalisées

[Préprocesseurs et processeurs personnalisés](Custom_Processor.html) obtiennent leur propre interface de journal. Sélectionnez {% appmenu Help, Show Custom Rules Log %} pour ouvrir la fenêtre. Cette fenêtre affichera un journal colorisé montrant quelles règles correspondent et quelles commandes elles exécutent.

### Signaler un problème

Utilisez {% appmenu Help, Report an Issue %} pour ouvrir une fenêtre qui affiche vos paramètres pour les touches les plus courantes et un modèle pour créer un rapport de bogue. Utilisez le bouton « Copier dans le Presse-papiers » pour copier le contenu de la fenêtre, puis cliquez sur « Ouvrir le site de support » pour ouvrir [le formulaire de nouvelle question](https://support.markedapp.com/questions/add) où vous pouvez coller votre rapport. J'essaie de répondre aux signalements dans les 48 heures.