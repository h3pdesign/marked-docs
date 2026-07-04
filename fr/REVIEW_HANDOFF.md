# Marked Help — review handoff (fr)

**Locale:** French (`fr`)  
**Generated:** 2026-07-03  
**Status:** Machine-translated drafts — human review required

This package is ready for post-editing. Work in the `fr/` folder on a
`translate/fr` (or `locale/fr`) branch; open one pull request per locale.

---

## What you received

| Item | Location |
|------|----------|
| Topic pages (MT drafts) | `fr/*.md` (117 files) |
| Help index metadata | `fr/config.yaml` |
| Style guide | `fr/SYNTAX.md` |
| Term glossary | `fr/GLOSSARY.md` |
| Menu path reference | `fr/APPMENU.md` |
| App UI strings (read-only reference) | `ui-strings/fr-ui-review.marked-l10n` |
| Screenshot folder (optional) | `fr/images/` (mirror English paths) |

- **English master:** `content/` at repo root (do not edit for locale work)
- **MT banner:** 115 pages still contain `<!-- MT-DRAFT: machine translation; human review required -->` — remove it when a page is reviewed

---

## Read first (30 minutes)

1. Root [`README.md`](../README.md) — tags, links, workflow
2. [`SYNTAX.md`](SYNTAX.md) — Spanish tone, pitfalls, checklist
3. [`GLOSSARY.md`](GLOSSARY.md) — agreed EN → French terms
4. [`APPMENU.md`](APPMENU.md) — `{% appmenu %}` paths vs the localized app
5. [`ui-strings/fr-ui-review.marked-l10n`](../ui-strings/fr-ui-review.marked-l10n) — Settings/menus wording to match

---

## Review priorities

### Priority 1 — high-traffic pages

Fix menus and Settings terminology first, then polish prose:

- `Overview.md`, `Live_Markdown_Preview_on_Mac.md`, `Opening_Files.md`
- `Settings_General.md`, `Settings_Preview.md`, `Settings_Export.md`, `Settings_Proofing.md`
- `Keyboard_Shortcuts.md`, `Exporting.md`, `Document_Navigation.md`

### Priority 2 — `config.yaml`

Edit in place under `fr/config.yaml`:

- `Title`, `MetaDescriptions`, section `title`, `folder` slugs
- Page `title`, `sidebar_title`, `description`
- `keywords` and `wiki_keywords` — rewrite for Spanish search; do not copy English phrases blindly
- **Never change** `file:` keys (English basenames) or build paths (`TargetProject`, `WebHelpBaseURL`, …)

### Priority 3 — integration pages

Editor/app pages (`VS_Code.md`, `Obsidian.md`, `Scrivener_Support.md`, …) — verify product names stay English.

### Priority 4 — spec / reference pages

Syntax spec pages (`CommonMark_Spec.md`, `Kramdown_Spec.md`, …) — keep code blocks intact; translate descriptions only.

---

## Leave unchanged

| Keep as-is | Examples |
|------------|----------|
| Topic filenames | `Exporting.md`, not translated names |
| Link targets | `Page.html`, `#anchors`, `https://…`, `x-marked-3://…` |
| Liquid tags | `{% prefspane General %}`, `{% kbd shift cmd P %}` |
| Shortcut tokens | `{{cmd}}`, `{{opt}}`, `{{shift}}` |
| `config.yaml` `file:` keys | `Overview`, `Settings_General`, … |
| Image paths in Markdown | `images/screenshots/…` |

---

## Fix carefully after MT

1. **`{% appmenu File, Export %}`** — each segment must match `MainMenu.strings` (see `APPMENU.md`)
2. **Settings panes in prose** — align with localized `Settings.strings` / `Preferences.strings`
3. **Reference links** — one `[label]: url` definition per line
4. **Syntax examples** — use Spanish demo words (`*cursiva*`, `**negrita**`) where the English source uses *italics* / **bold**
5. **`wiki_keywords`** — short phrases users might type; must not collide across pages (see root README)

---

## Suggested section order

### Commencer (`Commencer/`)

- [✓] **Aperçu** — `Overview.md`
- [✓] **Aperçu du Markdown en direct sur Mac** — `Live_Markdown_Preview_on_Mac.md`
- [✓] **Quoi de neuf** — `Whats_New.md`
- [✓] **Ouverture de fichiers** — `Opening_Files.md`
- [✓] **Utiliser les extensions du navigateur** — `Using_the_Browser_Extensions.md`
- [✓] **Ouverture rapide** — `Quick_Open.md`
- [✓] **Actions rapides** — `Quick_Actions.md`
- [✓] **Choisir un processeur** — `Choosing_a_Processor.md`
- [✓] **Aperçu** — `Previewing.md`
- [✓] **Fonctionnalités de l'interface** — `Interface_Features.md`
- [✓] **Exportation** — `Exporting.md`

### Comparaisons et FAQ (`Comparaisons_FAQ/`)

- [✓] **Aperçu marqué vs obsidienne** — `Marked_vs_Obsidian_Preview.md`
- [✓] **FAQ sur l'aperçu Markdown** — `Markdown_Preview_FAQ.md`

### Fonctionnalités de lecture (`Lecture_Fonctionnalités/`)

- [✓] **Navigation dans les documents** — `Document_Navigation.md`
- [✓] **Navigation dans les wikis** — `Wiki_Navigation.md`
- [✓] **Aperçu de Zoom** — `Zoom_Overview.md`
- [✓] **Défilement automatique** — `Autoscroll.md`
- [✓] **Lecture rapide** — `Speed_Reading.md`
- [✓] **Renseignez-vous sur le document** — `AI_Ask_About_Document.md`

### Fonctionnalités d'écriture (`Juste_pour_les_écrivains/`)

- [✓] **Mise en page et typographie** — `Layout_and_Typography.md`
- [✓] **Statistiques des documents** — `Document_Statistics.md`
- [✓] **Documents multi-fichiers** — `Multi-File_Documents.md`
- [✓] **Fontaine pour les scénaristes** — `Fountain_for_Screenwriters.md`
- [✓] **Mise en évidence des mots clés** — `Keyword_Highlighting.md`
- [✓] **Orthographe et grammaire** — `Spelling_Grammar.md`
- [✓] **Balisage critique** — `CriticMarkup.md`
- [✓] **MathJax** — `MathJax.md`
- [—] **Travailler avec DOCX** — `Working_with_DOCX.md`
- [✓] **Exportation HTML** — `HTML_Export.md`
- [✓] **Exportation EPUB** — `EPUB_Export.md`
- [✓] **Prise en charge RTF et RTFD** — `RTF_Support.md`
- [✓] **Importation et exportation PDF** — `PDF_Support.md`
- [✓] **Variantes d'images** — `Image_Variants.md`
- [✓] **Validation du lien** — `Link_Validation.md`
- [✓] **Commentaires et annotations** — `Comments_and_Annotations.md`
- [✓] **Fonctionnalités pour les codeurs** — `Features_For_Coders.md`
- [✓] **Utilisation de Marked with Agentic Coding** — `Using_Marked_with_Agentic_Coding.md`

### Applications prises en charge (`Applications_prises en charge/`)

- [✓] **Ours** — `Bear.md`
- [✓] **Curio** — `Curio.md`
- [✓] **DEVONpense** — `DEVONthink.md`
- [✓] **Brouillons** — `Drafts.md`
- [✓] **Surveillance de dossiers** — `Folder_Watching.md`
- [✓] **Montagnes** — `Highland.md`
- [✓] **Crochet** — `Hookmark.md`
- [✓] **iA Rédacteur** — `iA_Writer.md`
- [✓] **iPenséesX** — `iThoughtsX.md`
- [✓] **Mars** — `MarsEdit.md`
- [✓] **Noeud mental** — `MindNode.md`
- [✓] **Compositeur MultiMarkdown** — `MultiMarkdown_Composer.md`
- [✓] **nvUltra** — `nvUltra.md`
- [✓] **Obsidienne** — `Obsidian.md`
- [✓] **OmniOutliner et OPML** — `OmniOutliner_and_OPML.md`
- [✓] **Prise en charge de Scrivener 3** — `Scrivener_Support.md`
- [✓] **Les archives** — `The_Archive.md`
- [✓] **Ulysse** — `Ulysses.md`
- [✓] **Vim** — `Vim.md`
- [✓] **Code VS** — `VS_Code.md`
- [✓] **VoodooPad** — `VoodooPad.md`
- [✓] **Terrains de jeux Xcode** — `Xcode_Playgrounds.md`
- [✓] **Prise en charge DocC** — `DocC_Support.md`
- [✓] **Intégrations d'applications supplémentaires** — `Additional_Application_Support.md`

### Fonctionnalités avancées (`Fonctionnalités_spéciales/`)

- [✓] **Styles personnalisés** — `Custom_Styles.md`
- [✓] **Création de styles personnalisés** — `Writing_Custom_CSS.md`
- [✓] **Générateur de styles personnalisés** — `Custom_Style_Generator.md`
- [✓] **Gestionnaire de styles** — `Style_Manager.md`
- [✓] **Voleur de style** — `Style_Stealer.md`
- [✓] **Démarqueur** — `Markdownifier.md`
- [✓] **Processeur personnalisé** — `Custom_Processor.md`
- [✓] **Restrictions du bac à sable** — `Sandbox_Restrictions.md`
- [✓] **Paramètres par document** — `Per-Document_Settings.md`
- [✓] **Syntaxe spéciale marquée** — `Special_Syntax.md`
- [✓] **Création de tableaux à l'aide de fichiers CSV** — `Creating_Tables_using_CSV_files.md`
- [✓] **Intégration de cartes mentales et de plans** — `Embedding_Mind_Maps_and_Outlines.md`
- [✓] **Raccourcis clavier** — `Keyboard_Shortcuts.md`
- [✓] **Intégration du flux de travail** — `Workflow_Integration.md`
- [✓] **Gestionnaire d'URL** — `URL_Handler.md`
- [✓] **Prise en charge d'AppleScript** — `AppleScript_Support.md`
- [✓] **Utilitaire de ligne de commande** — `Command_Line_Utility.md`
- [✓] **Aperçu en streaming** — `Streaming_Preview.md`
- [✓] **Paramètres spécifiques au HTML** — `HTML_Specific_Settings.md`
- [✓] **Intégration de JavaScript** — `Embedding_Scripts.md`
- [—] **Documentation sur l'API JavaScript** — `.md`

### Paramètres (`Paramètres/`)

- [✓] **Paramètres : Général** — `Settings_General.md`
- [✓] **Paramètres : Aperçu** — `Settings_Preview.md`
- [✓] **Paramètres : Style** — `Settings_Style.md`
- [✓] **Paramètres : Processeur** — `Settings_Processor.md`
- [✓] **Paramètres : Applications** — `Settings_Apps.md`
- [✓] **Paramètres : Vérification** — `Settings_Proofing.md`
- [✓] **Paramètres : Exporter** — `Settings_Export.md`
- [✓] **Paramètres : Avancé** — `Settings_Advanced.md`

### Dépannage (`Dépannage/`)

- [✓] **Aperçu non mis à jour** — `Preview_doesn_t_update_when_file_is_saved.md`
- [✓] **Performance globale** — `Overall_Performance.md`
- [✓] **Débogage** — `Troubleshooting.md`
- [✓] **Aide supplémentaire** — `Additional_Help.md`

### À propos de la démarque (`À propos_Markdown/`)

- [✓] **Sélection du processeur** — `Processor_Selection.md`
- [✓] **Présentation de la démarque** — `Markdown_Tutorial.md`
- [✓] **Démarquage Dingus** — `Markdown_Dingus.md`
- [✓] **Spécification MultiMarkdown v5** — `MultiMarkdown_v5_Spec.md`
- [✓] **Spécification CommonMark** — `CommonMark_Spec.md`
- [✓] **Spécification Kramdown** — `Kramdown_Spec.md`
- [✓] **Remise Spécification GFM** — `Discount_GFM_Spec.md`

### Crédits (`Crédits/`)

- [✓] **Crédits** — `Credits.md`
- [✓] **Licence MultiMarkdown** — `MultiMarkdown_License.md`
- [✓] **Licence à prix réduit** — `Discount_License.md`
- [✓] **Licence Kramdown** — `Kramdown_License.md`
- [✓] **Licence CommonMark** — `CommonMark_License.md`
- [✓] **Licence pdf22md** — `PDF22MD_License.md`

---

## Before you open a PR

- [ ] `{% appmenu %}` paths checked against the localized Marked app
- [ ] Terms match `GLOSSARY.md`; new recurring terms added there
- [ ] `config.yaml` keywords/wiki_keywords reviewed for this locale
- [ ] Link targets and `{% … %}` tags unchanged
- [ ] MT banner removed from pages you finished reviewing
- [ ] Branch contains **only** `fr/` (and `ui-strings/` if UI wording changed)

Mention **@ttscoff** in the PR if you also edited `ui-strings/` (app string merge is separate from help).

---

## Maintainer commands (reference)

```bash
python3 HelpDocs/content/scripts/bootstrap_locales.py fr
python3 HelpDocs/content/scripts/machine_translate_help.py --locale fr
python3 HelpDocs/content/scripts/generate_help_review_handoff.py fr
```
