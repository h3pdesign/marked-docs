<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Options dans le {% prefspane General %} :

![Paramètres : Général][1]

[1]: images/screenshots/preferences-General.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Fenêtre

Gardez les nouvelles fenêtres en haut
: Définit automatiquement les nouvelles fenêtres pour qu'elles "flottent" au-dessus des autres applications.

Augmenter la fenêtre lors de la mise à jour
: Lorsqu'une modification est détectée dans un fichier surveillé, la fenêtre d'aperçu de ce document s'élèvera au-dessus des autres fenêtres de votre bureau sans activer Marqué.

Translucide en arrière-plan
: Estompe la fenêtre lorsqu'elle n'est pas focalisée. Utilisez le curseur pour définir l'opacité.

Désactivez les fonctionnalités gourmandes en mémoire sur les documents volumineux
 : désactivez certaines fonctionnalités gourmandes en ressources processeur, telles que les titres pliables lorsque les documents dépassent 100 000 octets.

Nouveaux documents ouverts dans
: Choisissez **windows**, **tabs** ou **automatic** (suivez les paramètres du système macOS pour la tabulation). Lorsque vous utilisez les onglets, naviguez avec {% kbd cmd shift [/] %} et le [Panneau d'ouverture rapide](Quick_Open.html).

Mettre le document mis à jour au premier plan
 : lorsqu'un aperçu est mis à jour, sélectionnez son onglet ou placez sa fenêtre au premier plan **dans Marqué uniquement**. Si une autre application est au premier plan (par exemple votre éditeur de texte), Marqué reste en arrière-plan — le bon onglet est sélectionné afin qu'il soit prêt lorsque vous revenez à Marqué. Pour afficher l'aperçu au-dessus de toutes les applications sans activer Marqué, utilisez plutôt **Augmenter la fenêtre lors de la mise à jour**.

Remettre le focus sur l'application précédente
: Lorsqu'il est activé, si une action d'augmentation/mise à jour fait passer Marked au premier plan, le focus clavier est renvoyé à l'application qui était au premier plan avant la mise à jour (telle que votre éditeur de texte). Lorsqu'il est désactivé, Marked n'effectue jamais ce transfert de focus. Si Marqué ne passe pas au premier plan, cette option n’a aucun effet.

### Barre d'état

Afficher le sélecteur de style
: affiche le sélecteur de style dans la barre inférieure de la fenêtre d'aperçu.

Afficher le nombre de mots
: Afficher le nombre de mots (et le bouton de statistiques) dans la barre inférieure de la fenêtre d'aperçu.

Le nombre de mots exclut
: Les calculs du nombre de mots peuvent ignorer toute combinaison de :

- **Notes de bas de page/Citations**
- **Citations**
- **Blocs de code en retrait** (les blocs de code clôturés sont toujours exclus)
- **Légendes des images**

### Raccourcis

Cliquez sur le champ de raccourci pour enregistrer une combinaison de touches de raccourci qui déclenche un événement :

Activer marqué
: Passez à Marqué lorsque cette touche de raccourci est enfoncée dans n'importe quelle application.

Lever la première fenêtre
: élève la fenêtre d'aperçu marquée la plus au premier plan (la dernière active) au premier plan sans quitter l'application actuelle.

Ouvrir la palette d'actions
: Ouvrez la palette de commandes [Actions rapides](Quick_Actions.html) lorsque Marqué est actif. Ce raccourci s'applique à {% appmenu File, Quick Actions… %} et fonctionne uniquement dans Marked (pas à partir d'autres applications).

Réinitialiser les alertes
: restaurez toutes les boîtes de dialogue d'alerte que vous avez précédemment ignorées afin qu'elles puissent réapparaître.