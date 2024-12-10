---
{"dg-publish":true,"permalink":"/3-resources/softwarearchitektur/system-architektur/clean-architecture/","tags":["architecture"],"created":"2024-11-11T09:00:04.734+01:00","updated":"2024-11-01T21:46:31.620+01:00"}
---


Wendet man das [[3 Resources/Softwarearchitektur/System Architektur/SOLID Pattern\|SOLID Pattern]] auf eine Softwarearchitektur und führt eine Zwiebellogik ein, so entsteht die Clean Architecture. Wichtig hierbei ist, dass diese Architektur keine Aussage über das Deployment macht: Ob diese Architektur in einem Monolithen oder verschiedenen Microservices implementiert wird, ist nicht relevant. Vor allem im Bereich der Enterprisearchitekturen konnte sich dieses Typus etablieren.
Wichtig ist, dass zu Beginn der Erstellung die Geschäftslogik verstanden ist und diese sich nach Implementierung nur noch sehr selten ändern sollte.
![Pasted image 20241101212819.png](/img/user/4%20Archive/Assets/Pasted%20image%2020241101212819.png)
Aufbauend darauf, setzen dann die verschiedenen Anwendungsfälle auf diese innerste Schicht auf und implementiert verschiedene Arbeitsabläufe. UI etc. setzen dann wiederum darauf auf. Wichtig hierbei ist, dass Abhängigkeiten stets von außen nach innen gehen. Manchmal lässt sich dies nicht vermeiden. Um diese Eigenschaft dennoch aufrecht zu erhalten, nutzt man aus dem [[3 Resources/Softwarearchitektur/System Architektur/SOLID Pattern\|SOLID Pattern]] die *Dependency Inversion*-Methodik. Mithilfe dieser lassen sich zwar nicht die Abhängigkeiten in Abläufen vermeiden, aber die technische Abhängigkeiten umdrehen, um das gewünschte Ergebnis und damit die echten Arbeitsabläufe bei den Entwicklern nach den gewünschten Eigenschaften zu steuern.

# Hexagonale Architekturen

Eine Abwandlung dieser Architektur, sind die hexagonalen Strukturen. Diese unterscheiden sich lediglich in der visuellen Darstellung der Architektur und das es eine Vorder- und Rückseite gibt, welche Ein- und Ausgaben darstellen. Diese müssen nicht auf derselben Ebene liegen, wie sie es bei den Clean Architecture sein müssen. Dies erlaubt eine etwas flexiblere Struktur, ändert aber kaum etwas an der Komplexität.

# Kritik

Die Clean Architecture führen eine höhere Komplexität ein, um komplexe Arbeitsabläufe, vor allem im Enterprise-Segment, leichter wartbar zu halten. Halten sich nicht alle Entwickler an die Abhängigkeitsregel, so degeneriert die Architektur. Dies ist eigentlich nicht auszuschließen.
Es ist also notwendig, dass eine technische Analyse des Codes vorgenommen wird, woran die Abhängigkeit analysiert werden und ggf. Gegenmaßnahmen ergriffen werden, bevor diese Degeneration zu schwerwiegend wird. In der Enterprise-Sparte existieren hierfür einige Tools zur statischen Codeanalyse, z.B. [JArchitect](https://www.jarchitect.com).
Außerdem benötigt die Architektur mehr Aufwand bei der Erstellung der Struktur des Projekts, sowie Kommunikation zwischen allen Beteiligten und ist somit nur zu empfehlen bei Projekten mit einem größeren Bedarf an Struktur und vorheriger Analyse der Businesslogik.

# Überlegungen

- [Clean Architecture is NOT a project structure. | by Steve Bishop | Medium](https://medium.com/@stevebishop_89684/clean-architecture-is-not-a-project-structure-b158c9c4163f)
- [Clean Coder Blog](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
- [Hexagonal Architecture, there are always two sides to every story | by Pablo Martinez | SSENSE-TECH | Medium](https://medium.com/ssense-tech/hexagonal-architecture-there-are-always-two-sides-to-every-story-bc0780ed7d9c)
- [Hexagonal architecture (software) - Wikipedia](https://en.wikipedia.org/wiki/Hexagonal_architecture_(software))