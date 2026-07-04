<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked includes an AppleScript dictionary for automating preview, export, and workflow integration. Vous pouvez ouvrir des documents, contrôler l'aperçu (rechargement, défilement, surlignages, défilement automatique, lecture rapide), lire les statistiques, modifier les processeurs et les styles, copier du HTML ou du RTF dans le presse-papiers et exporter vers la plupart des mêmes formats disponibles dans le menu {% appmenu File, Export %}. **Preview headings / table of contents via AppleScript is work in progress** (see below).

For URL-based automation (shell scripts, `open` commands, and callbacks), see the [URL Handler](URL_Handler.html). AppleScript et le gestionnaire d'URL se complètent : utilisez AppleScript lorsque vous devez cibler un document ou une fenêtre spécifique, et les URL lorsqu'un simple appel `open 'x-marked://...'` suffit.

## Viewing the dictionary

In **Script Editor**, choose **File → Open Dictionary…** and select Marked. Le dictionnaire répertorie les commandes sur les objets **application**, **document** et **window**, ainsi que les commandes d'exportation dans la suite Marked.

On macOS you can browse scripting definitions with **Script Editor**.

## Targeting Marked

Pour l'installation standard :

```applescript
tell application "Marked"
	-- commands here
end tell
```

## Documents and windows

**Application**

- `documents` -- open preview documents (ordered list).
- `windows` -- fenêtres d'aperçu.

**Document**

- `name` -- nom d'affichage.
- `path` -- file path when the document is saved on disk.
- `modified` -- whether the document has unsaved editor changes.
- `processor` -- Markdown processor for this preview (read/write). Valid names: `MultiMarkdown`, `Discount`, `CommonMark (GFM)`, `Kramdown`. Setting `processor` applies a per-document override and reloads the preview; cela ne change pas la valeur par défaut globale dans {% prefspane Processor %}.
- `preprocessor` -- preprocessor for this preview (read/write). Use `true` or `false` to enable or disable the custom preprocessor, or a preprocessor name when applicable.
- `source text` -- raw Markdown source (read-only).
- `critic markup mode` -- whether CriticMarkup processing is enabled (read/write). Le modifier recharge l’aperçu.
- `is autoscrolling` -- whether autoscroll is active (read-only).
- `is speed reading` -- whether speed read mode is active (read-only).
- Commandes de prévisualisation, de lecture, de statistiques et d'exportation (voir ci-dessous).

**Window**

- `document` -- the `MarkdownDocument` shown in that window.
- `style` -- current preview style name (read/write). Setting `style` reloads the preview with the chosen theme (same as picking a style from the preview style menu).
- `close`, `save`, `print` -- standard window commands.
- The same preview, reader, statistics, and export commands as on documents (forwarded to the window's document).

Prefer `tell document 1` or `tell window 1's document` when exporting a specific preview. Export commands on the application use the key window or current document when no receiver is specified.

### Example: open and read path

```applescript
tell application "Marked"
	open POSIX file "/Users/you/Documents/report.md"
	set docPath to path of document 1
end tell
```

### Exemple : modifier le style d'aperçu

```applescript
tell application "Marked"
	tell window 1
		set style to "Amblin"
	end tell
end tell
```

Style names match the preview style menu (display name, CSS resource name such as `swiss`, or internal identifier). Custom styles you added in the Style Manager are supported.

Use **`get preview style names`** on the application object to list enabled style display names.

### Exemple : processeur et texte source

```applescript
tell application "Marked"
	tell document 1
		set processor to "Kramdown"
		set md to source text
		set critic markup mode to true
	end tell
end tell
```

## Application commands

These commands apply to the **application** object (not a specific document).

| Command | Description |
| --- | --- |
| `open streaming preview` | Ouvrez une fenêtre [aperçu du presse-papiers en streaming](Streaming_Preview.html). |
| `preview clipboard` | Open a [clipboard preview](Opening_Files.html) of the current clipboard contents (same as {% appmenu File, New, Clipboard Preview ({{shift}}{{cmd}}V) %}). |
| `close all` | Fermez tous les documents d'aperçu ouverts (pas d'invite de sauvegarde ; Marqué ne modifie pas les fichiers source). |
| `get available processors` | Liste des noms de processeur : `MultiMarkdown`, `Discount`, `CommonMark (GFM)`, `Kramdown`. |
| `get preview style names` | List enabled preview style display names. |
| `get_available_formats` | List supported `convert_to` format names. |
| `get_available_profiles` | Répertoriez les noms des profils d'exportation (identiques à la propriété `profiles`). |

Bring Marked to the front with the standard AppleScript **`activate`** command:

```applescript
tell application "Marked"
	activate
	open streaming preview
end tell
```

## Preview control

Available on **document** and **window**. Most of these require a loaded preview WebView.

| Command | Parameters | Description |
| --- | --- | --- |
| `refresh preview` | — | Rechargez l'aperçu à partir du fichier source (identique à {% appmenu Preview, Refresh %}). |
| `reveal in finder` | — | Révélez le fichier du document dans le Finder. |
| `show highlights` | — | Activez la mise en évidence des mots clés (évitez les mots, les substituts, la voix passive, les listes personnalisées). |
| `full screen` | optional `enabled` boolean | Entrez, quittez ou basculez en mode aperçu plein écran. |
| `scroll to heading` | `title` or `id` | Scroll to a heading by visible title text or DOM `id`. |
| `scroll to position` | `percent` or `line` | Faites défiler par pourcentage de la hauteur du document ou par numéro de ligne approximatif. |
| `copy html` | — | Copiez l'aperçu HTML dans le presse-papiers (menu d'engrenage ou {% kbd shift cmd C %} ; voir [Copier HTML](Exporting.html#copyhtml)). |
| `copy rtf` | — | Copy rich text to the clipboard. |

```applescript
tell application "Marked"
	tell document 1
		refresh preview
		show highlights
		scroll to heading id "introduction"
		scroll to position percent 50
		full screen with enabled true
	end tell
end tell
```

## Autoscroll and speed read

| Command | Description |
| --- | --- |
| `autoscroll` | Start autoscroll. Optional `wpm` integer sets words per minute before starting. |
| `stop autoscroll` | Stop autoscroll. |
| `pause autoscroll` | Pause or resume autoscroll. |
| `speed read` | Start or toggle [speed read](Speed_Reading.html). |
| `stop speed read` | Stop speed read. |
| `pause speed read` | Mettre en pause ou reprendre la lecture rapide. |

Vérifiez l'état avec les propriétés du document `is autoscrolling` et `is speed reading`.

```applescript
tell application "Marked"
	tell document 1
		autoscroll with wpm 250
		-- or: speed read
	end tell
end tell
```

## Statistics

**`get statistics`** returns a `statistics_record` with numeric values computed from the current Markdown source (not the formatted strings shown in the statistics drawer).

| Property | Description |
| --- | --- |
| `word_count` | Word count |
| `sentence_count` | Sentence count |
| `character_count` | Character count |
| `paragraph_count` | Paragraph count |
| `average_words_per_sentence` | Mots moyens par phrase |
| `average_syllables_per_word` | Average syllables per word |
| `complex_word_percentage` | Complex word percentage |
| `reading_ease` | Flesch reading ease |
| `fog_index` | Gunning fog index |
| `grade_level` | Flesch–Kincaid grade level |
| `gulpease` | Indice Gulpease (lisibilité en italien ; `0` lorsqu'il n'est pas applicable) |
| `gulpease_band` | Gulpease band `1`–`4` (when applicable) |
| `reading_time_minutes` | Reading time at **250 WPM** |

```applescript
tell application "Marked"
	set stats to get statistics of document 1
	set wc to stats's word_count
	set fog to stats's fog_index
end tell
```

## Table of contents (work in progress)

{% note %}
**WIP — not reliable yet.** The dictionary includes a **`headings`** property and **`headings`** command for reading nested preview headings (`heading_item` records). Cette automatisation ne fonctionne **pas correctement** dans les versions actuelles (résultats vides, erreurs de coercition ou « aucun résultat n'a été renvoyé »). Il sera corrigé dans une version ultérieure. Préférez **`scroll to heading`** avec un titre ou un identifiant connu d'ici là.
{% endnote %}

**Comportement prévu** (une fois terminé) : enregistrements `heading_item` imbriqués à partir des en-têtes dans l'**aperçu** (`h1`–`h6`), et non à partir du Markdown brut.

| Property | Description |
| --- | --- |
| `title` | Heading text |
| `id` | DOM `id` attribute (empty string when absent) |
| `level` | Heading level `1`–`6` |
| `children` | Nested list of `heading_item` records |

**`headings`** (propriété du document) — tous les niveaux. **`headings levels {2, 3}`** (command) — optional filter: only those heading depths (not a range).

```applescript
-- Planned; do not rely on this yet
tell application "Marked"
	set toc to headings of document 1
	set filtered to headings levels {2, 3} of document 1
end tell
```

Utilisez les valeurs `id` avec **`scroll to heading id "..."`** une fois que l'automatisation des titres est stable.

## Print with profile

**`print with profile`** applies an export profile's print settings temporarily, then prints the document (same preference bundle as export profiles from {% prefspane Export %}).

```applescript
tell application "Marked"
	tell document 1
		print with profile "Print Letter"
	end tell
end tell
```

Profile names are case-sensitive. After printing, Marked restores the previously active export profile.

## Export profiles

Export profiles store bundles of export/print preferences (margins, headers, TOC options, and similar settings from {% prefspane Export %}).

**Read profile names**

```applescript
tell application "Marked"
	set profileList to profiles
	-- or: get_available_profiles
end tell
```

**Export with a profile**

```applescript
tell application "Marked"
	tell document 1
		export html to "/Users/you/Desktop/report.html" with profile "My Profile"
	end tell
end tell
```

Profile names are case-sensitive and must match a saved profile exactly.

## Export commands

Export commands are available on the **application**, **document**, and **window** objects. Each command requires a **`to`** parameter with the output path (POSIX path string or `file` object).

| Command | Output |
| --- | --- |
| `export markdown` | Markdown (.md) |
| `export html` | HTML |
| `export paginated pdf` | Paginated PDF (print layout) |
| `export continuous pdf` | Continuous-scroll PDF |
| `export epub` | EPUB |
| `export docx` | Microsoft Word (.docx) |
| `export odt` | OpenDocument Text |
| `export textbundle` | TextBundle |
| `export rtf` | RTF |
| `export opml` | OPML |

**Notes**

- Paginated PDF uses the same HTML-to-PDF pipeline as {% appmenu File, Export As, Save PDF (Paginated) %}. It is not available for raw HTML preview documents.
- HTML export uses the **rendered preview** (what you see in the WebView), not the raw Markdown source file.
- Continuous PDF captures the current preview WebView layout.

### Basic export

```applescript
tell application "Marked"
	tell document 1
		export paginated pdf to "/Users/you/Desktop/report.pdf"
	end tell
end tell
```

### Export paths and sandboxing

- Use a full POSIX path for the destination file.
- Marked can create intermediate folders when the export path is **inside the folder of the open document** (for example exporting to `.../MyProject/build/output.pdf` while previewing `.../MyProject/chapter.md`).
- Exports outside the document's folder require a writable path Marked can access (saved document location, security-scoped bookmarks, or folders you have granted via Open dialogs). If the path is not writable, the command returns an error before export starts.

## `with` options (properties record)

Instead of `with profile`, you can pass a record of options using **`with`** or **`with properties`**:

```applescript
export paginated pdf to "/path/out.pdf" with {pageSize:"A4", margins:"1in", fontSize:"14"}
```

AppleScript recognizes these keys directly (they are mapped before export):

| Key | Description | Example |
| --- | --- | --- |
| `style` | Preview style to apply before export (full preview reload) | `"Amblin"`, `"Swiss"` |
| `pageSize` | Print page size name | `"A4"`, `"Letter"` |
| `margins` | Print margins (see below) | `"1in"`, `"1in 2in"` |
| `fontSize` | Override export/print base font size in points (paginated and continuous PDF) | `"14"`, `"12pt"` |

`fontSize` enables the same **Custom font size for export/print** option from {% prefspane Export %}. It does not affect Fountain documents, which use fixed screenplay sizing.

When `style` is included, Marked applies that theme, waits for the preview to finish reloading, then exports. You do not need a separate `set style` step.

Other keys in the record can match **export preference** names from profiles (same keys stored in {% prefspane Export %}, such as `printBackgrounds`, `printTOC`, `topPrintMargin`). Those values are applied temporarily for the export.

You cannot combine conflicting sources carelessly: if you use `with profile`, load that profile first; if you use a `with` record, profile keys in the record override the current settings for that export.

### Margin shorthand

The `margins` value is a string with one to four measurements. Units: `in`, `cm`, `mm`, `pt`, or `"` for inches. A number without a unit is treated as points.

| Values | Signification |
| --- | --- |
| `1in` | All sides |
| `1in 2in` | Top and bottom `1in`, left and right `2in` |
| `1in 2in 1in` | Top `1in`, left and right `2in`, bottom `1in` |
| `1in 2in 1in 2in` | Top, right, bottom, left |

```applescript
export paginated pdf to "/path/out.pdf" with {pageSize:"A4", margins:"1in 2in"}
export paginated pdf to "/path/out.pdf" with {style:"Amblin", margins:"1in 2in 1in 2in"}
```

### Combined example

```applescript
tell application "Marked"
	tell document 1
		export paginated pdf to "/Users/you/Documents/MyBook/build/book.pdf" with {style:"Amblin", pageSize:"A4", margins:"1in"}
	end tell
end tell
```

## `convert_to`

L'objet application expose également les commandes de script héritées :

- **`convert_to`** -- convert Markdown text or a file path to a format (`html`, `pdf`, `epub`, `docx`, `rtf`, and others), optionally with a `profile` and `output_path`.
- **`get_available_formats`** -- list supported conversion format names.
- **`get_available_profiles`** -- liste les noms des profils d'exportation (identique à la propriété `profiles`).

`convert_to` reste disponible pour les anciens flux de travail et l'automatisation AppleScript uniquement.

## Debugging

Enable **Debug mode** in {% prefspane Advanced %} (or the debug preference in Settings). Marked then logs AppleScript export steps at Info level with the prefix `[AppleScript]` in Console.app and Marked's log viewer.

Lignes de journal utiles lors du traçage d'une exportation PDF paginée :

- `paginated PDF: fetching preview HTML`
- `HTMLToPDFGenerator: loadHTMLString`
- `HTMLToPDFGenerator: didFinishLoadForFrame`
- `paginated PDF: generator finished`

Long exports (especially paginated PDF) suspend the AppleScript event until completion so clients do not time out mid-export.

## Errors

Failed exports set the script error string on the command (visible in Script Editor and `on error` handlers). Common messages:

- Export path is required.
- Le répertoire d'export n'existe pas (en dehors du dossier document).
- Cannot create export directory or permission error writing the file.
- Nom du style d'aperçu inconnu.
- Délai d'attente pour le rechargement de l'aperçu après le changement de style.
- Paginated PDF export timed out or failed while generating pages.

## Intégration avec d'autres outils

Applications can use Marked's AppleScript surface to read document metadata. For the Shortcuts app, see [Shortcuts Integration](Shortcuts_Integration.html). For shell-driven workflows, folder watchers, and editor callbacks, the [URL Handler](URL_Handler.html) is often simpler. Le [Marked Bonus Pack](Workflow_Integration.html#marked-bonus-pack) comprend des scripts et des services supplémentaires.