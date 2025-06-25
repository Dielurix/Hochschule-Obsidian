## Version-001
![[Exposé-v001.pdf]]
### Inhaltsverzeichnis vom Exposé

1. Einführung in Thema und Forschungsfrage
2. Praxisfall und Zielsetzung der Arbeit
3. Konzept/Methodik
4. Durchführung(mit Zeitplan)
5. theoretische Grundlagen sowie vorläufige Literaturquellen
6. Gliederungsentwurf
7. KI-Verzeichnis

#### Einführung in Thema und Forschungsfrage
- Forschungsfrage:
	- Welche Vorteile bietet der Einsatz von Microservices in Kombination mit Rest-APIs im Vergleich zu Monolithen?
- Aufbau und funktionsweise eines Rest Services -> Kombination aus Microservices und Rest-APIs am Beispiel “Speedrun Kategorien” in der Sprache Java
- Welchen Vorteil bringen Microservices, welche mit Rest("Representational-State-Transfer")-APIs miteinander agieren, gegenüber monolithischen Anwendungen? 
- Diese Frage, da ich mit Rest-APIs, Microservices arbeite um ein Planungstool neu zu gestalten
	- dabei stellt sich die frage ob lieber ein Monolith oder Microservices mit Rest APIs verwendet werden sollen
- **Was ich fragen muss**: ist Plural Monolith? -> **ja**
	- Also weil wir Monolithen zu Microservice/ Restservice 
	
    Die Migration von Monolithen auf Microservices wird zu einem immer beliebteren Thema. Aber was macht Microservices und die entsprechend verwendeten APIs so (hier was hinschreiben) und welche Vorteile bietet die Migration? Mit der Frage: "Welche Vorteile bietet der Einsatz von Microservices in Kombination mit Rest-APIs gegenüber Monolithen", möchte ich her rausstellen, was mögliche Gründe sind, warum man von einer monolithischen Architektur zu einer Microservice Architektur wechselt und ob es nicht doch mehr Vorteile gibt, wenn man bei der monolithischen Architektur bleibt.

#### Praxisfall und Zielsetzung der Arbeit:
- In dem Fall Telekom:
	- geht um Programm, welches Planung von Ü-wegen, Anschlüssen und Geräten verwaltet -> veraltetes Programm(Monolith) neugestalten (Microservices mit Rest-APIs)
	- Soll möglichst übersichtlich und neu gestaltet sein, damit die zukünftigen Generationen an diesem Programm arbeiten können und einen nicht so veraltete Sprache lernen müssen, außerdem muss es für die Nutzer, also die Techniker möglichst einfach zu bedienen sein
- Im Beispielsfall mit Speedrun Kategorien:
	- geht darum einzelne Komponenten wie z.B. Spiel, Welche Kategorie man spielt (sei es 100%-Run oder Any%-Run), wer einen Run eingereicht hat, welche zeit er hat, welcher platz er ist, etc. aufzuschreiben, übersichtlich zu machen und generell das arbeiten an den einzelnen Komponenten einfacher zu gestalten
	- am ende sollte man möglichst einfach auf die einzelnen Komponenten zugreifen können, ohne das ganze Programm wieder umschreiben zu müssen, bzw. alles wieder anpassen zu müssen (code-Programmierer-Übersicht). Außerdem sollte man eine Übersicht darüber bekommen, wie es zu den Speedruns steht (Anwendung-Nutzer-Übersicht).
	
Wie schon erwähnt wird in meinem Betriebseinsatz ein veraltetes Programm, was den Namen "Plural TNP"(wird im folgenden als Plural geschrieben) hat, von Grund auf erneuert. Plural ist ein "Planningtool" zur Dokumentation von Kabelwegen, Geräten, Anschlüssen und Ü-Wegen (Übertragungswege), das eine monolithische Archietektur verwendet. Dieses Programm welches Plural ersetzen wird heißt "Plandok". Dieses kümmert sich genau wie Plural um die Dokumentation verschiedener Komponenten, verwendet aber eine Microservice-Archietektur. Plandok soll im Gegensatz zu Plural übersichtlicher und einfacher zu bedienen sein. Außerdem soll es für zukünftige Generationen einfacher werden Plandok erweitern zu können, da man von (Hier Programmiersprache von Plural) zu Java wechselt.
Am Ende der Arbeit sollen sich Gründe für den Wechsel und weitere Vorteile einer Microservice-Archietektur gegenüber einer monolithischen Archietektur herraus stellen.

#### Konzept/Methodik
- Für Microservices:
	- werde Speedrun Kategorien Programm selbst erstellen -> schauen wie es funktioniert und wie einfach der Umgang ist
- Für Monolithen:
	- Infos über Monolithen durch Quellen zusammensuchen -> sonst zu viel Aufwand 
- Werde am ende nach Kriterien sortieren und vergleichen, welches Konzept welche Vorteile besitzt und warum es Vorteile haben kann, von der einen Architektur auf die andere zu migrieren 
    Um die Zielsetzung einhalten zu können müssen zuerst Kriterien, welche den Vergleich der beiden Archietekturen leiten werden, definiert werden. Ein Beispiel hierfür ist Modularität. Dazu wird zuerst nach möglichst wichtigen Kriterien recherchiert, damit man das möglichst beste Ergebnis erziehlt. Um die Kriterien auf die Archietekturen anwenden zu können müssen auch hier Informationen über die jeweilige Archietektur herraus gesucht werden. Dazu werde ich zum einen, bei der Microservice-Archietektur ein eigenen Restservice mit Java Implementieren und für die monolithische Archietektur nach den einzelnen Kriterien Quellen herraussuchen, welche die Kriterien möglichst präzise beantworten. Dass ich zu der monolithischen Archietektur kein Programm Implementieren werde liegt daran, dass die Zeit die es dafür benötigt nicht ausreichen wird.
#### Durchführung:  
| Projektaufwand WAB [18 Tage]             | Dez | Jan | Feb | Mär | Stundenarbeit | Tage pro Aufgabe |
| ---------------------------------------- | --- | --- | --- | --- | ------------- | ---------------- |
| Thema finden (fachlich) und formulieren  | 5   |     |     |     | 5             | 1                |
| Kriterien für den Vergleich heraussuchen |     |     | 5   |     | 5             | 1                |
| Programmierprojekt umsetzen              | 3   | 10  | 7   |     | 20            | 4                |
| Recherche zu monolithischen Anwendungen  |     | 5   | 5   |     | 10            | 2                |
| Literatur recherche                      | 2   | 5   | 3   |     | 10            | 1                |
| Exposé schreiben                         | 5   | 10  |     |     | 15            | 3                |
| Wissenschaftliche Arbeit schreiben       |     |     | 10  | 15  | 25            | 5                |
| Verbesserungsarbeit/Formatierung/…       |     |     |     | 5   | 5             | 1                |
| Summe                                    | 15  | 30  | 30  | 20  | 95            | 18               |

- Entwicklung des Programms:
    Kriterien, nachdem die beiden Architekturen miteinander verglichen werden, bestimmen
- Microservices:
- Hilfestellung durch BE bekommen (Manual zur Erstellung eines eigenen Restservices)
	- damit eigenen Restservice erstellen
	- Kriterien während des Arbeiten herausschreiben, mit den man einen Vergleich führen kann
- Monolithen:
	- Quellen über Aufbau und Funktionsweise heraussuchen
	- schon benannte Kriterien raus suchen
Die Durchführung ist wie folgt. Zunächst werden Kriterien definiert, nach dem die Recherchen sich richten werden. Danach werde ich mich an die Umsetzung des Programmierprojektes wenden. Dafür wurden mir Hilfestellungen meiner Businessexpertin gestellt. Während der Implementation werden mögliche Auffälligkeiten dokumentiert und die zuvor aufgestellten Kriterien beibehalten und deren Ergebnisse auch dokumentiert. Währenddessen werde ich mich über Monolithen und die monolithische Archietektur durch verschiedene Quellen informieren und hier auch wieder, zu den Kriterien passende, Informationen herrausschreiben. Zum Schluss werde ich die gefundenen Kriterien beider Archietekturen miteinander vergleichen und anhand einem wissenschaftlich ausgearbeiteten Berichtes festhalten.

#### Theoretische Grundlagen, vorläufige Quellen:
- [https://medium.com/@MakeComputerScienceGreatAgain/understanding-rest-api-a-comprehensive-guide-52fc10f6c9ed](https://medium.com/@MakeComputerScienceGreatAgain/understanding-rest-api-a-comprehensive-guide-52fc10f6c9ed)
- [https://www.geeksforgeeks.org/monolithic-vs-microservices-architecture/](https://www.geeksforgeeks.org/monolithic-vs-microservices-architecture/)
- [https://medium.com/@roopa.kushtagi/system-design-trade-offs-monolithic-vs-microservices-architecture-1e14a9fe9e99](https://medium.com/@roopa.kushtagi/system-design-trade-offs-monolithic-vs-microservices-architecture-1e14a9fe9e99)
- [https://harsh05.medium.com/understanding-monolithic-architecture-and-the-shift-to-microservices-080a1768273c](https://harsh05.medium.com/understanding-monolithic-architecture-and-the-shift-to-microservices-080a1768273c)
- [https://arxiv.org/pdf/1905.07997](https://arxiv.org/pdf/1905.07997)
- [https://blog.dreamfactory.com/restful-api-and-microservices-the-differences-and-how-they-work-together](https://blog.dreamfactory.com/restful-api-and-microservices-the-differences-and-how-they-work-together)
- [https://www.seobility.net/de/wiki/REST-API](https://www.seobility.net/de/wiki/REST-API)    
- [https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10160171](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10160171)

#### Gliederungsentwurf:
1. Einleitung
	1. Einführung in das Thema
    	1. Problemstellung
		2. Forschungsfrage und Hypothesen
	    3. Ziel der Arbeit
    2. Relevanz des Projekts für den Betrieb
    3. Methodik und Vorgehensweise
2. Grundlagen
    1. Architekturen (Monolith und Microservices)
    2. Software-Intermediär (REST-APIs)
    3. Frameworks (Quarkus)
3. Bearbeitung beider Architekturen
    1. Microservices
		1. Implementierung
		    1. Planung
			2. Umsetzung 
	    		1. Erstellen eines Git Projekts
				2. Erstellung eines Quarkus Projekts
			    3. OpenAPI-First (yaml-Dateien)
	    2. Selection von Pro- und Kontra Punkten
    2. Monolithen
	    1. Recherche
	    2. Selection von Pro- und Kontra Punkten
4. Vergleich
5. Zusammenfassung und Ausblick
6. Literaturverzeichnis
7. Anhang

## Version-002
![[Exposé-v002.pdf]]
### Inhaltsverzeichnis vom Exposé

1. Forschungsfrage und Themenrelevanz
2. Praxisfall und Zielsetzung
3. Methodisches Vorgehen bei der Untersuchung
4. Durchführung der Untersuchung
5. Theoretische Grundlagen und vorläufige Literaturquellen
6. Gliederungsentwurf
7. Literaturverzeichnis
8. KI-Verzeichnis

#### Forschungsfrage und Themenrelevanz
Die Migration von Monolithen auf Microservices wird zu einem immer beliebteren Thema.
Aber was macht Microservices und die entsprechend verwendeten APIs so begehrt und welche
Vorteile bietet die Migration? Mit der Frage: "Welche Vorteile bietet der Einsatz von
Microservices in Kombination mit Rest-APIs gegenüber Monolithen", wird herausgestelle, was
mögliche Gründe sind, warum man von einer monolithischen Architektur zu einer Microservice
Architektur wechselt und ob es nicht doch mehr Vorteile gibt, wenn man bei der monolithischen
Architektur bleibt.

#### Praxisfall und Zielsetzung
In dem Betriebseinsatz wird ein veraltetes Programm, was den Namen "Plural TNP"(wird im
folgenden als Plural geschrieben) hat, von Grund auf erneuert. Plural ist ein "Planningtool" zur
Dokumentation von Kabelwegen, Geräten, Anschlüssen und Ü-Wegen (Übertragungswege),
dass mit der Programmiersprache CaGen (von Broadcom) geschrieben wurde und eine
monolithische Architektur verwendet. Plural, also ein das monolithische Programm, wird
hierbei in eine Service-orientierte Architektur transformiert und unter dem neuen Namen
"Plandok" als neues System abgelöst. Dieses kümmert sich genau wie Plural um die
Dokumentation verschiedener Komponenten, verwendet aber eine Microservice-Architektur.
Plandok soll im Gegensatz zu Plural übersichtlicher und einfacher zu bedienen sein. Außerdem
soll es für zukünftige Generationen einfacher werden Plandok erweitern zu können, da man von
CaGen (von IBM) zu Java mit Quarkus Framework wechselt. Am Ende der Arbeit sollen sich
Gründe für den Wechsel und weitere Vorteile einer Microservice-Architektur gegenüber einer
monolithischen Architektur herausstellen.

#### Methodisches Vorgehen bei der Untersuchung
Um die Zielsetzung einhalten zu können müssen zuerst Kriterien, welche den Vergleich der
beiden Architekturen leiten werden, definiert werden. Ein Beispiel hierfür ist Modularität.
Dazu wird zuerst nach möglichst wichtigen Kriterien recherchiert, damit man das möglichst
beste Ergebnis erzielt. Um die Kriterien auf die Architekturen anwenden zu können, müssen auch hier Informationen über die jeweilige Architektur herausgesucht werden. Dazu werden
beide für Architekturen praktische Beispiele verwendet, wobei der Monolith schon existiert und
der Microservice als Programmierprojekt geschrieben wird. Dass der Monolith nicht auch
implementiert wird, liegt daran, dass die Zeit, die es dafür benötigt, nicht ausreichen wird. Zum
Schluss werden die einzelne, nach den Kriterien sortierte Informationen, beider Architekturen
verglichen.
#### Durchführung der Untersuchung 
Zunächst wird eine Recherche zu Monolithen und zu Microservices durchgeführt. Dadurch
folgt eine Herausarbeitung der verschiedenen Kriterien. Im weiteren verlauf wird die praktische
Umsetzung ausgeführt, also die Implementation des Microservices und die beispielhafte
Verwendung des Monoliths. Im Anschluss wird auf Grundlagen der Kriterien eine Analyse der
beiden Architekturen durchgeführt und zum Schluss wird eine Zusammenfassung sowie
Evaluierung verfasst.

| Projektaufwand WAB [18 Tage]             | Dez | Jan | Feb | Mär | Stundenarbeit | Tage pro Aufgabe |
| ---------------------------------------- | --- | --- | --- | --- | ------------- | ---------------- |
| Thema finden (fachlich) und formulieren  | 5   |     |     |     | 5             | 1                |
| Kriterien für den Vergleich heraussuchen |     |     | 5   |     | 5             | 1                |
| Programmierprojekt umsetzen              | 3   | 10  | 7   |     | 20            | 4                |
| Recherche zu monolithischen Anwendungen  |     | 5   | 5   |     | 10            | 2                |
| Literatur recherche                      | 2   | 5   | 3   |     | 10            | 1                |
| Exposé schreiben                         | 5   | 10  |     |     | 15            | 3                |
| Wissenschaftliche Arbeit schreiben       |     |     | 10  | 15  | 25            | 5                |
| Verbesserungsarbeit/Formatierung/…       |     |     |     | 5   | 5             | 1                |
| Summe                                    | 15  | 30  | 30  | 20  | 95            | 18               |
#### Theoretische Grundlagen und vorläufige Literaturquellen
- [https://medium.com/@MakeComputerScienceGreatAgain/understanding-rest-api-a-comprehensive-guide-52fc10f6c9ed](https://medium.com/@MakeComputerScienceGreatAgain/understanding-rest-api-a-comprehensive-guide-52fc10f6c9ed)
- [https://www.geeksforgeeks.org/monolithic-vs-microservices-architecture/](https://www.geeksforgeeks.org/monolithic-vs-microservices-architecture/)
- [https://medium.com/@roopa.kushtagi/system-design-trade-offs-monolithic-vs-microservices-architecture-1e14a9fe9e99](https://medium.com/@roopa.kushtagi/system-design-trade-offs-monolithic-vs-microservices-architecture-1e14a9fe9e99)
- [https://harsh05.medium.com/understanding-monolithic-architecture-and-the-shift-to-microservices-080a1768273c](https://harsh05.medium.com/understanding-monolithic-architecture-and-the-shift-to-microservices-080a1768273c)
- [https://ieeexplore.ieee.org/abstract/document/8928192] (https://arxiv.org/pdf/1905.07997)
- [https://arxiv.org/pdf/1905.07997](https://arxiv.org/pdf/1905.07997)
- [https://blog.dreamfactory.com/restful-api-and-microservices-the-differences-and-how-they-work-together](https://blog.dreamfactory.com/restful-api-and-microservices-the-differences-and-how-they-work-together)
- [https://www.seobility.net/de/wiki/REST-API](https://www.seobility.net/de/wiki/REST-API)    
- [https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10160171](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10160171)

#### Gliederungsentwurf:
9. Einleitung
	1. Einführung in das Thema
    	1. Problemstellung
		1. Forschungsfrage und Hypothesen
	    1. Ziel der Arbeit
    1. Relevanz des Projekts für den Betrieb
    2. Methodik und Vorgehensweise
10. Grundlagen
    3. Architekturen (Monolith und Microservices)
    4. Software-Intermediär (REST-APIs)
    5. Frameworks (Quarkus)
11. Bearbeitung beider Architekturen
    6. Microservices
		2. Implementierung
		    1. Planung
			1. Umsetzung 
	    		1. Erstellen eines Git Projekts
				1. Erstellung eines Quarkus Projekts
			    1. OpenAPI-First (yaml-Dateien)
	    1. Selection von Pro- und Kontra Punkten
    1. Monolithen
	    1. Recherche
	    2. Selection von Pro- und Kontra Punkten
12. Vergleich
13. Zusammenfassung und Ausblick
14. Literaturverzeichnis
15. Anhang

## Version-003
![[Exposé-v003.pdf]]
### Inhaltsverzeichnis vom Exposé
1. Thema und Themenrelevanz
2. Leitfrage der Arbeit, mögliche Antworten und mögliche Hypothesen
3. Kurzbeschreibung des Praxisfall
4. Methoden
5. Benötigte theoretische Grundlagen/ zentrale Literaturquellen
6. Gliederungsentwurf
7. Literaturverzeichnis
8. KI-Verzeichnis

#### Thema und Themenrelevanz
Die Monolithische Architektur, also ein eng gekoppelter Code, beziehungsweise ein Code, bei
dem komplexe, kombinierte Aufgaben bearbeitet werden, welcher z.B. funktionale und nicht
funktionale Anwendungsanforderungen erfüllt, wurde und wird in der Informatik immer noch
verwendet.
Modulare Architekturen sind entstanden, um die Komplexität der monolithischen Architektur
zu erleichtern und besteht aus lose gekoppelten Modulen. Beispiele für eine modulare
Architektur sind Funktionen und Services.
Microservices, eine Art der modularen Architektur, hingegen sind Programme mit nur einer
(der kleinstmöglichen) Funktion. Außerdem erfüllen sie in der Regel nur eine einzige Aufgabe.
Um Microservices richtig verwenden zu können müssen diese in Kombination mit APIs
(Application Programm Interface), also Schnittstellen zwischen den einzelnen Services,
verwendet werden. Ein Beispiel einer API ist das “Representational State Transfer” (REST).
REST APIs bezeichnen verschiedene Regeln und Richtlinien, die festlegen, wie eine Web-API
aufgebaut sein soll.”
Durch die Fähigkeit monolithische Architekturprobleme, wie begrenzte Skalierbarkeit, schwere
Wartbarkeit und technologische Abhängigkeit, zu adressieren, wird die Microservice
Architektur immer populärer. Dennoch ist die Migration von einer monolithischen Architektur
zu einer microservice Architektur komplex. Daher stellt sich die Frage, ob es wirklich sinnvoll
ist, zu migrieren.

#### Leitfrage der Arbeit, mögliche Antworten und mögliche Hypothesen
Leitfrage:
“Welche Vorteile bietet der Einsatz von Microservices in Kombination mit Rest-APIs
gegenüber Monolithen?”
Hypothesen:
- Microservices in Kombination mit Rest-APIs bieten weitaus mehr Vorteile gegenüber Monolithen
- Microservices bieten kaum oder gar keine Vorteile gegenüber Monolithen
- Microservices bieten mehr Nachteile als Vorteile gegenüber Monolithen

#### Kurzbeschreibung des Praxisfalls
Zur Planung des Netzausbaus der Deutschen Telekom AG (DTAG) werden verschiedene
Applikationen sowie Tools angeboten, die diesen vereinfachen.
Ein Programm, Plural TNP (Plural), bietet so eine Erleichterung. Mit diesem “Planungssystem”
werden Kabelwege, Geräte und Übertragungswege geplant und dokumentiert. Plural wurde mit
dem System CaGen von IBM entwickelt und besitzt eine monolithische Architektur.
Dieses Programm ist veraltet, kompliziert zu bedienen und verwendet ein System, welches die
Entwicklung eines Pseudocodes, der dann zu C Code generiert wird, ermöglicht. Dadurch
entstehen Herausforderungen, wie das, durch den demographischen Wandel, verlassen der
Kollegen, welche das System verstehen, sowie, das CA Gen kaum noch verwendet wird.
Dadurch wurde entschieden dieses veraltete Programm von einem neuen System abgelöst.
Dieses ablösende System, unter dem Namen Plandok, wird mit der modernen
Programmiersprache Java mit dem Quarkus Framework  entwickelt und besitzt eine
Microservice-orientierte Architektur, welche in Verbindung mit REST-APIs verwendet wird.
Dadurch bietet Plandok zusätzlich zu der Planung und Dokumentation ein übersichtliches
Graphical User Interface (GUI) und eine erleichterte Erweiterung des Programms.

#### Methoden
Zur Beantwortung der Leitfrage wird die wissenschaftliche Methode der konzeptionell-
deduktiven Analyse in Kombination mit dem Prototyping angewandt.
Zunächst werden wesentliche Merkmale zu Monolithen sowie Microservices recherchiert, um
die Herausarbeitung verschiedener, für die Evaluation wichtiger Kriterien einzugrenzen.
Im weitern Verlauf wird die praktische Umsetzung eines Prototyps, hierbei der Microservice in
Kombination mit REST-APIs welches mit Java programmiert wird und auf dem Quarkus
Framework entsteht, umgesetzt.
Außerdem wird für die Evaluation eine beispielhafte Verwendung des Monolithen angewandt,
hier eine beispielhafte Verwendung von Plural.
Im Anschluss wird auf den erarbeiteten Grundlagen, eine Kriterien geleitete, konzeptionell-
deduktive Analyse durchgeführt und eine Zusammenfassung der Evaluation verfasst.
Die verwendete Methode soll zu einem klar verständlichen und geeigneten Vergleich, welcher
anhand des Implementierten REST-Services und der herangezogenen monolithischen Funktion
stattfindet, beitragen.

#### Benötigte theoretische Grundlagen/ zentrale Literaturquellen
Die Methode des Prototyping sowie die Methode der deduktiven Analyse sind hinlänglich
untersucht und etablierte Herangehensweisen in der Informatik.
Die Monolithische, sowie die Microservice Architektur sind weit verbreitete und viel
verwendete Architekturen in der Informatik.
Für die Modellierung des Prototyps wird Java 17 verwendet. Außerdem wird das Quarkus
Framework unter Beachtung der Dokumentation verwendet. Weitergehend wird eine
PostgreSQL Datenbank verwendet, hierbei unter der Beachtung der PostgreSQL
Dokumentation.
Die Funktionsweise von Rest-APIs ist weitgehend dokumentiert, dies unterstützt in der
Implementierung.
Der Monolith wurde unter Verwendung einer Oracle Datenbank und der Programmiersprache
CaGen entwickelt.

#### Gliederungsentwurf
1. Einleitung
	1.1 Einführung in das Thema
		1.1.1 Problemstellung
		1.1.2 Forschungsfrage und Hypothesen
		1.1.3 Ziel der Arbeit
	1.2 Relevanz des Projekts für den Betrieb
	1.3 Methodik und Vorgehensweise
2. Grundlagen
	2.1 Architekturen (Monolith und Microservices)
	2.2 Software-Intermediär (REST-APIs)
	2.3 Frameworks (Quarkus)
3. Bearbeitung beider Architekturen (Prototyping)
	3.1 Recherche
	3.2 Microservices
		3.2.1 Implementierung
			3.2.1.1 Planung
			3.2.1.2 Umsetzung
	3.3 Monolithen
		3.3.1 beispielhafte Verwendung
4. konzeptionell-deduktive Analyse
5. Zusammenfassung und Ausblick
6. Literaturverzeichnis
7. Anhang

#### Literaturverzeichnis
Again, M. C. S. G. (2024, 1. September). Understanding REST API: A Comprehensive guide -
Make Computer Science Great Again - Medium. Medium.
https://medium.com/@MakeComputerScienceGreatAgain/understanding-rest-api-a-comprehensive-guide-52fc10f6c9ed
GeeksforGeeks. (2025, 3. Januar). Monolithic vs. Microservices Architecture. GeeksforGeeks.
https://www.geeksforgeeks.org/monolithic-vs-microservices-architecture/
Kushtagi, R. (2024, 24. November). System Design Secrets: Monolith vs. Microservices
Explained. Medium. https://medium.com/@roopa.kushtagi/system-design-trade-offs-
monolithic-vs-microservices-architecture-1e14a9fe9e99
@Harsh. (2024, 15. November). Understanding Monolithic Architecture and the Shift to
Microservices. Medium. https://harsh05.medium.com/understanding-monolithic-architecture-and-the-shift-to-microservices-080a1768273c
Al-Debagy, O., & Martinek, P. (2018, November). A comparative review of microservices and
monolithic architectures. In 2018 IEEE 18th International Symposium on Computational
Intelligence and Informatics (CINTI) (pp. 000149-000154). IEEE.
https://ieeexplore.ieee.org/abstract/document/8928192/
H, J. (2024, 11. Juni). REST APIs vs Microservices: Key differences. Dreamfactory.
https://blog.dreamfactory.com/restful-api-and-microservices-the-differences-and-how-they-work-together
IEEE Xplore Full-Text PDF: (o. D.).
https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10160171
Seobility. (o. D.). Was ist eine REST API? Definition und Erklärung - Seobility Wiki.
https://www.seobility.net/de/wiki/REST-API
Houde, S., & Hill, C. (1997). What do prototypes prototype?. In Handbook of human-computer
interaction (pp. 367-381). North-Holland.
https://courses.cs.washington.edu/courses/cse440/08au/readings_files/Houde-Prototypes.pdf
Wilde, T., & Hess, T. (2006). Methodenspektrum der Wirtschaftsinformatik: Überblick und
Portfoliobildung (No. 2/2006). Arbeitsbericht.
https://www.econstor.eu/bitstream/10419/60077/1/71972564X.pdf
Carr, M., & Verner, J. (1997). Prototyping and software development approaches. Department
of Information Systems, City University of Hong Kong, Hong Kong, 319-338.
https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=0b05add730e04843e234937a070f24b19efaadc3
Quarkus documentation content types. (n.d.). Quarkus. https://quarkus.io/guides/doc-concept
PostgreSQL: documentation. (n.d.). The PostgreSQL Global Development
Group. https://www.postgresql.org/docs/
Database documentation - Database documentation. (2024, October 22). Oracle Help
Center. https://docs.oracle.com/en/database/
Inc, C. (2023, May 4). CA gen. https://techdocs.broadcom.com/us/en/ca-miscellaneous/legacy_bookshelves_and_pdfs/bookshelves_and_pdfs/bookshelves/ca-gen.html
Yousif, M. (2016). Microservices. IEEE Cloud Computing, 3(5), 4-5.
https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7742262
Was ist eine REST API? – Einführung in RESTful APIs. (o. D.).
https://www.redhat.com/de/topics/api/what-is-a-rest-api
Saucedo, A. M., Rodríguez, G., Rocha, F. G. & Santos, R. P. D. (2024). Migration of monolithic
systems to microservices: A systematic mapping study. Information And Software Technology,
1. https://doi.org/10.1016/j.infsof.2024.107590
Inc, C. (2023, May 4). CA gen. https://techdocs.broadcom.com/us/en/ca-miscellaneous/legacy_bookshelves_and_pdfs/bookshelves_and_pdfs/bookshelves/ca-gen.html

