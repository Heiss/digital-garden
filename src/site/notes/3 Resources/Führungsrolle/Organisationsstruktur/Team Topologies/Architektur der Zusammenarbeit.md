---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/architektur-der-zusammenarbeit/","created":"2024-04-28T16:28:13.711+02:00","updated":"2024-04-28T16:47:18.255+02:00"}
---


Durch Conways Law wissen wir, dass wir erst eine Softwarearchitektur brauchen, bevor wir eine Teamorganisation aufsetzen können. Ansonsten werden die Kommunikationspfade uns eine Softwarearchitektur diktieren.

Michael Nygard:
> Teamzuweisungen sind der erste Entwurf einer Architektur.

Praktischerweise haben sich folgende Konzepte als gute Praxis für Architekturen herausgestellt:
- Loose gekoppelte Komponenten haben nur kleine Abhängigkeiten gegenüber anderen
- Komponenten mit einer hohen Kohäsion / Zusammenhalt haben klare Verantwortlichkeiten, sind klar abgegrenzt zu anderen Komponenten und interne Elemente sind stark voneinander verbunden
- Klare und angemessene Versionskompatibilität
- Klare und angemessene Interteam Testfähigkeiten

Halten wir die Komponenten so klein, dass sie von einem Team bearbeitet werden können, so erstellen wir eine "Architektur der Zusammenarbeit" (MacCormack), erhöhen die Fähigkeit, wie viele Personen an der Software arbeiten können und minimieren die Größe der notwendigen Änderungen in unserem System.
