# <%= @title %>

[DEVONthink](https://www.devontechnologies.com/apps/devonthink) kann ausgewählte Markdown-Dateien mithilfe eines AppleScript direkt in Marked öffnen.

## Ausgewähltes Markdown in Marked öffnen

Verwenden Sie dieses Skript in DEVONthink, um die aktuelle Auswahl an Marked zu senden. Es überprüft, ob Sie etwas ausgewählt haben, bestätigt, dass es Markdown ist, und öffnet es dann mit `x-marked-3://` mit einem URL-codierten Dateipfad.

„Applescript
– Öffnen Sie die ausgewählte DEVONthink-Datei Markdown in Marked 3

Teilen Sie der Anwendungs-ID „DNtp“ mit.
	aktivieren
	
	sel auf Auswahl setzen
	wenn sel {} ist, dann
		Warnmeldung „Keine Auswahl“ anzeigen „Wählen Sie zuerst ein Markdown-Dokument in DEVONthink aus.“
		Rückkehr
	Ende wenn
	
	setze theRecord auf Punkt 1 von sel
	
	– Muss ein dateigestütztes Element sein
	setze p auf den Pfad des Datensatzes
	Wenn p ein fehlender Wert ist oder p „“ ist, dann
		Warnmeldung „Keine Datei“ anzeigen: „Das ausgewählte Element hat keinen Dateipfad.“
		Rückkehr
	Ende wenn
	
	-- Überprüfen Sie Markdown anhand der Erweiterung
	setze ext auf meine Kleinbuchstaben-Erweiterung(p)
	setze mdExts auf {"md", "markdown", "mdown", "mkd", "mkdn", "mdtxt"}
	Wenn mdExts ext nicht enthält, dann
		Warnmeldung „Nicht Markdown“ anzeigen: „Ausgewähltes Element ist kein Markdown-Dokument.“
		Rückkehr
	Ende wenn
Ende erzählen

setze encodedPath auf meinen urlEncode(p)
Setzen Sie markierteURL auf „x-marked-3://“ und encodedPath
Öffnen Sie den Standort markierteURL


auf KleinbuchstabenExtension(posixPath)
	Setzen Sie oldTIDs auf die Textelementtrennzeichen von AppleScript
	Setzen Sie die Textelementtrennzeichen von AppleScript auf „.“
	Teile auf Textelemente von posixPath setzen
	Setzen Sie die Textelementtrennzeichen von AppleScript auf oldTIDs
	
	Wenn (Anzahl der Teile) < 2, dann gib „“ zurück
	setze ext auf Element -1 der Teile
	return do Shell script „printf %s „ & Anführungszeichen von ext & „ | tr ‚[:upper:]‘ ‚[:lower:]‘“
Ende der Kleinbuchstaben-Erweiterung

auf URLEncode(s)
	-- URL-Pfad sicher für x-marked-3:// kodieren
	setze py auf „import sys, urllib.parse; print(urllib.parse.quote(sys.argv[1], safe='/'))“
	Rückkehr zum Shell-Skript „/usr/bin/python3 -c“ & Anführungszeichen von py & „ „ & Anführungszeichen von s
Ende URLEncode
„

## Im DEVONthink-Skriptmenü installieren

1. Kopieren Sie das obige Skript in den **Skript-Editor**.
2. Speichern Sie es als `Open in Marked.scpt`.
3. Öffnen Sie in DEVONthink das Menü **Skripte** und wählen Sie **Skriptordner öffnen**.
4. Verschieben Sie `Open in Marked.scpt` in den Ordner `Contextual Menu`.
5. Klicken Sie in DEVONthink mit der rechten Maustaste auf eine Datei und wählen Sie **Skripte -> In Marked.scpt öffnen**.

I> Marked kann auch `hook://` Assets auflösen, wenn es in {% prefspane Apps %} aktiviert ist; siehe [Hookmark](Hookmark.html).