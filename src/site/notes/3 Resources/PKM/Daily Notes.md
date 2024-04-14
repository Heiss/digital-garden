---
{"dg-publish":true,"permalink":"/3-resources/pkm/daily-notes/","created":"2024-04-14T12:46:28.250+02:00","updated":"2024-04-14T12:57:55.418+02:00"}
---


Das Core Plugin "Daily Notes" erstellt mir im Ordner "6 Journal" und dem Dateiformat `YYYY/MM/YYYY-MM-DD ddd` jeden Tag eine neue Datei, in der ich meine Gedanken und Aufgaben aufschreibe, welche nicht direkt mit einem Projekt oder einer Ressource zuzuordnen sind. Zusammen mit dem Plugin [GitHub - liamcain/obsidian-calendar-plugin: Simple calendar widget for Obsidian.](https://github.com/liamcain/obsidian-calendar-plugin) ist es gut möglich, die Übersicht der letzten Tage und Wochen zu behalten. Das Plugin zeigt dann auch an, ob die Aufgaben der letzten Tage erledigt wurden (ein kleiner Punkt im Kalender).

Mein Template ist sehr schmal gehalten, um nicht vom wesentlichen abzulenken. Es enthält ein kleines Snippet mithilfe des Plugins [GitHub - SilentVoid13/Templater: A template plugin for obsidian](https://github.com/SilentVoid13/Templater) und [GitHub - javalent/dice-roller: Inline dice rolling for Obsidian.md](https://github.com/javalent/dice-roller) womit ein zufälliges Zitat aus [[3 Resources/Verhalten/The Daily Stoic Journal von Ryan Holiday/The Daily Stoic Journal von Ryan Holiday\|The Daily Stoic Journal von Ryan Holiday]] genommen und eingefügt wird.

Weiterhin wird noch mittels [GitHub - blacksmithgu/obsidian-dataview: A data index and query language over Markdown files, for https://obsidian.md/.](https://github.com/blacksmithgu/obsidian-dataview) eine Übersicht aller an diesem Tag erstellten Dateien erzeugt. Darunter kommen dann die Notizen und Aufgaben des Tages.


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





# Stoic Quote

`<% tp.user.print(`dice-mod: [[3 Resources/Verhalten/The Daily Stoic Journal von Ryan Holiday/Gedanken\|3 Resources/Verhalten/The Daily Stoic Journal von Ryan Holiday/Gedanken]]|paragraph`) %>`

----

# Created Files Today


{ .block-language-dataview}

# Notices & Marks

- 


</div></div>


Dafür ist außerdem noch folgendes Script notwendig:
![[print.js]]