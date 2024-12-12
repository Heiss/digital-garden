---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/erfolgreiche-team-patterns/","created":"2024-11-11T08:59:48.247+01:00","updated":"2024-04-28T16:53:17.353+02:00"}
---


Bereits vor den [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team Topologies\|Team Topologies]] gab es erfolgreiche Entwürfe für Teams. Hier werden einige vorgestellt.

Feature-Teams sind cross-funktionale Teams, welche ein gesamtes Features, kundenzentriert und ganzheitlich konstant ausliefert. Ihr Deployment muss also nicht synchronisiert werden und können so schneller auf Erkenntnisse, z.B. durch Nutzungs- und Performancemetriken, reagieren.

Dafür benötigt es ein hohes Maß an Erfahrung und Teamreife, sodass sie auch der "Boy-Scout Regel" folgen können, da sie mehrere Codebasen und verschiedene Techniken anfassen müssen, um das neue Feature zu erschaffen. Sie müssen dafür Sorge tragen, dass die [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/technische Schulden\|technischen Schulden]] nicht zu hoch werden. Sind zusätzlich die Besitzrechte (Ownership) der Codes nicht eindeutig geklärt, so wird der Code degenerieren und das Vertrauen zwischen den Teams und in den Teams selbst wird durch die Fehlschläge zerrieben.

> [!NOTE] Boy-Scout Regel
> Hinterlasse den Code besser als Du ihn vorgefunden hast.

Hier können Techniken von DevOps helfen, z.B. durch automatische Tests oder Kontrollen von Codebasen anhand von Heuristiken.
Um die Kommunikation von Subsystemen, dessen Teams und das gewünschte Design in Einklang zu halten, werden neue Rollen benötigt wie Systemarchitekten, Systemowner etc.

Product Teams besitzen den gesamten Code eines Produktes, benötigen Hilfen von Support-Teams wegen der kognitiven Belastung. Kompletiert wird diese Dreifaltigkeit durch die Cloud-Teams bzw. Infrastructure Teams, klassische Operator, welche dabei helfen, die Software in den Betrieb zu nehmen durch eine leicht zu nutzende Plattform. Es wird dabei darauf geachtet, nicht selbst die Software aufzusetzen und damit das ursprüngliche Team zu entmündigen, sondern sie zu befähigen.
