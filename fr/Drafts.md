<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Les [Brouillons][les brouillons] sur Mac peuvent refléter le brouillon actif dans Marked à l'aide de **Aperçu en streaming marqué**, le même canal basé sur le presse-papiers décrit dans [Aperçu en streaming](Streaming_Preview.html). Vous pouvez également envoyer le brouillon actuel une fois avec une **action** communautaire (pas de mises à jour en direct jusqu'à ce que vous l'exécutiez à nouveau).

## Aperçu en streaming (Brouillons pour Mac)

1. Dans Marqué, choisissez {% appmenu File, New, Streaming Preview %} pour qu'une fenêtre d'aperçu en streaming soit prête.
2. Dans **Brouillons pour Mac**, ouvrez **Paramètres** et activez **Activer la prise en charge de l'aperçu du streaming des applications marquées**.
3. Utilisez **Ouvrir marqué** si Drafts le propose pour faire avancer Marked, puis modifiez-le dans Drafts ; l'aperçu est mis à jour à mesure que votre brouillon change.

![][draftsprefs]

Lorsque cette option est activée, Drafts pousse Markdown vers Marked via l'intégration Marked expose pour les aperçus en streaming (plutôt que de compter sur la visualisation d'un fichier sur le disque).

### Soyez marqué

Si **Get Marked App** apparaît dans la feuille de paramètres de Drafts, utilisez-la lorsque Marked n'est pas encore installé.

## Aperçu dans l'action marquée (actualisation manuelle)

Installez l'action communautaire [**Aperçu dans Marqué**](https://actions.getdrafts.com/a/11f) à partir du répertoire Drafts. Il envoie le **projet de texte actuel** à Marked à l'aide d'une URL `x-marked://preview?text=…` (les brouillons remplacent votre brouillon de contenu). **Le contenu n'est pas mis à jour en direct** : réexécutez l'action chaque fois que vous souhaitez que Marked corresponde au brouillon.

Cette approche est pratique pour les vérifications occasionnelles, tandis que l'**aperçu en streaming** convient aux sessions d'écriture continues.

Les brouillons fonctionnent également sur iPhone et iPad ; L'intégration de l'aperçu en streaming documentée ici s'applique aux **Brouillons pour Mac** avec Marqué sur le même Mac.

[draftsprefs]: images/Drafts_streaming_preview_preference.png width=842px height=182px class=center

[drafts]: https://getdrafts.com/