# <%= @title %> [toc]

## Le code de licence a déjà été utilisé [license_code_has_already_been_utilized]

Si vous effectuez une nouvelle installation de Marked 2 et recevez l'erreur « License code has already been utilized » lors de la saisie de votre licence, veuillez <a href="mailto:me@brettterpstra.com">me contacter</a> pour demander une nouvelle licence. **Veuillez inclure l'adresse e-mail sous laquelle vous vous êtes inscrit et/ou votre code de licence actuel.**

Les premières licences générées pour Marked avaient une limite d'utilisation au lieu d'une limite de machine, si bien que 3 installations, même sur la même machine, épuisaient les activations. Ces limites ont été corrigées dans les licences générées plus récemment. L'achat d'une licence Marked 2 vous permet de l'installer sur n'importe quelle machine que vous possédez, alors n'hésitez pas à demander un remplacement si vous rencontrez des problèmes.

[Table des matières](#toc)

## Licences de site et remises éducatives [site_licenses_and_educational_discounts]

Des licences de site/en gros à prix réduit sont disponibles pour Marked 2. Pour demander un lien d'achat, veuillez contacter <a href="mailto:me@brettterpstra.com">Brett</a> et spécifier le nombre de licences que vous souhaitez acheter.

**Réductions**

- 5-9 : **10 % de réduction**
- 10-19 : **12 % de réduction**
- 20-49 : **15 % de réduction**
- 50+ : **20 % de réduction**

Une remise éducative est également disponible pour les versions directe et Mac App Store. Pour le Mac App Store, les remises éducatives Apple standard sont activées. Pour acheter une version directe avec une réduction éducative, <a href="mailto:me@brettterpstra.com">contactez-moi</a> et demandez un coupon.

[Table des matières](#toc)

## Une URL ne sera pas validée ou renvoie « Inconnu » [a_url_wont_validate_or_returns_unknown]

La [validation du lien](http://marked2app.com/help/Link_Validation.html) de Marked utilise une requête HEAD de base pour déterminer si un lien est valide. Tout résultat autre qu'un résultat 200 (succès) donnera soit un « inconnu », soit une erreur s'il s'agit d'un code d'erreur courant tel que 404 (introuvable) ou 500 (erreur de serveur). Les URL derrière l'authentification (telles que les URL des développeurs Apple ou tout ce qui nécessite une connexion pour y accéder) renverront un « inconnu », tout comme certains sites tels qu'Amazon.com où le serveur renvoie des codes de réponse bizarres. Marked ne peut pas faire grand-chose à ce sujet.

[Table des matières](#toc)

## Autorisations de processeur personnalisées dans la version MAS [custom_processor_permissions_in_mas_version]

En raison des restrictions du sandboxing, la version Mac App Store de Marked 2 n'est pas en mesure d'exécuter certains types d'outils binaires en tant que processeurs personnalisés. Si vous rencontrez cette limitation, vous pouvez essayer quelques étapes.

1. Assurez-vous d'être allé dans les préférences **Marked 2** (⌘,), dans le volet **Avancé** et d'avoir cliqué sur « Mettre à jour les autorisations ». Cela tentera d'accorder à Marked un accès à l'intégralité de votre lecteur par défaut, résolvant ainsi les problèmes liés aux scripts et aux utilitaires qui doivent accéder aux dossiers temporaires et aux emplacements non par défaut.
2. Essayez d'utiliser un script. Référencez l'utilitaire que vous souhaitez exécuter (multimarkdown, kramdown, etc.) dans un script shell. Il peut s'agir d'un script bash, Ruby, Perl ou Python. Définissez ensuite le processeur dans les préférences avancées sur le shell ou l'exécutable associé, et les paramètres sur l'emplacement du script. Par exemple, je peux créer un script bash enregistré dans ~/scripts/mmd_wrapper.sh :
    
        #!/bin/bash
        cat | /usr/local/bin/multimarkdown
    
    Rendez-le ensuite exécutable (`chmod a+x ~/scripts/mmd_wrapper.sh`) et configurez vos préférences de processeur personnalisé :

        Processeur : /bin/bash
        Arguments : /Users/me/scripts/mmd_wrapper.sh
3. Certains exécutables (en particulier Pandoc) ne fonctionneront tout simplement pas dans le sandboxing. Dans ce cas, veuillez me contacter via la fenêtre d'erreur qui apparaît lors de l'exécution pour recevoir une licence crossgrade vers la version directe.

[Table des matières](#toc)

## Liens intra-document dans les PDF exportés [intra-document_links_in_exported_pdfs]

L'exportation PDF de Marked utilise actuellement les fonctionnalités d'impression de WebKit. Une conséquence de ceci est que les liens intra-document (internes), y compris ceux d'une table des matières, ne mèneront pas à d'autres points du document. Cela ne semble pas être quelque chose qu'Apple a l'intention de corriger dans la version de WebKit utilisée par Marked 2.

Dans certains cas, vous pouvez obtenir de bons résultats en exportant du HTML avec un style intégré, puis en utilisant votre navigateur Web pour imprimer au format PDF. Vous n'obtiendrez pas toutes les fonctionnalités d'exportation de Marked, mais vous obtiendrez généralement un PDF avec des liens internes fonctionnels. C'est un compromis pour l'instant.

[Table des matières](#toc)

## Chemins relatifs dans les fichiers inclus [relative_paths_in_included_files]

Les fichiers inclus à l'aide de la [syntaxe include][include] de Marked, ainsi que les [fichiers Scrivener][scriv], peuvent utiliser des chemins relatifs pour référencer d'autres fichiers. (_**Remarque :** cela ne s'applique pas aux fichiers inclus à l'aide de la syntaxe `/file` d'iA Writer ou des fichiers CSV_). Depuis les versions récentes (2.5.10+), ces chemins sont _relatifs au fichier inclus_, et non au fichier de base.

Étant donné une structure de fichiers/dossiers comme celle-ci :

    - base_file.md
    - subfolder
        - included_file.md
    - images
        - image1.jpg

Si `included_file.md` fait référence à image1.jpg via un chemin relatif, il doit être écrit comme `../images/image1.jpg`, _et non_ `images/image1.jpg`. (`..` indique le répertoire parent.)

[include]: http://marked2app.com/help/Multi-File_Documents.html
[scriv]: http://marked2app.com/help/Scrivener_Support.html

[Table des matières](#toc)

## Comment récupérer une licence perdue (version directe) [how_do_i_retrieve_a_lost_license_direct_version]

Si vous avez perdu une licence que vous avez achetée pour Marked 2 via Paddle, vous pouvez la récupérer sur [my.paddle.com](https://my.paddle.com/). Si vous rencontrez des difficultés pour vous connecter, vous pouvez demander une recherche via une demande privée sur le [site d'assistance](http://support.markedapp.com).

[Table des matières](#toc)

## Problèmes d'achat via l'application (Error Domain=Paddle Code=0 "(null)") [in-app_purchase_issues_error_domainpaddle_code0_null]

Paddle m'a récemment informé que les IAP étaient défectueux et qu'ils n'avaient pas l'intention de les réparer car trop peu de développeurs les avaient implémentés. (Ce qui est aussi frustrant pour moi que pour vous.) Ce qui est vraiment frustrant, c'est qu'ils n'ont pas cessé d'autoriser les paiements. Je dois donc rembourser manuellement les achats jusqu'à ce que quelque chose soit fait concernant la façon dont les licences sont gérées. Un nouveau système est censé être déployé dans les prochaines semaines, donc si vous êtes prêt à attendre, je ferai tout ce que je peux pour m'assurer que tous les achats actuels de l'IAP Orthographe/Grammaire soient honorés, quel que soit le système fourni ensuite.

Si vous préférez un remboursement, il vous suffit de <a href="mailto:me@brettterpstra.com">m'envoyer un e-mail directement</a> avec le compte de messagerie utilisé pour la licence ou l'ID de transaction figurant sur le reçu.

**Mise à jour :** Paddle a officiellement annoncé la nouvelle solution IAP, et elle sera mise en œuvre dès qu'elle sera disponible publiquement. Les licences d'achat in-app actuelles (orthographe/grammaire) seront automatiquement migrées et un nouveau code promo sera fourni. Cela devrait arriver bientôt.

[Table des matières](#toc)

## Blocs de code clôturés à l'intérieur de blocs de code indentés [fenced_code_blocks_inside_indented_code_blocks]

Dans des circonstances assez rares, vous souhaiterez peut-être afficher les clôtures d'un bloc de code clôturé. Normalement, cela pourrait être accompli dans Markdown en indentant le code clôturé, forçant ainsi un bloc « verbatim » indenté contenant le bloc de code clôturé, qui ne serait alors pas traité. Marked gère le code clôturé différemment (dans le cadre de sa capacité à fonctionner avec plusieurs options de syntaxe), donc pour ce faire, vous devez utiliser une double clôture. Comme vous pouvez utiliser n'importe quel nombre de backticks ou de tildes pour clôturer un bloc de code (à condition que le nombre d'ouverture et de fermeture correspondent), vous pouvez simplement utiliser deux clôtures de longueur différente. Par exemple :

    `````
    ```
    Actual fenced code
    ```
    `````

[Table des matières](#toc)
