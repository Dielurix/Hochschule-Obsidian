## Einleitung
- Buch:![[ds.pdf]]
### Algorithmen
- Pizza(Ausgabe) als Beispiel -> braucht spezielle Zutaten(Input) -> immer gleiche Zubereitung(nach Rezept)(schrittweise Lösung)
- Formal, ein Algorithmus ist ein:
	- wohldefiniertes
	- endlich beschreibbares
	- schrittweises
	- Verfahren
- zum Lösen eines Problems oder der Erfüllung einer Aufgabe

- Summation als Algorithmus?
	- Ja, aber mit sehr schlechter Run-time
	- Gaußalgorithmus(Gauß'sche Summenformel) als alternative
	- sonst noch Rekursion


- Was zeichnet einen guten Algorithmus aus?
	- hängt davon ab, was man machen will
	- Alle Algorithmen erfüllen "Summation"
	- Andere Kriterien:
		- Effizienz(Schnelligkeit)
		- Verständlichkeit(Lesbarkeit)
		- Wartbarkeit
		- \[...]

- Wie bestimmt man Effizienz/Wie "beherrscht" man komplexe Probleme?

### Teile und Herrsche/devide and conquer
- Aufteilen um Probleme zu lösen
	- Beispiel: Liste in GdI(Racket)

### Rekursion
- gibt verschiedene Ausprägungen der Rekursion
	- bis jetzt strukturelle Rekursion (folgt der Struktur der Daten)

- Ausprägungen:
	- Lineare Rekursion
		- rekursiver Aufruf im Rumpf der Funktion
			- strukturelle Rekursion über Listen ist linear
	- Baumartige Rekursion:
		- mehrere rekursive Aufrufe im Rumpf der Funktion
	- Wechselseitige Rekursion:
		- zwei Funktionen rufen sich gegenseitig auf
	- Verschachtelte Rekursion:
		- Argument der Rekursion wird durch rekursiven Aufruf berechnet
			- Ackermann-Funktion
	- Endrekursion(endständig)
		- rekursiver Aufruf ist letzte Berechnung im Rumpf
- weitere Einteilungen existieren

- Komma Zahlen sind Problem :(
	- bei uns: 1,5
	- bei den Amerikanern: 1.5

- Papier in 16 gleichmäßige Teile teilen
	- 1. Ansatz
		- Papier in 2 Teile teilen
		- linke Seite in n/2 Teile teilen
		- rechte Seite in n/2 Teile teilen
		- n = n/2 Teile + n/2 Teile
	- passt das?
		- Nein, was ist mit n = 1, bzw. n = ungerade Zahl
	- 2. Ansatz
			- n = 2^i, i ist Natürliche Zahl
- Ergebnis:
	- Ansatz 2 mit stopp bei beherrschbarkeit -> also bei n = 2
	- Teile und Herrsche als Idee
- Anderes Beispiel:
	- LöseProblem(Problemgröße(Meistens: n)):
		- ist das Problem trivial einfach lösbar?
			- Löse das Problme direkt
		- sonst
			- Zerlege das Problem in Teilprobleme (gleichen Typs)
			- Löse das Teilproblem (kleinere Problemgröße)
			- Füge die Teillösungen zu Ganzem zusammen
	- **Klausurrelevanz** -> Was muss ein Problem haben um Teile und Herrsche? -> Zerteilbar sein, gleiche Art, müssen zusammensetzbar sein

### Exponentielle Rekursion
- Towers of Hanoi -> **Klasurrelevanz**: Skizzieren sie einen Algorithmus -> Pseudocode reicht, aber normaler code reicht auch, soll gut, klar und endlich geschrieben wird
	- was ist der Zwischenstapel?
		- 6 - x(Ursprung) - y(Ziel)
		- n-1 Scheiben von x nach z
		- 1 Scheibe von x nach y
		- n-1 Scheiben von z = 6 - x- y nach y
	- Bedeutung von x, y, z verändert sich in jeder Runde -> x Ursprung, y Ziel, z Zwischenstapel
	- Code:
		- def hanoi(anzahl, x, y):
		- if anzahl == 1:
			- print("Zug von" + x + "nach" + y)
		- else:
			- hanoi(anzahl -1, x, 6- x -y)
			- hanoi(1, x, y)
			- hanoi(anzahl-1, 6 -x -y, y)
		- mit 64 Scheiben dauert lange -> viele Scheiben, Python nicht laufzeitoptimiert, I/O(Input Output ist langsam) 
- **Scoping** -> Python mag nur äußere Variablen lesen und nicht verändern -> global count -> nimmt dann globale variable
- Ähnliche Probleme die mit Teile und Herrsche berechnet werden kann
	- Aus der Mathematik:
		- Fibonacci -> fn = f(n-1)+f(n-2) -> f0 = f1 = 1
			- Schleife hier besser als Rekursion
		- Fakultät -> fn = n * f(n-1) -> f1 = 1
	- Aus Informatik
		- Backtracking -> 8-Damen-Problem
		- Traversing
		- Wegeprobleme

## Komplextität
### Wiederholung asymptotische obere Schranke
- Summation Algorithmen
	- Schnelligkeitsfrage
	- Wie berechnet man Schnelligkeit
		- alle Implementieren -> Zeit Messen
		- Operationen Zählen
			- Unterschiede bei den Operationen
	- Funktionsaufrufe -> Sachen im Arbeitsspeicher werden gemacht (Stackfrain, Frainpointer, Stackpointer) -> Aufwändig
- Wie bestimmt man Effizienz
	- Wie gut ist ein Algorithmus
		- Lässt sich ein Problem mit einem bestehendem Algorithmus lösen?
			- (Beispiel: 8-Damen-Problem)
		- Lässt sich das Problem auch in Akzeptabler Zeit lösen?
			- (etwa <10s)
		- Welche Problemgrößen lassen sich überhaupt lösen?
			- (etwa nur bis x = 1.000000?)
	- Primzahlen als Beispiel
		- Wichtig für Verschlüsselung
	- (Exponentielle Funktion umdrehen -> Logarithmus) Tabellen mit Logarithmus werte -> Chip schlägt Werte nach -> grob geschätztes, gerundetes Ergebnis heraus -> diskreter Logarithmus -> kommt ganze Zahl heraus
	- Sieb des Eratosthenes
	- Welches der beiden Besser?
		- Vor- und Nachteile beider
		- Effizienter -> weniger Rechenschritte
		- schwierig zu entscheiden welches Verfahren günstiger
		- Brauchen maß der Effizienz -> Komplexität -> Ressourcenbedarf -> Abhängigkeit der Länge der Eingabe
			- Rechenzeit
			- Belegter Speicher
			- Eingabe/Ausgabe
		- Faktoren
			- Hardware(Leistungsfähigkeit)
			- Code Qualität(Computer, ...)
			- Eingabe(Länge/Größe n der Eingabegröße)
			- der Algorithmus selbst
				- Laufzeit als Funktion der Eingabegröße ausgedrückt: T(ime)(n)
		- bekannte Maschiene, bekannte Daten -> Messen -> langweilig
		- unbekannte Maschiene, bekannte Daten -> Zählen -> schon interessant
		- unbekannte Maschine, unbekannte Daten -> Berechnen (algebraisch), asymptotisch abschätzen
### Komplexitätstheorie befasst sich mit 
- Zeitkomplexität (Ressourcenbedarf Rechenzeit)
- Speicherkapazität(Ressourcenbedarf Speicherplatz)
### Zugrunde liegt ein Abstraktes Maschinenmodell
- Turing maschine, Random access Maschine
- Elementaroperation
	- zuweisung, Vergleich, arithmetische Operation, Array zugriff
- nicht elementare Operationen
	- Schleife, Funktionsaufruf

### Komplexitätsklasse

### Kömplexität von "contains"
- gegeben: Array A von ganzen Zahlen, sowie von Konstante c
- Frage: ist c in A enthalten
- Prinzipell gibt nun drei möglichkeiten für Komplexität
	- Bester Fall (bestcase) -> Tbest -> c nicht im Array -> 4 * n
	- Schlimmster Fall (worst case) -> Tworst ->nur c ist im Array -> 5 * n
	- Durchschnitt (average case) -> Tavg -> Zusatzannahme erforderlich: c sei mit p = 0.5 gar nicht, sonst genau einmal enthalten -> 4* n + 0.5
- Ist ok-ish

### Randbetrachtung
- Vorzeitiges Abbrechen bei Erfolg/Misserfolg
	- Treffer beim Ersten Zeichen oder gar kein Treffer
- Duplikate vs. einmalige werte in EIngaben
	- Bei Duplikation je nur einmal Berechnung nötig
- Sortierung der Eingabemenge
	- Früheres Abbrechen, oder direktes Springen zum Zielbereich
- Müssen wissen wie aufwändig sortierverfahren ist 
- müssen wissen wie die Daten aufgelistet sind

## asymptotische  obere Schranke
- Bei Betrachtung der Komplexität die Verhältnisse bei hohen Problemgrößen interessant
	- Viele Datensätze
- Niederrangige Terme werden bei wachsender Eingabegröße irrelevant
- bei n gegen unendlich -> n^2 wichtiger als n
- Bei großem n ist daher nur der höchstgradige Term interessant
	- verbesserung der Präzision
	- Verbesserung ...
- Funktionsverlauf:
	- Verbesserung im Funktionsverlauf nützt bedeutend mehr als eine Justierung von Konstanten 
	- Konzentrazion auf verbesserung des höchstgradigen Terms
	- konstantes nicht wachstum -> gaußsche Summenformel
	- logarithmisches Wachstum -> umkehrfunktion der exponentialfunktion -> binäre logarithmus (log2(n)) -> Binäre suche -> Bäume -> wächst ins unendliche -> log2(2^18) = 18
	- lineares Wachstum -> verlauf von contains-methode -> alle algorithmen die eine Schleife durchlaufen -> lineare suche
	- n-log n Wachstum-> n* der logarithmus(n) -> algorithmus mit logn -> irgendiwe schleife -> n elemente in Baum einfügen
	- quadratisches Wachstum -> geschachtelte Schleifen
	- kubisches Wachstum -> drei geschachtelte Schleifen :D 
	- exponentielles Wachstum -> 2^n -> umkehrfunktion zu logarithmisches Wachstum -> Türme von Hanoi
	- fakultatives (? ist das ein echtes Wort) Wachstum
- Effekt eines schnelleren Rechners
	- nimmt mit wachsender Zeitkomplexität ab
	- Moore's Law
		- nicht ganz das
			- Rechner geschwindigkeit verdoppelt sich alle 1.5 - 2 Jahre
				- Verbesserung im Rahmen von 2^n (n = Jahre)
		- richtig
			- Komplexität (Anzahl der Transistoren) verdopppelt sich etwa alle 1.5 - 2 Jahren
	- May's/ Wirth's Law -> Intel
		- software effizienz halbiert sich alle 18 Monate
		- nichts gewonnen :(
	- relevant ist Komplexität bei sroßen eingaben n
	- Größenordnung der Zeitkomplexität abschätzen
		- asymptotische Zeitkomplexität
- Obere Schranke
	- 1. Funktionen (Polynom) sieht recht unhandlich aus
	- 2. mit constante c wächst die Funktion schneller -> auf Funktion Koeffizienten multiplizieren -> Kurvenverbiegen -> c = biege Koeffizient
	- g liegt unter f -> für kleine werte von n  -> nicht so gut -> aber sagen es ist egal -> gewisse größe
	- n0 und c sind wichtig
	- Für ein ausreichend Großes c wächst g ab einem Punkt n0 schneller als f
		- Formal:
			- c > 0
			- Es gibt ein n0 wo für alle n > n0 gilt: c * g(n) > f(n)
		- O(g) = {f: Es gibt ein n0 aus den Natürlichen Zahlen, ein c aus den Reellen Zahlen, es gilt c>0 für alle n >= n0, gilt f(n) <= c* g(n)}
		- Intuitiv:
			- O(g) ist die Menge aller Funktionen f, die höchstens so stark wachsen wie g -> groß O -> in Latek: \scriptO
		- man sagt, falls f aus O(g), dann ist f durch g nach oben beschränkt
		- Allgemein:
			- "langsam wachsende aus o(Schneller wachsend)"
			- f muss kleist mögliche menge sein -> kann aber auch alle g sein, die ein größeres Wachstum haben
			- f = O(g) -> funktion nicht gleich menge -> also falsch
				- immer elementschreibweise hierbei 
				- typischer weise f:N -> N und g: N  -> N
			- Funktionen die Laufzeit abbilden sind monoton
				- wäre nicht der fall, so müsste Laufzeit für Problemgrößen n1 < n2 höher sein als jene für n2, so könnte man das problem bis n2 berechnen und die "überflüssigen Ergebnisse" bis n1 wegwerfen
				- eliminierte Konstanten:
					- O(n), O(n/2), O(17n) -> gleichen Funktionen enthalten
					- bildet obere Schranke:
						- f(n) aus O(n log n) folgt auch f(n) aus O(n^2)
					- logb x = c* loga x -> basis des Logarithmus spielt kein Rolle
				- Regeln: 
					- f aus O(g) => c * f aus O(g)
					- Inklusionsbeziehung
					- Optimale Schranke -> Schranke so eng wie möglich setzen
				- Landau Symbole: Theta Notation
				- Mittels der Menge O(g) und Omega(g) kann man definieren:
					- Theta(g) ) O(g) n Omega(g)
					- Menge aller Funktionen die genau so stark wachsen wie g
					- exakte/optimale Schranke -> wenn f in allen mengen ist
	- Teilprogramme:
		- Zeitkomplexität eines Programmes -> Zeitkomplexität der Teilprogramme
		- Komplexität einer Elemtaroperation ist O(1)
		- definierte Folge von Elementaroperationen (unabhängig von n) hat weiterhin konstante dauer -> O(1)
		- Teilprogramme S1 und S2 -> T1(n) aus O(g1(n)) ^T2(n) aus O(g2(n))
			- Summenregel, wenn Teilprogramme hintereinander ausgeführt werden -> sachen addieren -> T1(n) + T2(n) aus O(g1(n)+g2(n)) = O(max(g1(n),g2(n)))
			- Produktregel: -> geschachtelte Ausführung von S1 und S2
				- T1(n) * T2(n) aus O(g1(n) * g2(n)) 
- Rekkurenzrelation
	- Prozeduren werden alleine Analysiert -> Laufzeit bei Aufrufen eingesetzt
	- Rekursive Aufrufe -> rekkurenzrelation -> Differenzengleichung
		- Wieder geschlossene Form finden
	- Basisfall für kleine n -> n = 1 (Rekursionsanker)
	- generischer Fall wird in Abhängigkeit von vorherigen Berechnungsschritt berechnet
		- geht auf eine konstante zu 
		- fakultät mit rekursion ist O(n)
		- Türme von Hanoi -> O((2^n)-1)
- Sortierverfahren
	- Essentiell für UI's
	- beschleunigt datenabfrage (Join)
	- 25% der Rechenzeit für Dortieren
	- Duplikate finden
- Sortierproblem
	- Eingabe
		- Folge von Elementen (Datensätze)
		- {S1, S2, S3, S4,...,Sn} -> n Elemente
		- Datensätze sortiert man nicht, sondern die dazugehörigen Schlüssel(Key)(Schlüssel verweist auf Datensatz)
			- Ki für jedes Si mit i aus \[1;n]
	- Ausgabe
		- Sortierte Folge von Elementen
		- Permutation -> Groß Psi
			- Ki < kj? mit i, j aus \[1;n]
		- in Java Methode -> compareTo(otherObject) -> wenn man Ordnungsrelationen haben will
	- Vergleichsbasierte Sortieralgorithmen
		- Transposition
			- Bubble Sort
		- Einfügen
			- Insertion Sort
			- Tree Sort
		- Prioritäts-Schlangen
			- Selection Sort
			- Heapsort
		- Teile und Herrsche
			- Quicksort
			- Merge Sort
		- Diminishing Increment
			- Shell Sort
	- Hardwarebasierte Sortieralgorithmen
		- Systoiic Arrays
	- Adress-basierte Sortieralgortihmen
		- Proxmap Sort
		- Radix Sort
- Sortierverfahre - Basis
	- Folge/Liste/Array von Elementen/Schlüsseln
	- Einteilen in sortierte und unsortierte Teil
		- Bei Teile und Herrsche Abschnittsweise
	- Reihe von Vergleichs und Tauschoperationen
	- Stabilität 
		- Schlüssel haben den gleichen wert
		- Tauschen niemals ihre position miteinander
	- Aufwand für Selectionsort
		- kann nicht erkennen, wenn Array frühzeitig sortiert ist
		- Zuweisungen 4 (max 8)
		- Vergleiche 7 (immer)
		- Vertauschungen 1(max 1)
			- 2n+1 Niedergradiger Term nach O -Notation
			- Anwendugnsreduktion in jeder Runde
			- im endeffekt n* n = n^2
- Sortierverfahren in der Praxis 
	- TimSort -> Soritierverfahren in Phython das erst mal Implementiert
		- Sortierte Listen müssen nicht sortiert werden
			- Liste durchgehen und schon Sortierte Teile (nennt man "runs")  identifiziert
				- O(n)
			- War liste schon sortiert? -> fertig
			- Flasch/absteigend sortierte Liste? -> umdrehen O(n)
		- Teils sortierte Listen
			- Sortierte Runs identifizieren und nicht sortierte Elemente mittels Insertions sort einfügen
			- Sortierte Runs zusammenführen (MergeSort)
- Laufzeit
	- Speicher in GPUs sind langsamer als register im Prozessor
	- Laufzeiten kann man im Deutschen Wiki nachschauen
- Abstraktion
	- Abstrakte Darstellung als "Graph"
	- Kanten und Knoten
	- Anzahl Kanten pro Knoten muss gerade sein um rundweg zu erstellen
- Graphentheorie
	- Darstellung von Objekten und deren Bezihung
	- Graphen gehören zu den wichtigsten allgemeinen Denkstrukturen der Informatik
	- Anwendungen in vielen anderen Wissenschaften
	- Graph G=(V, E) besteht aus
		- Menge V = {v1, v2, ..., vn} von Knoten (vertices)
		- Menge E echte Teilmenge V x V von Kanten (edges)
		- Graphische Darstellung
			- Knoten als Kreis
			- Kante als verbindungslinie
			- **Einfacher** Graph -> keine Mehrfachkante erlaubt
				- Aber im Computer kann das mit mehrfachkanten funktionieren
					- Imemr angeben, wenn mehrfach kanten erlaubt sind
			- Gibt auch schlinge -> Kante auf sich selbst
			- **ungerichteter** Graph -> sind nur kanten, nicht arrows
			- **Gerichteter** Graph -> vertices und arrows -> anstelle von kanten Pfeile
				- G = (V, A) -> V -> vertices, A -> arrows -> A echte Teilmenge {(vk, vj) | vk aus V und vj aus V} -> Knotenpaare sind geordnet
				- gerichtete Graphen heißen auch DiGraph ( directed Graph) ( gibt auch noch gerichteter a Graph)
			- Knoten heißen **adjazent** wenn sie durch kanten verbunden sind
			- Eine kante (vk, vj) oder andersrum , die einen Knoten vk berührt heißt **indizent**
			- Ein knoten v ist ein Nachbar von vk wenn knoten adjazent sind
				- Menge ller Nachbarn sind N(vk) (neighbour)
				- Vorgänger (**predecessor**) P() =
				- Nachfolger(**successor**) S()=
					- Das hier merken :D
				- **Grad** eines Knoten d(v) -> **degree** -> alle Kanten die zu einem Knoten inzident sind (anzahl der Kanten eines Knotens)
					- wenn Schlinge, zählt als 2
				- bei digraph kann man auch noch zwischen **Außengrad**(Kanten die weggehen) und **innengrad**(kanten die auf einen zukommen) unterschieden
				- wenn Knoten d(v) = 0 -> heißen **Isoliert**
					- z.B. isolierte Bahnhöfen, Netzwerkdaten -> Follower, Likes, etc.
				- Sanity check
					- Summe aller innengrade und summe aller außengrade sollen gleich sein
				- Ein Graph dessen Knoten alle den gleichen Grad haben heißen **regulär**
				- In einem **vollständigen** (vollvermascht) Graph ist jeder Knoten mit jedem anderen verbunden
				- Ein **Teilgraph** G'=(V', E') entsteht durch entfernen von Knoten und Kanten
					- V' echte Teilmenge V und E' echte Teilmenge E bzw. A' echte Teilmenge A (nicht so gern)
					- an sich geht auch unechte Teilmenge -> unechter Teilgraph (ist lieber)
					- Dann schreibt man auch G' Teilmenge G
					- Wenn Knoten entfernt werden müssen auch inzidente Kanten entfernen, sonst nicht mehr verbunden
				- Eine **Clique**(Klicke :D) ist ein **vollständiger** Teilgraph
				- **Untergraph**(Partialgraph) G' = (V', E') entsteht durch das entfernen **von Knoten** (und deren inzidenten Kanten)
					- nur Kanten, deren Knoten noch existieren und die auch vorher (in G) schon eine Kante war
					- jeder Untergraph ist ein Teilgraph
					- Nicht jeder Teilgraph ist ein Untergraph
				- Zwei Graphen G1(V1, E1) und G2(V2, E2) sind **isomorph**, wenn eine bijektive Abbildung Phi zwischen G1 und G2 mit
				- Phi: V1 -> V2 so dass
					- (v, w) aus E1 <=> (Phi(v),Phi(w)) aus E2
						- kann sich beim abbilden aussuchen, welchen Knoten man nimmt 
							- muss nur die gleiche Anzahl an Kanten haben
						- Abbildung durch Tabellen darstellen
					- Isomorphe Graphen haben gleiche graphentheoretische Eigenschaften
					- Zwei vollständige Graphen mit der selben Knoten Anzahl sind isomorph
				- **Pfade** 
					- Ein weg p (Path) ust eine Folge p = w1, w2, ..., wk von Knoten mit (wi, wi+1) aus E für 1<= i <= k
					- Wenn G ein gerichtieter Graph ist, spricht man analog von einem **gerichtetem Pfad**
					- für Pfad p = w1, w2, ..., wk heißt w1 der **Anfangsknoten** von P und wk der **Endknoten** von p
					- Pfad heißt **Knoteneinfach**, falls jeder Knoten in p nur einmal vorkommt
					- Pfad heißt **Kanteneinfach**, falls jede Kante in p nur einmal vorkommt
					- Ein kanteneinfacher Pfad heißt **Kantenzug**
					- **Zyklus**(geschlossener Weg, Kreis) ist ein Pfad bei dem Anfangs und Endknoten gleich sind
					- Ein **kanteneinfacher** Zyklus ist ein Zyklus, bei dem akke Kanten nur einmal vorhommen
					- **knoteneinfacher** Zyklus ist ein Zyklus bei dem alle Knoten mit Ausnahme des Anfangsknoten nur einmal vorkommt
					- **Länge** eines Pfades |p| ->ist gleiche Anzahl der Kanten in p, d.h. |p| = k -1
					- Knoten zwischen denen ein Pfad existiert heißen **verbundene Knoten**
					- Wenn in einem Graph belibige Knotenpaare verbunden sind heißt der Graph **zusammenhängend**
					- Ein nicht zusammenhängender Graph besteht aus zwei oder mehr **Komponenten** die zusammenhängende Graphen sind
				- **Eulersche Graphen**
					- **Eulersche linie** (eulerscher Kreis) eines Graphen ist der kanteneinfache Zyklus der alle Kanten umfasst
					- Ein **eulerscher Graph** ist ein Graph in dem eine Eulersche Linie existiert
					- **Satz**(besondere Eigenschaften Eulerscher Graphen)
						- Ein **zusammenhängender** graph G ist ein Eulerscher Graph genau dann, wenn alle Knoten in G einen **geraden Grad** haben
				- **Hamiltonsche Graphen**
					- Die **Hamiltonsche Linie** (Hamiltonscher Kreis) eines Graphen ist der knoteneinfache Zyklus der alle Knoten umfasst
					- Ein **hamiltonscher Graph** ist ein Graph zu dem eine Hamiltonsche Linie existiert
					- Die Länge einer Hamiltonsche Linie in einem Graphen mit n Knoten ist n
					- gibt keine einfache Charakterisierung Hamiltonscher Graphen
						- gibt auch keine einfachen Algorithmen zu deren Überprüfung
	- Anwendungsbeispiel:
		- **Erreichbarkeit** -> sind Computer über irgendwelche Pfade erreichbar
		- wichtiges Problem für Routing, Garbage Collection, etc.
			- **Wegegraph** 
				- existiert zwischen zwei Knoten ein Weg
				- macht meist nur bei gerichteten graphen sinnvoll
				- G+ =(V, A+)
				- Knotenmenge bleibt gleich
				- in A+ immer dann einen Pfeil im Knoten, wenn es zwischen den Knoten in G einen Pfad gibt
				- werden zusätzliche Knaten eingefügt, verbinden Knoten zwischen denen ein Weg existiert
				- Triviale Ege (verbindungen zwischen Nachbarn) existiert bereits ein G. "Schlingen" nur dann, wenn es einen Zyklus gibt
		- **Prozessabhängigkeit**:
			- Zyklus finden -> negative sache -> problem, wenn zyklus
			- Schlinge weist auf zyklen hin
		- Zyklen in Graphen und Wegegraphen
			- Wir wollen feststekken ob in einem gerichteten Grapd Zyklen existieren
			- Wichtiges Problem z.B. bei Ressourcenallokation -> Deadlock vermeiden
			- Ein gerichteter Graph G heißt azyklisch wenn in G keine Zyklen existieren
				- DAG (direct acyclic graph)
- **Planare Graphen**
	- Graphen so darstellen, dass sich keine Kanten schneiden
	- Praxisbeispiel: PCB(printed circutboard)-Design und chip desing
		- Leitende Bahnen dürfen sich nicht schneiden
	- Analog: Infrastruktur, wie Wasser, Strom, Straßen, Schienen, ...
	- Praxisbeispiel: Färbeproblem
		- Landkarten mit Flächen als Knotengemeinsame Landesgrenzen als Knaten
		- Kanten zwischen Ländern -> unterschiedliche Farben
		- 4 Farben genügen immer in planaren Graphen
	- Einbettung
		- Abbildung in Ebene
		- Abbildung von Knoten in Ebene
			- Koordinaten zuweisen
			- G = (V;E) -> R^2
				- Beispiele
					- v1:(2;1)
					- v2:(5;1)
			- Abbildung von Kanten in Ebene
				- Pfade zuweisen ... aber ...
			- Für planare Einbettung
				- Jordankurven zuweisen
				- Kanten müssen keine Geraden sein
					- Kurve welche sich selbst nicht berührt/schneidet Ausnahme: Start und Endpunkt
			- Planare Einbettung/ "Plättung"
				- Bedingungen an planare Einbettung
					- keine zwei Knoten an gleicher Position
					- Alle Kanten sind Jordan Kurven
					- Keine zwei Jordankurven berühren oder schneiden sich gegenseitig
						- außer gemeinsame endpunkte
				- Ein Graph der eine Planare Einbettung hat, ist ein Planarer Graph -> also falls er irgendwie Planar sein kann ist er das auch
			- Testen auf Planarität
				- Jeder einfache planare Graph mit mindestens 3 Knoten ...
					- Vollständiger Graph mit 5 Knoten ist der Kleinst mögliche nicht planare Graph
				- hat höchstens 3 * |v| - 6 Kanten
					- Eulerischer Polyeder Satz (n(Knoten)- m(Kanten) +f(Flächen) = 2)
						- notwendig aber nicht hinreichend
						- Weder K5 noch K3,3 sind als Minoren enthalten -> Kuratowski
							- K5 ist der kleinste vollständige Automat der nichtmehr Planar einbettbar ist
						- K3,3 ist ein Bipartierter Graph -> hat zwei seiten, innerhalb der Seiten garnicht verbunden, innerhalb beider vollständig
							- ist der kleinste bipartierter Graph 
					- Minoren und unterteilungsgraphen
						- Minoren -> also satz von Kuratowski
						- Unterteilung -> Kante durch Knoten und Zwei Kanten ersetzen
						- Satz von Kuratowski 
							- ein Graph ist genau dann planar, wenn er keinen teilgraphen enthält, welcher als Unterteilungsgraph aus den Minoren K5 und K3,3 entstanden ist
						- Ein graph ist planar wenn er sich geometrisch in der Ebene darstellen lässt, so dass sich keine zwei Kanten überschneiden
						- geometrische Farstellung in der Ebene Dan Knoten werden Koordinaten in R^2 zugewiesen
						- Kanten, welhe sich nicht selbst schneiden heißen Jordan kurven
						- Für eine Planare Einbettung gelten die regeln oben
				- Markierungen
					- Straßen wechsel soll z.B. als neue Knoten eingefüegt werden können
					- Markierungen von Kanten und Knoten sind notwendig
						- Knotenmarkierungen
							- S sei eine beliebig nicht leere Wertemenge
								- Knotenmarkierung eines Graphen ist eine Abbildung f: V ->S
						- Kantenmarkierungen
							- S sei eine beliebig nicht leere Wertemenge
								- Kantenmarkierung eines Graphen ist eine Abbildung g: V x V ->S
						- Für eine Kante e = (u, v) nennen wir g(e) das Gewicht von e
							- Gewicht stellen häufig Entfernung oder flüsse dar
						- Klassische Problemstellungen in kantenmarkierten Graphen sind Wegeprobleme und Flussprobleme
- **Graphen - Algorithmen**
	- Darstellung in Computern
		- Meist einfache Graphen 
		- Formen der Darstellung 
			- *Adjazenzmatrix*
				- n x n Matrix bei n = |v| Knoten
				- sagt aus ob knoten verbunden sind
					- bei ungerichteten Graphen ist Matrix symmetrisch
				- Adjazenztabellen(exotisch)(Sammlung von Adjazenzlisten)
				- Nachfolger oder Nachbartabellen
					- Nachbartabellen
					- **Adjazenzlisten** -> mit welchen Nachbarn man Adjazent ist
				- Auch relevant -> verkettete Listen als Warteschlange oder Deque
			- **traversieren** ->Aufzählen, Besuchen, Inspektion aller Knoten bzw Kanten
			- **Traversierungsalgorithmus** -> Systematischer Aufruf einer speziellen Operation auf jeden Knoten z.B. ausgabe des Knotenschlüssels
			- **Tiefensuche** -> depth first search(dfs) -> also erst bis zum ende eines Knoten
				- Reihenfolge in der die Knoten besucht wurden ist die Traversierungsreihenfolge
					- Kanten, die Während des Algorithmus zu einem noch nicht besuchten Knoten führen bilden einen Teilgraphen
			- **Breitensuche** ->alle Kinderknoten zuerst und dann immer weiter runter
				- Aufwand: |v|-1 -> min, (|v|* (|v| -1))/2 -> Max
- Topologische Sortierung
	- **Partielle Ordnung** -> Halbordnung
		- besteht aus Menge M und reflexiv, transitiven ordnungrelation <=
		- Eine **strenge partielle Ordnung** ist irreflexiv und transitiv (Ordnungsrelation <)
		- Einige Elemente sind u.U. unvergleichbar
	- **Azyklische Graphen** beschreiben partielle Ordnungen Seien
		- G =(V, A) ein azyklischer, gerichteter Graph
		- G+ = (V, A+) der dazugehörige Wegegraph
			- Hat keine Schlingen, sonst wäre er nicht Azyklisch
		- G* = (V, A*) definiert als A* = A+ U {(v,v)| v aus V}
	- Prozassabhängigkeit dann erfüllt, wenn es keine Zyklen gibt
	- **Azyklische Graphen** (DAGs) **beschreiben** (strenge) **partielle Ordnungen**
	- Idee: strenge partielle Ordnung wieder auf Graph übertragen
		- Topologische Sortierreihenfolge
			- Sequenz von Objekten die einer (strengen) partiellen Ordnung entspircht
		- Anordnung von Elementen mj einer partiellen geordneten Menge (M, <=) in einer Folge m1, m2, ..., mk heißt topologische Sortierung wenn für zwei beliebige Indexpaare i und j mit 1 <= i < j <= k gilt:
			- Entweder ist mi <= mj oder
			- mi und mj sind unvergleichbar
			- Bei Topologischer sortierung kann man auch mit Komma getrennte Liste machen -> sortierte liste von Knoten
		- **Top-down** -> solang G nicht leer ist:
			- Finde einen Knoten v mit Eingangsgrad 0
			- Lösche v mit allen dazugehörigen Kanten aus G
			- Speichere die gelöschten Knoten in dieser Reihenfolge
			- Aufwand -> O(|v|^2)
		- **Bottom-up** 
			- Ausgehend von allen Knoten mit Eingangsgrad 0, starte eine DFS-Traversierung
			- Vergebe rückwärts Besuchsnummern vom tiefsten Knoten aus beginnend
			- Aufwand:schleife ist O(max(|V|, |A|) -> O(|A|) -> ist schneller :D
		- wenn Zyklus vorhanden -> keine topologische Sortierung
	- **Spannbäume**
		- Verkabelung
			- Beispiel: 8 Geräte -> verkabeln
			- Ziel 1: Jedes Gerät erreichbar -> BUS-System wird verwendet
			- Ziel 2: Möglichst "günstige" verkabelung
			- keine Zyklen (bei BUS auch problematisch)
			- Algorithmus:
				- solange min ein Zyklus -> entferne beliebige Kante
				- Testen auf Zyklen -> DFS zum Startknoten zurückgefunden, dann Zyklus
					- O(max|V|, |E|) -> meist O(|E|)
		- Teilgraph B ist ein **Spannbaum** eines Graphen G wenn keine Zyklen in B existieren und B alle Knoten von G enthalten
			- Hier schauen, dass am Ende eine Kante weniger als Knoten
			- kann mehrere Spannbäume geben
			- Welche Kante entfernen? -> letzte Kante der Traversierung
		- Was ist ein guter Spannbaum?
			- Jeder Kabelabschnitt hat Länge -> Kantengewichte
		- Ziel 3: möglichst kurze verkabelung
		- **Kantenmarkierung c**
		- **Gewicht c** eines Spannbaumes B = (V, T) ist die Summer der Gewichte seiner Kanten
			- c(B) = Sigma e aus T c(e)
		- **Minimaler Spannbaum** eines Graphen G wenn für jeden Spannbaum B' = (V, T') von G gilt c(B)<=c(B')
		- **Kruskal Algorithmus** -> minimale Spannbäume
			- **Greedy Prinzip** -> entscheide aufgrund des Wissens was aktuell vorliegt, revidiere diese Entscheidung nie -> wähle das aktuell beste
				- ist effizient 
			- T = {};
			- while (noch nicht fertig -> |T| < |V|-1) {
				- wähle geeignete Kante e aus E;
				- T = T U {e} 
			- }
		- Geeignete Kante -> prinzip des geringsten Kantengewichts
			- sortiere Kante nach ihrem Gewicht
			- Für Kante mit niedrigstem Gewicht:
				- Falls T U {e} ein Zyklus bilden würde: verwerfe
				- sonst T = T U {e}
		- Komplexität ergibt sich aus
			- Aufwand für Sortieren der Kanten -> O(|E| log |E|) (Heapsort) -> 1-mal
			- Aufwand für Test auf Zyklen (ebenfalls O(|E| log |E|)) -> im schlimmsten Fall |E|-mal -> |E| * |E| = |E|^2
				- Testen auf Zyklen kann auch über Test auf verschiedene Komponenten erfolgen -> Speicher O(2 * |V|) -> dinge in die einzelnen Komponenten packen
				- Gesamtaufwand: **O(|E| log |E|)**
		- Verbesserung von Kruskals Algorothmus durch Prim (manchmal auch Dijkstra)
			- G = (V, E) mit Markierung c
			- ges.: minimaler Spannbaum B = (V, T) von G
			- ![[Pasted image 20250423091157.png]]
				- Vorteil: kein testen auf Zyklen, Nachteil: haben zusätzliche Datenstruktur V'
				- hat  O(|E| + |V| log |V|), |E| >= |V| -1 gilt in zusammenhängenden Graphen
				- Weitere Verbesserung durch Cheriton und Tarjan -> O(|E| log log |V|)
				- für planare Graphen Verwendung von Heuristiken möglich: Aufwand O(|V|)
					- kommt aber nur selten vor
				- für minimale veränderung an Aufgabenstellung gibt Probleme:
					- Schranke auf Maximalem Knotengrad im Spannbaum
					- **Steiner-Baum**: minmaler Spannbaum auf Teilgraph mit Teilmenge der Knoten, der min eine gegebene Menge von Knoten enthält
					- NP -> nicht deterministisch polynomiell -> alle möglichen Lösungen ausprobieren
		- **Wegeproblem/Pfadproblem**
			- hier kann nach kürzesten Pfaden gesucht werden
			- 1. Ansatz: Brute-force
				- einfachster Algorithmus
				- meistens: robiere alle Möglichkeiten aus
				- Hier: backtracking
				- Aufwand: normal exponentiell
				- vollständiger Graph, alle wege können begangen werden
				- n Städte -> (n-1)! verschiedene Wege mit je n-1 streckenabschnitten
					- Komplexität: O(nn!)
			- #

## Bäume
- Baum hat kein Zyklus
- Ebene/Stufe 
	- wurzelknoten ist ebene 0 
	- kind ist ebene 1
	- kind kind ist ebene 2
	- ...
- Ist länge des Pfades von der Wurzel aus
- Höhe
	- max Ebene +1
	- Anzahl der Ebene 
- Gewicht 
	-  Anzahl der Blätter
- Baum der Höhe h und Ordnung k hat max N(h, k) = ((k^h)-1)/k-1 knoten
	- also max von N(h)=(2^h)-1
	- Umkehrung: h(N) = log2(n+1) -> minimale Höhe
- Baum wächst logarithmisch
- Geordneter Baum
	- wenn reihenfolge vom unterbaum relevant ist
	- Unterbäume bilden eine geordnete menge
- Binärbaum
	- endliche Menge von Elemente
	- ist entweder leer oder enthält ausgezeichnetes Element w und Eigenschaften
		- verbleibende Elemente sind in zwei disjunkte Untermengen aufgeteilt
		- jede Untermenge ist selbst wieder Binärbaum
			- heißt linker bzw rechter unterbaum von B
	- ist geordnet (nicht der leere) -> nicht jeder geordnete ist ein binärbaum
- ähnlich
	- zweii Bäume ähnlich, wenn gleiche Struktur
	- Isomorphie bei Graphen
- äquivalenz
	- zwei Binärbäume sind ähnlich und enthalten gleich informationen
- vollständiger Binärbaum
	- enthält max Anzahl an Knoten für seine Höhe
	- jeder Knoten der ebene h-1 ist ein Blatt
	- jeder Knoten der ebene i < (h-1) hat nichtleere linke und rechte unterknoten
- strikter Binärbaum
	- jeder innerer Knoten hat Grad 2
	- vollständige Binrbäume sind auch strikt, aber nicht umgekehrt
	- sind nicht bis nach unten aufgefüllt
- fas vollständiger Binärbaum
	- es existiert k >= 0, sodass
		- jedes Blatt im Baum auf Stufe k oder k+1 ist
		- falls innerer Knoten rechten Nachfahren auf stuef k+1 hat, ist linkerteilbaum vollständig mit blättern auf stufe k+1
		- jeder Knoten auf kleinerer Stufe als k hat Grad 2
		- baum wird zeilenweise von links nach rechts auffüllen
- ausgeglichener Binärbaum
	- es existiert ein k >= 0 sodass:
		- jedes Blatt auf stufe k oder k+1 ist
		- jeder Knoten auf einer kleineren Stufe als k Grad 2 hat
			- Ähnlich zu fast vollständigen 
				- dürfen aber auf untersten stufe überall Blätter "fehlen"
		- fast vollständiige Binärbäume sind auch ausgeglichen, aber nicht umgekehrt
- verkettete Darstellung
	- Höchste flexibilität
	- Normalerweise Speicherverwaltung durch Programmiersprache
	- Jedes Element hat zwei Verweise

## Suchbäume
- Baum, der nach Kriterium sortiert ist
- geht nicht nur mit Knoten, sondern auch über Kanten
- Hohler Baum
	- wenn nur auf der Untersten Ebene -> bei den Blatt knoten Dinge enthalten sind und in den anderen nicht
## Traversierung auf Binärbäume
- ergibt lineare Ordnung auf Knoten
	- Verarbeiten der Wurzel -> W
	- Durchlauf linker Teilbaum -> L
	- Durchlauf rechter Teilbaum -> R

- Permutation der Schritte
	- **WLR**
	- **LWR**
	- **LRW**
	- WRL
	- RWL
	- RLW

- Konvention: L vor R also nur
	- Wann wird Wurzel betrachtet
	- WLR -> Pre-Order (Vorordnung)
	- LWR -> In-Order (Zwischenordnung)
	- LRW -> Post-Order (Nachordnung)
		- ist anwendungsabängig
		- In-order ist hier besser
![[Pasted image 20250625083347.png]]
- Pre-Order in Python Code -> kein schauen ob schon besucht, braucht nicht wegen Binärbaum Struktur
- für andere Orders einfach **print(self, end= '   ')** verschieben
![[Pasted image 20250625083103.png]]

## Mittlere Suchtiefe
- geht nur in Suchbäumen -> Binary-Search-Tree
- Maßzahl für Qualität der Suche
	- Mittlere Suchtiefe für Baum mit n Knoten![[Pasted image 20250625084201.png]]
	-  Beispiel:![[Pasted image 20250625084459.png]]
	- gucken ob das sinn ergibt -> alle Werte  > 4 ergeben kaum Sinn

## Suchtiefe mit Gewichten
- Knoten haben unterschiedliche Gewichte -> Suchwahrscheinlichkeit
	- "leichte"/selten benötigte Knoten -> weit unten
	- "schwerer"/häufig benötigte Knoten -> weit oben
	- ![[Pasted image 20250625085053.png]] p -> Wahrscheinlichkeit (**p**robability)

## Datencodierung - Anwendungsbeispiel
- Genförscher  -> genetische Codes effizient speichern/übertragen![[Pasted image 20250625090214.png]]
- geht noch besser -> nur werte, die auch vorkommen

## Codebaum
- Code als Baum statt Tabelle
	- Leichtere Codierung und Decodierung
	- ![[Pasted image 20250625090748.png]]![[Pasted image 20250625090757.png]]
	- hier nur 5 Schritte -> Tabelle wäre wesentlich mehr
		- Huffman-Codierung ist ein Beispiel
	- Codes variabler Länge:
		- keine Kodierung eines Zeichens ein Präfix der Codierung eines anderen Zeichens
	- Basiert auf Statistik/Abweichungen

## Huffman Codierung
- Häufigkeit der Buchstaben als Gewichtung der Blätter
	- Baum mit min. mittl. Suchtiefe wird mit "Mobile-Technik" erzeugt
- Dann die 2 leichtesten Werte miteinander verbinden
- Algorithmus zur Erzeugung eines gewichteten Binärbaums mit minimaler mst