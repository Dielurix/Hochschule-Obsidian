## Vorarbeit
[[Exposé]]

# Zwischenstand-v001
## Inhaltsverzeichnis
1. Einleitung
	1.1 Einführung in das Thema
		1.1.1 Problemstellung
		1.1.2 Forschungsfrage und Hypothesen
		1.1.3 Ziel der Arbeit
	1.2 Relevanz des Projekts für den Betrieb
	1.3 Methodik und Vorgehensweise
2. Grundlagen
	2.1 Softwareentwicklung Technologien(Java und CA Gen)
	2.2 Architekturen (Monolith und Microservices)
	2.3 Software-Intermediär (REST-APIs)
	2.4 Frameworks (Quarkus)
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

## Einleitung
- Irgendein Zitat 
- Software design is an exercise in human relationships -Kent Beck
- oder 
- "If you can’t build a well-structured monolith, what makes you think microservices are the answer?" -Simon Brown
- oder was auch gut ist 
- "Monolithic architectures are not inherently bad, just as microservices are not inherently good. The key is knowing when to use each."  -ThoughtWorks Technology Radar
	- monolithic vs microservice architecture (IBM)
- auch noch ein gutes
- "Good architecture comes from understanding the problem deeply, not just applying the latest trends." -Martin Fowler
	- hier das buch mit den Patterns (AnalysisPattern.pdf)
### Einführung in das Thema
- irgendwie eine Einführung ins Thema -> vllt. Entstehung von Architekturen, Mainframes, dann Monolithen und danach Microservices -> wie die Welt immer schneller wird
	- hab quelle: Evolution of software architecture
#### Problemstellung
- Wegen schneller werden ist umstieg auf Microservices häufiger -> was ist Vorteil, oder gibt es einen Vorteil, warum?
- Durch schnellere Welt wird mehr auf Microservices gewechselt, aber ist das richtiger ansatz
- gab/ gibt immernoch monolithen die gut verwendet werden
#### Forschungsfrage und Hypothesen
- Das und das meine forschungsfrage, ich erwarte das und das, aber es kann vorkommen, dass auch das und das raus kommt
Leitfrage:
“Welche Vorteile bietet der Einsatz von Microservices in Kombination mit Rest-APIs
gegenüber Monolithen?”
Hypothesen:
- Microservices in Kombination mit Rest-APIs bieten weitaus mehr Vorteile gegenüber Monolithen
- Microservices bieten kaum oder gar keine Vorteile gegenüber Monolithen
- Microservices bieten mehr Nachteile als Vorteile gegenüber Monolithen
- kann einen Hybrid benutzen, welcher Vorteile von Monolithen und Microservices bietet -> möglichst wenig Nachteile
#### Ziel der Arbeit
- Ziel der Arbeit ist den unterschied der Architekturen klar darzustellen und herauszufinden, welche Vorteile die Jeweiligen Dinger mit sich bringen
- Möchte zeigen, welches der beiden besser ist, ob vielleicht sogar ein beide sind gut oder gibt ein Hybrid welcher gut ist
- Vielleicht die Leser zum Wechsel animieren oder überzeugend klarstellen warum ein Wechsel schlau ist
### Relevanz des Projekts für den Betrieb
- bisschen das Ding vom Exposé ausführen
### Methodik und Vorgehensweise
- das ding von Exposé ausführen
	- erklären was Prototyping ist und was konzeptionell Deduktive Analyse ist
## Grundlagen
- Was sind wichtige Grundlagen, die unbedingt klargestellt werden müssen 
### Wissenschaftliche Methode (Vielleicht)
- konzeptionell deduktive Analyse
- Prototyping
### Softwareentwicklung Technologien
- Java
- CA Gen
### Architekturen
- Microservices
	- 
- Monolithen
### Software-mediär
- Rest-APIs
### Framework
- Quarkus
	-  basiert auf Kubernetes
		- 
## Prototyping (Bearbeitung beider Architekturen)
- Im folgenden die Bearbeitung beider Architekturen mithilfe meines eigen erstelltem Restservice und einem schon vorhandenem Monolithen -> Plural
### Recherche (vielleicht ändern zu Kriterien? Weil Recherche ist ja in die Grundlagen mit eingeflossen)
Was sind Kriterien die wichtig werden könnten
hier kann ich die Dinger von dem Modulithen Beitrag nehmen save
vielleicht noch mehr die find ich schon
### Microservices
- wie schon erwähnt das und das ist wichtig
#### Implementierung
erklären, was gemacht hab um mit dem Endergebnis herauszukommen
##### Planung
- Hab mich mit dem Thema befasst,
	- über APIs nachgeleseni
##### Umsetzung
- zeige Codebeispiele und weitere Methoden erklärt
- hab die Struktur
	- Repository Ordner
		- enthält Klassen, die auf die DB zugreifen können
	- Entity Ordner
		- enthält Klassen, die sozusagen ein Bauplan für Objekte sind
	- Mapper Ordner
		- enthält Klassen, die von Entities zu Models Mappen
	- Resource Ordner
		- Beinhaltet Klassen, mit den Methoden von REST-APIs -> also Get, Delete, Put und Post
	- Service Ordner
		- enthält Klassen, welche die ganze Logik der API enthalten, also des einen Services
- Wichtige andere Sachen die ich erwähnen sollte:
	- pom.xml
		- für die Dependencies -> bekommt man/ bei uns aus Sachen, wie z.B. Maven Central Repository (MCR)
	- Models
	- Tests -> Unit-Tests
	- open-api.yaml
		- Hülle für die API
- Dann noch die DB -> fehlt noch... aber dazu irgendwie bisschen erklären
	- hier werden halt Daten gespeichert, was soll ich sagen . _ .
### Monolithen
- wie schon erwähnt, was das ist
#### Beispielhafte Verwendung
- einzelne dinge die ich in meinem Restservice gemacht habe auch hier machen um zu zeigen was anders ist -> auch anhand der Kriterien Testen
## Konzeptionell-deduktive Analyse
- anhand der gefundenen dinge werde ich Sachen vergleichen und die aufgestellten wichtigen Kriterien vergleichen
	- Hab die Kriterien von beiden Dingern nebeneinander aufgestellt, in z.B. einer Tabelle ->damit kann ich die einzelnen Punkte aufstellen und vergleichen
	- noch eine Zusammenfassung was wie besser ist und warum etc.
## Zusammenfassung und Ausblick
- was habe ich herausgefunden? Warum war das jetzt wichtig, was bedeutet das für die zukunft?
	- hab Modulithen gefunden -> Amazon hat glaube sowas ähnliches, vielleicht ist das was was wichtige werden kann
	- hier einmal alles gelernte zusammenfassen bitte :D
## Literaturverzeichnis
- alle wichtigen Quelle 
	- Zotero ist hier benötigt :D -> da sollte alles drin sein :D
## Anhang
- hier die Bilder save juhu
## KI Verzeichnis
- *Frage*:
Kannst du mir Quotes heraussuchen, welche über software-Archietektur gehen(spezifisch über Microservices und Monolithen)?
- *Antwort:*
**Über Microservices:**
- 1. If you can’t build a well-structured monolith, what makes you think microservices are the answer?" -Simon Brown
- "Microservices are not about scaling development, but about scaling deployment and operations." -Sam Newman
- "The big advantage of microservices is the ability to deploy independently. If you don’t need that, you might not need microservices." -Martin Fowler
- "A microservice is not a small monolith, it’s a different way of thinking about modularity." -James Lewis
 **Über Monolithen:**
- "A well-structured monolith is better than a poorly designed microservices system." -Kelsey Hightower
- "Monolithic architectures are not inherently bad, just as microservices are not inherently good. The key is knowing when to use each." -ThoughtWorks Technology Radar
- "Monoliths are easy to start with, but hard to scale. Microservices are hard to start with, but easy to scale."  -Unknown
**Allgemein über Software-Architektur:**
- "Architecture isn’t about frameworks, it’s about how you structure your code and services to meet business needs."  -Uncle Bob (Robert C. Martin)
- "A good software architecture is one that makes the system easy to change." -Kent Beck
- "Good architecture comes from understanding the problem deeply, not just applying the latest trends." -Martin Fowler

- *Frage:*
Von welcher Seite kommt das Zitat (hier eine verlinkung zu dem Zitat: "Good architecture comes from understanding the problem deeply, not just applying the latest trends.")
- *Antwort:*
Das Zitat "Good architecture comes from understanding the problem deeply, not just applying the latest trends." stammt von Martin Fowler. Es betont die Bedeutung eines tiefen Verständnisses des zugrunde liegenden Problems bei der Entwicklung einer guten Softwarearchitektur, anstatt lediglich aktuellen Trends zu folgen. Dieses Konzept wird in seinem Buch "Analysis Patterns: Reusable Object Models" behandelt.

# Zwischenstand-v002
![[WAB- Microservices und Monolithen im Vergleich.pdf]]

# Hier ist jetzt nur für die Recherche
## Einführung(also hier wie Softwarearchitekturen entstanden sind und warum sie heute noch verwendet und verbessert werden)
- ~1940 -> Mainframes und Monolithen
	- Mainframes
		- große, mächtige Hardware Maschinen, welche einen ganzen Raum einnahmen
		- wurden als alleinstehende Maschinen, welche komplexe Aufgaben bewältigen konnten, entwickelt
		- vor 1970 -> input von mainframes kamen über lochkarten oder magnetisches tape, output kam über den Drucker
		- erster Mainframe -> Havard Mark I und ENIAC
			- war für militärische Nachforschungen
		- batch processing transachtional data <- outstanding ability of mainframe
		- wurden in COBOL programmiert und hatten eine monolithische Softwarearchitektur

# Zwischenstand-v003

# Präsentation zu der WAB
- WAB über Monolithen und microservices

- Zur Forschungsfrage:
- hier kann ich auch noch die problemstellung zeigen
	- evolution ist in der heutigen zeit immer wichtiger, dadurch entstehen auch immer modernere softwarearchitekturen, zu der gehört zb auch die Microservice architektur
	- ältere Architekturen sind also nicht mehr sinnvoll zu nutzen, fragen sie sich, aber kann man das so einfach behaupten? also hier jetzt forschungsfrage
	- Welche Vorteile Bietet der Einsatz von Microservices gegenüber Monlithen
- gab auch Hypothesen zu dem ding, und zwar:
- "Microservices bieten weitaus mehr Vorteile gegenüber Monolithen”
- “Microservices bieten kaum oder gar keine Vorteile gegenüber Monolithen”
- “Monolithen bieten mehr Vorteile als Microservices” 
- “Man kann einen Hybrid aus Microservice und Monolith nutzen, welcher Vorteile von beiden bietet, dieser heißt modularer Monolith (Modulith)”

- Zu betriebseinsatz
	- Gibt eben noch dieses Programm -> Plural, ist mit CA Gen entwickelt worden, CA Gen erstellt durch Pseudo Code C code, Plural ist ein Monolith, mit verschiedenen Komponenten , wie z.B. Knoten, Übertragungswege oder Kanten
	- Ist jetzt 30 Jahre alt, und wurde entschieden, dass es veraltet ist -> Altes, graues User interface, mit unbeschrifteten Knöpfen, nicht skalierbar
	- Da das Programm aber wichtig für den Netzausbau ist, wurde entschieden es neu zu entwickeln
	- unter dem namen Plandok -> hier das zweite bild
	- In diesem Programm wurde unter Verwendung einer Microservice Architektur wurden die Komponenten des Monolithen in einzelne Microservices aufgeteilt, die über verschiedene APIs miteinander kommunizieren
	- Durch die Microservices ist, falls fehler in einem der Services auftreten sollt, nicht gleich die ganze netzplanung in gefahr
	- dadurch, dass dieses Programm mit Java geschrieben wurde, wird auch gewährleistet, dass neue Generationen an dem Programm weiter entwickeln können, sowie Fehler einfacher beheben können falls es nötig sein sollte

- Methodik:
	- Als methodik habe ich mich für prototyping und  Konzeptionell Deduktive Analyse entschieden
	- Was das?
		- Prototyping -> entwicklung eines Prototypen, der dann in der deduktiv konzeptionellen Analyse verwendet werden kann
		-  konzeptionell Deduktiv Analyse -> man verwendet konzepte, durch die verschiedene Kriterien herausgestellt werden können und Analyysiert, was das ergebnis bedeutet
	- Warum hab ich das gewählt?
		- Prototyping -> um ersteinmal selbst in das thema hinen zu kommen, außerdem um einen der zwei konzepte für die Analyse selbst zu erstellne
		- Analyse -> damit ich die beiden Konzepte, also meinen microservice in dem fall und den monolithen des Unternehemns anhand verschiedener Kriterien vergleichen zu können
	- Wie hab ich sie verwendet?
		- Prototyping -> am anfang den Prototypen erstellt
		- den microservice hab ich im laufe des Projektes verwendet
		- Konzeptionell deduktive analyse -> ich wollte durch verwendung des microservices und des monolithen und auch unter verwendung der Kriterien: Usability, Laufzeit und Wartbarkeit die Forschungsfrage beantworten

- Fazit und ausblick:
	- Hatten also jetzt Monolith und microservice unter den schon genannten kriterien verglichen, also, was ist jetzt das ergebnis? -> Im betriebseinsatz haben microservices weitaus mehr vorteile, aber generell?
	- generell kann man die beiden architekturen nicht vergleichen, denn es kommt immer auf den kontext, die Vorgaben und die Entwicklung an, in dem es benutzt wird. Denn stellen sich mal vor, spotify oder netflix als monolith, das wäre relativ schwer umzusetzen, aber als gegenbeispiel stackoverflow, die entwickler haben entschieden, dass hierbei eine monolithische architektur sinnvoller wäre als eine Microservice architektur.

- Ausblick
	- hier bringe ich noch den modulith mit -> mischung zwischen monolith und einem microservice bzw einer modularen architektur
	- -> werden zb auch von amazon verwendet

- Danke fürs zuhören :D