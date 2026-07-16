# <%= @title %>

Vous pouvez inclure votre propre JavaScript à partir de CDN ou en collant du code brut.

## Remarque sur Marked Conductor [a-note-about-marked-conductor]

La façon la plus simple d'implémenter du JavaScript personnalisé qui varie selon le type de document et son emplacement est d'utiliser [Marked Conductor][conductor]. Cela vous permet d'utiliser une configuration YAML pour ajouter des scripts à l'aide de « filtres ». Consultez la [page Conductor][conductor] pour plus de détails, et l'[exemple de configuration][sample config] pour des exemples.

[conductor]: https://brettterpstra.com/projects/conductor/
[sample config]: https://github.com/ttscoff/conductor-config/

## Ajout de JavaScript à partir des CDN [cdns]

![][1]

[1]: images/screenshots/AdditionalJavascript.jpg @2x width=592px height=576px class=center

Vous pouvez ajouter des URL CDN JavaScript dans la fenêtre "Scripts supplémentaires", accessible depuis {% prefspane Style %}. Saisissez les URL CDN, une par ligne. N'incluez aucune balise `<script>`, juste l'URL :

```
https://cdn.jsdelivr.net/gh/user/repo@version/file
https://cdn.jsdelivr.net/npm/micromark-extension-gfm-strikethrough@2.1.0/lib/html.min.js
```

> Notez que jQuery est déjà inclus dans la fenêtre d'aperçu.

Ces scripts seront insérés à la fin de l'aperçu, avant la balise du document. Si vous devez appeler une fonction init ou mettre à jour à chaque fois que l'aperçu est effectué, consultez [Inclusion de JavaScript brut](#rawjs). Pour inspecter le DOM et déboguer ces scripts dans un aperçu Marked en direct, vous pouvez attacher l'inspecteur Web de Safari comme décrit dans [WebKit Inspector](Writing_Custom_CSS.html#webkitinspector).


### Inclusion de JavaScript brut [rawjs]

Dans le champ de texte inférieur de la fenêtre Scripts supplémentaires, vous pouvez insérer du JavaScript brut. Ceci sera inclus entre une paire de balises `<script></script>`, donc ne les incluez pas dans le texte saisi. Ce champ peut contenir n'importe quelle commande JavaScript dont vous avez besoin pour initialiser une bibliothèque incluse, effectuer des modifications DOM ou tout ce que vous souhaitez faire dans une vue WebKit. jQuery est déjà inclus pour faciliter la manipulation du DOM.

Ces scripts ne s'exécutent qu'au premier chargement de la fenêtre. Lorsque l'aperçu se met à jour, cela se fait sur place en remplaçant certaines parties du DOM ; les scripts qui doivent agir sur le contenu mis à jour doivent donc utiliser les [Hooks](Embedding_Scripts.html#hooks).

Incluez dans le champ JavaScript brut un appel comme celui-ci :

```javascript
Marked.hooks.register('update', function() { myCustomFunction(); });
```
