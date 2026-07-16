# <%= @title %>

Die Funktion „Zum Bearbeiten scrollen“ in Marked verfolgt die Unterschiede zwischen dem letzten und dem letzten Update und versucht, den Punkt zu finden, an dem Sie Ihre letzten Änderungen vorgenommen haben. Marked verfolgt dies immer und in der Vorschau erscheint eine kleine rote Linie, die Ihnen den Ort der ersten erkannten Änderung anzeigt. Im Einstellungsfenster „Verhalten“ können Sie „Zur ersten Bearbeitung scrollen“ aktivieren. Wenn eine Vorschau aktualisiert wird, wird die Ansicht sanft zu dieser Position gescrollt.

Wenn „Zur ersten Bearbeitung scrollen“ deaktiviert ist, können Sie in der Vorschau jederzeit die Taste „e“ drücken, um zum letzten gespeicherten Bearbeitungspunkt zu gelangen.


### Hinweise zu „Zum Bearbeiten scrollen“ [notes-on-scroll-to-edit]

Dies ist eine tolle Funktion, wenn sie funktioniert, aber es gibt viele Komplikationen. Vor allem bei den ersten Aktualisierungen des Dokuments kann es beim Scrollen zu Rucklern kommen. Wenn sich Ihre Änderungen alle innerhalb eines sehr großen Elements (z. B. eines übermäßig langen Absatzes) befinden, kann es nur in die Nähe der Markierung gelangen. Wenn Sie am Ende des Dokuments ein oder zwei Wörter hinzufügen, wird die Änderungsmarkierung entsprechend im darüber liegenden Element positioniert, bis genügend Inhalt für die Verankerung im neuen Element vorhanden ist.