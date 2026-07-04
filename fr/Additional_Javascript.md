<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Vous pouvez inclure votre propre JavaScript à partir de CDN ou en collant du code brut.

## Une note sur le conducteur marqué

The easiest way to implement custom JavaScript that varies between document types and locations is with the [Marked Conductor][conductor]. It allows you to use a YAML configuration to append scripts using "filters." Consultez la [page Conductor][conductor] pour plus de détails et consultez le [exemple de configuration][exemple de configuration] pour des exemples.

[conductor]: https://brettterpstra.com/projects/conductor/
[sample config]: https://github.com/ttscoff/conductor-config/

## Ajout de JavaScript à partir des CDN [cdns]

![][1]

   [1] : images/screenshots/AdditionalJavascript.jpg @2x width=592px height=576px class=center

Vous pouvez ajouter des URL CDN JavaScript dans la fenêtre "Scripts supplémentaires", accessible depuis {% prefspane Style %}. Saisissez les URL CDN, une par ligne. N'incluez aucune balise `<script>`, juste l'URL :

```
https://cdn.jsdelivr.net/gh/user/repo@version/file
https://cdn.jsdelivr.net/npm/micromark-extension-gfm-strikethrough@2.1.0/lib/html.min.js
```

> Note that jQuery is already included in the preview window.

These scripts will be inserted at the end of the preview, before the document tag. Si vous devez appeler une fonction init ou mettre à jour à chaque fois que l'aperçu est effectué, consultez [Inclure le JavaScript brut] (#rawjs). Pour inspecter le DOM et déboguer ces scripts dans un aperçu marqué en direct, vous pouvez attacher l'inspecteur Web de Safari comme décrit dans [WebKit Inspector](Writing_Custom_CSS.html#webkitinspector).


### Y compris le JavaScript brut [rawjs]

Dans le champ de texte inférieur de la fenêtre Scripts supplémentaires, vous pouvez insérer du JavaScript brut. This will be included within a `<script></script>` pair, so don't include that in the input. Ce champ peut contenir n'importe quelle commande JavaScript dont vous avez besoin pour initialiser une bibliothèque incluse, effectuer des modifications DOM ou tout ce que vous souhaitez faire dans une vue WebKit. jQuery est déjà inclus pour faciliter la manipulation du DOM.

These scripts will only run when the window is first loaded. When the Preview updates, it's done in place by replacing parts of the DOM, so scripts that need to act on the updated content should do so using [Hooks](Embedding_Scripts.html#hooks).

Incluez dans le champ JavaScript brut un appel comme celui-ci :

```javascript
Marked.hooks.register('update', function() { myCustomFunction(); });
```
