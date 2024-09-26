---
description: Technische Dokumentation
icon: info
---

# QuickIndex Zurücksetzen

**Funktionsweise:** Die Methode `btnResetQuickIndex_Click` wird aufgerufen, wenn der Benutzer den ' QuickIndex zurücksetzen ' Button klickt, um die QuickIndex-Einstellungen zurückzusetzen.

#### Warum zurücksetzen?

Die Fensterparamater für Quickindex sind außerhalb eines verwendbaren Bereiches und müssen zurückgesetzt werden. Das Dokument wird nicht angezeigt!

**Beschreibung:**

1. **Registry-Pfade:** Zwei Pfade zu den Registry Schlüssel werden definiert:
   * `keyName`: Pfad zu `Software\pro effectus\topfact6 MyWork\DockManager`.
   * `keyName2`: Pfad zu `Software\topfact\topfact6 MyWork\DockManager`.
2. **Schlüssel öffnen und löschen:**
   * Es wird versucht, die Registry-Schlüssel im aktuellen Benutzerbereich zu öffnen.
   * Existiert der Schlüssel, wird der Unterschlüssel `frmQuickIndex` und sein Inhalt gelöscht.
3. **Popup-Meldung:** Nach dem Zurücksetzen erscheint eine Meldung: "Die QuickIndexeinstellungen wurden zurückgesetzt."
4. **Fehlerbehandlung:** Tritt ein Fehler auf, wird er im `catch`-Block unterdrückt, ohne eine spezifische Fehlermeldung anzuzeigen.

Link zum Teil des Codes von dieser Funktion:  [<mark style="color:blue;">Link</mark>](https://github.com/topfact-AG/topfact6/blob/97253914e8f78c153a791c816fd44a15f42987ed/topfact.MyWork/topfact.MyWork/Forms/Settings/frmUserSettings.cs#L378)
