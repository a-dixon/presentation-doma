![](https://blog.cleancoder.com/uncle-bob/images/2012-08-13-the-clean-architecture/CleanArchitecture.jpg)
- Es gibt viele Architekturen, jedoch ist der Kern immer gleich: Separation of Concerns.
	- Software wird in Layers getrennt, um Separation of Concerns umzusetzen
- Clean Architecture strebt an, alle dieser Architekturideen in einer Architektur zu vereinen.

## The Dependency Rule
- Je enger im Kreis (Bild oben), desto mehr high level
- Äußere Kreise sind Mechanismen, innere Kreise sind Policies
- Source Code Dependencies zeigen nur nach innen
- Nichts in einem inneren Kreis kann irgendwas über etwas in einem äußeren Kreis wissen
- Nichts in einem äußeren Kreis kann etwas in einem inneren Kreis beeinflussen

## 1. Entitäten
- Entitäten bilden Business Regeln ab, die für das ganze Unternehmen bestehen
- Entität kann ein **Objekt mit Methoden** oder eine **Menge an Datenstrukturen und Funktionen**
- egal was es ist, solange es von verschiedensten Applikation im Unternehmen verwendet werden kann
- Entitäten verändern sich sehr sehr selten. Keine operative Änderungen sollten Entitäten verändern.

## 2. Use Cases
- Ebene enthält Applikation-spezifische Business Regeln
- kapselt und implementiert alle Use Cases des Systems
- Use Cases orchestrieren den Flow der Daten von und zu den Entitäten
- Keine Änderungen bei den Use Cases sollten die Entitäten beeinflussen
- Use Cases sollten nicht durch Änderungen von extern beeinflusst werden (Datenbank, UI, Frameworks)
- Änderungen der Operationen der Applikation werden die Use Cases beeinflussen und Änderungen am Code der Use Cases hervorrufen

## 3. Interface Adapters
- Ebene an Adaptern, die Daten konvertieren von dem besten Format für die Use Cases und Entitäten zu dem besten Format für externe Anschlüsse (DB, Web).
- MVC Architektur einer GUI liegt vollständig in dieser Ebene
- SQL für Datenbankaufrufe liegt vollständig in dieser Ebene

## 4. Frameworks and Drivers
- Ebene besteht aus Frameworks und Tools, z.B. Datenbank, Web Framework, ...
- meistens wenig Code außer "glue code", der mit der nächsten Ebene kommuniziert
- Hier sind alle Details, z.B. DB und Web, soweit außen wie möglich, damit sie keinen Schaden anrichten können

