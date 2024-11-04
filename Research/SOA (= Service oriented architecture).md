https://aws.amazon.com/what-is/service-oriented-architecture/#:~:text=Service%2Doriented%20architecture%20(SOA),other%20across%20platforms%20and%20languages.
- Software-Entwicklungs Methode bei der Software in Komponenten (=Services) aufgeteilt entwickelt wird
- Jeder Service erfüllt eine gewisse Aufgabe und interagiert mit anderen Services
- SOA ermöglicht z.B die Wiederverwendung von Services in unterschiedlichen Applikationen
- Grundprinzipien der SOA


Buchquelle: Requirements Modelling and Specification for Service Oriented Architecture - Edition 1 - Ian Graham - 2008 - Publisher: John Wiley % Sons, Incorporated

Seite 8:
- Software-Architekturelles Konzept bei dem Geschäftsanwendungen durch kombinierbare, loose gekoppelte Services gestaltet werden
- Hebt das Abstraktionslevel, sodass Anforderungen in einer für Geschäftspersonen und IT Fachleuten verständlichen Sprache beschrieben werden können
- Grundidee hinter SOA: Erstellung von Anwendungen für einen Geschäftsprozess durch die Kombination kleinerer Services die jeweils eine Geschäftsanforderung / Funktionalität erfüllen
- Beispiele für einen Service:
	- Kundendaten abrufen
	- Zahlungen validieren
	- Rechnungen senden
	- Daten zwischen Systemen synchronisieren
Seite 9:
- SOA ist technologieunabhängig

Eigenschaften von Services (S9f)

- Jeder Service hat einen Vertrag (engl: Contract) - eine Beschreibung was der Service tut, und wie man ihn verwendet
	- Ein wohldefiniertes Interface ist essenziell
- Services können gefunden und aufgerufen werden
- Services sind abstrakt - Nur der Contract ist sichtbar. Implementierungsdetails sind verborgen
- Services sind autonom. Sie kontrollieren ihre eigene Logik und wie Nachrichten verarbeitet werden
- Komposition - Services können mit anderen kombiniert werden, um neue Geschäftsanforderungen zu erfüllen
- Loose Kopplung - Minimierung von Abhängigkeiten zwischen Services
- Services sind Zustandslos - diese Anforderung kann "aufgeweicht" werden indem der Zustand beim Austausch von Nachrichten mitgeliefert wird
- Services sind Wiederverwendbar - Systeme sollten derart in Services aufgeteilt werden, dass die Services in anderen System wiederverwendet werden können

Zusammenhang zwischen den Eigenschaften (S.11):
- Wiederverwendbarkeit ist abhängig von allen anderen Eigenschaften
- Wiederverwendung findet bei Komposition mit anderen Services zur Erfüllung neuer Aufgaben statt

Seite 14:
- Zusammenfassend ist der perfekte Service eine Black Box, die lose gekoppelt zu allen Benutzern ist. Seine Funktionalität ist Input-Verarbeitung-Output, ohne jegliche "Erinnerung" an den Input nachdem der Output ausgegeben wurde
- Services müssen erweiteterbar sein, um sie an neue Anforderungen anzupassen