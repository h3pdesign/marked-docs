# <%= @title %>

## Eingezäunte Codeblöcke

Abgeschirmte Codeblöcke sind in beiden enthaltenen Prozessoren standardmäßig aktiviert (MultiMarkdown und Discount). Umzäunte Codeblöcke werden durch drei oder mehr Tilden (~) oder Backticks (\`) begrenzt. Sie können mehr als drei verwenden, aber die Anfangs- und Endtrennzeichen müssen genau die gleiche Anzahl von Zeichen haben.

~~~~
    Etwas Code, der als Vor-/Codeblock gerendert werden soll
    ~~~~

Sprachen können mit dem Sprachtitel (oder Kurztitel) nach dem Trennzeichen in der ersten Zeile oder in geschweiften Klammern (mit oder ohne führenden Punkt) nach dem letzten Trennzeichen angegeben werden. Zum Beispiel:

~~~~~Rubin
    etwas Ruby-Code
    ~~~~~

Wird wie folgt gerendert:

<pre><code class="ruby">etwas Ruby-Code</code></pre>


Oder mit Backticks:

`````
    etwas Java-Code
    `````{.java}

Marked kann sowohl die Sprachspezifikationen Markdown Extra/Python Markdown (`{.lang}` nach dem Schließen des Zauns) als auch Rabatt (`lang` nach dem ersten Zaun) erkennen. Das Folgende (Discount-Format) würde zum gleichen Ergebnis führen wie oben (Python Markdown-Format):

    `````java
    some Java code
    `````


Marked verarbeitet auch eingerückte, eingezäunte Codeblöcke, sodass Sie sie in verschachtelten Listen verwenden können.

Die integrierte Syntaxhervorhebung erkennt **256** Sprachspezifizierer (siehe [Supported languages](#supported-languages) unten). Wenn keine Sprache angegeben ist, wird sie automatisch erkannt und ist daher für die Vorschau nicht erforderlich. Die angegebene Sprachzeichenfolge wird im endgültigen HTML als Klasse im Tag `<code>` ausgegeben.

Im Abschnitt [Marked Special Syntax](Special_Syntax.html#includingcode) erfahren Sie, wie Sie externe Codedateien in Ihr Dokument einbinden.

## Syntaxhervorhebung

![Automatic Syntax Highlighting][highlight]

[highlight]: images/screenshots/mainwindow-feature-code-crop.jpg @2x width=564px height=188px class=center

Die Syntaxhervorhebung kann im {% prefspane Style %} aktiviert werden. Es erkennt Codeblöcke, erkennt die Sprache und rendert die farbcodierte Ausgabe in der Vorschau. Es stehen mehrere Themen zur Verfügung, die über das Dropdown-Menü unter der Option in den Einstellungen ausgewählt werden können. Das ausgewählte Thema gilt für alle Dokumente.

Marked verwendet [highlight.js](https://highlightjs.org/), um eine konsistente Farbcodierung für alle Arten von eingebettetem Code bereitzustellen, einschließlich Standard-Markdown-Syntaxen, die keine Angabe einer Sprache zulassen. Highlight.js erkennt gut automatisch. Es gibt einige geringfügige Rendering-Unterschiede zwischen ihm und Kolorierern wie Pygments (GitHub-Stil), aber die Ausgabe ist ähnlich. Wenn Sie beispielsweise das github.css-Design für Ruby-Code verwenden, wird fast genau die Ausgabe gerendert, die Sie auf GitHub sehen würden.

> *Das Stylesheet GitHub bietet Backup-Stile für mit Pygments gerenderte Blöcke. Wenn sich das Tag `<pre>` in einem Div mit der Klasse „highlight“ befindet, wird es im Standardstil GitHub und nicht im Stil von Marked angezeigt. Sie können den Code extern rendern und HTML einfügen oder `pygmentize` verwenden, um ihn in HTML-Dateien zu rendern und diese mit [<!--MKPH2--> syntax](Special_Syntax.html#includingcode)* einzuschließen.

Die Option „Nur wenn Sprache angegeben“ rechts neben der Syntaxstilauswahl gilt für abgeschirmte Codeblöcke. Wenn diese Option aktiviert ist, wird die Syntaxhervorhebung nur auf Codeblöcke mit einem Sprachspezifizierer nach dem Eröffnungszaun angewendet, z. B.

    ```js
    code
    ```

Die Syntaxhervorhebung wird in der Vorschau sowie beim Drucken und PDF-Export angezeigt. Wenn die Option in den Einstellungen aktiviert ist und das Design beim Exportieren von HTML enthalten ist, wird die von Marked verwendete Bibliothek „highlight.js“ in die Ausgabe von HTML eingebettet, sodass Ihr exportiertes HTML genauso angezeigt wird wie in Marked.

### Unterstützte Sprachen

Marked wird mit **highlight.js 11.11.1** geliefert, einschließlich aller Kernsprachen sowie Grammatiken von Drittanbietern aus der [highlight.js supported languages](https://highlightjs.readthedocs.io/en/latest/supported-languages.html)-Liste. Geben Sie unten einen beliebigen primären Sprachnamen (oder einen dokumentierten Alias ​​wie `js` für JavaScript) nach dem Eröffnungszaun an.

Zwei auf der Seite „highlight.js“ aufgeführte Sprachen sind nicht im Bundle von Marked enthalten: **Pine Script** (Upstream-Paket nicht verfügbar) und **Supercollider** (inkompatibel mit highlights.js 11).

1c, 4d, GN, abap, abnf, accesslog, actionscript, ada, alan, angelscript, apache, apex,
    Applescript, Arcade, Arduino, Armasm, Asciidoc, Aspectj, Autohotkey, Autoit, Avrasm, Awk,
    axapta, ballerina, bash, basic, bbcode, klinge, bnf, bqn, brainfuck, c, c3, cal, capnproto,
    ceylon, chaos, kapelle, cisco, clojure, clojure-repl, cmake, cobol, Coffeescript,
    coq, cos, cpc, cpp, crmsh, crystal, csharp, cshtml-razor, csp, css, curl, cypher, d, dafny,
    dart, delphi, diff, django, dns, dockerfile, dos, dsconfig, dts, staub, dylan, ebnf, elixier,
    ulme, erb, erlang, erlang-repl, excel, extempore, fix, flix, fortran, fsharp, func, gams,
    Gauss, Gcode, GDScript, Gf, Gherkin, Glimmer, GLSL, GML, Go, Golo, Gradle, Graphql, Groovy,
    gsql, haml, handlebars, haskell, haxe, hlsl, hsp, http, hy, inform7, ini, iptables, irpf90,
    isbl, java, javascript, jboss-cli, jolie, json, julia, julia-repl, kotlin, lang, lasso,
    Latex, LDIF, Leaf, Lean, Less, Lisp, Livecodeserver, Livescript, llvm, Lookml, LSL, Lua,
    macaulay2, Makefile, Markdown, Mathematica, Matlab, Maxima, Mel, Mercury, Mint, Mipsasm,
    mirc, mizar, mkb, mlir, mojolicious, Monkey, Moonscript, Motoko, n1ql, nestedtext, never,
    Nginx, Nim, Nix, Node-Repl, NSIS, Eiche, Objectivec, Ocaml, OCL, OpenScad, Oxygene, Papyrus,
    parser3, perl, pf, pgsql, php, php-template, klartext, pony, powershell, verarbeitung,
    Profil, Prolog, Eigenschaften, Protobuf, Puppet, Purebasic, Python, Python-Repl, Q, QML,
    qsharp, r, reasonml, rebol, rib, riscript, riscvasm, roboconf, robot, routeros,
    rpm-specfile, rsl, ruby, RulesLanguage, Rust, rvt-script, sas, scala, scheme, scilab, scss,
    sfz, shell, shexc, smali, smalltalk, sml, solidity, spl, sqf, sql, stan, stata, step21,
    strukturierter Text, Stift, Untereinheit, schlank, schnell, Taggerscript, Tippen, TCL, Terraform, Sparsamkeit,
    toit, tp, tsql, twig, typescript, unicorn-rails-log, vala, vba, vbnet, vbscript,
    vbscript-html, verilog, vhdl, vim, wasm, wren, x86asm, x86asmatt, xl, xml, xquery, xsharp,
    Yaml, Yul, Zenscript, Zephir

### Syntaxhervorhebungsthemen

**239** Syntaxhervorhebungsthemen sind im Dropdown-Menü {% prefspane Style %} verfügbar. Themes werden automatisch aus den gebündelten Stylesheets von Marked geladen; Namen stimmen mit dem CSS-Dateinamen ohne Erweiterung überein (z. B. `github-dark` lädt `github-dark.css`).

Allgemeine Themen:

1c-light, a11y-dark, a11y-light, achat, an-old-hoffnung, androidstudio, arduino-light, arta,
    atom-one-dark, atom-one-dark-reasonable, atom-one-light, codepen-embed, color-brewer, dunkel,
    Standard, Stiftung, Github, Github-Dark, Github-Dark-Dimmed, Googlecode, Graustufen,
    hybrid, idee, intellij-light, ir-black, isbl-editor-dark, isbl-editor-light, kimbie-dark,
    kimbie-light, mono-blau, monokai, monokai-sublime, nachteule, nnfx-dark, nnfx-light, nord,
    Obsidian, Panda-Syntax-Dunkel, Panda-Syntax-Licht, Paraiso-Dunkel, Paraiso-Licht, Pojoaque,
    purebasic, qtcreator-dark, qtcreator-light, rainbow, rose-pine, rose-pine-dawn,
    Rose-Pine-Moon, Schulbuch, Shades-of-Lila, Srcery, Stackoverflow-Dark,
    Stackoverflow-Licht, Sunburst, Tokio-Nacht-Dunkel, Tokio-Nachtlicht, Morgen-Nacht-Blau,
    morgen-abend-hell, vs, vs2015, xcode, xt256

Base16-Themen (176 Varianten, jeweils mit dem Präfix `base16-`):

base16-3024, base16-athy, base16-apprentice, base16-ashes, base16-atelier-cave,
    base16-atelier-cave-light, base16-atelier-dune, base16-atelier-dune-light,
    base16-atelier-mündung, base16-atelier-mündung-licht, base16-atelier-wald,
    base16-atelier-forest-light, base16-atelier-heide, base16-atelier-heide-licht,
    base16-atelier-lakeside, base16-atelier-lakeside-light, base16-atelier-plateau,
    base16-atelier-plateau-light, base16-atelier-savanna, base16-atelier-savanna-light,
    base16-atelier-seaside, base16-atelier-seaside-light, base16-atelier-sulphurpool,
    base16-atelier-sulphurpool-light, base16-atlas, base16-bespin, base16-black-metal,
    base16-black-metal-bathory, base16-black-metal-burzum, base16-black-metal-dark-funeral,
    base16-black-metal-gorgoroth, base16-black-metal-immortal, base16-black-metal-khold,
    base16-black-metal-marduk, base16-black-metal-mayhem, base16-black-metal-nile,
    base16-black-metal-venom, base16-brewer, base16-bright, base16-brogrammer,
    base16-brush-trees, base16-brush-trees-dark, base16-chalk, base16-circus,
    base16-classic-dark, base16-classic-light, base16-codeschool, base16-colors,
    base16-cupcake, base16-cupertino, base16-danqing, base16-darcula, base16-dark-violet,
    base16-darkmoss, base16-darktooth, base16-decaf, base16-default-dark, base16-default-light,
    base16-dirtysea, base16-dracula, base16-edge-dark, base16-edge-light, base16-eighties,
    base16-glut, base16-equilibrium-dark, base16-equilibrium-grey-dark,
    base16-equilibrium-gray-light, base16-equilibrium-light, base16-espresso, base16-eva,
    base16-eva-dim, base16-flat, base16-framer, base16-fruit-soda, base16-gigavolt,
    base16-github, base16-google-dark, base16-google-light, base16-grayscale-dark,
    base16-grayscale-light, base16-green-screen, base16-gruvbox-dark-hard,
    base16-gruvbox-dark-medium, base16-gruvbox-dark-pale, base16-gruvbox-dark-soft,
    base16-gruvbox-light-hard, base16-gruvbox-light-medium, base16-gruvbox-light-soft,
    base16-hardcore, base16-harmonic16-dark, base16-harmonic16-light, base16-heetch-dark,
    base16-heetch-light, base16-helios, base16-hopscotch, base16-horizon-dark,
    base16-horizon-light, base16-humanoid-dark, base16-humanoid-light, base16-ia-dark,
    base16-ia-light, base16-icy-dark, base16-ir-black, base16-isotope, base16-kimber,
    base16-london-tube, base16-macintosh, base16-marrakesh, base16-materia, base16-material,
    base16-material-dunkler, base16-material-heller, base16-material-heller,
    base16-material-vivid, base16-mellow-purple, base16-mexico-light, base16-mokka,
    base16-monokai, base16-nebula, base16-nord, base16-nova, base16-ocean, base16-oceanicnext,
    base16-one-light, base16-onedark, base16-outrun-dark, base16-papercolor-dark,
    base16-papercolor-light, base16-paraiso, base16-pasque, base16-phd, base16-pico,
    base16-pop, base16-porple, base16-qualia, base16-railscasts, base16-rebecca,
    base16-ros-pine, base16-ros-pine-dawn, base16-ros-pine-moon, base16-sagelight,
    base16-sandcastle, base16-seti-ui, base16-shapeshifter, base16-silk-dark,
    base16-silk-light, base16-snazzy, base16-solar-flare, base16-solar-flare-light,
    base16-solarized-dark, base16-solarized-light, base16-spacemacs, base16-summercamp,
    base16-summerfruit-dark, base16-summerfruit-light, base16-synth-midnight-terminal-dark,
    base16-synth-midnight-terminal-light, base16-tango, base16-tender, base16-tomorrow,
    base16-morrow-night, base16-twilight, base16-unikitty-dark, base16-unikitty-light,
    base16-vulcan, base16-windows-10, base16-windows-10-light, base16-windows-95,
    base16-windows-95-light, base16-windows-high-contrast, base16-windows-high-contrast-light,
    base16-windows-nt, base16-windows-nt-light, base16-woodland, base16-xcode-dusk,
    base16-zenburn

## GitHub Zeilenumbrüche

Marked kann Zeilenumbrüche in Ihren Absätzen beibehalten. Wählen Sie einfach {% prefspane Processor %} aus und aktivieren Sie das Kontrollkästchen, um Zeilenumbrüche in Absätzen beizubehalten.

## GitHub Kontrollkästchen

Listen Sie Elemente auf, die wie folgt formatiert sind:

- [ ] Unvollendete Aufgabe
    - [x] Aufgabe erledigt

werden in der Vorschau als gerenderte Kontrollkästchenelemente angezeigt. Mit ihnen kann nicht interagiert werden, aber ihr Status spiegelt alle Änderungen im Quelldokument wider.

## Codeblockumbruch

Im {% prefspane Style %} finden Sie unter „Layout und Typografie“ eine Option: „Themen erlauben, Text in Codeblöcke einzuschließen.“ Wenn Sie dies deaktivieren, werden alle Codeblöcke dazu gezwungen, den horizontalen Überlauf zu scrollen, anstatt ihn zu umbrechen, unabhängig vom aktuellen Vorschaustil.