<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked works with many editors and writing apps. This page covers shared **settings**, the **clipboard preview**, pointers to **streaming preview**, and scripting resources. Detailed guides for popular apps live in their own help topics (see the **Supported Apps** section in the sidebar).

## Per-app guides

Start with [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html) for the overall workflow. Si vous utilisez Obsidian, consultez [Marked vs Obsidian Preview](Marked_vs_Obsidian_Preview.html) pour décider quand Marked ajoute de la valeur aux côtés de l'aperçu intégré d'Obsidian.

| Topic | Help page |
| :-- | :-- |
| **Bear** | [Bear](Bear.html) |
| **Curio** (streaming preview) | [Curio](Curio.html) |
| **Brouillons** (aperçu en streaming + actions) | [Drafts](Drafts.html) |
| **DEVONthink** (Script menu integration) | [DEVONthink](DEVONthink.html) |
| **Folder watching** (nvALT, nvUltra, etc.) | [Surveillance de dossiers](Folder_Watching.html) |
| **Highland** | [Highland](Highland.html) |
| **Résolution d'URL de crochet** | [Hookmark](Hookmark.html) |
| **iA Writer** | [iA Writer](iA_Writer.html) |
| **iThoughtsX** `.itmz` maps | [iThoughtsX](iThoughtsX.html) |
| **MarsEdit** aperçu en direct | [MarsEdit](MarsEdit.html) |
| **MindNode** | [MindNode](MindNode.html) |
| **Compositeur MultiMarkdown** | [MultiMarkdown Composer](MultiMarkdown_Composer.html) |
| **nvUltra** | [nvUltra](nvUltra.html) |
| Voûtes et légendes **Obsidienne** | [Obsidian](Obsidian.html) |
| **OmniOutliner / OPML** | [OmniOutliner and OPML](OmniOutliner_and_OPML.html) |
| **RTF / RTFD** (Pages, TextEdit, etc.) | [RTF and RTFD Support](RTF_Support.html) |
| **PDF** | [PDF Support](PDF_Support.html) |
| **Scrivener 3** | [Support Scrivener 3](Scrivener_Support.html) |
| **The Archive** streaming preview | [The Archive](The_Archive.html) |
| **Ulysses** export workflow | [Ulysses](Ulysses.html) |
| **Vim** (vim-marked plugin) | [Vim](Vim.html) |
| **VS Code** (Open in Marked extension) | [VS Code](VS_Code.html) |
| **VoodooPad** | [VoodooPad](VoodooPad.html) |
| **Xcode playgrounds** | [Terrains de jeux Xcode](Xcode_Playgrounds.html) |

## Application settings

I> Plusieurs intégrations exposent des bascules à l'intérieur de {% prefspane Apps %} et {% prefspane Preview %}.

![Application Settings][appsettings]

Use these panes for wiki-link defaults, Scrivener hand-off, streamed clipboard settings, Mind Map embedding options for OPML/OmniOutliner, Obsidian integrations, or other processors that rely on cooperative editors.

## Clipboard Preview

![][ClipboardPreviewMenu]

Le Markdown (ou le texte brut compatible) dans le presse-papiers s'ouvre avec {% appmenu File, New, Clipboard Preview %} ({% kbd shift cmd V %}). Si le presse-papiers contient **HTML ou RTF**, Marked le convertit en source de type Markdown avant l'aperçu, y compris la détection de titre approximatif lorsque les paragraphes RTF utilisent de grandes tailles de police de feuille de style.

## Streaming Preview

Bear, Curio, Drafts, The Archive, nvALT, nvUltra, and several other editors can push Markdown into Marked as you type via **Streaming Preview**. Voir [Streaming Preview](Streaming_Preview.html) pour la configuration et le dépannage.

## Scripts et pack bonus

Automations for BBEdit, TextMate, DEVONthink, Emacs, Vim, and more ship with the [Marked Bonus Pack][bonus]. Install or adapt those scripts when you want menu-bar or editor macros beyond the integrations listed above.


[appsettings]: images/screenshots/preferences-Apps.jpg @2x width=689px height=1031px class=preferencepane
[ClipboardPreviewMenu]: images/ClipboardPreviewMenu.jpg @2x width=600px height=198px class=center
[bonus]: https://github.com/kotfu/marked-bonus-pack