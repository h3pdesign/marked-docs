<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

## Blocs de code clôturés

Les blocs de code clôturés sont activés par défaut dans les deux processeurs inclus (MultiMarkdown et Discount). Les blocs de code clôturés sont délimités par au moins trois tildes (~) ou backticks (\`). Vous pouvez en utiliser plus de trois, mais les délimiteurs de début et de fin doivent avoir exactement le même nombre de caractères.

    ~~~~
    Du code à rendre sous forme de bloc pré/code
    ~~~~

Les langues peuvent être spécifiées en utilisant le titre de la langue (ou le titre abrégé) après le délimiteur de la première ligne, ou entre accolades (avec ou sans point) après le dernier délimiteur. Par exemple :

    ~~~~~rubis
    du code Ruby
    ~~~~~

Rendu comme suit :

    <pre><code class="ruby">du code Ruby</code></pre>


Ou avec des backticks :

    `````
    du code Java
    `````{.java}

Marked peut détecter à la fois les spécifications linguistiques Markdown Extra/Python Markdown (`{.lang}` après la clôture) et Discount (`lang` après la première clôture). Ce qui suit (format Discount) créerait le même résultat que ci-dessus (format Python Markdown) :

    `````java
    du code Java
    `````


Marked gère également les blocs de code clôturés en retrait afin que vous puissiez les utiliser dans des listes imbriquées.

La coloration syntaxique intégrée reconnaîtra **256** spécificateurs de langue (voir [Langues prises en charge](#supported-linguals) ci-dessous). Si aucune langue n'est spécifiée, il la détectera automatiquement, elle n'est donc pas requise pour l'aperçu. La chaîne de langue donnée sera affichée dans le code HTML final en tant que classe sur la balise `<code>`.

Consultez la section sur [Syntaxe spéciale marquée](Special_Syntax.html#includingcode) pour savoir comment inclure des fichiers de code externes dans votre document.

## Mise en évidence de la syntaxe

![Surlignage automatique de la syntaxe][surligner]

[highlight]: images/screenshots/mainwindow-feature-code-crop.jpg @2x width=564px height=188px class=center

La mise en évidence de la syntaxe peut être activée dans le {% prefspane Style %}. Il reconnaîtra les blocs de code, détectera la langue et affichera une sortie codée par couleur dans l'aperçu. Plusieurs thèmes sont disponibles, sélectionnés dans la liste déroulante située sous l'option dans les paramètres. Le thème sélectionné s'appliquera à tous les documents.

Marked utilise [highlight.js](https://highlightjs.org/) pour fournir un codage couleur cohérent pour tous les types de code intégré, y compris les syntaxes Markdown standard qui ne permettent pas de spécifier la langue. Highlight.js se détecte bien automatiquement. Il existe quelques différences de rendu mineures entre celui-ci et les coloriseurs tels que Pygments (style GitHub), mais le résultat est similaire. L'utilisation du thème github.css sur le code Ruby, par exemple, donne presque exactement le résultat que vous verriez sur GitHub.

> *La feuille de style GitHub fournit des styles de sauvegarde pour les blocs rendus avec Pygments. Si la balise `<pre>` se trouve à l'intérieur d'un div avec la classe "highlight", elle s'affichera en utilisant le style standard de GitHub, et non celui de Marked. Vous pouvez restituer le code en externe et coller du HTML, ou utiliser `pygmentize` pour le restituer dans des fichiers HTML et les inclure avec la [`<<(source.html)` syntaxe](Special_Syntax.html#includingcode)*.

L'option « Uniquement si la langue est spécifiée » à droite du sélecteur de style de syntaxe s'applique aux blocs de code isolés. Si elle est activée, la coloration syntaxique ne sera appliquée qu'aux blocs de code avec un spécificateur de langage après la clôture d'ouverture, par ex.

    ```js
    coder
    ```

La mise en évidence de la syntaxe apparaîtra dans l'aperçu et lors de l'impression et de l'exportation PDF. Si elle est activée dans les paramètres et que le thème est inclus lors de l'exportation HTML, la bibliothèque highlight.js utilisée par Marked sera intégrée dans la sortie HTML, permettant à votre HTML exporté d'apparaître comme il le fait dans Marked.

### Langues prises en charge

Marqué est livré avec **highlight.js 11.11.1**, y compris toutes les langues principales ainsi que les grammaires tierces de la liste [langues prises en charge par highlight.js](https://highlightjs.readthedocs.io/en/latest/supported-languages.html). Spécifiez n'importe quel nom de langue principale ci-dessous (ou un alias documenté tel que `js` pour JavaScript) après la clôture d'ouverture.

Deux langages répertoriés sur le site highlight.js ne sont pas inclus dans le bundle de Marked : **Pine Script** (package en amont indisponible) et **Supercollider** (incompatible avec highlight.js 11).

    1c, 4d, GN, abap, abnf, accesslog, actionscript, ada, alan, angelscript, apache, apex,
    applescript, arcade, arduino, armasm, asciidoc, aspectj, autohotkey, autoit, avrasm, awk,
    axapta, ballerine, bash, basique, bbcode, lame, bnf, bqn, brainfuck, c, c3, cal, capnproto,
    ceylan, chaos, chapelle, cisco, nettoyer, clojure, clojure-repl, cmake, cobol, coffeescript,
    coq, cos, cpc, cpp, crmsh, crystal, csharp, cshtml-razor, csp, css, curl, cypher, d, dafny,
    dart, delphi, diff, django, dns, dockerfile, dos, dsconfig, dts, poussière, dylan, ebnf, élixir,
    orme, erb, erlang, erlang-repl, excel, improviser, réparer, flix, fortran, fsharp, func, gams,
    gauss, gcode, gdscript, gf, cornichon, lueur, glsl, gml, aller, golo, gradle, graphql, groovy,
    gsql, haml, guidons, haskell, haxe, hlsl, hsp, http, hy, inform7, ini, iptables, irpf90,
    isbl, java, javascript, jboss-cli, jolie, json, julia, julia-repl, kotlin, lang, lasso,
    latex, ldif, feuille, maigre, moins, lisp, livecodeserver, livescript, llvm, lookml, lsl, lua,
    macaulay2, makefile, markdown, mathematica, matlab, maxima, mel, mercure, menthe, mipsasm,
    mirc, mizar, mkb, mlir, mojolicious, singe, moonscript, motoko, n1ql, nestedtext, jamais,
    nginx, nim, nix, node-repl, nsis, oak, objectivec, ocaml, ocl, openscad, oxygène, papyrus,
    parser3, perl, pf, pgsql, php, modèle php, texte brut, poney, powershell, traitement,
    profil, prologue, propriétés, protobuf, marionnette, purebasic, python, python-repl, q, qml,
    qsharp, r, ReasonML, rebol, nervure, riscript, riscvasm, roboconf, robot, routeros,
    fichier de spécification rpm, rsl, ruby, langage de règles, rouille, rvt-script, sas, scala, schéma, scilab, scss,
    sfz, shell, shexc, smali, smalltalk, sml, solidité, spl, sqf, sql, stan, stata, step21,
    texte structuré, stylet, sous-unité, svelte, rapide, taggerscript, tap, tcl, terraform, thrift,
    toit, tp, tsql, brindille, dactylographié, unicorn-rails-log, vala, vba, vbnet, vbscript,
    vbscript-html, verilog, vhdl, vim, wasm, wren, x86asm, x86asmatt, xl, xml, xquery, xsharp,
    yaml, yul, zenscript, zéphir

### Thèmes de mise en évidence de la syntaxe

**239** thèmes de coloration syntaxique sont disponibles dans la liste déroulante {% prefspane Style %}. Les thèmes sont chargés automatiquement à partir des feuilles de style fournies par Marked ; les noms correspondent au nom du fichier CSS sans l'extension (par exemple, `github-dark` charge `github-dark.css`).

Thèmes généraux :

1c-light, a11y-dark, a11y-light, agate, un vieil espoir, androidstudio, arduino-light, arta,
    atome-un-sombre, atome-un-sombre-raisonnable, atome-une-lumière, codepen-embed, brasseur de couleurs, sombre,
    par défaut, fondation, github, github-dark, github-dark-dimmed, googlecode, niveaux de gris,
    hybride, idée, intellij-light, ir-black, isbl-editor-dark, isbl-editor-light, kimbie-dark,
    kimbie-light, mono-blue, monokai, monokai-sublime, oiseau de nuit, nnfx-dark, nnfx-light, nord,
    obsidienne, panda-syntax-dark, panda-syntax-light, paraiso-dark, paraiso-light, pojoaque,
    purebasic, qtcreator-dark, qtcreator-light, arc en ciel, rose-pine, rose-pine-dawn,
    rose-pin-lune, livre scolaire, nuances de violet, srcery, stackoverflow-dark,
    stackoverflow-light, sunburst, tokyo-night-dark, tokyo-night-light, demain-night-blue,
    demain soir-lumineux, vs, vs2015, xcode, xt256

Thèmes Base16 (176 variantes, chacune préfixée par `base16-`) :

base16-3024, base16-apathie, base16-apprenti, base16-ashes, base16-atelier-cave,
    base16-atelier-cave-light, base16-atelier-dune, base16-atelier-dune-light,
    base16-atelier-estuaire, base16-atelier-estuaire-lumière, base16-atelier-forêt,
    base16-atelier-forest-light, base16-atelier-heath, base16-atelier-heath-light,
    base16-atelier-lakeside, base16-atelier-lakeside-light, base16-atelier-plateau,
    base16-atelier-plateau-light, base16-atelier-savanna, base16-atelier-savanna-light,
    base16-atelier-bord de mer, base16-atelier-bord de mer-lumière, base16-atelier-sulphurpool,
    base16-atelier-sulphurpool-light, base16-atlas, base16-bespin, base16-noir-métal,
    base16-black-metal-bathory, base16-black-metal-burzum, base16-black-metal-dark-funeral,
    base16-black-metal-gorgoroth, base16-black-metal-immortel, base16-black-metal-khold,
    base16-black-metal-marduk, base16-black-metal-mayhem, base16-black-metal-nile,
    base16-black-metal-venom, base16-brewer, base16-bright, base16-brogrammer,
    base16-brush-trees, base16-brush-trees-dark, base16-chalk, base16-circus,
    base16-classique-dark, base16-classic-light, base16-codeschool, base16-colors,
    base16-cupcake, base16-cupertino, base16-danqing, base16-darcula, base16-violet foncé,
    base16-darkmoss, base16-darktooth, base16-décaf, base16-default-dark, base16-default-light,
    base16-dirtysea, base16-dracula, base16-edge-dark, base16-edge-light, base16-eighties,
    base16-braises, base16-équilibre-foncé, base16-équilibre-gris-foncé,
    base16-equilibrium-gray-light, base16-equilibrium-light, base16-espresso, base16-eva,
    base16-eva-dim, base16-flat, base16-framer, base16-fruit-soda, base16-gigavolt,
    base16-github, base16-google-dark, base16-google-light, base16-grayscale-dark,
    base16-niveaux de gris-clair, base16-écran vert, base16-gruvbox-dark-hard,
    base16-gruvbox-dark-medium, base16-gruvbox-dark-pâle, base16-gruvbox-dark-soft,
    base16-gruvbox-léger-dur, base16-gruvbox-léger-moyen, base16-gruvbox-light-soft,
    base16-hardcore, base16-harmonic16-dark, base16-harmonic16-light, base16-heetch-dark,
    base16-heetch-light, base16-helios, base16-marelle, base16-horizon-dark,
    base16-horizon-light, base16-humanoïde-dark, base16-humanoïde-light, base16-ia-dark,
    base16-ia-light, base16-icy-dark, base16-ir-noir, base16-isotope, base16-kimber,
    base16-london-tube, base16-macintosh, base16-marrakesh, base16-materia, base16-material,
    base16-material-plus foncé, base16-material-plus clair, base16-material-palenight,
    base16-matériau-vivant, base16-violet-doux, base16-mexique-clair, base16-moka,
    base16-monokai, base16-nébuleuse, base16-nord, base16-nova, base16-océan, base16-océanicnext,
    base16-one-light, base16-onedark, base16-outrun-dark, base16-papercolor-dark,
    base16-papercolor-light, base16-paraiso, base16-pasque, base16-phd, base16-pico,
    base16-pop, base16-porple, base16-qualia, base16-railscasts, base16-rebecca,
    base16-ros-pine, base16-ros-pine-aube, base16-ros-pine-moon, base16-sagelight,
    base16-château de sable, base16-seti-ui, base16-shapeshifter, base16-soie-foncé,
    base16-silk-light, base16-snazzy, base16-solar-flare, base16-solar-flare-light,
    base16-solarisé-dark, base16-solarisé-lumière, base16-spacemacs, base16-summercamp,
    base16-summerfruit-dark, base16-summerfruit-light, base16-synth-minuit-terminal-dark,
    base16-synth-minuit-terminal-light, base16-tango, base16-tender, base16-demain,
    base16-demain-nuit, base16-crépuscule, base16-unikitty-dark, base16-unikitty-light,
    base16-vulcan, base16-windows-10, base16-windows-10-light, base16-windows-95,
    base16-windows-95-light, base16-windows-contraste élevé, base16-windows-high-contraste-light,
    base16-windows-nt, base16-windows-nt-light, base16-woodland, base16-xcode-crépuscule,
    base16-zenburn

## Sauts de ligne GitHub

Marqué peut conserver les sauts de ligne dans vos paragraphes. Sélectionnez simplement le {% prefspane Processor %} et cochez la case pour conserver les sauts de ligne dans les paragraphes.

## Cases à cocher GitHub

Répertoriez les éléments au format :

    - [ ] Tâche inachevée
    - [x] Tâche terminée

apparaîtra dans l'aperçu sous forme d'éléments de case à cocher rendus. Il n’est pas possible d’interagir avec eux, mais leur état reflétera toute modification apportée au document source.

## Emballage du bloc de code

Dans le {% prefspane Style %}, vous trouverez une option sous Mise en page et typographie : "Autoriser les thèmes à envelopper le texte dans des blocs de code." La désactivation de cette option forcera tous les blocs de code à faire défiler le débordement horizontal plutôt que de l'envelopper, quel que soit le style d'aperçu actuel.