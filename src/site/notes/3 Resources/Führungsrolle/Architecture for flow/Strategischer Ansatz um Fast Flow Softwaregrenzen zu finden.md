---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/architecture-for-flow/strategischer-ansatz-um-fast-flow-softwaregrenzen-zu-finden/","created":"2024-04-22T11:06:52.363+02:00","updated":"2024-05-18T14:49:55.341+02:00"}
---


In einer Welt, in der schnelle Änderungen notwendig werden, um sich der unbestimmten Umgebung besser anpassen zu können, müssen auch Organisationen eine hohe Anpassungsfähigkeit beweisen. Um schnell zu adaptieren und sich weiterzuentwickeln, braucht es eine Business Strategie und die verfolgte Architektur (Software und Organisation) müssen für diesen Wandel ausgelegt sein und zur Mitarbeit motivieren.

>[!NOTE] Quellen
>[Mini-book: Finding software boundaries for fast flow - Team Topologies and Domain-Driven Design — Team Topologies](https://teamtopologies.com/all-mini-books/finding-software-boundaries-for-fast-flow-team-topologies-and-domain-driven-design-mini-book-mb81-v1)
>[[3 Resources/Führungsrolle/Anforderungsmanagement/Wardley Mapping von Simon Wardley/Wardley Mapping von Simon Wardley\|Wardley Mapping von Simon Wardley]]
>[[3 Resources/Führungsrolle/Softwarearchitektur/Domain Driven Design von Eric Evans/Domain Driven Design von Eric Evans\|Domain Driven Design von Eric Evans]]
>[[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies von Matthew Skelton/Team Topologies von Matthew Skelton\|Team Topologies von Matthew Skelton]]

Kombiniert man [[3 Resources/Führungsrolle/Anforderungsmanagement/Wardley Mapping von Simon Wardley/Wardley Mapping\|Wardley Mapping]], [[Domain-Driven Design\|Domain-Driven Design]] und [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team Topologies\|Team Topologies]], kann dies helfen die Punkte zwischen der [[Business Strategie\|Business Strategie]], des Softwaredesigns und der Architektur zu verbinden und so eine teamorientierte Organisation zu konzipieren, welche für einen [[Fast Flow of Change\|Fast Flow of Change]] und Adaption ausgelegt ist.

Mithilfe des folgenden Ablaufs wird eine Idee über mehrere Etappen hin zu einer Architektur für die Organisation, der Software und einer Business Strategie ausgebaut.

# Fast Flow of Change - Durchführung

Die erste Etappe verbindet Purpose und Landscape, da diese stark zusammen spielen. Aber man sieht deutlich, wo das eine aufhört und das andere beginnt. Der Purpose wird in der Landschaft stets deutlich ganz oben dargestellt, als allgegenwärtiges Wesen.

## Purpose und Landscape

Besonderer Wert sollte auf das Landscape und die Doctrine gelegt werden.
![Pasted image 20240516170123.png](/img/user/4%20Archive/Assets/Pasted%20image%2020240516170123.png)

Das Bild zeigt eine Wardley Map in erster Ausbaustufe. Die Y-Achse stellt die Sichtbarkeit einer Komponente in einer [[Value Chain\|Value Chain]] dar. Je niedriger, desto unsichtbarer ist sie. Das Erstellen der Kette beginnt von den [[Persona\|Persona]] aus, für die das Business konzipiert wird.

In der zweiten Stufe wird die X-Achse hinzugefügt, welche die evolutionäre Stufe darstellt.
![Pasted image 20240516171308.png](/img/user/4%20Archive/Assets/Pasted%20image%2020240516171308.png)

Dafür werden die vorher identifizierten Komponenten der [[Value Chain\|Value Chain]] nach deren gewünschten Charakteristiken einsortiert auf der Skala von Genesis / Experimentell hin zu Commodity / Handelsware.

Damit wäre eine erste hilfreiche Landschaftskarte erstellt. Bevor nun der Aspekt der zukünftigen Entwicklung mit aufgegriffen wird, indem das Thema Climate betrachtet wird, schauen wir uns die Möglichkeiten des [[Domain-Driven Design\|Domain-Driven Design]] an dieser Stelle an.

## Die Domain Driven Design Perspektive

Das Kernkonzept von [[Domain-Driven Design\|Domain-Driven Design]] ist es, dass bessere Software geschrieben wird, indem der Entwurf entlang der Business Domain, den Bedarfen des Businesses und der [[Business Strategie\|Business Strategie]] konzipiert wird.
![Pasted image 20240516171959.png](/img/user/4%20Archive/Assets/Pasted%20image%2020240516171959.png)

Die Landschaft kann nun als Problemlösung definiert werden und DDD bringt uns einen Lösungsraum ins Spiel, indem es uns verschiedene Fragen an das Business stellt und mögliche Lösungen präsentiert. Dabei betrachtet es vor allem die hohen, strategischen Entscheidungen ([[Bounded Contexts\|Bounded Contexts]] und [[Context map\|Context map]]), statt die niedrigen, taktischen Entscheidungen, welche erst später in der Implementierungsphase behandelt werden.
![Pasted image 20240516172417.png](/img/user/4%20Archive/Assets/Pasted%20image%2020240516172417.png)

Mithilfe der zuvor erstellten Landschaft kann nun die [[Value Chain\|Value Chain]] noch weiter einsortiert, zuerst in [[Bounded Contexts\|Bounded Contexts]] und diese später wiederum nach Core Domain, Supporting Subdomain und Generic Subdomain.
![Pasted image 20240516172640.png](/img/user/4%20Archive/Assets/Pasted%20image%2020240516172640.png)

## Climate

Nun wissen wir, was uns wichtig ist. Betrachten wir nun die Entwicklung der Domains auf der X-Achse, können wir womöglich feststellen, dass einige Subdomains, welche zuvor in Custom-Built sind, in Zukunft eher ein buchbares Produkt sein werden. Hier sollten also keine Aufwände investiert werden, sondern lieber auf entsprechende Lösungen gesetzt werden.
Core Domains sind die Kontexte, in denen wir uns absetzen können in einer Anwendung gegenüber Mitbewerbern. Hier sollte also stets Genesis / Custom Built angestrebt werden. Mithilfe der Kontexte können also Aussagen über die Evolution getroffen werden bzw. andersherum auch Aussagen über einen Kontext aufgrund dessen zukünftigen Entwicklung.
Sollte ein Teil eines Kontextes sich in Zukunft durch ein "Einkauf" erledigen können, so ist dies ebenfalls ein Hinweis darauf, eine weitere Supporting Subdomain zu eröffnen, um die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Kognitive Belastung\|Kognitive Belastung]] vom Entwicklerteam abzunehmen und die Arbeit zu konzentrieren.

## Doctrine

Diese stellen Prinzipien dar, welche in allen Situationen, auf alle Organisationen jeglicher Art angewendet werden können. Sie sind sehr allgemeiner Natur und helfen bei der Einordnung der eigenen Erwartungen an die Organisation. Sie sind unter [Doctrine | Wardley Maps](https://www.wardleymaps.com/doctrine) und [Doctrine](https://learnwardleymapping.com/doctrine/) zu finden und sind in 4 Phasen gruppiert, da ihre schiere Menge, es sind 40 Prinzipien, sonst erschlagen wirken würden. Die Gruppen sollen helfen, die Organisation im Jetzt-Zustand einzuordnen und einen Wunschzustand zu identifizieren. Ein Tool gibt es unter [Doctrine assessment](https://doctrine.wardleymaps.com). Die Erkenntnisse dieser Fragen können und sollten auf die Landschaft einwirken.
In Gruppe 2 ist das Prinzip "thinking small as in teams" aufgelistet. Es ist also so, dass wir in der Landschaft, welches dank DDD bereits einen ersten Softwareentwurf darstellt, nun auch die Teams berücksichtigen sollten.

Dank des [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Gesetz von Conway]] wissen wir, dass es eine homomorphe Abbildung zwischen [[3 Resources/Führungsrolle/Softwarearchitektur/Softwarearchitektur\|Softwarearchitektur]] und [[3 Resources/Führungsrolle/Organisationsstruktur/Organisationsstruktur\|Organisationsstruktur]] gibt. Hier kommen also die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team Topologies\|Team Topologies]] ins Spiel, welche uns nun helfen, den ersten Architekturentwurf mit einer möglichen Teamstruktur zu verbinden. Besonderes Augenmerk ist hier darauf zu setzen, dass Abhängigkeiten zwischen Systemen und Teams ganz deutlich in der Map hervorgehoben werden, sie also sichtbar gemacht werden.
Außerdem haben wir bisher nicht von UI, Backend oder Datenbank gesprochen, denn wir möchten möglichst [[crossfunktionales Team\|crossfunktionale Teams]] aufbauen, da diese die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Kognitive Belastung\|Kognitive Belastung]] deutlich reduzieren durch wenige Kontexte und das Team für einen [[Fast Flow of Change\|Fast Flow of Change]] aufstellen, da eine hohe Kommunikation innerhalb des Teams erwünscht ist. Aus diesem Grund sind nur die Abhängigkeiten zwischen Teams erwünscht, welche entweder zeitlich befristet sind [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Facilitating\|Facilitating]] oder [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Enabling Team\|Enabling Team]]) oder kognitive Entlastung versprechen (z.B. [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Platform Team\|Platform-Team]] oder [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Complicated Subsystem Team\|Complicated Sub-system Team]]).

> [!NOTE] Vermeide verschiedene Teamarten
> Alles, was nicht durch eine entsprechende [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team Topologies\|Teamart]] bereitgestellt wird, darf nicht weiterverwendet werden. Ein [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Stream-aligned Team\|SAT]] muss explizit in anderen Kontexten eine andere Rolle einnehmen, was die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Kognitive Belastung\|Kognitive Belastung]] erhöht, was nicht zu empfehlen ist.

Eine ausgearbeitete Landschaft zeigt nun eindrücklich alle notwendigen Kommunikationen, Abhängigkeiten und Zuständigkeiten. Die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Software Ownership\|Software Ownership]] ist geklärt und auch die Nachnutzung von Dingen ist geklärt.
![Pasted image 20240516174017.png](/img/user/4%20Archive/Assets/Pasted%20image%2020240516174017.png)

Zur Belastung sollte außerdem gesagt werden, dass sich diese erhöht, je weiter links eine Komponente sich auf der Evolutionsachse befindet. Bedeutet also auch, dass das jeweilige Team nicht wesentlich mehr Kontexte bearbeiten können wird. Je weiter sich andere Kontexte von diesem experimentellen Kontext befinden, je schwächer wird die Leistung des Teams. Kontexte die sich stark ähneln und mit ähnlichen Tools und Methoden bearbeitet werden können, können von einem Team wesentlich effizienter bearbeitet und Änderungen effektiver vorgenommen werden.

## Leadership

Als letzter Schritt, nachdem wir so viele Informationen in eine einzige Landkarte gegeben haben, können wir nun die [61 Kriegsstrategien von Wardley](https://learnwardleymapping.com/leadership/) nutzen, um Entscheidungen für unsere Organisation zu tätigen. Dabei überlegen wir uns, was wir erreichen wollen und welche Maßnahmen dies begünstigen würde, statt die nötigen Schritte zu beschreiben.
> An alternative approach is to examine the _conditions_ that would make desirable _consequences_ inevitable.

Wir fragen also nicht "was müssen wir nun tun?", sondern "welche Bedingungen brauchen wir, damit wir unausweichlich unsere Vision erreichen?". Und dadurch haben wir unsere (Kriegs-)Strategie und die Taktik versucht nun, die Bedingungen aufzustellen, statt das Ergebnis, meist vergeblich, mittels brachialer Gewalt (Brute-Force) zu erreichen.

Besonders spannend wird es, wenn man ein Ziel in einer höhere Ebene verfolgt durch die Veränderung der darunterliegenden Komponenten. Hier sind die Effekte meist nicht sofort ersichtlich, können sich aber auf das gesamte Umfeld, auch außerhalb der Organisation, auswirken. Hier sind die Strategien von Wardley besonders mächtig, denn durch die Veränderung des Umfelds kann sich die eigene Position verbessern. (Siehe auch das Beispiel beim oberen Link bezüglich der Erstellung von Unterhaltungscontent).

# Weiterführende Überlegungen

Um die [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Interaktionsmodi\|Interaktionsmodi]] und [[Kommunikationspfade\|Kommunikationspfade]] mit den Teams zu kommunizieren im Kontext der [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team Topologies\|Team Topologies]] und die dafür nötigen [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/Kommunikationskanäle\|Kommunikationskanäle]] einzurichten, könnte es sich anbieten, eine [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/Stakeholder-Landkarte\|Stakeholder-Landkarte]] für jedes Team zu erstellen, um die Einarbeitung ins Thema zu vereinfachen und die richtigen Kanäle zu wählen.

Außerdem könnte sich das Etablieren einer organisationsweiten [[3 Resources/Führungsrolle/Prozesssteuerung/Prozesssteuerung\|Prozesssteuerung]], z.B. durch [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/Kanban Flight Levels\|Kanban Flight Levels]] 2, um die Erarbeitung und Fortschritte der Wardley Map zu steuern und das Umsetzen der Ergebnisse eng zu begleiten, vor allem das Etablieren der identifizierten Bedingungen im letzten Schritt.

Um taktische Entscheidungen zu dokumentieren und für die Implementierung aufzubereiten, könnte nach Abschluss der strategischen Überlegungen je ein [[C4 Modell\|C4 Modell]] für sämtliche [[Bounded Contexts\|Bounded Contexts]] erstellt werden. Auch hierfür könnte eine [[3 Resources/Führungsrolle/Prozesssteuerung/Kanban/Stakeholder-Landkarte\|Stakeholder-Landkarte]] helfen, um die Arbeiten zu priorisieren und die Kommunikation anzuleiten, z.B. um nur die wichtigsten Stakeholder zur Konzeptphase einzuladen.