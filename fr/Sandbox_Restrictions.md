<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

La version Mac App Store (MAS) de Marked s'exécute dans un environnement sandbox qui restreint certaines opérations pour des raisons de sécurité. Cela peut affecter certaines fonctionnalités, en particulier lors de l'utilisation de processeurs personnalisés avec des binaires ou des scripts externes.

## Restrictions courantes du bac à sable

### Exécuter les binaires de commandes

Le problème le plus courant rencontré par les utilisateurs est que les binaires externes ne peuvent pas être exécutés directement dans la version MAS. Cela affecte :

- **Processeurs externes** comme Pandoc, Kramdown ou d'autres outils de ligne de commande
- **Scripts personnalisés** qui s'appuient sur des binaires externes
- **Utilitaires système** qui ne sont pas accessibles depuis le bac à sable

### Solutions de contournement

#### Copie de fichiers binaires vers l'App Bundle

Si vous devez utiliser des processeurs externes comme Pandoc dans la version MAS, vous pouvez copier le binaire dans l'app bundle :

1. Cliquez avec le bouton droit sur Marked.app → **Afficher le contenu du package**
2. Accédez à **Contenu/Ressources/**
3. Créez un dossier `bin` s'il n'existe pas
4. Copiez votre binaire (par exemple, `pandoc`) dans ce dossier `bin`
5. Rendre le exécutable : `chmod +x` le binaire
6. Dans l'action Exécuter la commande, référencez-la comme :
   - `YOUR_BINARY_NAME [arguments]`
   - Ou utilisez le chemin complet : `/Applications/Marked.app/Contents/Resources/bin/YOUR_BINARY_NAME [arguments]`

**Remarque** : Les scripts avec des shebangs externes (comme les scripts Python pointant vers `/opt/homebrew/bin/python`) seront automatiquement exécutés via des interpréteurs système lorsqu'ils seront copiés dans le bundle. La version MAS peut encore avoir des difficultés à exécuter des binaires qui sont en réalité des scripts Python ou Ruby au lieu de fichiers binaires.

**Important** : Vous devrez recopier les fichiers binaires après chaque mise à jour de l'application, car les mises à jour remplacent l'ensemble du package.

#### Utilisation de scripts intégrés

Au lieu d'exécuter des commandes externes, vous pouvez utiliser l'action **Exécuter le script intégré** dans les règles personnalisées. Cela vous permet d'écrire des scripts directement dans l'éditeur de code de Marked, qui peut accéder aux interpréteurs système disponibles dans le bac à sable.

## Passage à la version sans bac à sable [crossgrade]

Si vous avez fréquemment besoin d'utiliser des binaires externes ou si vous rencontrez d'autres limitations du sandboxing, vous souhaiterez peut-être passer à la version sans sandbox de Marked. La version sans bac à sable n'a pas de telles restrictions et peut exécuter n'importe quel outil ou script de ligne de commande que vous avez installé.

### Pour les utilisateurs abonnés

Si vous disposez d'un abonnement actif au Mac App Store :

1. **Annulez votre abonnement MAS** dans Paramètres système → Identifiant Apple → Médias et achats → Abonnements
2. **Téléchargez l'essai gratuit** à partir de [https://markedapp.com](https://markedapp.com)
3. **Démarrez un abonnement Paddle** directement via l'application ou le site Web

La version Paddle offre les mêmes fonctionnalités sans restrictions de sandboxing.

### Pour les détenteurs de déverrouillage permanent

Si vous avez acheté une licence de déverrouillage permanent ou à vie via le Mac App Store, veuillez [envoyer un e-mail au développeur](mailto:marked@brettterpstra.com?subject=Marked%20License%20Crossgrade&body=S'il vous plaît%20include%20your%20UUID%20%28Help-%3ECopy%20UUID%20in%20Marked%29%20in%20this%20email%20for%20receipt%20verification.) pour demander une licence Paddle gratuite à vie.

**Important** : Pour vérifier votre achat, veuillez inclure l'un des éléments suivants dans votre e-mail :

- Votre **identifiant utilisateur** (UUID) - utilisez **Aide->Copier l'UUID** pour le copier dans votre presse-papiers, puis collez-le dans votre courrier électronique
- Votre **ID de transaction** provenant de votre reçu App Store (vous pouvez le trouver dans votre historique d'achats dans l'application App Store)

Le Mac App Store ne fournit pas votre adresse e-mail aux développeurs, nous vérifions donc les achats à l'aide des identifiants de transaction ou des identifiants d'utilisateur stockés sur notre serveur. L’inclusion de ces informations nous aidera à vérifier rapidement votre achat et à générer votre licence Paddle gratuite.

### Version de l'application

Alternativement, si vous disposez d'un abonnement Setapp, vous pouvez utiliser la version Setapp de Marked, qui est également sans bac à sable et dispose d'un accès complet aux ressources système.

## Ressources supplémentaires

Pour plus d'informations sur les processeurs personnalisés et leurs capacités, voir [Processeur personnalisé](Custom_Processor.html).