---
{"dg-publish":true,"permalink":"/3-resources/fuehrungsrolle/organisationsstruktur/team-topologies/interaktionsmodi/","created":"2024-04-28T15:27:23.449+02:00","updated":"2024-04-28T21:36:22.204+02:00"}
---


Durch nicht klar definierte Interaktionen zwischen den Teams, kann es zu Brüchen in der Arbeit und Unklarheiten in den Verantwortlichkeiten kommen. Auf der einen Seite wird den Teams gesagt, sie sollen autonom und selbstorganisierend arbeiten, auf der anderen Seite sind sie abhängig von anderen Teams, um ihre Arbeit erledigen zu können. Wenn man sich diesen Umstand bewusst macht, kann man Entscheidungen zur Interaktion treffen. Soll das abhängige Team mit dem anderen Team sprechen dürfen oder nicht? Wenn nein, dann muss es eine andere Form der Interaktion geben, z.B. APIs, welche konsumiert werden können, welche durch das andere Team bereitgestellt und dokumentiert werden muss.

> [!NOTE] Intermittent collaboarion gives the best results
> Unregelmäßige, kurzfristige Kommunikation bringt die besten Resultate und erhöht die durchschnittliche Qualität. Diese Form der Kommunikation findet bessere Lösungen als konstante Interaktion.

Es konnten 3 Modi identifiziert werden, welche [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Gesetz von Conway\|Conways Law]] und die Team-first Dynamiken berücksichtigen: [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Collaboration\|Collaboration]], [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/X-as-a-Service\|XaaS]] und [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Facilitating\|Facilitating]].

Für die meisten mittleren bis großen Unternehmungen wird eine Mischung aus allen 3 Modi gebraucht, um die Arbeit effizient zu unterstützen. Aber auch für kleine Organisation wird eine der Modi früher nötig sein als einem bewusst ist.
Ein Team sollte nicht zwangsweise sämtliche Kommunikation auf eine der Modi reduzieren, sondern die Interaktion wird angepasst, je nach Situationsbedarf. Zwischen denselben Teams sollte jedoch nur eine der Modi vereinbart werden. Ein Wechsel ist möglich, aber muss bewusst kommuniziert werden.
Das Verwenden der Modi sollte ein Verhalten sein, dass das gesamte Team bewusst einhält. Dies wird die Expertise und das Engagement des Teams erhöhen und Frustration durch abhängige Teams verringern.
Ein Team sollte sich selbst Fragen: "Welche Art der Interaktion sollten wir mit dem anderen Team haben? Sollten wir eng zusammenarbeiten mit dem anderen Team? Sollten wir einen Service erwarten oder anbieten? Oder sollten wir Hilfe von ihnen einfordern oder ihnen anbieten?"

>[!NOTE]
>A key part of the [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team Topologies\|Team Topologies]] approach is in the choice between two teams [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Collaboration\|Collaboration]] and one team consuming something "as a service" from another team.


> [!TIP] Promise theory as a way to design systems for team interaction.
> Promise theory -- devised by technologist and reasearch Mark Burgess -- explains how and why it is preferable to construct interteam relationships in terms of promises rather than in terms of commands and enforceable contracts. For example, by adhering to the meaning of the major/minor/patch/build numbering indicated by semantic versioning (SemVer), the team promises not to break software that depends on their code. (S. 142)

# Die richtige Interaktion auswählen

Einige [[3 Resources/Führungsrolle/Organisationsstruktur/Team Topologies/Team Topologies\|Teamarten]] können leichter mit einigen Modi umgehen als andere, weil es deren Natur eher entspricht. Die folgende Tabelle zeigt die Häufigkeit der Zuweisungen der Modi zu den Arten.

|     | Collaboration | X-as-a-Service | Facilitating |
| --- | ------------- | -------------- | ------------ |
| SAT | typisch       | typisch        | gelegentlich |
| CST | gelegentlich  |                | typisch      |
| ET  | gelegentlich  | typisch        |              |
| PT  | gelegentlich  | typisch        |              |
