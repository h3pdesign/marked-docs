# Custom Prozessorberechtigungen in der MAS-Version [custom-processor-permissions-in-mas-version]

Aufgrund von Sandboxing-Einschränkungen ist die Mac App Store-Version von Marked nicht in der Lage, bestimmte Arten von Binärtools als benutzerdefinierte Prozessoren auszuführen. Wenn Sie auf diese Einschränkung stoßen, können Sie einige Schritte ausprobieren.

1. Stellen Sie sicher, dass Sie zu den **Marked**-Einstellungen ({% kbd cmd , %}) im Bereich **Erweitert** gegangen sind und auf „Berechtigungen aktualisieren“ geklickt haben. Dadurch wird versucht, Marked Zugriff auf Ihr gesamtes Standardlaufwerk zu gewähren, wodurch Probleme mit Skripten und Dienstprogrammen behoben werden, die auf temporäre Ordner und nicht standardmäßige Speicherorte zugreifen müssen.
2. Versuchen Sie es mit einem Skript. Verweisen Sie in einem Shell-Skript auf das Dienstprogramm, das Sie ausführen möchten (Multimarkdown, Kramdown usw.). Es kann ein Bash-, Ruby-, Perl- oder Python-Skript sein. Stellen Sie dann in den erweiterten Einstellungen den Prozessor auf die zugehörige Shell oder ausführbare Datei und die Parameter auf den Speicherort des Skripts ein. Ich kann zum Beispiel ein Bash-Skript erstellen, das unter ~/scripts/mmd_wrapper.sh gespeichert ist:

#!/bin/bash
        Katze | /usr/local/bin/multimarkdown

Machen Sie es dann ausführbar (`chmod a+x ~/scripts/mmd_wrapper.sh`) und richten Sie meine Custom Prozessoreinstellungen ein:

Prozessor: /bin/bash
        Argumente: /Users/me/scripts/mmd_wrapper.sh
3. Einige ausführbare Dateien (insbesondere Pandoc) funktionieren im Sandboxing einfach nicht. Bitte kontaktieren Sie mich in diesem Fall über das bei der Ausführung erscheinende Fehlerfenster, um eine Crossgrade-Lizenz auf die Direktversion zu erhalten.

