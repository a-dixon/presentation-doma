 ## Uber Vorstellung
- Dienstleistungsunternehmen
- Gründung März 2009 in San Francisco - https://www.uber.com/de/newsroom/history/
- Produkte / Dienstleistungen [https://www.uber.com/de/en/?uclick_id=97e7fdf3-88d5-4fff-8fa5-eec9198df8c5]
	- Ride
	- Drive
	- Deliver
	- Eat
	- Uber for Business
	- Uber Freight

### Ausgangssituation (2-stellige Anzahl an Entwicklern)
- 2 Monolithen, folgende Probleme ergaben sich hierbei:
	- Verfügbarkeit - Ein einziger Fehler kann zum Absturz des gesamten Monolithen führen
	- Deployments - Risikoreich und zeitaufwändig (vorallem wegen eventueller rollbacks) -> teuer
	- Seperation of concerns - schwer innerhalb einer großen, wachsenden code base aufrecht zu erhalten
- Mit steigender Anzahl an Entwicklern und Teams wurde es schwerer für die Teams unabhängig an dem Monolithen zu arbeiten

Umstieg auf Microservice Architektur (3-stellige Anzahl an Entwicklern)
- Erhöhung der Stabilität des Systems, da der Ausfall (und evtl. rollback) eines Microservices nicht das ganze System lahmlegt
- Microservice Architektur zwingt einen dazu sich mehr Gedanken um die Rollen einzelner Komponenten zu machen -> fördert Seperation of Concerns
- Klarere Grenzen zwischen den Services -> klarere Verantwortlichkeiten der Teams
- Weniger Abhängigkeiten zwischen den Teams -> unabhängige Deployments -> Teams können in ihrer Geschwindigkeit arbeiten.

## Motivation für Umstieg auf DOMA:

Weiteres Wachstum auf 4-stellige Anzahl an Entwicklern + Steigende Komplexität des Systems
- Entwickler mussten sich um die 50 Microservices aus 12 verschiedenen Teams anschauen um die Ursache eines einzigen Problems zu finden
- Neue Features erfordern Änderungen vielen Microservices, die alle von eigenständigen Teams entwickelt werden
- Grenzen zwischen Microservices verschwimmen -> Zuständigkeitsbereiche werden wieder unklarer -> bildung von vernetzten Monolithen (scheinbar unabhängige Services müssen immer zusammen deployed werden um Wechselwirkungen zu vermeiden)
	-> Beeinträchtigung der Produktivität der Entwicklungsteams