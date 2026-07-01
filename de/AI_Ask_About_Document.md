# <%= @title %>

„Ask About Document“ verwendet **Apple Intelligence** und das in neueren Versionen von macOS integrierte geräteinterne Sprachmodell, um Ihre Markdown-Vorschau zusammenzufassen und Fragen zu ihrem Inhalt zu beantworten. Die gesamte Verarbeitung erfolgt auf Ihrem Mac; Für diese Funktion wird der Dokumenttext nicht an die Server von Marked oder an KI-Dienste von Drittanbietern gesendet.

## Was Apple Intelligence bietet

Apple Intelligence ist Apples System für generative Funktionen auf dem Gerät. Marked nutzt das **Foundation Models**-Framework von Apple, um auf dasselbe Modell auf dem Gerät zuzugreifen, das die Systemschreibtools antreibt und direkt in Marked für dokumentenbezogene Aufgaben verfügbar gemacht wird.

Marked sendet den Klartext Ihres Dokuments (aus Gründen der Übersichtlichkeit wurde die Syntax von Markdown entfernt) an dieses lokale Modell. Das Modell generiert Zusammenfassungen, Gliederungen und Antworten in einem schwebenden Bereich neben Ihrem Vorschaufenster. Da das Modell lokal ausgeführt wird, funktioniert es offline, sobald Apple Intelligence eingerichtet ist und der Download des Systemmodells abgeschlossen ist.

Apple Intelligence eignet sich am besten für Sprachaufgaben wie Zusammenfassungen, Gliederungen, das Extrahieren wichtiger Punkte und das Beantworten von Fragen zu bereitgestelltem Text. Es handelt sich nicht um einen allgemeinen Codierungsassistenten oder Rechner, und sehr lange Dokumente werden in Abschnitten behandelt, sodass die Ergebnisse innerhalb der Kontextgrenzen des Modells bleiben.

## Systemkompatibilität

„Nach Dokument fragen“ wird nur angezeigt, wenn Ihr Mac die Funktion ausführen kann.

**Erforderlich:**

- **macOS 26 (Tahoe)** oder höher
- Ein **Mac mit Apple Intelligence-Unterstützung** (Apple-Silicon-Macs, die die Geräteanforderungen von Apple erfüllen)
- **Apple Intelligence aktiviert** in den Systemeinstellungen

**Nicht unterstützt:**

– Intel-Macs und andere Macs, die für Apple Intelligence als nicht berechtigt markiert sind
- macOS-Versionen vor Tahoe 26
- Rohe **HTML-Vorschauen** (die Funktion gilt für Markdown- und textbasierte Dokument-Workflows)

Wenn Ihr Mac die Voraussetzungen erfüllt, das Menüelement jedoch fehlt, bestätigen Sie, dass Apple Intelligence aktiviert ist und dass Sie einen aktuellen Build von Marked ausführen, der diese Funktion enthält. Das Menü wird auf nicht unterstützten Systemen vollständig ausgeblendet und nicht im deaktivierten Zustand angezeigt.

## Aktivieren von Apple Intelligence

1. Öffnen Sie **Systemeinstellungen**.
2. Gehen Sie zu **Apple Intelligence & Siri** (oder **Apple Intelligence**, abhängig von Ihrer macOS-Version).
3. Aktivieren Sie **Apple Intelligence** und führen Sie alle von Apple angeforderten Einrichtungsschritte aus.
4. Warten Sie, bis der Download des Modells auf dem Gerät abgeschlossen ist, wenn Sie dazu aufgefordert werden. Bis das Modell fertig ist, zeigt Marked möglicherweise den Menüpunkt an, zeigt jedoch eine Meldung an, dass Apple Intelligence noch vorbereitet wird.

Marked enthält keine separate Einstellung für diese Funktion. Die Verfügbarkeit richtet sich nach dem von macOS gemeldeten Systemmodellstatus.

## Öffnung „Nach Dokument fragen“.

Öffnen Sie das Panel mit einer der folgenden Methoden:

- **Vorschau > Nach Dokument fragen…**
- Tastaturkürzel {% kbd shift ctrl cmd I %} (während ein Markdown-Vorschaudokument das aktive Fenster ist)

Das Bedienfeld wird an der linken Seite des Dokumentfensters angedockt. Sie benötigen ein offenes Dokument mit lesbarem Text; Ein leeres Dokument oder eine Nur-HTML-Vorschau bietet den Befehl nicht an.

## Das Fenster „Nach Dokument fragen“.

Das Panel ist wie eine einfache Chat-Ansicht organisiert:

- **Voreingestellte Aktionen** oben für häufige Aufgaben
- Ein **Antwortbereich** in der Mitte, in dem Zusammenfassungen und Antworten angezeigt werden (Streaming, während sie generiert werden)
- Ein **Fragenfeld** unten, in das Sie benutzerdefinierte Fragen eingeben können, mit den Schaltflächen **Fragen** und **Abbrechen**

Nachdem eine Antwort abgeschlossen ist, kehrt der Fokus zum Fragefeld zurück, sodass Sie ohne Klicken eine weitere Frage stellen können.

### Voreingestellte Aktionen

| Aktion | Was es tut |
| :-- | :-- |
| **Dokument zusammenfassen** | Erstellt eine kurze, zusammenhängende Zusammenfassung des gesamten Dokuments. Lange Dokumente werden in Abschnitten zusammengefasst und zusammengefasst. |
| **Auswahl zusammenfassen** | Fasst nur den aktuell in der Vorschau ausgewählten Text zusammen. Wählen Sie zuerst den Text aus; Andernfalls werden Sie von Marked aufgefordert, eine Auswahl zu treffen oder „Dokument zusammenfassen“ zu verwenden. |
| **Umriss** | Erstellt mithilfe von Überschriften und Aufzählungspunkten einen hierarchischen Überblick über die Dokumentstruktur. |
| **Wichtige Punkte** | Listet die wichtigsten Punkte aus dem Dokument als Aufzählungsliste auf. |

Voreingestellte Aktionen erfordern keinen Text im Fragefeld. Klicken Sie auf eine Schaltfläche und warten Sie auf die Antwort im Panel oben.

### Stellen Sie Ihre eigenen Fragen

1. Geben Sie eine Frage in das Feld unten im Panel ein, zum Beispiel „Welches Problem löst dieses Dokument?“ oder „Wer ist die Zielgruppe?“
2. Drücken Sie **Return** oder klicken Sie auf **Ask**.
3. Lesen Sie die Antwort, während sie in den Antwortbereich gelangt.

Bei Fragen zu einer bestimmten Passage **wählen Sie diesen Text in der Vorschau aus**, bevor Sie fragen. Marked sendet die Auswahl als Kontext statt des gesamten Dokuments, wenn eine Auswahl aktiv ist.

Klicken Sie auf **Abbrechen**, um eine laufende Anfrage zu stoppen.

## Beispiele

### Kurzer Überblick über einen langen Artikel

Öffnen Sie einen längeren Blogbeitrag oder Bericht in Marked, wählen Sie **Vorschau > Nach Dokument fragen…** und klicken Sie auf **Dokument zusammenfassen**. Nutzen Sie die Zusammenfassung, um zu entscheiden, ob Sie den gesamten Artikel lesen oder Ihr Gedächtnis auffrischen möchten, nachdem Sie sich eine Weile vom Entwurf getrennt haben.

### Notizen zu einem ausgewählten Absatz

Markieren Sie in der Vorschau einen dichten Absatz, öffnen Sie „Nach Dokument fragen“ und klicken Sie auf **Auswahl zusammenfassen**. Nützlich, wenn Sie nur eine kürzere Version eines Abschnitts benötigen.

### Strukturüberprüfung

Klicken Sie bei einem Entwurf mit vielen Überschriften auf **Gliederung**, um zu sehen, ob die Argumentation logisch verläuft, oder verwenden Sie **Hauptpunkte**, bevor Sie ein Dokument an jemand anderen senden, um zu überprüfen, ob die Hauptgedanken klar sind.

### Gezielte Fragen

Wenn keine Auswahl aktiv ist, geben Sie Fragen ein wie:

- „Was sind die drei wichtigsten Empfehlungen?“
- „Erwähnt dieses Dokument die Lizenzierung?“
- „Listen Sie alle genannten Termine oder Fristen auf.“

Stellen Sie bei aktiver Auswahl enger gefasste Fragen wie „Was sagt dieser Absatz über den Leser aus?“ oder „Formulieren Sie diese Idee in einem Satz um“ (das Modell antwortet zur Auswahl; Ihre Quelldatei wird nicht bearbeitet).

## Tipps und Einschränkungen

- **Datenschutz:** Die Verarbeitung erfolgt über das On-Device-Modell von Apple. Marked liest Ihren Dokumenttext weiterhin lokal, um diesem Modell Inhalte bereitzustellen; Behandeln Sie empfindliches Material entsprechend.
- **Genauigkeit:** Überprüfen Sie wichtige Fakten anhand Ihrer Quelle. KI-Zusammenfassungen können Details auslassen oder mehrdeutige Passagen falsch interpretieren.
- **Länge:** Extrem lange Dokumente werden in Blöcken verarbeitet. Zusammenfassungen und Antworten geben indirekt den vollständigen Text wieder; Um die Genauigkeit eines Abschnitts zu gewährleisten, wählen Sie zuerst diesen Abschnitt aus.
- **Sprache:** Die Ergebnisse richten sich nach den Sprachfunktionen des Systemmodells Apple Intelligence auf Ihrem Mac.
- **Ablehnungen:** Das System lehnt möglicherweise einige Anfragen aufgrund der Sicherheitsrichtlinien von Apple ab.

Wenn „Nach Dokument fragen“ nicht verfügbar ist, überprüfen Sie die Systemeinstellungen auf den Status „Apple Intelligence“ und stellen Sie sicher, dass Sie eine Vorschau eines Dokuments „Markdown“ auf einem unterstützten Mac mit macOS 26 oder höher anzeigen.