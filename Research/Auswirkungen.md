Allgemein gefasst, sollten hier zum einen die Vorteile/ gelösten Probleme aufgezeigt werden und zum anderen die Herausforderungen, die mit der Änderung einhergegangen sind.

## Vorteile

Notizen:
- Versionierung und Deployment von einzelnen Services leichter möglich
- Weiterentwicklung durch stärkere Modularisierung mit Gateways leichter möglich (weniger Migrationen erforderlich)
	- 50% aller Microservices werden in 1,5 Jahren neu geschrieben
- Weniger Pfuschen in andere Teams (?)

## Probleme

- Wenn man durch die Gateways hindurch blicken will, um die Logik dahinter zu verstehen (bspw. Debuggen) muss eine Abstimmung mit anderen Teams stattfinden
- Durchsetzung der verschiedenen Maßnahmen wurde nicht erläutert, aber essenziell
- Latenzbalg verschlechtert durch eingeschobene Gateways
- Extensions
	- Antipattern legal geworden?
	- Weichen Modularisierung auf?
- Verkomplizierung der Infrastruktur um ein gewaltiges
	- Gleichzeitig steigende Kosten
- Durch stärkere Modularisierung (Microservices, Gateways) sinkt die Beobachtbarkeit des Systems
	- Dieser Aspekt erfordert Aufwand, wie [UBER gezeigt hat](https://www.uber.com/en-DE/blog/distributed-tracing/)