---
{"dg-publish":true,"permalink":"/3-resources/softwarearchitektur/residuality-theory/residuality-theory/","created":"2025-02-24T10:03:03.383+01:00","updated":"2025-02-23T21:07:41.114+01:00"}
---


Für die Erarbeitung einer Softwarearchitektur gibt es verschiedene Ansätze, aber es konnte bisher nicht nachvollzogen werden, wie Senior Architects Entscheidungen treffen, um daraus ein Verfahren entwickeln zu können, sodass auch andere Personen zu guten Architekturen kommen könnten.
Barry M. O’Reilly hat dazu den Ansatz _Residual Theory_ mitentwickelt [[4 Archive/Readwise Sync/A Residuality Theory, random simulation, and attractor networks\|A Residuality Theory, random simulation, and attractor networks]] mit dessen Hilfe bessere Architekturen entwickelt werden sollen. Unter [[4 Archive/Readwise Sync/A An Introduction to Residuality Theory Software Design Heuristics for Complex Systems\|A An Introduction to Residuality Theory Software Design Heuristics for Complex Systems]] und [[4 Archive/Readwise Sync/A Residuality Theory - Good idea, bad name\|A Residuality Theory - Good idea, bad name]] ist dazu ein Beitrag geschrieben worden, dass das Verfahren konkret ausdefiniert, plastischer darstellt und an einem Beispiel bespricht.

## Kritik

Im Allgemein muss man sagen, dass es nur dann gut angewendet werden kann, wenn es bereits einen Architekturvorschlag bzw. mindestens eine Idee dafür gibt, an dessen man sich abarbeiten kann. Denn andernfalls lassen sich die Stressoren nicht gut anwenden und ausprobieren. Die Erarbeitung dieser naiven Architektur lässt die Theorie offen.
Aber sie zeigt eine gute Alternative zum erraterischen Vorgehen, um stabile und flexible Architekturen daraus zu erarbeiten.
Besonders wertvoll scheint aber der Ansatz dort zu sein, wo kein Anforderungs- und Risikomanagement vollzogen wird. Hier kann dieser Ansatz zu erkenntnisreichen Diskussionen führen. Vor allem der Fokus auf nicht-funktionale Anforderungen hilft dabei, die notwendigen, unbekannten Abläufe des Systems besser zu verstehen und zu berücksichtigen.

## Überlegung

Kann dies irgendwas mit Monaden aus der funktionalen Programmierung zu tun haben bzw. dadurch unterstützt werden? Irgendwie kommt mir es so vor, dass die Architektur als strukturiertes System in einem unstrukturiertem System (der Umwelt) damit modelliert werden könnte bzw. die Architektur deshalb an der Realität scheitert, da die Eingaben nicht durch das System verarbeitet werden können, da es doch Ansprüche an die Umwelt stellt, welche uns zuvor nicht bewusst waren. Mittels Monaden könnte man diese Unbekannten modellieren und begreifbar machen. Mir ist aber unklar, ob das überhaupt wirklich gilt und ob es dann auch gehen würde. Außerdem ist nicht klar, was man damit dann zeigen könnte. Womöglich könnte man damit eine Architektur formal beweisen, wenn man die Stressoren ebenfalls in eine solche Umgebung eingeben könnte.
