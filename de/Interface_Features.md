# <%= @title %>

Flexibilität ist der Schlüssel.

## Zahnradmenü

![][4]

   [4]: images/gearmenu.jpg @2x width=740px height=235px class=center

Das Zahnradmenü bietet die meisten Funktionen der Menüleiste sowie einige vorschauspezifische Funktionen. Klicken Sie einfach auf das Zahnrad unten rechts im Fenster, um auf diese Funktionen zuzugreifen.

## Bleiben Sie an der Spitze

![][5]

   [5]: images/KeepOnTopPin.jpg @2x width=740px height=345px class=center

Das Schlosssymbol unten links bringt das Vorschaufenster in den Vordergrund und lässt es dort schweben (schweben), wenn Sie zu anderen Anwendungen wechseln. Sie können im {% prefspane General %} eine Transparenz für das Fenster festlegen, die es ermöglicht, das Fenster auszublenden, wenn Sie andere Anwendungen verwenden.

Diese Funktion kann auch mit {% kbd shift-opt-cmd-f %} umgeschaltet werden.

## Standardeinstellungen auf Fensterebene

Im {% prefspane General %} können Sie mit „Neue Fenster im Vordergrund halten“ festlegen, dass neue Fenster immer über anderen Fenstern bleiben und/oder Fenster so einstellen, dass sie nach oben verschoben werden, wenn das zugehörige Dokument aktualisiert wird. Windows, die so eingestellt sind, dass sie bei einem Update aktiviert werden, „stiehlt“ Ihrem Editor nicht den Fokus, sie werden nur angezeigt, ohne aktiv zu werden.

## Quelle anzeigen

![][6]

   [6]: images/view_source.jpg @2x width=740px height=345px class=center

Mit der Schaltfläche in der oberen rechten Ecke können Sie zwischen Vorschau- und Quellcode-Ansicht wechseln. Diese Ansicht kann auch mit U umgeschaltet werden.

## Suchen

![][7]

   [7]: images/SearchBarFull.jpg @2x width=818px height=195px class=center

Die Suchleiste kann mit {% kbd cmd F %} aufgerufen werden und ermöglicht die Suche in der Vorschau nach einem Wort oder einer Phrase. Sobald Sie eine Suche durchgeführt haben, können Sie mit {% kbd cmd G %} und {% kbd shift cmd G %} vorwärts und rückwärts durch weitere Ergebnisse navigieren.

Mit den Kontrollkästchen auf der rechten Seite der Suchleiste können Sie die Suche nach Groß-/Kleinschreibung, nur ganzen Wörtern und regulären Ausdrücken eingrenzen. Zusätzlich zur Suche nach regulären Ausdrücken funktionieren Wildcard-Suchen (*?) immer, auch wenn die Regex-Option deaktiviert ist.

Sie können einen Suchbegriff oder eine Phrase auch mit Schrägstrichen umgeben, um ihn automatisch als regulären Ausdruck zu interpretieren (z. B. „/term.+?\b/“).


Verwenden Sie die Suchfunktion in Kombination mit Lesezeichen, um Orte zu speichern, sobald Sie sie finden. Drücken Sie die Tabulatortaste ({% kbd ⇥ %}), um das Dokument zu fokussieren, und geben Sie dann Umschalt-[1-9] ein, um ein Lesezeichen für diese Nummer zu setzen. Sie können zum Lesezeichen zurückspringen, indem Sie einfach die Nummer eingeben (ohne die Umschalttaste) oder mit n/p in der Dokumentreihenfolge durch die Lesezeichen navigieren. N/P navigiert in numerischer Reihenfolge. Informationen zu Lesezeichen, dem Inhaltsverzeichnis, der Minikarte und der schnellen Kopfzeilensuche finden Sie unter [Document Navigation](Document_Navigation.html). Weitere Optionen finden Sie im Abschnitt [Preview Navigation](Keyboard_Shortcuts.html#previewnavigation), oder geben Sie „?“ ein. jederzeit in der Vorschau.

> **Hinweis:** Die Suche kann nicht zwischen Elementen umbrechen, was bedeutet, dass eine Suchzeichenfolge nicht zwischen einem Absatz und einer Überschrift, über Listenelemente usw. fortgesetzt werden kann.

Sie können die Kontrollkästchen „Ganze Wörter“, „Groß-/Kleinschreibung beachten“ und „Regex“ mit {% kbd ctrl shift 1 %}, {% kbd 2 %} bzw. {% kbd 3 %} umschalten.

### Erweiterte Suche ###

Sie können Platzhalter in einer Nicht-Regex-Suche verwenden. `*` entspricht jeder Reihe von Zeichen, die keine Leerzeichen sind, und `?` entspricht jedem einzelnen Zeichen.

Wenn Sie eine Suche mit einem `*` starten, wird daraus eine jQuery-Selektorsuche. Sie können einen beliebigen jQuery-Selektor verwenden und alle passenden Elemente werden hervorgehoben und sind mit {% kbd cmd G %} und {% kbd shift cmd G %} navigierbar. Um den Umfang einer Textsuche auf einen bestimmten Elementtyp zu beschränken, fügen Sie die Suchbegriffe in doppelten Anführungszeichen nach der Selektordefinition ein:

*h2 „Alice“

Dies entspricht `*h2:contains(Alice)`

## Dokumentennavigation (Inhaltsverzeichnis, Lesezeichen, Minikarte)

Die Seite [Document Navigation](Document_Navigation.html) umfasst das Inhaltsverzeichnis (einschließlich Öffnen des Filters mit {% kbd Space %}), die Schnellsuche mit {% kbd f %}, Lesezeichen und die Minikarte.

## Tastaturnavigation

Mithilfe von Tastaturkürzeln kann schnell im Vorschaufenster navigiert werden. Verwenden Sie {% kbd j %} und {% kbd k %}, um sich nach oben und unten zu bewegen, und halten Sie die Umschalttaste ({% kbd J %}/{% kbd K %}) gedrückt, um sich schneller zu bewegen. {% kbd t %} und {% kbd b %} werden an den oberen und unteren Rand des Dokuments verschoben (ebenso wie {% kbd gg %} und {% kbd G %} für Vim-Fans). {% kbd u %} und {% kbd d %} verschieben eine halbe Seite nach oben und unten.

### Kopfball springen

Durch Drücken der Komma- ({% kbd , %}) und der Punkttaste ({% kbd . %}) können Sie durch alle Kopfzeilen im Dokument vor- und zurückspringen. Wenn Sie die Umschalttaste ({% kbd shift  %}) gedrückt halten, wird nur zwischen den Kopfzeilen der Ebenen 1 und 2 gesprungen.


## Vollbild

Der Vollbildmodus kann über das Vorschaumenü oder durch Eingabe von {% kbd ctrl cmd F %} umgeschaltet werden.

## Klicken auf externe Links

![][10]

[10]: images/linkpopover.png @2x width=706px height=213px class=center

Wenn Sie in der Vorschau Ihres Dokuments auf einen externen Link klicken, wird es in Ihrem Standardbrowser geöffnet. Wenn Sie klicken und gedrückt halten, erhalten Sie beim Loslassen von Marked drei Optionen: Sie können die URL des Links in Ihre Zwischenablage kopieren, den Link validieren oder den Link in Ihrem Standardbrowser öffnen. Klicken Sie einfach irgendwo in Ihrer Vorschau, um das Fenster zu schließen. Diese Funktion kann im {% prefspane Preview %} („Link-Popover aktivieren“) deaktiviert werden.

Siehe ein [overview video on YouTube](https://www.youtube.com/watch?v=nrt7YZPrnv0&list=PLNoOPRHOBV0ptk_ka386xltm3VyVw6QgZ&index=1).

## Zusammenklappbare Schlagzeilen ##

Wenn in {% prefspane Preview %} die Option „Abschnitte ausblenden für Überschriften“ aktiviert ist, wird durch Klicken auf Überschriften der Abschnitt zwischen dieser Überschrift und der nächsten Überschrift auf derselben Ebene ausgeblendet. Unterabschnitte innerhalb dieses Abschnitts werden ausgeblendet. Optional können Sie dieses Verhalten auf {% kbd cmd %}-Klicks beschränken.

![][13]

[13]: images/headlines.jpg @2x width=740px height=287px class=center

Wenn Sie beim Klicken {% kbd opt  %} gedrückt halten (oder beim Klicken auf {% kbd cmd %} klicken), werden alle untergeordneten Abschnitte unterhalb der angeklickten Überschrift erweitert/reduziert. Wenn Sie beim Klicken die {% kbd shift  %} (Umschalt)-Taste gedrückt halten, werden alle anderen Abschnitte auf derselben Ebene ausgeblendet, sodass nur der angeklickte Abschnitt angezeigt wird.

Reduzierte Abschnitte werden mit einer gelben Hervorhebung rechts neben dem Titel markiert und der Cursor zeigt an, was passiert, wenn auf das Element geklickt wird.

Wenn eine Bearbeitung vorgenommen wird, die sichtbar sein muss, oder auf einen Inhaltsverzeichnisabschnitt geklickt wird, der sich derzeit in einem minimierten Abschnitt befindet, werden die erforderlichen übergeordneten Abschnitte erweitert, um ihn anzuzeigen.

Sie können alle Abschnitte in einem Dokument gleichzeitig reduzieren/erweitern, indem Sie „Alle Abschnitte reduzieren“ ({% kbd opt cmd left  %}) und „Alle Abschnitte erweitern“ ({% kbd opt cmd right  %}) verwenden.

Weitere Einzelheiten finden Sie unter [Document Navigation video on YouTube](https://www.youtube.com/watch?v=Z2p5BvBpbmA&list=PLNoOPRHOBV0ptk_ka386xltm3VyVw6QgZ&index=2).

## Custom Prozessoranzeigen/-schalter ##

![][indicators]

[indicators]: images/processorindicators.png @2x width=874px height=255px class=center

Wenn der benutzerdefinierte Prozessor und/oder der Vorprozessor aktiviert sind, werden in der Symbolleiste Anzeigeleuchten angezeigt. Diese können verwendet werden, um zu sehen, ob der Prozessor für das aktuelle Dokument aktiviert ist (Anzeige wird hervorgehoben), und wenn Sie darauf klicken, wird die Verwendung des benutzerdefinierten Präprozessors bzw. Prozessors umgeschaltet.

## Scrollen Sie zum Bearbeiten

Die Funktion „Zum Bearbeiten scrollen“ in Marked verfolgt die Unterschiede zwischen dem letzten und dem letzten Update und versucht, den Punkt zu finden, an dem Sie Ihre letzten Änderungen vorgenommen haben. Marked verfolgt dies immer und in der Vorschau erscheint eine kleine rote Linie, die Ihnen den Ort der ersten erkannten Änderung anzeigt. Im {% prefspane Preview %} können Sie „Zur ersten Bearbeitung scrollen“ aktivieren. Wenn eine Vorschau aktualisiert wird, wird die Ansicht sanft zu dieser Position gescrollt.

Wenn „Zur ersten Bearbeitung scrollen“ deaktiviert ist, können Sie in der Vorschau jederzeit die Taste „e“ drücken, um zum letzten gespeicherten Bearbeitungspunkt zu gelangen.

## Autoscroll

Siehe die spezielle Seite [Autoscroll](Autoscroll.html). Wenn Sie Autoscroll als Teleprompter verwenden, [special syntax can insert pauses](Special_Syntax.html#pauses).

## Zoom-Übersicht

Siehe die Seite [Zoom Overview](Zoom_Overview.html) ({% kbd z %} in der Vorschau; funktioniert auch in der Wortwiederholung mit {% kbd ctrl cmd w %}).

## Markdown Referenz

![][11]

   [11]: images/markdown_reference.jpg @2x width=1148px height=267px class=center

Wählen Sie im Menü {% appmenu Help %} die Option Markdown Reference aus, um einen Leitfaden anzuzeigen, der über Ihren anderen Fenstern schwebt. Dies ist praktisch für diejenigen, die noch dabei sind, die Syntax von Markdown zu lernen. Sie können dieses Panel über die Tastatur mit {% kbd opt cmd M %} öffnen.

## Globale Tastaturkürzel

Im {% prefspane General %} können Sie eine benutzerdefinierte Tastenkombination zum Aktivieren von Marked und eine zum Anheben nur des vorderen Fensters nach oben festlegen, ohne Ihren Editor zu verlassen.