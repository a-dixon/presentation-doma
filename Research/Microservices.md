https://www.uber.com/en-DE/blog/microservice-architecture/
- Erweiterung der Service Oriented Architecture
- Applikationen mit eng zugeschnittenem Funktionsumfang
- Kommunikation zwischen den Applikationen über Remote Procedure Calls (=RPC)
- Hauptmerkmal der Microservice-Architektur ist wie der Code gehosted, aufgerufen und deployed wird.
	- Eine Monolithische Applikation wird in gekapselte Komponenten mit klar definierten Interfaces aufgeteilt. Die Komponenten rufen sich gegenseitig direkt innerhalb des Prozesses auf
	- In einer Microservice Architektur finden diese Aufrufe über das Netzwerk statt -> Zusätzliche Latenzen, erforderliche Rechenleistung für Netzwerk I/O und De-/Serialisierung
	- Diese Nachteile sollen durch Vorteile wie unabhängige Deployments und Skalierbarkeit ausgeglichen werden. In monolithischen Systemen müssen immer alle Komponenten gleichzeitig deployed werden. -> Aufwändig und Riskant
	- D.h. beim Umstieg auf Microservice Architekturen werden betriebliche / organisatorische Vorteile gegen Performance eingetauscht

https://www.atlassian.com/de/microservices/microservices-architecture#:~:text=Eine%20Microservice%2DArchitektur%20teilt%20eine,unabhängig%20bereitgestellt%20und%20skaliert%20werden.
## Wichtige Merkmale einer Microservice-Architektur

- Einzelne, lose gekoppelte Services, die unabhängig voneinander entwickelt, betrieben, geändert und neuentwickelt werden können
- Gute Wartbarkeit und Testbarkeit
- Services werden von kleinen unabhängigen Teams entwickelt -> Fördert Praktiken wie agile Softwareentwicklung und DevOps
- Organisation nach Geschäftsfunktionen
- Automatisierte Infrastruktur -> Continuous Integration, Continuous Delivery und Continuous Deployment

## Beispiel Microservice-Architektur E-Commerce-Softwareprojekt

![](https://wac-cdn.atlassian.com/dam/jcr:d76e535a-b5ad-473a-b697-26dab8b73c18/microservice_architecture_v2.png?cdnVersion=2364)

- Web APP CDN (=Content Distribution Network)
	- Bereitstellung von Web-Anwendungen und Ressourcen auf Servern weltweit

Microservices in der Grafik:
- Konto-Service - Hält Informationen zu Kundenkonten wie Zahlungsinformationen, Adresse etc.
- Bestandsservice - Hält Bestandsinformationen zu verkauften Waren
- Einkaufswagenservice - Sammelt Waren die der Kunde kaufen will
- Bezahlservice - Bezahlung der Waren im Einkaufswagen
- Versandservice - Planung der Verpackung und Lieferung der Waren