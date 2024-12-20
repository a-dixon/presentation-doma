
Hier ist eine kleine Zusammenfassung des Podcasts. Ergänzt die Notizen gerne!

- Uber ist eines der großen Unternehmen, die Microservices eingeführt haben
- Uber geht offen mit seiner Herangehensweise an Softwareentwicklung heran
- Uber als eigentliches Unternehmen ist umstrittenes Unternehmen
- Grundeinstellung des Podcast ist positiv, da nur gelöste Probleme betrachtet werden
- Warum macht Uber Microservices und Warum macht Uber DOMA?
- Problem: Verfügbarkeit (Systemausfall ca. 2012/ Risikoreiche Deployments/ Schlechte Separation of concerns -> Schwer unabhängig zu arbeiten)
- Lösung: Modularisierung mit Microservices
- Bewertung: Es fällt erstmal nur ein Service aus -> Rest läuft weiter/ Unabhängigere Deployments sind realistisch mit Microservices/ Microservice gut für Separation und Zuständigkeitszuweisung, aber andere Modularisierungen haben vergleichbaren Effekt
- Probleme: Zuständigkeitsfrage kann auch organisatorische Gründe haben, weshalb Microservices nicht helfen
- Notiz: Microservices sind enabler, aber organisatorische Änderungen können erforderlich sein für manche Verbesserungen
- Problem: 2.200 kritische Microservices (Keine Infos von Uber über Technologien oder Größe der Microservices) bei mehreren Tausend Entwicklern und Entwicklerinnen
- Ziel: Idee von DOMA: Ein Weg finden, die Komplexität zu verringern und gleichzeitig die Flexibilität erhalten (Zielgruppe sind große Unternehmen)
- Problem genauer: Bei einem Pick-Up gibt es einen Fehler -> Debuggen von 50 Services mit 12 Teams nötig + Grenzen zwischen den Services verwaschen zunehmend -> Temas pfuschen sich gegenseitig rein, wodurch die Zuständigkeit von einem Team zu einem Microservice nicht mehr vollständig gegeben ist + Sehen die Gefahr bei einem verteilten Monolith zu landen
- Ziel: DOMA (DDD, Clean Architecture, SoA) -> Relativ neuer Weg diese Konzepte im großen Stil zu nutzen (Welche Elemente aus den Konzepten genommen werden, wird nicht aufgeführt)
- Domain: Sammlung von in Beziehung stehender Services
	- Beispiele: Map Search Engine, Fair service, Matching platform
	- Meinung: Definition nicht besonders stark -> Zusammenhang zwischen Services nicht klar ersichtlich
	- Abhängigkeiten können eingeschränkt werden
	- Alleine nicht besonders hilfreich, aber Voraussetzung für Weiteres
- Layer: Sammlungen von Domainen
	- Obere Schichten dürfen unteren Verwenden, nicht umgekehrt
	- Untere Layer generisch -> Obere Spezifisch
	- Potentielles Problem: Synchrone Microservices (Einer fällt in der Kette aus -> Problem)
	- Mögliche Layer: Infrastructure (Von allem genutzt) -> Business (Logik, die von vielen Produkten genutzt werden können) -> Product (Spezifisch für eine Produktkategorie) -> Presentation (Funktionalität für Kundenanwendungen (Mobile oder Web)) -> Edge (Exponieren von Schnittstelle zum Kunden)
	- Notiz: Wie wird das durchgesetzt? Sonst Zweifel an konstanter Einhaltung
- Gateway: Schnittstellen für Domainen
	- Ziel: Zukünftige Migrationen erleichtern und Systemkomplexität verringern -> Hält er für realistisch
	- Notiz: Wie setzt man das durch?
- Extensions:
	- Logic
		- Validierung (Beispiel: Darf ein Fahrer online gehen, weil er ein Auto hat, fahren kann, ...)
		- Er sieht keinen Unterschied zu Schnittstellen
	- Data
		- System kann mit irgendwelchen Daten erweitert werden
		- Meinung/Notiz: Widerspricht DDD -> Zuständigkeiten werden stärker aufgelöst
		- Weitere Meinung: Wirrwarr in Datenhaltung und Abstimmungsschwierigkeiten zwischen Teams und durch fehlende Typisierung ist keine Validierung möglich
	- Custom:
		- Aufgaben mit D(irected) A(cyclic) G(raph) ausführen
		- Meinung: Zuständigkeit werden aufgelöst
- Debuggen mit vielen Abhängigkeiten mit vielen Teams:
	- Angegangen durch Gateways -> Logik hinter Gateways schwerer einsehbar
	- Alternative: Fachlichkeit anders formieren und Teams anders aufstellen
- Komplexe Abhängigkeiten: Gelöst mit Gateways durch Reduzierung der Abhängigkeiten auf Schnittstellen der Domainen (Abstimmungsaufwand steigt potenziell)
- Teams pfuschen sich ein: Legalisiert durch Extensions (Er wäre vorsichtig, da möglicherweise Workaround gebaut wurde, um fachliches Problem zu umgehen -> Seiteneffekte, die niemand versteht entstehen?)
- Latenzbalg: Wird schlimmer, weil Gateways zusätzlich eingebaut werden
- Aussage von Uber: 50% aller Microservices werden in 1,5 Jahren neu geschrieben
	- Meinung: Überraschend, kann aber sinnvoll -> Er will wissen, ob das ein Bug oder ein Feature ist
- Meinung: Beziehung zu DDD: Keywords der Definition kommen nicht vor. Er vermisst die Erkennbarkeit von Konzepten. Domain gibt es, ist aber anders definiert.
	- DDD könnte hilfreich sein
	- Was man sieht weißt nicht auf Nutzung von DDD hin
	- Nichtinterpretierbare Daten speichern ist voll blöd
- Meinung: Organisationsprobleme angesprochen, aber Lösungen beziehen sich rein auf die technische Seite
- Fragen:
	- Modularisierung wird durch Extensions aufgeweicht