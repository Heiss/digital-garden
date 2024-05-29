---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/gesetz-von-conway/","created":"2024-04-19T07:45:03.668+02:00","updated":"2024-04-28T17:29:14.305+02:00"}
---


Organisationen können alternative Strukturen nicht effektiv verfolgen, da sie nicht die notwendigen Kommunikationspfade besitzen. Dadurch beschränkt sich die Organisation selbst, welche Lösungen sie verfolgen können.
Es kann hier lediglich begünstigt oder erschwert werden, welche Entwürfe sich selbst setzen. Dabei ist nicht garantiert, dass unser gewünschtes Design entsteht, aber durch die Beeinflussung der Kommunikationswege sind ähnliche Entwürfe zumindest begünstigt.

> [!NOTE] [Conway's Law](https://www.melconway.com/research/committees.html)
> The basic thesis of this article is that organizations which design systems (in the broad sense used here) are constrained to produce designs which are copies of the communication structures of these organizations. We have seen that this fact has important implications for the management of system design. Primarily, we have found a criterion for the structuring of design organizations: a design effort should be organized according to the need for communication.

Das Gesetz von Conway beschreibt demnach eine Isomorphie / Abbildung der Kommunikationsstrukturen einer Organisation auf die Softwarearchitektur.

Besonderer Fokus liegt hier auf der Kommunikationsstruktur, welche nicht zwangsweise (und es in den meisten Fällen es auch nicht ist) deckungsgleich mit dem Organigramm einer Unternehmung sein muss.
Je weiter die Lücke zwischen den Kommunikationspfaden und dem Organigramm ist, desto schwieriger ist eine kontrollierte Softwarearchitektur aufzubauen oder gar zu warten. Andersherum kann eine Erfassung der aktuell vorliegenden Softwarearchitektur Informationen liefern über die aktuell vorliegenden Kommunikationspfade. Somit ist also die Planung einer Architektur für Systeme eng verbunden mit der gelebten Struktur einer Organisation.

# Zusammenfassung

Conways Law: Teamstrukturen müssen der notwendigen Softwarearchitektur übereinstimmen oder man riskiert ein nicht intendiertes Design.

> Organisations which design systems... are constrained to produce designs which are copies of the communication structures of these organisations.

Die Dokumentation garantiert nicht, dass kleine Entscheidungen während der Entwicklung sich nicht aufsummieren, sodass der vorherige Entwurf im Ganzen nicht mehr verfolgt wird. Um zu garantieren, dass der Entwurf auch in der echten Implementierung wiederzufinden ist, müssen zuerst die sozialen Systeme entworfen werden und dessen Interaktionsmodi.

> If you have 4 groups working on a compiler, you'll get a 4-pass compiler.
