---
{"dg-publish":true,"permalink":"/3-resources/obsidian-benutzung/outlook-integration-anleitung/","created":"2024-04-14T21:35:41.677+02:00","updated":"2024-04-14T21:36:44.449+02:00"}
---


In dieser Anleitung beschreibe ich die notwendigen Schritte in Outlook und Obsidian, um Obsidian in einen [[3 Resources/Obsidian Benutzung/Outlook\|Outlook]]-Workflow zu integrieren.

# Obsidian

Plugins installieren:

- https://github.com/Vinzent03/obsidian-advanced-uri

# Windows Registry

Folgendes in eine Textdatei schreiben und diese in `outlook.reg` umbenennen. Anschließend ausführen.

```
Windows Registry Editor Version 5.00

[HKEY_USERS\S-1-5-21-2418847262-3847352916-1284767363-2812_Classes\Outlook]
@="URL:Outlook Folders"
"URL Protocol"=""

[HKEY_USERS\S-1-5-21-2418847262-3847352916-1284767363-2812_Classes\Outlook\shell]

[HKEY_USERS\S-1-5-21-2418847262-3847352916-1284767363-2812_Classes\Outlook\shell\open]

[HKEY_USERS\S-1-5-21-2418847262-3847352916-1284767363-2812_Classes\Outlook\shell\open\command]
@="\"C:\\Program Files\\Microsoft Office\\root\\Office16\\OUTLOOK.EXE\" /select \"%1\""
```

## QueryBuilder

Wenn man bessere Filter bauen möchte in Outlook (z.B. um Suchordner ordentlich nutzen zu können), fügt man unten noch folgende Zeile an, welche den QueryBuilder aktiviert.

```

[HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\QueryBuilder]
```

# Outlook

## Dev-Tools aktivieren

Einmal nachvollziehen:
https://learn.microsoft.com/en-us/office/vba/outlook/how-to/using-visual-basic-to-customize-outlook-forms/run-in-developer-mode-in-outlook

Im Trust Center von Outlook noch Makros aktivieren: Datei->Optionen->Trust Center->Einstellungen->Makroeinstellungen->Benachrichtigungen für digital signierte Makros. Alle anderen Makros sind deaktiviert.

## VBA Makro

Im neuen Reiter im Ribbon Entwicklertools -> Visual Basic auswählen.

Standardmäßig fehlt eine notwendige Funktion bei den Makros. Der muss erst noch importiert werden. Also einmal oben im Reiter: Macro Tools->Extras->Verweise->Durchsuchen-> Wähle
`C:\WINDOWS\SYSTEM32\FM20.DLL` -> ok

Nicht signierte Makros sind gesperrt. Also einmal unser eigenes Skript selbstsignieren: 

Erst ein eigenes Cert anlegen (womöglich nicht nötig, falls ein Cert schon vorhanden ist): Einmal das Programm `C:\Program Files\Microsoft Office\root\Office16\SELFCERT.EXE` ausführen.
Dieses nun unter Extas -> Digitale Signatur auswählen.

Nun folgenden Code als Makro unter dem Namen `ThisOutlookSession` (ist standartmäßig angelegt und ausgewählt) kopieren.

```
Function SetClipBoardText(ByVal Text As Variant) As Boolean
SetClipBoardText = CreateObject("htmlfile").parentWindow.ClipboardData.SetData("Text", Text)
End Function

Function GetLinkFromItem(ByVal objMail As Object) As String

If objMail.Class = olMail Then
    GetLinkFromItem = "[MAIL: " & objMail.Subject & " (" & objMail.SenderName & ")](outlook:" & objMail.EntryID & ")"
ElseIf objMail.Class = olAppointment Then
    GetLinkFromItem = "[MEETING: " & objMail.Subject & " (" & objMail.Organizer & ")](outlook:" & objMail.EntryID & ")"
ElseIf objMail.Class = olTask Then
    GetLinkFromItem = "[TASK: " & objMail.Subject & " (" & objMail.Owner & ")](outlook:" & objMail.EntryID & ")"
ElseIf objMail.Class = olContact Then
    GetLinkFromItem = "[CONTACT: " & objMail.Subject & " (" & objMail.FullName & ")](outlook:" & objMail.EntryID & ")"
ElseIf objMail.Class = olJournal Then
    GetLinkFromItem = "[JOURNAL: " & objMail.Subject & " (" & objMail.Type & ")](outlook:" & objMail.EntryID & ")"
ElseIf objMail.Class = olNote Then
    GetLinkFromItem = "[NOTE: " & objMail.Subject & " (" & " " & ")](outlook:" & objMail.EntryID & ")"
Else
    GetLinkFromItem = "[ITEM: " & objMail.Subject & " (" & objMail.MessageClass & ")](outlook:" & objMail.EntryID & ")"
End If

End Function

Function ObsidianTodo(txtObsLink As String)
Dim URL As String

URL = "obsidian://advanced-uri?daily=true&data=%0A" & txtObsLink & "&mode=append"
CreateObject("Shell.Application").ShellExecute (URL)

End Function

'Moves the mail to archive and add todo
Sub MoveAndTodo()
Dim objMail As Object
Dim newMail As Object
Dim txtObsLink As String

'One and ONLY one message muse be selected
If Application.ActiveExplorer.Selection.Count <> 1 Then
MsgBox ("Select one and ONLY one message.")
Exit Sub
End If

Set objMail = Application.ActiveExplorer.Selection.Item(1)

If objMail.Class <> olMail Then
MsgBox ("Only mail are supported.")
Exit Sub
End If

Set myNameSpace = Application.GetNamespace("MAPI")
Set myDestFolder = myNameSpace.Folders(objMail.Parent.Store.DisplayName).Folders("Archiv")
Set newMail = objMail.Move(myDestFolder)

ObsidianTodo ("- [ ] " + GetLinkFromItem(newMail))

End Sub


'Adds a link to the currently selected message to the clipboard
Sub ObsidianLink()

Dim objMail As Object
Dim exito As Boolean

Dim doClipboard As New DataObject

'One and ONLY one message muse be selected
If Application.ActiveExplorer.Selection.Count <> 1 Then
MsgBox ("Select one and ONLY one message.")
Exit Sub
End If

Set objMail = Application.ActiveExplorer.Selection.Item(1)

doClipboard.SetText GetLinkFromItem(objMail)
doClipboard.PutInClipboard

exito = SetClipBoardText(txtObsLink)

End Sub
```

Speichern schließen.

## Ribbon anpassen

Für einen schnellen Zugriff kann man nun unter Datei->Optionen->Menüband anpassen die neuen Funktionen hinterlegen. 

Die beiden dafür nötigen Funktionen sind unter der Kategorie `Makros` im linken Auswahlfeld zu finden. Sobald Du eines der Makros auswählst, wirst Du nach einem Namen und Icon gefragt. Fühl Dich da frei, dass so anzupassen, wie du magst.

Für mich selbst habe ich dafür unter `Start (E-Mail)` 2 Aktionen hinterlegt. Einmal `add Todo` und `Get link`.

Die Funktion `ObsidianLink` kopiert die ID des aktuellen Elementes in den Zwischenspeicher. (Funktioniert auch auf Terminen und Aufgaben).
`MoveAndTodo` verschiebt die aktuelle E-Mail (falls keine ausgewählt ist, gibts ne Fehlermeldung) in den Archivordner und erstellt einen Eintrag in die Notiz für den heutigen Tag / DailyNote. Gibts keine, wird eine erstellt. Dafür ist das Plugin von Obsidian zuständig. Dort kannst Du das verhalten auch anpassen.

Hinweis: Das verschieben der Mail in den Archivordner ist notwendig, da die ID sich ändert, sobald eine Mail in einen Ordner verschoben wird. WIllst Du also die Mail in einen anderen Ordner verschieben, dann ist die erste Funktion dein Freund. Oder Du passt das Makro an.

---

Ich nutze Suchordner, um Mails in Ordner zu sortieren. Daher ist das mit dem Archiv ein super Anlass für Dich, diese auch einmal auszuprobieren. Auf youtube gibt es tolle Tutorials dafür. Mit dem Querybuilder von oben kriegst du bestimmt gute Filter hin und erleichterst Dir die Einordnung von Mails.
