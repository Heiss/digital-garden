---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/verbesserungstrigger/","created":"2024-06-23T19:46:00.582+02:00","updated":"2024-04-28T16:59:30.984+02:00"}
---


Änderungsprozesse an der Teamstruktur sind nicht leicht und es ist noch schwerer, den richtigen Moment zu finden. Zu lernen die verschiedene Hinweise und Muster kann dabei helfen, eine Verbesserungsüberlegung in der Organisation auszulösen. 

# Software ist zu groß für ein einzelnes Team geworden

Symptome:
- ein Startup hat mehr als 50 Angestellte (Dunbars number)
- Ein anderes Team wartet eine substantielle Zeit auf ein einziges anderes Team Änderungen vorzunehmen
- Änderungen an einzelnen Komponenten werden routiniert an dieselbe Person zugewiesen, obwohl diese Person bereits vollständig ausgelastet ist
- Teammitglieder beschweren sich über fehlende Dokumentationen

Erfolgreiche Systemen haben die Eigenheit, immer größer und größer zu werden; an Line of Codes, Features und zu berücksichtigende Kunden. Konnte zu Beginn jedes Teammitglied noch alles verstehen, so wird sich nach und nach eine Spezialisierung herausstellen. Diese selbstverstärkende Spezialisierung ist eine lokale Optimierung, welche einen negativen Effekt auf den kompletten Teamfluss haben kann. Es wird die Frage gestellt : "Wer weiß was?" statt "Was hat die höchste Priorität?" Dies wird in den Büchern [[The Phoenix Project\|The Phoenix Project]] und [[The DevOps Handbook\|The DevOps Handbook]] thematisiert.
Weiterhin wird das Team einen holistischen Blick auf das System verlieren, wodurch das Selbstvertrauen schwinden wird. Stabilität, Performance und Änderungsgeschwindigkeit des Systems werden abnehmen.

# Auslieferungskadenz nimmt ab

Symptome:
- Teammitglieder empfinden qualitativ, dass das Veröffentlichen von Änderungen länger dauert als sonst üblich
- die Metrik für Teamgeschwindigkeit oder -durchsatz zeigt über einen längeren Zeitraum klar nach unten
- Teammitglieder beschweren sich, dass der Auslieferungsprozess leichter und mit weniger Schritten sein sollte
- Work in Progress nimmt zu, während viele Arbeiten auf Änderungen von anderen Teams warten

In einem langlebigen Team sollten Verbesserungen an ihrem Prozess auch direkt zu Verbesserungen an ihren Metriken führen. Sollte dies nicht so sein, existieren starke Abhängigkeiten zu anderen Teams oder Technologien. Es ist also ein Hinweis darauf, dass eine [[hard dependency\|hard dependency]] sichtbar wird oder fehlende Kenntnisse das Team ausbremsen. Ebenfalls kann es ein Hinweis darauf sein, dass die [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/technische Schulden\|technischen Schulden]] inzwischen ein hohes Maß erreicht haben, sodass sie deutlich die Effizienzanstrengungen untergraben.

# Mehrere Businessdienste setzen auf eine große Anzahl darunterliegender Dienste

Symptome:
- ein [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Stream-aligned Team\|SAT]] hat nur einen limitierten Blick auf den Ende-zu-Ende Fluss innerhalb ihres Dienstbereiches
- es wird schwieriger einen reibungslosen und schnelles Änderungsfluss aufrechtzuerhalten durch die Anzahl und dessen Komplexität der Integrationen von Subsystemen
- Bestrebungen bestehende Dienste nachzunutzen wird immer aufwändiger und langwieriger.

Zum Beispiel in hoch regulierten Bereichen wie das Finanzbusiness gibt es viele Dienste, welche darunterliegende APIs verwenden, um ihre Aufgaben zu erfüllen. Damit nicht jedes [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Stream-aligned Team\|SAT]] mit jedem einzelnen Dienst interagieren muss, kann eine "innere Plattform" etabliert werden, um die DevEx hochzuhalten z.B. mit einer request-tracking correlation ID, Health checks, Servicelevel Objects, und APIs zur Diagnose. Vor allem Fehler in der Ausgabe eines Dienstes, welches bei einem anderen Dienst wiederverwendet werden soll, kann sonst zu einer langen und beschwerlichen Debug-Session führen.

Alternativ kann das [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Stream-aligned Team\|SAT]] auch für die Telemetrie- und Diagnosefähigkeit eines unterliegenden Systems verantwortlich gemacht werden, sodass sie für ihren Dienst und die benötigen Dienste sämtliche Werkzeuge selbst entwerfen und ihren Fluss so wieder beschleunigen können.
