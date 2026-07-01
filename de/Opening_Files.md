# <%= @title %>

Marked bietet Ihnen Optionen.

## Live-Vorschau-Workflow

1. Ziehen Sie eine Markdown-Datei auf Marked (oder verwenden Sie {% appmenu File, Open... ({{cmd}}O) %}).
2. Bearbeiten Sie die Datei in Ihrem bevorzugten Editor.
3. Speichern --- Marked aktualisiert die Vorschau automatisch.

Siehe [Live Markdown Preview on Mac](Live_Markdown_Preview_on_Mac.html) für Tresorüberwachung, Streaming-Vorschau und editorspezifische Anleitungen.

## Zum Dock-Symbol ziehen

Der einfachste Weg, Marked für eine Datei zu verwenden, die Sie bereits bearbeiten, besteht darin, das Dokumentsymbol aus der Symbolleiste Ihres Editors oder aus dem Finder auf das Marked-Symbol in Ihrem Dock zu ziehen. Marked beginnt sofort mit der Verfolgung aller darauf abgelegten Markdown-Dateien (oder Textdateien). Sie können Dateien auch direkt aus dem Finder ziehen.

## Verwenden des Menüs

![][2]

   [2]: images/file_open.jpg @2x width=300px height=118px class=center

Sie können Markdown-Dateien natürlich auch direkt über die Menüoption {% appmenu File, Open... ({{cmd}}O) %} öffnen. Marked funktioniert auch ohne Texteditor einwandfrei. Sie können Ihren Markdown mit nur einem Klick in der Vorschau anzeigen und konvertieren.

Marked kann auch **`.rtf`- und `.rtfd`**-Dateien direkt öffnen (z. B. Exporte aus Pages oder TextEdit). Sie werden zur Vorschau und Aktualisierung in Markdown konvertiert, wenn Sie sie in der Original-App speichern. Einzelheiten, einschließlich Bilder und Einschränkungen, finden Sie unter [RTF and RTFD Support](RTF_Support.html).

Marked kann **`.pdf`** Dateien auf die gleiche Weise öffnen: Die Konvertierung wird im Hintergrund ausgeführt und die Vorschau wird nach Abschluss aktualisiert. Dies funktioniert am besten für kürzere, textbasierte PDFs; Große Handbücher und gescannte Dokumente sind langsamer und ungenauer. Einzelheiten und Einschränkungen finden Sie unter [PDF Support](PDF_Support.html).

## Aus der Zwischenablage

Wenn Sie kompatiblen Text (z. B. Markdown) in Ihrer Zwischenablage haben, können Sie eine sofortige Vorschau öffnen, indem Sie {% appmenu File, New, Clipboard Preview ({{shift}}{{cmd}}V) %} auswählen. Wenn Sie eine Auswahl aus einem Webbrowser oder einer anderen App kopiert haben, die HTML oder RTF in der Zwischenablage abgelegt hat, konvertiert Marked sie zur Vorschau in Markdown. Wenn Sie RTF aus einer App wie TextEdit oder Pages einfügen, werden größere Schriftgrößen grob in Überschriftenebenen konvertiert (z. B. wird sehr großer Text zu einer Überschrift der Ebene 1, kleinerer großer Text zur Überschrift der Ebene 2 usw.). Sie können mehrere Zwischenablagevorschauen gleichzeitig öffnen und diese in einer neuen Datei speichern, indem Sie {% appmenu File, Save Clipboard Preview %} wählen.

## Ein neues Dokument erstellen

Mit Marked können Sie mit dem Befehl {% appmenu File, New ({{cmd}}N) %} eine neue, leere Textdatei erstellen. Sie werden sofort nach einem Speicherort für die Datei gefragt und Sie können die Option „Neue Dateien automatisch bearbeiten“ im {% prefspane Apps %} neben der Schaltfläche „Texteditor“ aktivieren, um die neu erstellte Datei automatisch in Ihrem Standardeditor zu öffnen.

## Zuletzt geöffnet

![][3]

   [3]: images/open_recent.jpg @2x width=300px height=174px class=center

Marked behält auch den Überblick über aktuelle Dokumente. Die Menüoption {% appmenu File, Open Recent %} zeigt Ihnen die Dateien an, die Sie geöffnet hatten, und ermöglicht Ihnen, zu ihnen zurückzukehren. Mit {% kbd shift cmd R %} können Sie die zuletzt angezeigte Datei schnell wieder öffnen. Verwenden Sie {% kbd shift cmd P %} oder [Quick Actions](Quick_Actions.html), um Menü- und Vorschaubefehle über die Tastatur auszuführen. Es gibt auch viele andere Tastaturkürzel. Wenn Sie sie lernen möchten, finden Sie unten eine Tabelle [Keyboard Shortcuts](Keyboard_Shortcuts.html).

## Schnell öffnen ##

Sie können schnell zwischen geöffneten Dokumenten wechseln, zuletzt verwendete Dokumente öffnen oder den Dialog Datei->Öffnen mit [Quick Open panel](Quick_Open.html) ({% kbd cmd shift o %}) öffnen.