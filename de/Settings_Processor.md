# <%= @title %>

Optionen im {% prefspane Processor %}:

![Settings: Processor][1]

[1]: images/screenshots/preferences-Processor.jpg @2x width=689px height=1031px class=preferencepane-scroll

### Verarbeiten Sie Markdown mit

Standardprozessor Markdown. Der CommonMark-Prozessor wird für GitHub-Benutzer bevorzugt, MultiMarkdown ist ideal für Autoren und Discount und Kramdown haben spezielle Zwecke. Marked gleicht einige Unterschiede in der Syntax aus. Weitere Informationen finden Sie unter __Help->Markdown Reference__.

Custom Regeln
: Klicken Sie auf die Schaltfläche „Custom-Regeln“, um den Regeleditor zu öffnen, in dem Sie verschiedene Prozessoren und Dokumenttransformationen angeben können, die basierend auf übereinstimmenden Kriterien ausgeführt werden sollen. Weitere Informationen finden Sie unter [Custom Processor](Custom_Processor.html).

Neue Dokumente verwenden benutzerdefinierte
: Wenn diese Option aktiviert ist, verwenden neue Dokumente automatisch Ihren gespeicherten **Präprozessor** und/oder **Prozessor** aus Custom-Regeln, ohne dass eine dokumentspezifische Einrichtung erforderlich ist.

Vollständiger Festplattenzugriff
: Klicken Sie auf **Erteilen**, um Marked die Berechtigung zu erteilen, Dateien außerhalb seiner Sandbox zu lesen, wenn benutzerdefinierte Prozessoren oder andere Funktionen verwendet werden, die einen umfassenderen Dateizugriff erfordern.

Um die Unterschiede zwischen den Prozessoren zu erkunden, sehen Sie sich [Markdown Dingus](Markdown_Dingus.html) an.

### HTML

Generieren Sie IDs für Schlagzeilen
: Header-IDs basierend auf dem Inhalt des h1-h6-Tags generieren.

Verwenden Sie zufällige Fußnoten-IDs
: Generieren Sie zufällige Fußnoten-IDs, um Konflikte zu vermeiden, wenn mehrere Dokumente auf einer Seite angezeigt werden.

Verarbeiten Sie Markdown innerhalb von HTML
: Standardmäßig wird Markdown innerhalb von HTML-Tags normalerweise ignoriert. Diese Option zwingt Marked, die Verarbeitung innerhalb von Blockelementen fortzusetzen. Beachten Sie, dass einige Markups Probleme verursachen können.

### Rendern

Behalten Sie Zeilenumbrüche in Absätzen bei
: Zeilenumbrüche im Absatztext berücksichtigen und durch harte Umbrüche ersetzen, anstatt sie mit der vorherigen Zeile zu verketten.

Rendern Sie GitHub-Kontrollkästchen
: Rendern Sie `- [ ]` und `- [x]` zum Erstellen von Kontrollkästchen in Listen. Kontrollkästchen werden zur Vorschau gerendert, sind jedoch innerhalb von Marked nicht funktionsfähig.

Rendern GitHub :emoji:
: Rendern Sie `:name:` Shortcodes als Emoji im GitHub-Stil in der Vorschau.

\#Text ist Tag
: Ermöglicht die Interpretation von Hashtags (`#` unmittelbar gefolgt von Text ohne Leerzeichen) als Tags und nicht als Überschriften. Diese Funktionalität ist für Bear-Benutzer standardmäßig verfügbar.

Stil-Tags
: Wenn **#Text ist Tag** aktiviert ist, werden erkannte Tags mit Kapselstil angezeigt. Tags können in {% appmenu {{gear}}, Proofing, Show Comments %} angezeigt oder ausgeblendet werden.

![#Text is tag enabled][textistag]

[textistag]: images/textistag.jpg @2x width=896px height=274px class=center

Rendern Sie `==highlight==` und `~~delete~~`
: Wenn diese Option aktiviert ist, wird der `==highlight==`-Text als HTML `<mark>`-Tag gerendert, das als gelbe Hervorhebung angezeigt wird, sofern nicht anderweitig durch einen Stil geändert. Darüber hinaus wird die Syntax `~~delete~~` mit einem Tag `<del>` gerendert.

: Wenn __Render as CriticMarkup__ aktiviert ist, wird die Syntax `==highlight==` und `~~delete~~` in CriticMarkup konvertiert, das dann in der Original-, Markup- und bearbeiteten Ansicht angezeigt werden kann.

Rendern Sie `~text~` als Unterstrich
: Wenn diese Option aktiviert ist, werden `~text~`, die von einzelnen Tilden umgeben sind, unterstrichen dargestellt. Dies steht in Konflikt mit der MultiMarkdown-Syntax für Subskripte und ist standardmäßig deaktiviert.