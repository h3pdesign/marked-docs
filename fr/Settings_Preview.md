<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Options dans le {% prefspane Preview %} :

![Paramètres : Aperçu][1]

[1]: images/screenshots/preferences-Preview.jpg @2x width=714px height=1031px class=preferencepane-scroll

### Aperçu du comportement

Activer la navigation sur la mini-carte
: Générez une carte visuelle du document qui apparaît lorsque "0" est enfoncé. Peut entraîner de courts retards lors du rendu de documents volumineux.

Les titres réduisent les sections
: cliquer sur un élément de titre réduit la section située entre celui-ci et le titre suivant.

Nécessite {% kbd cmd %}‑clic
: Si cette case est cochée, les titres ne se réduiront/s'agrandiront que lorsque vous cliquerez dessus avec la touche Commande enfoncée.

Synchroniser l'aperçu et le défilement des sources
: Lorsque votre éditeur le prend en charge, faites défiler l'aperçu pour qu'il corresponde à l'emplacement correspondant dans le document source.

Synchronisation de la lecture rapide avec la position de défilement
: Gardez la superposition [Lecture rapide](Speed_Reading.html) alignée avec la position de défilement de l'aperçu. Vous pouvez également activer cette option à partir de la superposition Speed ​​Read.

### Faites défiler pour modifier

Faites défiler pour modifier
: Lors de la mise à jour de l'aperçu, Marked peut déterminer le premier point où le document a changé et y faire défiler automatiquement. Cela maintient l'aperçu synchronisé avec votre emplacement actuel dans le document que vous modifiez. Le marqueur de modification le plus récent constitue la première différence dans le document depuis la dernière actualisation. L'activation de « Ordre de comparaison inversé » considérera à la place la dernière différence dans le document (de haut en bas) comme la modification la plus récente.

Afficher le marqueur de modification le plus récent
: Un petit marqueur rouge apparaît au point de la première modification détectée. Désactivez-le pour le rendre invisible. (Nécessite **Faites défiler pour modifier**.)

Afficher tous les marqueurs de différence
: Si cette option est activée, toutes les différences entre la dernière actualisation et le contenu actuel seront mises en évidence dans la gouttière. Vous pouvez parcourir les modifications en les faisant défiler jusqu'au milieu de la vue, en utilisant <kbd>e</kbd> (avant) et {% kbd shift E %} (en arrière).

Ordre de comparaison inversé
: Si cette option est activée, les différences seront marquées dans l'ordre inverse (de bas en haut). Cela affecte la navigation, donc <kbd>e</kbd> naviguera vers le haut et {% kbd shift E %} naviguera vers le bas. La « modification la plus récente » deviendra la dernière différence dans le document.

### Fonctionnalités supplémentaires

La table des matières suit la position de défilement
: La table des matières met en évidence la section actuelle.

Statistiques contextuelles pour la sélection de texte
: Afficher une fenêtre contextuelle de comptage de mots pour le texte sélectionné chaque fois qu'une sélection est effectuée.

Activer les popovers de liens
: Afficher un menu contextuel lorsque les liens externes sont cliqués et maintenus avant de les relâcher.

Valider automatiquement les URL lors de la mise à jour
 : Validez les URL lors du chargement et de l'actualisation du document. Affiche uniquement les résultats s'il y a des erreurs.
: Ceci exécute [link validation](Link_Validation.html) à chaque fois que le document est mis à jour (si vous avez un nombre important de liens, cela peut être un processus lent et doit être évité).

### Lien wiki

Convertir [[Liens Wiki]]
: Activez la [navigation wiki](Wiki_Navigation.html) de Marked pour la syntaxe `[[wiki link]]`.

Extension par défaut
: L'extension de nom de fichier Marked est utilisée lors de la résolution de liens wiki qui n'incluent pas d'extension (par exemple, `md`).

### Apparence

Mode sombre
: Afficher toutes les fenêtres en mode "Contraste élevé", avec du chrome foncé et, si disponible, la version inversée du Style actuel (peut ne pas s'appliquer aux Styles personnalisés).

Paramètre du système de correspondance
: Basculez automatiquement le mode sombre lorsque le mode sombre de macOS est activé ou désactivé à l’échelle du système.

Afficher le chemin complet dans le titre de la fenêtre
: Lorsqu'il est activé, Marqué affichera le chemin complet du document actuel dans le titre de la fenêtre.