# <%= @title %>

Die Linkvalidierung pingt das Ziel einer URL an und prüft auf Fehler. Dies trägt dazu bei, defekte und ungültige Links in Ihrem veröffentlichten Dokument zu vermeiden und ist besonders nützlich für Blogger.

## Validierung einzelner Links

![][1]

   [1]: images/validate_single.png @2x width=832px height=267px class=center

Klicken Sie in der Vorschau auf einen Link und halten Sie ihn gedrückt, bis er blinkt. Lassen Sie ihn dann los, um das Link-Aktionsmenü zu öffnen. Wählen Sie „Link validieren“, um den Test auszuführen. Die Ergebnisse werden im Popup angezeigt.

## Validierung aller Links

![][2]

   [2]: images/screenshots/mainwindow-feature-urlvalidate-crop.jpg @2x width=1089px height=300px class=center

Wählen Sie „Alle Links validieren“ (Verknüpfung {% kbd ctrl cmd L %}) aus dem Zahnradmenü oder dem Rechtsklick-Menü. Alle Remote-Links im Dokument werden überprüft und die Ergebnisse werden in einem Popup angezeigt. Durch Klicken auf einen Link im Popup wird zum entsprechenden Link im Dokument gescrollt und dieser hervorgehoben.

Gültige URLs können im Popup mit der Schaltfläche „Gültige ausblenden“ oben ausgeblendet werden. Dadurch werden nur URLs angezeigt, die einen Fehlerstatus zurückgegeben haben.

Durch Drücken von Escape werden die Validierungsergebnisse ausgeblendet. Sie können mit {% kbd ctrl cmd L %} oder dem Ausrüstungsmenü wieder angezeigt werden.

## Automatische Validierung

Aktivieren Sie „URLs bei Aktualisierung automatisch validieren“ in den Vorschaueinstellungen (oder unten im Popup zur Linkvalidierung). Beim Laden des Dokuments werden die darin enthaltenen Links im Hintergrund getestet. Ein Dialog wird nur angezeigt, wenn Fehler vorliegen.

Um das Popup zu deaktivieren, deaktivieren Sie es in den Einstellungen oder deaktivieren Sie das Kontrollkästchen unten im Popup-Fenster.