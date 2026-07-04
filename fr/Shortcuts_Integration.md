<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marqué inclut des actions natives de **Raccourcis** (App Intents) pour ouvrir des fichiers, modifier les styles d'aperçu et exporter des documents. Ces actions apparaissent dans l'application Raccourcis lorsque vous recherchez **Marqué** et sont disponibles sur **macOS 13 (Ventura)** ou version ultérieure.

Pour une automatisation basée sur un script avec un modèle objet complet, voir [Prise en charge AppleScript](AppleScript_Support.html). Pour les flux de travail basés sur des URL à partir du shell, consultez le [URL Handler](URL_Handler.html).

## Rechercher des actions

1. Ouvrez l'application **Raccourcis**.
2. Créez un nouveau raccourci ou modifiez-en un existant.
3. Recherchez **Marqué** dans la bibliothèque d'actions.

Les actions sont regroupées sous **Documents** et **Exporter**. Marked enregistre également des expressions Siri telles que « Exporter le fichier avec Marked » et « Ouvrir dans Marked » pour des raccourcis rapides.

## Présentation des actions

| Actions | Objectif |
| --- | --- |
| **Ouvrir le fichier dans Marqué** | Ouvrez un Markdown ou un fichier texte dans une fenêtre d'aperçu. |
| **Définir le style d'aperçu** | Modifiez le thème d'aperçu d'un document ouvert (ou ouvrez d'abord un fichier). |
| **Ouvrir et exporter le fichier** | Ouvrez un fichier, puis exportez-le dans un autre format. |
| **Document d'exportation** | Exporter un document ouvert (fenêtre avant ou un fichier spécifique). |
| **Exporter les documents ouverts** | Exportez tous les documents actuellement ouverts dans Marqué. |

Toutes les actions d'exportation renvoient le ou les fichiers exportés sous forme de sortie Raccourcis **Fichier** afin que vous puissiez les transmettre à l'étape suivante (Mail, Finder, une autre application).

## Ouvrir le fichier dans Marqué

**Paramètre :** **Fichier** -- le document à ouvrir (à partir du Finder, de la feuille de partage ou d'une étape précédente de raccourcis).

Marqué ouvre le fichier dans une fenêtre d'aperçu. Utilisez-le lorsque vous souhaitez prévisualiser ou modifier dans Marqué avant de faire autre chose.

## Définir le style d'aperçu

**Paramètres :**

- **Style** -- style d'aperçu à partir d'un sélecteur (mêmes noms que le menu de style d'aperçu et le gestionnaire de styles).
- **Fichier** (facultatif) -- un fichier spécifique. En cas d'omission, Marked utilise le document de couverture. Si le fichier n'est pas déjà ouvert, Marked l'ouvre en premier.

La définition d'un style recharge l'aperçu avec ce thème (comme si vous choisissiez un style dans le menu des styles d'aperçu).

## Actions d'exportation

Les actions d'exportation partagent les mêmes options principales :

| Paramètre | Descriptif |
| --- | --- |
| **Format** | Markdown, HTML, PDF paginé, PDF continu, EPUB, DOCX, ODT, RTF, RTFD, TextBundle, TextPack ou OPML. |
| **Profil** (facultatif) | Un profil d'exportation enregistré à partir de {% prefspane Export %}. |
| **Style** (facultatif) | Style d'aperçu à appliquer avant l'export (rechargement complet de l'aperçu). |
| **Taille de la page** (facultatif) | Imprimez le nom de la taille de la page, tel que `A4` ou `Letter`. |
| **Marges** (facultatif) | Raccourci de marge (voir ci-dessous). |
| **Taille de police** (facultatif) | Taille de police de base en points pour l'exportation PDF, par exemple `14` ou `12pt`. |
| **Fichier de sortie** / **Dossier de sortie** (facultatif) | Chemin de destination. En cas d'omission, Marked écrit à côté du fichier source en utilisant l'extension correcte. |

**Remarques**

- **Le PDF paginé** utilise le même pipeline de mise en page d'impression que {% appmenu File, Export As, Save PDF (Paginated) %}. Il n'est pas disponible pour les documents d'aperçu HTML bruts.
- L'exportation **HTML** utilise l'aperçu rendu (ce que vous voyez dans WebView), et non le fichier source Markdown brut.
- **Le PDF continu** capture la mise en page actuelle de l'aperçu WebView.
- **Taille de police** active la même option de taille de police d'exportation/impression personnalisée à partir de {% prefspane Export %}. Cela n’affecte pas les documents Fountain.

### Ouvrir et exporter le fichier

Idéal pour les flux de travail du Finder : choisissez un fichier Markdown, ouvrez-le dans Marked et exportez-le en une seule étape.

**Paramètres :** **Fichier** (obligatoire), plus les options d'exportation ci-dessus.

Exemple d'utilisation : une action rapide qui extrait des fichiers du Finder et exporte des **PDF paginés** avec un profil et un style choisis.

### Exporter le document

Exportez un document **déjà ouvert** dans Marqué.

**Paramètres :**

- **Fichier** (facultatif) -- un fichier ouvert spécifique. En cas d'omission, Marked exporte le document de couverture.
- Options d'exportation et **Fichier de sortie** comme ci-dessus.

Utilisez-le lorsque Marked est déjà en cours d'exécution et que vous souhaitez exporter l'aperçu actuel sans rouvrir le fichier.

### Exporter les documents ouverts

Exportez **tous** les documents d'aperçu actuellement ouverts dans Marqué.

**Paramètres :**

- **Format** et options d'exportation (profil, style, taille de page, marges, taille de police).
- **Dossier de sortie** (facultatif) -- répertoire pour les fichiers exportés. En cas d'omission, chaque fichier est exporté à côté de son document source.

Utile pour l'exportation par lots après avoir examiné plusieurs chapitres ou notes dans Marqué.

## Raccourci de marge

Lorsque **Marges** est défini sur une action d'exportation, utilisez une chaîne comportant une à quatre mesures. Unités : `in`, `cm`, `mm`, `pt` ou `"` pour les pouces. Un nombre sans unité est traité comme des points.

| Valeur | Signification |
| --- | --- |
| `1in` | Tous côtés |
| `1in 2in` | Haut et bas `1in`, gauche et droite `2in` |
| `1in 2in 1in` | Haut `1in`, gauche et droite `2in`, bas `1in` |
| `1in 2in 1in 2in` | Haut, droite, bas, gauche |

Cela correspond à la clé `margins` dans les enregistrements d'exportation [AppleScript](AppleScript_Support.html#with-options-properties-record).

## Exemples de workflows

### Fichier du Finder au format PDF

1. **Ouvrir et exporter le fichier**
2. **Fichier** -- entrée à partir de la feuille de partage ou de l'action rapide du Finder.
3. **Format** -- PDF paginé.
4. **Style** -- thème facultatif (par exemple Amblin).
5. **Profil** -- profil d'exportation enregistré facultatif.
6. **Fichier de sortie** -- facultatif ; laissez vide pour écrire `filename.pdf` à côté de la source.

### Exporter ce qui est ouvert dans Marqué

1. **Exporter le document**
2. Laissez **Fichier** vide pour utiliser la fenêtre avant.
3. Choisissez **Format** et un profil ou un style facultatif.

### Exporter par lots des documents ouverts

1. **Exporter les documents ouverts**
2. Choisissez **Format** (par exemple EPUB).
3. Définissez éventuellement **Dossier de sortie** pour collecter toutes les exportations dans un seul répertoire.

### Style puis export (deux étapes)

1. **Définir le style d'aperçu** : choisissez un style (ciblez éventuellement un **fichier** spécifique).
2. **Exporter le document** -- même fichier ou document frontal, avec le **Format** souhaité.

Vous pouvez également transmettre **Style** directement sur une action d'exportation ; Marqué applique le thème et attend le rechargement de l'aperçu avant d'exporter.

## Chemins d'exportation et sandboxing

- Si **Fichier de sortie** ou **Dossier de sortie** est omis, Marqué écrit à côté du document source.
- Marqué peut créer des dossiers intermédiaires lorsque le chemin d'exportation est **à l'intérieur du dossier du document ouvert**.
- Les exportations en dehors du dossier du document nécessitent un chemin d'accès en écriture auquel Marked peut accéder (emplacement du document enregistré, signets de sécurité ou dossiers que vous avez accordés via les boîtes de dialogue Ouvrir).

Voir [Prise en charge AppleScript](AppleScript_Support.html#export-paths-and-sandboxing) pour les mêmes règles de bac à sable.

## Action Héritage `convert_to`

Le dictionnaire AppleScript expose toujours **`convert_to`** pour convertir du texte ou des fichiers Markdown sans aperçu ouvert. Les actions de raccourcis natifs ci-dessus sont préférées : elles ouvrent les documents correctement, attendent le chargement de l'aperçu et prennent en charge l'exportation PDF paginé de manière asynchrone.

Voir [Raccourcis et `convert_to` dans la prise en charge AppleScript](AppleScript_Support.html#shortcuts-and-convert_to) pour plus de détails sur la commande héritée.

## Dépannage : les actions n'apparaissent pas dans les raccourcis

Les raccourcis indexent **un** Installation marquée par identifiant de bundle (`com.brettterpstra.marked`). Il préfère la copie avec le **numéro de build le plus élevé** (`CFBundleVersion`), pas nécessairement l'application que vous venez de créer dans Xcode.

Si Marqué n'apparaît pas sous **Applications** dans la bibliothèque d'actions Raccourcis :

1. Répertoriez chaque copie sur le disque :
   ```bash
   mdfind 'kMDItemCFBundleIdentifier == "com.brettterpstra.marked"'
   ```
2. Supprimez ou renommez les copies obsolètes (par exemple un ancien `Marked.app` sur le bureau ou dans `/Applications` qui a été copié à partir d'une build **sans** métadonnées de raccourcis).
3. Exécutez la version que vous souhaitez que les raccourcis utilisent (Xcode **Run**, ou ouvrez directement le `.app` dans DerivedData).
4. Quittez et rouvrez l'application **Raccourcis**.

Une version qui inclut des raccourcis contient `Contents/Resources/Metadata.appintents`. Vous pouvez vérifier :

```bash
ls "/path/to/Marked.app/Contents/Resources/Metadata.appintents"
```

Au lancement, Marked enregistre `[MKShortcuts] Registering App Intents` dans Console.app lors de l'exécution de l'enregistrement (macOS 13+).

## Débogage

Activez le **Mode débogage** dans {% prefspane Advanced %}. Étapes d'exportation des journaux marqués au niveau Info avec le préfixe `[AppleScript]` dans Console.app et la visionneuse de journaux de Marked (le pipeline d'exportation est partagé avec AppleScript).

## Erreurs

Messages courants lorsqu'une action échoue :

- Aucun document marqué n'est disponible (rien d'ouvert et aucun fichier spécifié).
- Ce fichier n'est pas ouvert dans Marked (utilisez **Open File** ou **Open and Export File**).
- Profil d'exportation ou nom du style d'aperçu inconnu.
- Délai d'attente expiré pour le chargement ou le rechargement de l'aperçu.
- Erreurs d'autorisation de chemin d'exportation ou échec de génération de PDF paginé.