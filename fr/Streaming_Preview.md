<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

En ouvrant {% appmenu File, New, Streaming Preview %}, Marked reçoit des mises à jour en direct sur un presse-papier nommé au lieu de regarder un fichier sur le disque. L'application source doit s'intégrer à Marked.

[Curio](Curio.html), [Brouillons](Drafts.html) et [The Archive](The_Archive.html) documentent leurs propres bascules et commandes de menu. nvUltra, nvALT, Bear et d'autres utilisent le même canal : ouvrez l'aperçu en streaming dans Marked, activez l'intégration dans votre éditeur et commencez à taper ; les mises à jour arrivent presque en temps réel.

## Développeurs

Pour intégrer le Streaming Preview à votre application, il vous suffit de placer le texte markdown à prévisualiser dans un presse-papier nommé. Utilisez le code suivant (Objective-C) pour mettre à jour, de préférence sur une méthode didEndEditing ou à intervalles limités :

```obj-c
NSString *rawString = @"the text to process";
// pasteboard *must* be named 'mkStreamingPreview'
NSPasteboard* pb = [NSPasteboard pasteboardWithName:@"mkStreamingPreview"];
[pb clearContents];
[pb setString:rawString forType:(NSString*)kUTTypeUTF8PlainText];
```

### Déclarer une URL de base pour les actifs relatifs

Vous pouvez également fournir une URL de base pour l'aperçu en streaming, permettant ainsi aux URL relatives dans les images et autres ressources de fonctionner comme elles le feraient dans l'application source. Si l'URL de base inclut un nom de fichier, son nom et son extension seront mis à la disposition des processeurs personnalisés, mais ce n'est pas obligatoire. Pour inclure l'URL de base, placez simplement un objet NSURL dans le presse-papier :

```obj-c
NSString *rawString = @"The text to be processed\\n\\n![](images/screenshots/mainwindow-feature-stats.jpg)";
NSURL *baseURL = [NSURL fileURLWithPath:@"/Users/username/Documents/HelpDocs/Main Window.md"];
NSPasteboard* pb = [NSPasteboard pasteboardWithName:@"mkStreamingPreview"];
[pb clearContents];
[pb writeObjects:@[rawString, baseURL]];
```

Ou en Swift :

```swift
let rawString = "The text to be processed\n\n![](images/screenshots/mainwindow-feature-stats.jpg)"
let baseURL = URL(fileURLWithPath: "/Users/username/Documents/HelpDocs/Main Window.md")
let pb = NSPasteboard(name: "mkStreamingPreview")
pb.clearContents()
pb.writeObjects([rawString, baseURL])
```

Si la version Mac App Store de Marked est utilisée et que l'URL de base n'est pas accessible via le sandboxing, l'autorisation sera demandée la première fois que l'URL est chargée dans l'aperçu.

### Déclarer l'application source

Les applications peuvent également se déclarer comme source du contenu d'aperçu en incluant une ligne de métadonnées `source`. Cela sera généralement accompli dans un commentaire HTML pour permettre la compatibilité avec les processeurs GFM et MultiMarkdown. Indiquez simplement le nom de l'application ou l'identifiant du bundle :

```html
<!--
source: Bear.app
-->
```

### Ouverture de l'aperçu du streaming par programmation

Votre application peut ouvrir l'aperçu du streaming par programme à l'aide de la méthode de gestionnaire d'URL `x-marked-3://stream/`. Cette méthode accepte également un paramètre `x-success` dans lequel vous pouvez transmettre un ID de bundle d'une application à activer une fois terminée.