<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked comprend un système de navigation wiki qui vous permet de passer rapidement d'un fichier texte associé à l'autre à l'aide de simples liens `[[wiki]]`. Ce système est conçu pour une navigation transparente et fonctionne mieux lorsqu'il est configuré pour ouvrir des liens dans la fenêtre actuelle.

## Paramètres optimaux

Pour utiliser la liaison wiki, activez **Convertir `[[wiki links]]`** en {% prefspane Preview %} et définissez l'extension par défaut que Marked utilisera lors de la recherche de fichiers correspondants.

Pour une expérience optimale, définissez **"Les liens vers les fichiers texte doivent s'ouvrir dans :"** sur *"la fenêtre actuelle"* dans {% prefspane Apps %}. Cela garantit que la navigation semble naturelle et que l’histoire est préservée.

Si **Mettre en évidence les erreurs de syntaxe Markdown** est activé dans {% prefspane Proofing %}, la syntaxe `[[wiki link]]` qui ne correspond pas à un nom de fichier dans le répertoire actuel sera surlignée en rouge pour indiquer qu'un fichier référencé n'existe pas. Ces faits saillants seront mis à jour au fur et à mesure que les fichiers sont ajoutés, mais seulement après que le fichier actuel soit enregistré ou rechargé. En cliquant sur un lien de fichier manquant en surbrillance, vous proposerez de créer un nouveau fichier pour vous, en ajoutant l'extension par défaut si nécessaire. Le nouveau fichier vide sera ouvert dans Marqué, et si Modifier de nouveaux documents est activé, votre éditeur sera ouvert avec le nouveau fichier.

## Comment fonctionnent les liens wiki

- Les **liens Wiki** utilisent le format : `[[wiki link]]`.
- Lorsque vous cliquez sur un lien wiki, Marked recherchera un fichier correspondant dans le **même répertoire** que le document actuel.
- Le fichier doit avoir l'extension spécifiée dans les paramètres de Marked (par exemple, `.md`), sauf si vous fournissez un nom de fichier complet avec une extension dans le lien (par exemple, `[[notes.txt]]`).
- Si vous souhaitez utiliser pour le lien un texte différent du nom du fichier, ajoutez-le après un tube (`|`) dans le lien, par ex. `[[wiki linking|A note about linking]]`, qui s'affichera sous la forme `[A note about linking](wiki-link.md)`.
- Si un lien wiki commence par un `#`, il sera vu comme un lien d'ancrage sur la même page. Les noms d’ancres sont normalisés en minuscules et en remplaçant tous les espaces par des tirets. Pour les processeurs qui créent des ID d'en-tête sans tirets (comme MultiMarkdown), par ex. `## wiki links` obtient un identifiant de `wikilinks`, cette navigation pourrait être interrompue. Dans ces cas, spécifiez l'identifiant du lien correct, avec une barre verticale et un titre si nécessaire, par ex. `[[#wikilinks|#wiki links]]`.

### Noms de fichiers correspondants

Lorsque vous utilisez un lien tel que `[[wiki link]]`, Marked recherchera un fichier portant l'un des noms suivants (en supposant que votre extension par défaut est `.md`) :

- `wiki link.md`
- `WikiLink.md`
- `wiki-link.md`
- `Wiki-Link.md`
- `wiki_link.md`
- `Wiki_Link.md`
- `wikilink.md`
- `WikiLink.md`
- (et d'autres combinaisons d'espaces, de tirets, de traits de soulignement et d'InterCaps)

**Toutes les correspondances ne sont pas sensibles à la casse et sont flexibles grâce aux séparateurs.**
Si vous spécifiez une extension dans le lien (par exemple, `[[notes.txt]]`), Marked recherchera exactement ce fichier.

## Liens retour

Lorsqu'un fichier texte est ouvert et que la navigation wiki est activée, le reste des fichiers du répertoire sera analysé pour rechercher `[[links]]` dans le fichier actuel. Cela se produira en arrière-plan et le document ouvert sera mis à jour avec une liste de backlinks s'il y en a. Pour afficher les backlinks, la barre latérale des commentaires doit être ouverte. S'il est fermé, utilisez le menu Gear (**Vérification->Afficher les commentaires**) ou appuyez sur {% kbd ^@c %} pour l'ouvrir.


## Historique de navigation

Marked suit votre navigation via des liens wiki, vous permettant de vous déplacer **en arrière et en avant** dans l'historique de vos fichiers, tout comme un navigateur Web.

- **Retour :** {% kbd @[ %}
- **Avant :** {% kbd @] %}

Vous pouvez également utiliser le menu **Historique** pour accéder à n'importe quel fichier précédemment visité.