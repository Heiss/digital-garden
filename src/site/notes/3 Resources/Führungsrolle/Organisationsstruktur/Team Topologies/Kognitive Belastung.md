---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/kognitive-belastung/","created":"2024-11-11T08:59:46.438+01:00","updated":"2024-05-22T11:10:39.233+02:00"}
---


Ein Team, welches überlastet ist, wird nicht effektiv und schnell Systeme ändern können, denn sie sind mit der Belastung durch andere Dienste oder den nötigen Folgeänderungen innerhalb eines Systems zu sehr beschäftigt, um innovativ zu sein oder ihre Arbeitsweise zu hinterfragen.

Wenn niemals in einem entsprechenden [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/Kaizen\|Kaizen]] die [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/technische Schulden\|technischen Schulden]] abgegolten werden, so wird die Komplexität und die immer größer werden Codebasis des Systems die kognitiven Limitierungen des Teams erreichen. Diese dehnen sich auch auf ausführende Teams aus, da immer mehr Anforderungen durch das System an sie gestellt werden (z.B. Ops, Infrastruktur etc.).
Ein Team-first Ansatz kann diese Problematik angehen, denn die Verantwortlichkeiten der Teams entspricht ihrer kognitiven Belastung. Das bedeutet zu aller erst, die Belastung wird limitiert, was wiederum eine Limitierung der zu bearbeitenden Systeme bedeutet. Deshalb darf die Organisation es nicht erlauben, dass Subsysteme diese Limitierung sprengen.
Durch verschiedene Maßnahmen, kann die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Kognitive Belastung limitieren\|kognitive Belastung limitiert]] werden.
Z.B. mit gut definierten [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team-API\|Team-API]]s , welche u.a. die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Software Ownership\|Software Ownership]] klar regelt, wird dies auch noch weiter unterstützt. Auch die Anpassung der [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Environment & Workspace\|Arbeitsumgebung]] hilft bei den Anstrengungen.

# Kognitive Belastung

Kognitive Belastung wurde von John Sweller 1988 als "the total amount of mental effort being used in the working memory". Dabei hat er 3 verschiedene Arten definiert:
- Intrinsische kognitive Belastung: Dinge, die fundamental mit der Aufgabe zu tun haben
- Extrinsische kognitive Belastung: Die Umgebung, in der die Aufgabe erledigt wird
- Germane / relevanter kognitive Belastung: Aspekte der Aufgabe, welche besondere Aufmerksamkeit benötigt, wie High Performance Bedingungen oder zu lernende Informationen
{ #ea3558}


Im besten Falle wird das Team wenig intrinsischer, keiner extrinsischer und maximaler relevanter kognitiver Belastung ausgesetzt, worin die wirkliche Wertgenerierung stattfindet.

Um diese Belastungen zu steuern, können z.B. (nach Driskell) die Aufgaben in kleinere Unteraufgaben zerlegt werden, sodass die Aufmerksamkeit auf die Erledigung gelegt werden kann. Zur gleichen Zeit kann das Team durch Weiterbildung ausgebildet werden, um die Belastung weiter zu reduzieren durch neues Wissen.

Eine Möglichkeit zur Messung kann das Gespräch sein: "Do you feel like you are effective and able to respond in a timely fashion to the work you are asked to do?" Anders kann man sich auch die Komplexität der verantwortlichen Domäne betrachten und die Belastung abschätzen, denn sie ist leichter zu verstehen als der entsprechende Code. Dabei ist zu sehen, dass das Aufsetzen bestehender Software weniger Belastung darstellt als eine vollständig neue, welche Kunden zu Gesicht bekommen.

Achtung: Goodhart's law
> That every measure which becomes a target becomes a bad measure.

# Bedeutung für die Softwarentwicklung

Wenn die kognitive Belastung eines Teams nicht berücksichtig wird, wird die Arbeitskraft durch die Verteilung auf verschiedene Domänen und die Verantwortlichkeiten stark reduziert. Jede Person hat ein kognitives Limit für Dinge, mit denen man sich beschäftigen oder Informationen "im Kopf behalten" kann. Teams haben ein höheres Limit als die Personen selbst, aber bei Überbelastung wird ein Team verschieden reagieren, z.B. durch Vermeidung, Widerstand oder Verfolgung von "leichten Wegen", welches die Leistungsfähigkeit reduziert. Dies kann u.a. durch sehr häufigen [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/Kontextwechsel\|Kontextwechsel]] oder Überbelastung durch Informationen geschehen.
![Pasted image 20240416200825.jpg](/img/user/4%20Archive/Assets/Pasted%20image%2020240416200825.jpg)

Neue Dienste werden häufig mit der Annahme entworfen, dass das zukünftig zuständige Team Vollzeit verfügbar und keine kognitive Belastung besitzen. Aber das Team muss weiterhin alte Dienste warten, Fehler beheben und diese an neue Anforderungen anpassen. Am Ende wird das Team zum Flaschenhals bei der Auslieferung neuer Dienste, da ihre kognitive Belastung vollständig ausgeschöpft ist. Dies führt zu starken Verzögerungen, Qualitätsproblemen und meist zu einer Verminderung der Motivation einzelner Teammitglieder.
