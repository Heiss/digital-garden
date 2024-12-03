---
{"dg-publish":true,"permalink":"/3-resources/softwarearchitektur/system-architektur/solid-pattern/","tags":["softwareentwicklung"],"created":"2024-11-11T08:59:37.110+01:00","updated":"2024-11-01T22:05:09.878+01:00"}
---


Dies ist ein Muster aus 5 verschiedenen Prinzipien. Eine Software kann diesen Prinzipien folgen und soll so besser wartbar, flexibler und länger verständlich werden. Vor allem in objektorientierten Programmiersprachen finden diese Prinzipien Anwendungen. Es müssen nicht immer alle Prinzipien implementiert werden, jedoch empfiehlt es sich, die verfolgten Prinzipien bewusst und explizit zu erwähnen, da sie teilweise den Code massiv beeinflussen und teils kontraintuitiv für einige Entwickler sind.
Diese Prinzipien wurden im Zuge der Clean Code von Robert C. Martin zusammengeschrieben und als Akronym SOLID verbreitet.

# Single responsibility Principle (SRP)

Jede Klasse implementiert einen einzigen Aufgabenbereich. Dies bedeutet, dass ähnliche Aufgaben zusammengefasst werden. Hierfür ist eine vorherige Analyse sinnvoll und hilfreich. Außerdem kann dies durch eine klare Benamung der Klasse und eine ausführliche Aufgabenbeschreibung in der Dokumentation dazu helfen, dass diese Klasse nicht über die Zeit degeneriert.

# Open–closed Principle (OCP)

Eine Klasse ist geschlossen für Veränderungen und offen für Erweiterungen. Dies bedeutet, dass die Weiternutzung einer bestehenden Klasse nicht den bisherigen Code beeinflussen kann (z.B. via Monkeypatching in Python), sie jedoch von einem Nachnutzer erweitert werden kann. Typisch hierfür ist das Decorator-Pattern.

# Liskov substitution Principle (LSP)

Erlaube es, dass eine Subklasse ebenfalls in deinem Programm verwendet werden kann, ohne das das Programm fehlschlägt. In OOP ist dies typischerweise über Vererbung implementiert. Es dürfen also keine Abhängigkeiten implementiert werden, welche nur auf eine Oberklasse angepasst sind und keine Unterklassen zulassen.

# Interface segregation Principle (ISP)

Erzwinge einem Nutzer nicht die Implementierung von Methoden auf, welche er nicht verwendet. Separiere hierfür die verwendeten Interfaces. Typische Fehler, welche dieses Prinzip nicht beachtet haben, sind NotImplemented-Exceptions. Hierbei wird in einer Klasse, welche der Nutzer implementiert und dann in eine Methode hineingibt, eine Methode implementiert, welche er selbst nicht benötigt.
Reduziere das benötigte Interface auf das absolut Notwendigste und biete lieber verschiedene Interfaces an, welche implementiert werden müssen, sodass ein Nachnutzer hier selbst entscheiden kann, was er wirklich benötigt und implementieren kann.

# Dependency inversion Principle (DIP)
{ #0df14f}


Eine Klasse sollte abhängig von Abstraktionen sein, nicht von konkretem. Hierbei ist die Nutzung von Interfaces typisch für dieses Prinzip. Mithilfe der zuvor genannten ISP ist es so möglich, recht schlanke und gut nutzbare Methoden anzubieten, welche die Entkopplung und die Flexibilität einer Software erhöhen.

# Überlegungen

- [SOLID - Wikipedia](https://en.wikipedia.org/wiki/SOLID)
