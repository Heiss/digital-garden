---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/team-first-boundaries/","created":"2024-04-28T15:37:07.296+02:00","updated":"2024-04-28T16:47:18.327+02:00"}
---


Viele Probleme kommen daher, dass Grenzen zwischen den Teams und ihren Verantwortlichkeiten unklar oder ungeklärt bleiben. Das wird dann noch häufig durch die Softwarearchitektur verschleiert, sodass die entsprechenden Dienste stark verknüpft miteinander sind. Dadurch wird die Software ein Monolith.
Um die Software wieder zu entkoppeln, kann das Konzept des [[Bounded Contexts\|Bounded Contexts]] des [[Domain Driven Design\|Domain Driven Design]] verwendet werden, um Grenzen mit klaren Verantwortlichkeiten zu erzeugen. Dabei müssen wir aber auch die kognitive Belastung jedes involvierten Teams berücksichtigen, wenn wir lose gekoppelte Dienste erzeugen wollen.
Falls der Monolith an den falschen Stellen aufgespalten wird, weil diese Dinge nicht berücksichtigt wurden, so kann ein distributed Monolith entstehen, welcher dieselben Eigenschaften des Monolithen besitzt, nun aber noch schwieriger zu managen ist, da er auf mehrere Services aufgeteilt ist, aber so stark verknüpft ist, dass man nichts gewonnen hat. 

Dieser Monolith kann durch verschiedene Stellen im Stack entstehen:
- Application monolith: durch die Applikation selbst, welche eine einzige Software ist, aber viele Abhängigkeiten besitzt
- Joined-at-the-database: die Abhängigkeit entsteht in der Datenbank und die Nutzung der Daten
- coupled Releases: Das Ausliefern kann nur in Zusammenspiel mit anderen Diensten funktionieren, wodurch das eigenständige ausliefern unmöglich wird.
- Monolithic model: Ein Model wird in sämtlichen Teilen der Software verwendet, wodurch Änderungen nur schwer möglich wird (single view of the world) und das Model nicht für die derzeitige Nutzung angepasst ist
- Monolithic Thinking (Standardization): Unnötige Begrenzungen in der Technologie und Implementierungsansätze beschneiden das Team dabei, die richtigen Werkzeuge zu verwenden
- Monolithic Workplace (Open-Plan Office): Alle Büros sind gleich aufgebaut und können so unnötig Interaktionen zu stark fördern oder behindern, was die Kopplung der Systeme erschwert oder ungewollt fördert.

Am Ende ist es wichtig, dass die Grenzen der Softwarekomponente so gewählt werden, dass die kognitive Belastung kein Team überlastet. Dies ist also ein Henne-Ei-Problem, wenn man ein Team an den Business-Fluss anpassen soll, aber gleichzeitig die Software, welches diesen Fluss nachempfunden ist, an das Team angepasst und zerlegt werden soll. Dadurch wird ein Team-First Ansatz notwendig, um dieses Problem zu lösen. Um jedoch eine Intuition zu erhalten, sollte man sich den [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Fracture Planes\|Bruchstellen]] in seiner Domäne bewusst sein.
