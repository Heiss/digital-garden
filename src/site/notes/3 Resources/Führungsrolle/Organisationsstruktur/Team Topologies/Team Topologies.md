---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/team-topologies/","pinned":true,"created":"2024-04-28T15:43:24.088+02:00","updated":"2024-04-28T17:09:54.315+02:00"}
---


Kleine und simple Systeme sind ein wertvolles Ziel, [Lehman's laws of software evolution](https://en.wikipedia.org/wiki/Lehman%27s_laws_of_software_evolution)  zeigt uns aber, dass dies nicht für erfolgreiche Systeme gilt, denn der Druck neue Funktionen einzubauen und sich neuen Anforderungen anzupassen, wird dieses System automatisch degenerieren.

> [!NOTE] Buchempfehlung
> Das hier vorgestellte Konzept [Team Topologies](teamtopologies.com) stammt aus dem zugehörigen Buch von Matthew Skelton und Manuel Pais. Die hier verwendeten Bildern stammen ebenfalls aus dem Buch.

Die Team Topologies versucht [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Conways Law]] Rechnung zu tragen und durch eigenständig, unabhängigen Teams Systeme zu entwickeln, welche für einen schnellen Veränderungsfluss ausgelegt sind.

Das Konzept der Team Topologies besteht aus 4 Teamtypen und 3 [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Interaktionsmodi\|Interaktionsmodi]].
![Pasted image 20240416191308.png](/img/user/4%20Archive/Assets/Pasted%20image%2020240416191308.png)

Zusammen mit gut gesetzten Systemgrenzen und Teaminteraktionen, sind die folgenden 4 Teamarten alles, was man benötigt, um eine effektive [[3 Resources/Führungsrolle/Organisationsstruktur/Organisationsstruktur\|Organisationsstruktur]] für den Flow zu erstellen: [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Stream-aligned Team\|SAT]], [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Enabling Team\|ET]], [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Complicated Subsystem Team\|CST]] und [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Platform Team\|PT]].

![Pasted image 20240423080532.jpg](/img/user/4%20Archive/Assets/Pasted%20image%2020240423080532.jpg)

Sie sollten als eine Art Magnet für die Teams funktionieren, die Teams sollten also danach streben, eine der 4 Typen zu entsprechen. Dies reduziert die Ambiguität in der Organisation und erleichtert somit auch die Kommunikation. Als Startpunkt fungiert das [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Stream-aligned Team\|Stream-aligned Team]] und nur wenn wirklich nötig bis zu 2 complicated subsystem Teams.

> [!NOTE] Wo sind die Ops und Support Teams?
> Es gibt keine. Die Teams der 4 Typen sind cross-funktional und leben genau so lange, wie ihre erstellten Systeme. Es gibt keine Handover zu einem separaten Team. Sogar die SRE (Site Reliability Engineering) Teams, welche die Stabilität der Systeme erhöhen sollen, sind in den Typen enthalten. Die Stream-aligned Teams folgen der guten Auslieferungspraxis (CI/CD) und sind so für den Betrieb verantwortlich.

# Wozu Team Topologies?

Die unten genannten Organisationsproblemen stammen daraus, dass man [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Conways Law]] ignoriert hat beim Entwurf der Teamstrukturen. Verfolgt man einen Team-first Ansatz mit klaren Aufträgen und der Förderung von wichtigen Interaktionsmuster, welche den Arbeitsfluss und strategische Anpassungsfähigkeit priorisieren, die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Kognitive Belastung\|kognitive Belastung]] bewusst limitieren und [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Conways Law]] bei der Erstellung von Softwarearchitekturen berücksichtigen, kann man diese Probleme lösen und eine Teamstruktur als Schlüsselunterscheider für den zukünftigen Erfolg aufbauen.
Es ist das Ziel der Team Topologies, die Organisation zu befähigen, anpassungsfähig aufzustellen und dynamisch den richtigen Ort und Zeit zu finden, wann [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Collaboration\|Kollaboration]] benötigt wird im Arbeitsfluss und wann es besser ist, sich zu fokussieren und den Kommunikationsüberschuss zu reduzieren. 

## Probleme mit Organisationsdiagrammen

Viele Organisationen strukturieren ihre Angestellten und Teams so, dass sie kontraproduktiv zur modernen Softwareentwicklung sind. Sie setzen zu sehr auf die Diagramme und Matrizen, um Arbeit aufzuteilen und zu kontrollieren und scheitern damit die notwendigen Bedingungen aufzubauen, um Innovation zu fördern und dennoch schnell Änderungen auszuliefern.
Um in der heutigen Zeit zu bestehen, brauchen Organisation stabile, effektive Teammuster und -interaktionen. Sie müssen in selbstständige, eigenverantwortliche, fähige Teams als Grundlage für Agilität und Anpassungsfähigkeit investieren.
Es muss aufgehört werden, die Menschen in Teams als auswechselbare Individuen zu sehen, welche nur dem "richtigen" Prozess folgen und das "richtige" Tool einsetzen müssen, um erfolgreich zu sein. Um Menschen intrinsisch zu motivieren und ihnen eine realistische Chance zu geben, ihre beste Arbeit zu leisten, müssen wir die Menschen und Technologie als eine einzige Mensch-Computer- / Kohlenstoff-Silizium soziotechnisches Ökosystem verstehen.
Team Topologies ist ein adaptives Modell für Technologie-Organisationen, welche ein Design für das Business erlaubt, um Geschwindigkeit und Stabilität zu erreichen.

## Das Denken in Organigramme ist das Problem

In den meisten Unternehmen unterscheidet sich die gelebte Kommunikationsstrukturen drastisch zum Organigramm. Ein realistisches Bild würde dann entstehen, wenn das erwartete Organigramm und die echten, notwendigen Kommunikationen betrachtet werden würde. So kann die Distanz zur echten Arbeit erkannt und bessere Arbeitsprozesse für die wirkliche Arbeit identifiziert werden. Tiefgreifende Entscheidungen anhand des Organigramms ignorieren deren Effekte auf- und abwärts und sind meist auch nur lokaler Natur. Diese lokalen Änderungen optimieren nicht zwangsläufig die Entwicklungsgeschwindigkeit, obwohl sie das Organigramm verbessert. Es wird sich nicht auf den Arbeitsfluss konzentriert, sondern die reale Arbeit und die notwendigen Verantwortlichkeiten werden getrennt.

## Was kommt nach den Organigrammen

Es gibt 3 verschiedene organisatorische Strukturen in jeder Organisation nach Niels Pflaeging - Organize for Complexity:
- Formale Struktur (Organigramm) - unterstützt die Compliance
- Informelle Struktur - der Einflussbereich zwischen Individuen
- Wertschöpfungsstruktur - Wie Arbeit erledigt wird, basierend auf interpersonelle und interteam Verbindungen


5 Daumenregeln nach Naomi Stanford - Guide to Organisation Design: Creating High-Performing and Adaptable Enterprises
1. Entwerfe, wenn es einen dringenden Grund gibt
2. Entwickle Entscheidungsoptionen bereits im Entwurf
3. Wähle den richtigen Zeitpunkt für den Entwurf
4. Suche nach Hinweisen die aufzeigen, dass Dinge falsch angeordnet sind
5. Bleibe wachsam in der Zukunft
