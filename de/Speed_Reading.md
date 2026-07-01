# <%= @title %>

Speed ​​Read ist ein Lesemodus im RSVP-Stil, der jeweils ein Wort in einer fokussierten Überlagerung anzeigt.

## So funktioniert Speed ​​Read

Speed ​​Read verwendet eine Methode namens **Rapid Serial Visual Presentation** (RSVP). Anstatt Ihren Blick über Textzeilen zu bewegen, erscheinen die Wörter an einer festen Position. Dadurch werden die Augenbewegungen, Zeilenwechsel und Rückwärtsbewegungen reduziert, die normalerweise beim Lesen auftreten, was sich zum Überfliegen, Wiederholen von vertrautem Material oder zum schnellen Durchblättern von Texten eignet, ohne den Überblick zu verlieren.

Die Methode ist keine Zauberei und garantiert kein besseres Verständnis bei sehr hohen Geschwindigkeiten. Das Leseverständnis hängt immer noch von der Komplexität des Textes, Ihrer Vertrautheit mit dem Thema und der WPM-Einstellung ab. Bei dichtem oder unbekanntem Material ist eine mäßige Geschwindigkeit in der Regel effektiver als eine möglichst hohe Geschwindigkeit.

Der rote Buchstabe markiert den visuellen Ankerpunkt des Wortes, der manchmal auch **optimaler Erkennungspunkt** genannt wird. Mit anderen Worten, Leser erkennen das Wort am effizientesten, wenn ihr Blick leicht links von der Mitte landet und nicht auf den ersten Buchstaben. Indem der Ankerpunkt an der gleichen Stelle bleibt und hervorgehoben wird, gibt Speed ​​Read Ihrem Auge ein konsistentes Ziel. Das Ergebnis ist eine geringere Neufokussierung zwischen den Wörtern und ein gleichmäßigerer Rhythmus beim Fortschreiten des Textes.

## Öffnungsgeschwindigkeit lesen

Verwenden Sie **Vorschau > Speed ​​Read**, den Eintrag **Speed ​​Read** im Zahnradmenü des Vorschaufensters, oder drücken Sie {% kbd ctrl opt S %}. Der Menüpunkt ist verfügbar, wenn ein Markdown-Vorschaudokumentfenster aktiv ist (es ist für Rohvorschauen von HTML deaktiviert und wenn kein Dokument geöffnet ist).

Wenn Speed ​​Read geöffnet wird, wird es im angehaltenen Zustand gestartet, sodass Sie sich vor Beginn der Wiedergabe orientieren können.

<Video steuert preload="metadata" poster="images/speedread-poster.png">
  <source src="images/speedread.webm" type="video/webm">
  <source src="images/speedread.mp4" type="video/mp4">
  Ihr Browser unterstützt das Speed Read-Demovideo nicht.
</video>
<p><em>Speed Read-Overlay mit Wiedergabesteuerung, Synchronisierungsoption und Hilfezugriff.</em></p>

## Overlay-Steuerelemente

Sobald das Overlay sichtbar ist, sind diese Tasten verfügbar:

| Verknüpfung | Funktion |
| :-- | :-- |
| {% kbd space %} | Wiedergabe/Pause |
| {% kbd [ %} | Zum Absatzanfang springen (erneut drücken, um zum vorherigen Absatz zu gelangen) |
| {% kbd ] %} | Zum Anfang des nächsten Absatzes springen |
| {% kbd left %} | Lesegeschwindigkeit (WPM) verringern |
| {% kbd right %} | Lesegeschwindigkeit erhöhen (WPM) |
| {% kbd esc %} | Ausgangsgeschwindigkeit lesen |

Klammern werden für die Absatznavigation erfasst und Links-/Rechtspfeile werden für Geschwindigkeitsänderungen erfasst, sodass diese Tasten keine Vorschaunavigation auslösen, während Speed ​​Read geöffnet ist. Sie können auch auf die kreisförmige Schaltfläche **X** in der oberen linken Ecke des Overlays klicken, um es zu schließen.

Andere normale Vorschau-Navigationsverknüpfungen funktionieren weiterhin, während Speed ​​Read aktiv ist, einschließlich `t`/`gg` (oben), `G`/`b` (unten) und `,`/`.` (Kopfnavigation). Die vollständige Liste finden Sie unter [Preview Navigation](Keyboard_Shortcuts#preview-navigation).

Das Inhaltsverzeichnis kann auch beim Schnelllesen verwendet werden. Drücken Sie {% kbd cmd t %}, um es zu öffnen und zu navigieren, oder drücken Sie {% kbd f %}, um die Schnellsuche sofort auf die Navigation in den Dokumentköpfen zu konzentrieren.

## Ausgehend von einer Auswahl

Wenn beim Starten von Speed ​​Read in der Vorschau Text ausgewählt ist, wird bei der Wiedergabe der ausgewählte Text verwendet. Wenn keine Auswahl aktiv ist, verwendet Speed ​​Read den vollständigen Dokumenttext.

## Synchronisierung mit Bildlaufposition

Aktivieren Sie **Speed ​​Reading mit Scroll-Position synchronisieren** in {% prefspane Preview %} oder verwenden Sie das Kontrollkästchen im Speed ​​Read-Overlay, um die Vorschau und die Speed ​​Read-Position zusammenzuhalten.

Wenn diese Option aktiviert ist, beginnt Speed ​​Read mit dem aktuell oben in der Vorschau sichtbaren Inhalt und nicht am Anfang des Dokuments. Während die Wiedergabe fortschreitet, scrollt die Vorschau zusammen mit den angezeigten Wörtern.

Wenn Sie Speed ​​Read schließen, durch die Vorschau scrollen und das Overlay erneut öffnen, beginnt die Wiedergabe an der neuen sichtbaren Position. Wenn Sie das Overlay-Kontrollkästchen aktivieren, nachdem Speed ​​Read bereits geöffnet ist, wird die Wiedergabe auf die aktuelle Bildlaufposition zurückgesetzt und von dort aus fortgesetzt.

## Erinnerte Geschwindigkeit

Der WPM-Wert wird automatisch gespeichert, wenn Sie ihn mit {% kbd ← %} und {% kbd → %} ändern. Ihre gewählte Geschwindigkeit wird bei der nächsten Verwendung von Speed ​​Read wiederhergestellt.