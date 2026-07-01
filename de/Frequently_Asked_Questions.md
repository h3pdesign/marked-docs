# <%= @title %> [toc]

## Lizenzcode wurde bereits verwendet [license_code_has_already_been_utilized]

Wenn Sie eine Neuinstallation von Marked 2 durchführen und bei der Eingabe Ihrer Lizenz die Fehlermeldung „Lizenzcode wurde bereits verwendet“ erhalten, <a href="mailto:me@brettterpstra.com">kontaktieren Sie mich bitte</a> und fordern eine neue Lizenz an. **Bitte geben Sie die E-Mail-Adresse an, unter der Sie sich registriert haben, und/oder Ihren aktuellen Lizenzcode.**

Frühe Lizenzen, die für Marked generiert wurden, hatten ein Nutzungslimit anstelle eines Maschinenlimits, sodass drei Installationen – selbst auf demselben Computer – Aktivierungen verbrauchen würden. Diese Grenzwerte wurden in neueren Lizenzen korrigiert. Der Kauf einer Marked 2-Lizenz ermöglicht Ihnen die Installation von Marked 2 auf jedem Computer, den Sie besitzen. Zögern Sie also nicht, nach einem Ersatz zu fragen, wenn Sie auf Probleme stoßen.

[Table of contents](#toc)

## Site-Lizenzen und Bildungsrabatte [site_licenses_and_educational_discounts]

Ermäßigte Site-/Massenlizenzen sind für Marked 2 verfügbar. Um einen Kauflink anzufordern, wenden Sie sich bitte an <a href="mailto:me@brettterpstra.com">Brett</a> und geben Sie die Anzahl der Lizenzen an, die Sie kaufen möchten.

**Rabatte**

- 5-9: **10 % Rabatt**
- 10-19: **12 % Rabatt**
- 20-49: **15 % Rabatt**
- 50+: **20 % Rabatt**

Sowohl für die Direktversion als auch für die Mac App Store-Version ist ein Bildungsrabatt verfügbar. Für den Mac App Store sind standardmäßige Bildungsrabatte von Apple aktiviert. Um eine Direktversion mit Bildungsrabatt zu erwerben, <a href="mailto:me@brettterpstra.com">kontaktieren Sie mich</a> und fordern Sie einen Gutschein an.

[Table of contents](#toc)

## Eine URL wird nicht validiert oder gibt „Unbekannt“ zurück [a_url_wont_validate_or_returns_unknown]

[link validation](http://marked2app.com/help/Link_Validation.html) von Marked verwendet eine einfache HEAD-Anfrage, um zu bestimmen, ob ein Link gültig ist. Alles andere als ein Ergebnis von 200 (Erfolg) führt entweder zu „Unbekannt“ oder zu einem Fehler, wenn es sich um einen häufigen Fehlercode wie 404 (nicht gefunden) oder 500 (Serverfehler) handelt. URLs hinter der Authentifizierung (z. B. Apple-Entwickler-URLs oder alles, für dessen Zugriff eine Anmeldung erforderlich ist) geben „Unbekannt“ zurück, ebenso wie bestimmte Websites wie Amazon.com, bei denen der Server bizarre Antwortcodes zurückgibt. Dagegen kann Marked nicht viel tun.

[Table of contents](#toc)

## Custom Prozessorberechtigungen in der MAS-Version [custom_processor_permissions_in_mas_version]

Aufgrund von Sandboxing-Einschränkungen ist die Mac App Store-Version von Marked 2 nicht in der Lage, bestimmte Arten von Binärtools als benutzerdefinierte Prozessoren auszuführen. Wenn Sie auf diese Einschränkung stoßen, können Sie einige Schritte ausprobieren.

1. Stellen Sie sicher, dass Sie in den **Marked 2**-Einstellungen (⌘,) im Bereich **Erweitert** auf „Berechtigungen aktualisieren“ geklickt haben. Dadurch wird versucht, Marked Zugriff auf Ihr gesamtes Standardlaufwerk zu gewähren, wodurch Probleme mit Skripten und Dienstprogrammen behoben werden, die auf temporäre Ordner und nicht standardmäßige Speicherorte zugreifen müssen.
2. Versuchen Sie es mit einem Skript. Verweisen Sie in einem Shell-Skript auf das Dienstprogramm, das Sie ausführen möchten (Multimarkdown, Kramdown usw.). Es kann ein Bash-, Ruby-, Perl- oder Python-Skript sein. Stellen Sie dann in den erweiterten Einstellungen den Prozessor auf die zugehörige Shell oder ausführbare Datei und die Parameter auf den Speicherort des Skripts ein. Ich kann zum Beispiel ein Bash-Skript erstellen, das unter ~/scripts/mmd_wrapper.sh gespeichert ist:
    
        #!/bin/bash
        Katze | /usr/local/bin/multimarkdown
    
    Machen Sie es dann ausführbar (`chmod a+x ~/scripts/mmd_wrapper.sh`) und richten Sie meine Custom Prozessoreinstellungen ein:

Prozessor: /bin/bash
        Argumente: /Users/me/scripts/mmd_wrapper.sh
3. Einige ausführbare Dateien (insbesondere Pandoc) funktionieren im Sandboxing einfach nicht. Bitte kontaktieren Sie mich in diesem Fall über das bei der Ausführung erscheinende Fehlerfenster, um eine Crossgrade-Lizenz auf die Direktversion zu erhalten.

[Table of contents](#toc)

## Intra-Dokument-Links in exportierten PDFs [intra-document_links_in_exported_pdfs]

Der PDF-Export von Marked verwendet derzeit die Druckfunktionen von WebKit. Eine Folge davon ist, dass dokumentinterne (interne) Links, einschließlich derjenigen in einem Inhaltsverzeichnis, nicht zu anderen Punkten im Dokument springen. Apple hat offenbar nicht die Absicht, dies in der Version von WebKit zu beheben, die Marked 2 verwendet.

In einigen Fällen erzielen Sie möglicherweise gute Ergebnisse, indem Sie HTML mit eingebettetem Stil exportieren und dann mit Ihrem Webbrowser nach PDF drucken. Sie erhalten nicht alle Exportfunktionen von Marked, aber normalerweise erhalten Sie ein PDF mit funktionierenden internen Links. Im Moment ist es ein Kompromiss.

[Table of contents](#toc)

## Relative Pfade in eingebundenen Dateien [relative_paths_in_included_files]

Dateien, die mit [include syntax][include] sowie [Scrivener files][scriv] von Marked eingebunden werden, können relative Pfade verwenden, um auf andere Dateien zu verweisen. (_**Hinweis:** Dies gilt nicht für Dateien, die mit der `/file`-Syntax von IA Writer oder CSV-Dateien_ eingebunden wurden). Ab neueren Versionen (2.5.10+) sind diese Pfade _relativ zur enthaltenen Datei_, nicht zur Basisdatei.

Bei einer Datei-/Ordnerstruktur wie dieser:

- base_file.md
    - Unterordner
        - include_file.md
    - Bilder
        - Bild1.jpg

Wenn `included_file.md` über einen relativen Pfad auf image1.jpg verweist, muss es als `../images/image1.jpg`, _not_ `images/image1.jpg` geschrieben werden. (`..` gibt das übergeordnete Verzeichnis an) .

[include]: http://marked2app.com/help/Multi-File_Documents.html
[scriv]: http://marked2app.com/help/Scrivener_Support.html

[Table of contents](#toc)

## Wie kann ich eine verlorene Lizenz wiederherstellen (direkte Version) [how_do_i_retrieve_a_lost_license_direct_version]

Wenn Sie eine Lizenz verloren haben, die Sie für Marked 2 über Paddle erworben haben, können Sie sie unter [my.paddle.com](https://my.paddle.com/) abrufen. Wenn Sie Probleme mit der Anmeldung haben, können Sie über eine private Anfrage unter [support site](http://support.markedapp.com) eine Suche anfordern.

[Table of contents](#toc)

## In-App-Kaufprobleme (Error Domain=Paddle Code=0 „(null)“) [in-app_purchase_issues_error_domainpaddle_code0_null]

Paddle hat mich kürzlich darüber informiert, dass IAPs kaputt sind und dass sie nicht planen, das Problem zu beheben, weil nicht genügend Entwickler sie implementiert haben. (Was für mich genauso frustrierend ist wie für Sie.) Das wirklich Frustrierende daran ist, dass sie weiterhin Zahlungen zulassen, sodass ich Käufe manuell zurückerstatten muss, bis etwas bezüglich der Art und Weise, wie die Lizenzen gehandhabt werden, geändert wird. Ein neues System soll angeblich in den nächsten Wochen eingeführt werden. Wenn Sie also bereit sind zu warten, werde ich alles tun, was ich kann, um sicherzustellen, dass alle aktuellen Käufe des IAP für Rechtschreibung/Grammatik über das als nächstes bereitgestellte System berücksichtigt werden

Wenn Sie eine Rückerstattung bevorzugen, senden Sie mir einfach <a href="mailto:me@brettterpstra.com">direkt eine E-Mail</a> mit dem für die Lizenzierung verwendeten E-Mail-Konto oder der Transaktions-ID aus der Quittung.

**Update:** Paddle hat die neue IAP-Lösung offiziell angekündigt und sie wird implementiert, sobald sie öffentlich verfügbar ist. Aktuelle In-App-Kauflizenzen (Rechtschreibung/Grammatik) werden automatisch migriert und ein neuer Gutscheincode wird bereitgestellt. Dies sollte bald geschehen.

[Table of contents](#toc)

## Eingezäunte Codeblöcke innerhalb eingerückter Codeblöcke [fenced_code_blocks_inside_indented_code_blocks]

In relativ seltenen Fällen möchten Sie möglicherweise die Zäune eines umzäunten Codeblocks anzeigen. Normalerweise könnte dies in Markdown durch Einrücken des abgeschirmten Codes erreicht werden, wodurch ein eingerückter „wörtlicher“ Block erzwungen wird, der den abgeschirmten Codeblock enthält, der dann unverarbeitet wäre. Marked behandelt eingezäunten Code unterschiedlich (im Rahmen seiner Fähigkeit, mit mehreren Syntaxoptionen zu arbeiten). Um dies zu erreichen, müssen Sie daher einen doppelten Zaun verwenden. Da Sie eine beliebige Anzahl von Backticks oder Tilden verwenden können, um einen Codeblock einzuzäunen (solange die Anfangs- und Endanzahl übereinstimmen, können Sie einfach zwei Zäune unterschiedlicher Länge verwenden. Beispiel:

    `````
    ```
    Actual fenced code
    ```
    `````

[Table of contents](#toc)

