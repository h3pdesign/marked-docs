# <%= @title %>

Marked funktioniert mit vielen Editoren und Schreib-Apps. Auf dieser Seite werden freigegebene **Einstellungen**, die **Vorschau in der Zwischenablage**, Verweise auf die **Streaming-Vorschau** und Skriptressourcen behandelt. Detaillierte Anleitungen für beliebte Apps finden Sie in eigenen Hilfethemen (siehe Abschnitt **Unterstützte Apps** in der Seitenleiste).

## Pro-App-Anleitungen

Beginnen Sie mit [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html) für den gesamten Workflow. Wenn Sie Obsidian verwenden, lesen Sie [Marked vs Obsidian Preview](Marked_vs_Obsidian_Preview.html), um zu entscheiden, wann Marked neben der integrierten Vorschau von Obsidian einen Mehrwert bietet.

| Thema | Hilfeseite |
| :-- | :-- |
| **Bär** | [Bear](Bear.html) |
| **Curio** (Streaming-Vorschau) | [Curio](Curio.html) |
| **Entwürfe** (Streaming-Vorschau + Aktionen) | [Drafts](Drafts.html) |
| **DEVONthink** (Integration des Skriptmenüs) | [DEVONthink](DEVONthink.html) |
| **Ordnerüberwachung** (nvALT, nvUltra usw.) | [Folder Watching](Folder_Watching.html) |
| **Hochland** | [Highland](Highland.html) |
| **Hookmark** URL-Auflösung | [Hookmark](Hookmark.html) |
| **iA-Autor** | [iA Writer](iA_Writer.html) |
| **iThoughtsX** `.itmz` Karten | [iThoughtsX](iThoughtsX.html) |
| **MarsEdit** Live-Vorschau | [MarsEdit](MarsEdit.html) |
| **MindNode** | [MindNode](MindNode.html) |
| **MultiMarkdown Komponist** | [MultiMarkdown Composer](MultiMarkdown_Composer.html) |
| **nvUltra** | [nvUltra](nvUltra.html) |
| **Obsidian**-Tresore und Beschriftungen | [Obsidian](Obsidian.html) |
| **OmniOutliner / OPML** | [OmniOutliner and OPML](OmniOutliner_and_OPML.html) |
| **RTF / RTFD** (Seiten, TextEdit usw.) | [RTF and RTFD Support](RTF_Support.html) |
| **PDF** | [PDF Support](PDF_Support.html) |
| **Scrivener 3** | [Scrivener 3 Support](Scrivener_Support.html) |
| **Das Archiv** Streaming-Vorschau | [The Archive](The_Archive.html) |
| **Ulysses** Export-Workflow | [Ulysses](Ulysses.html) |
| **Vim** (vim-markiertes Plugin) | [Vim](Vim.html) |
| **VS-Code** (Öffnen in der Erweiterung Marked) | [VS Code](VS_Code.html) |
| **VoodooPad** | [VoodooPad](VoodooPad.html) |
| **Xcode-Spielplätze** | [Xcode Playgrounds](Xcode_Playgrounds.html) |

## Anwendungseinstellungen

I> Mehrere Integrationen stellen Schalter innerhalb von {% prefspane Apps %} und {% prefspane Preview %} bereit.

![Application Settings][appsettings]

Verwenden Sie diese Bereiche für Wiki-Link-Standardeinstellungen, Scrivener-Übergabe, gestreamte Zwischenablageeinstellungen, Mind Map-Einbettungsoptionen für OPML/OmniOutliner, Obsidian-Integrationen oder andere Prozessoren, die auf kooperative Editoren angewiesen sind.

## Vorschau der Zwischenablage

![][ClipboardPreviewMenu]

Markdown (oder kompatibler Klartext) in der Zwischenablage wird mit {% appmenu File, New, Clipboard Preview %} ({% kbd shift cmd V %}) geöffnet. Wenn die Zwischenablage **HTML oder RTF** enthält, konvertiert Marked sie vor der Vorschau in eine Markdown-ähnliche Quelle – einschließlich grober Überschriftenerkennung, wenn RTF-Absätze große Stylesheet-Schriftgrößen verwenden.

## Streaming-Vorschau

Bear, Curio, Drafts, The Archive, nvALT, nvUltra und mehrere andere Editoren können Markdown während der Eingabe über **Streaming Preview** in Marked verschieben. Informationen zur Einrichtung und Fehlerbehebung finden Sie unter [Streaming Preview](Streaming_Preview.html).

## Skripte und Bonuspaket

Automatisierungen für BBEdit, TextMate, DEVONthink, Emacs, Vim und mehr werden mit [Marked Bonus Pack][bonus] geliefert. Installieren oder passen Sie diese Skripte an, wenn Sie Menüleisten- oder Editor-Makros benötigen, die über die oben aufgeführten Integrationen hinausgehen.


[appsettings]: images/screenshots/preferences-Apps.jpg @2x width=689px height=1031px class=preferencepane
[ClipboardPreviewMenu]: images/ClipboardPreviewMenu.jpg @2x width=600px height=198px class=center
[bonus]: https://github.com/kotfu/marked-bonus-pack