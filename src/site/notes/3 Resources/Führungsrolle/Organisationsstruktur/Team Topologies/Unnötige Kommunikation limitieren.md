---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/unnoetige-kommunikation-limitieren/","created":"2024-06-23T19:46:00.578+02:00","updated":"2024-06-02T19:20:40.376+02:00"}
---


Nicht jede Kommunikation und Kooperation ist wertvoll. Deshalb ist es wichtig "Teamschnittstellen" festzulegen, um Erwartungen festzuhalten, welche Arbeit welche Kommunikation benötigt und vor allem, welche Arbeit keine brauchen soll. Es ist eben nicht so, dass mehr Kommunikation besser ist, vor allem nicht, wenn sie vorausgesetzt ist, um eine Tätigkeit zu erledigen.
Was gebraucht wird, ist fokussierte Kommunikation zwischen ausgewählten Teams. Unerwartete Kommunikation sind ein Hinweis auf fehlerhafte Strukturen im Organigramm oder missverständliche Abläufe.

> [!NOTE] Überlegung
> Hier kann [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/Kanban\|Kanban]] einen Hinweis geben. Denn es hilft dabei, Blocker zu identifizieren und nötige Diskussionen über Informationsbeschaffungen zu führen. Es hilft auch dabei, die nötige Kommunikation auf ein Minimum zu reduzieren und damit auch zu fokussieren auf spezielle Zustände einer Tatigkeit.
> Es ist also ersichtlich, dass die gewählte Methode zur Prozesssteuerung auch einen Einfluss auf die Organisationsstruktur haben kann und sollte. Eine Wechselwirkung ist, genau wie zwischen Organigramm und Softwarearchitektur, zu erkennen.


Wenn man sich die Kommunikation in der Organisation anschaut und sich diese nicht mit den erwarteten Pfaden deckt, so ist dies ein Hinweis darauf, dass das bestehende System nicht der anfallenden Arbeit folgt. (Wenn 2 Teams, welche nichts miteinander zu tun haben sollten, miteinander kommunizieren müssen, dann muss man den Fehler suchen.)
Ist die API nicht gut genug? Ist die Plattform falsch gewählt? Fehlt eine Komponente?
Wir sollten versuchen eine niedrige, sogar keine, Kommunikationsbandbeite zwischen Teams zu etablieren und dennoch Software sicher, effektiv und schnell bauen und veröffentlichen können. Dies kann schon dadurch gelingen, indem die Teams geografisch (verschiedene Büros, Etagen, Gebäude) getrennt sind oder indem sie verschiedene Tools (Messengingdienste) oder Channels für ihre Kommunikation nutzen müssen, das andere Team aber nicht für sie erreichbar sind.
Gleiches gilt für ein Team, welches mehrere Bereiche eines Systems bearbeiten; es kann Sinn ergeben, dieses Team aufzuspalten, sodass jeder Bereich einem Team zugehörig ist, jedoch nur, wenn es diese logische Trennung von Team und Systembereich gibt (Backend / Database).

# Nicht jeder muss mit jedem reden

Bei Many-to-many Kommunikation, z.B. durch "demokratische Meeting" (jeder wird eingeladen), besagt [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Conways Law]], dass monolithische, hoch verknüpfte, verschränkte, abhängige Systeme entstehen müssen, welche nicht fast flow unterstützen, denn es benötigt viel Kommunikation die Veränderungen zu entscheiden und umzusetzen.

> [!NOTE] Überlegung
> Ein Hinweis für eine solche Policy könnte sein, wenn mehrere Chats existieren, worin eine hohe Überschneidung der Teilnehmer existiert, denn "jeder soll die Nachrichten sehen".


Auf der einen Seite schränkt [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Conways law]] die Anzahl der Möglichkeiten der Architekturentwürfe aufgrund der Organigramms ein. Auf der anderen, besagt es auch aus, dass die Geschwindigkeit der Softwareauslieferung stark davon abhängt, wie viele Teams voneinander durch das Organigramm abhängig sind.
Fast Flow benötigt also eine Beschränkung der Kommunikation zwischen Teams. Kooperation und Kommunikation sind in Graubereichen gut, in der man Erforschen möchte und viel Expertise benötigt wird. Geht es aber um die Entwicklung und tägliche Arbeit, ist die Kommunikation ein unnötiger Mehraufwand.
Durch die Erkenntnis der Isomorphie zwischen Teamentwurf und Softwarearchitektur durch [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Conways Law]], kann man zwischen diesen beiden Gedankenwelten wandern und so neue Erkenntnisse für die andere erhalten, welche sich in der anderen Sicht womöglich schwieriger zu entdecken gewesen wäre.
