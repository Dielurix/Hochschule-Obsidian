
# Kombinatorik und Abzählbarkeit
- Was kann ein Computer berechnen - was nicht?
 Zählproblem
- Kombinatorik -> Abzähl- und Nummerierungs-Frage
	- Wie groß Chance auf Lotto gewinn
	- Wie viele Passwörter
	- Wie viele Gespräche muss Projektteam führen
	- Wie viele Aufnahmen, wenn Besetzung sich ändern soll
	- Gibt zu jeder Rechenaufgabe ein Computerprogramm, welches Aufgabe lösen kann
- Anwendungsbeispiel: All that Jazz
	- 3 Bandmitglieder -> Klavier, Schlagzeug, Bass
	- In jeder Kombi die Aufnahme ein mal machen + A-capella ohne Instrumente
	- Jede Aufnahme 500€, Budget ist 8.000€

	- a)
		- {{}, {B}, {K}, {S}, {B,K}, {B, S}, {K, S}, {B, K, S}}= Potenzmenge({B, K, S}) -> 8
	- b)
		- {{T}, {B, T}, {K, T}, {S, T}, {B, K, T}, {B, S, T}, {K, S, T}, {B, K, S, T}}= Potenzmenge({B, K, S, T}) -> 8
	- c) 
		- 2^n -> Potenzmengenformel
			- |Potenzmenge(M)| = 2^|M| -> kommt aus Mathe 1
	- d)
		- Bei Allen Instrumenten -> n!


- Permutationen(Reihenfolgenänderung) -> eine Möglichkeit/Anordnung
	- A endliche Menge -> bijektive Abbildung -> klein Sigma: A -> A
	- ist die Permutation der Menge A
	- bijektiv -> Zuordnung der Elemente zweier Mengen, die man auch umtauschen kann
- Menge der Permutationen(**symmetrische Gruppe vom Grad n**)
	- Menge Sn := {klein Sigma/klein Sigma ist Permutation der Menge{1, ..., n}}
	- wie viele Permutationen gibt es -> |Sn| oder \#Sn -> n!
	- neutrale Gruppe id  -> hintereinander Ausführung ° von Permutationen
	- n+1 * n! -> n+1!

- Beispiel: Routenplanung
	- Wie viele versch. Strecken kann man von Hamburg nach München gemäß Routenoptionen fahren
		- 4-Elementige Teilmenge, 3-Elementige Teilmenge, 5-Elementige Teilmenge
		- Mehrere Mengen -> cartesische Produkt bilden
- Mächtigkeit cartesisches Produkt
	- Seien A1, ..., An nicht-leere, endliche Mengen
		- |A1 x ... x An = |A1| * ... * |An|
	- wie kann man sich das vorstellen -> Tabelle -> n * m Einträge 
	- Angenommen
		- A1 x **A2 x ... x An** -> wieder eine Menge -> B -> also ist wieder A x B -> |A1 x ... x An| = |A x B| = |A| * |B| -> Rekursion -> Induktiv beweisen 
		- Cartesisches Produkt mit sich selbst -> {1, 0}^n -> bei 64 Bit Systemen -> {1,0}^64 -> 2^64 -> sind 18,4 Exabytes
- Beispiel: Passwort
	- a)
		- s(m, n) = n Sigma k=m |A|^k -> geometrische Summenformel -> (|A|^n+1 -|A|^n )/ |A|-1
	- b)
		-  aus der ganzen Menge 3 Teilmengen machen -> A = B U Z U S
		- Pj = A^j ((B U Z)^j U (B U S)^j) -> (B U Z)^j n (B U Z)^j = B^j 
		- somit ist n Sigma m = j |Pj| = |A|^j - ((|B| + |Z|)^j + (|B| + |S|)^j-|B|^j)
			- mit geometrischer Summenformel -> was langes -> 8,6 * 10^25
- Beispiel:Lotto
	- Binomialkoeffizient
		- n über k ( n k ) := |{A aus P({1, ..., n})| \#A = k}| -> alle Anzahl an elementen ist eine natürliche Zahl 
		- zählt wie viele k-elementige Teilmengen eine n-elementige Menge hat
		- Der Fall n = 0 ist zugelassen, da auch leere Menge erlaubt ist
		1. Ist eine Anzahl also Natürliche Zahl
		2. ist 0 wenn k > n, ANzahl der Teilmenge kann nicht größer sein als Anzahl der Obermenge
		3. (n 0) = 1 = (n n) jede n-elementige Menge hat genau eine Teilmenge mit 0 Elementen (leere Menge)
		4. ada
		5. k-elementige Zeilmenge B von A bestimmt eindeutig eine (n - k)-elemtige Teilmengen von A, nämlich A\B und umgekehrt -> folgende symmetrie
			1. (n k) = (n n-k) für alle k = 0, ..., n
	- s(n) -> addiere die k elementige Teilmengen von n-elementige menge ->                      n Sigma k=0 (n k)
		- zählne die Anzahl einer Potenzmenge einer n elementige Menge
		- formel ohne Addition:
			- n^2 
	- (n 0) -> 1 + (n 1) -> n!/ k!* (n-k)! -> n!/n-1! 
- Pascal'sches Dreieck:
	- Rekursionsformel führt auf das Pascal'sche Dreieck
	- Binomialkoeffizient lässt sich als Pascal'sches Dreieck darstellen
- Binomischer Lehrsatz
	- Sei R ein Komutativer Ring , x, y aus R und n aus Natürlichen Zahlen
		- (x+y)^2 = n Sigma k = 0 (n k) x^k y^n-k
			- für n = 2 -> (2 0)y^2 + (2 1)xy + (2 2) x^2 
		- Beweis
			- Induktionsbeweis nach n
				- für n = 1 -> gilt
				- n -1 als vorraussetzung
				- für n -1 = n -> gilt auch -> (x + y)^2 = (x + y) * (x + y)^n-1
				- summanend bis n laufen lassen, aber letztenn summanden abspalten
				- x^4 + (4 1)(x * 2^3) + ((4 2)x^2 * 2^2) + ((4 3)x^3 * 2)+2^4
					- x^4 +8 x^3 + 24x^2 + 32x + 16
				- b) -> (x - y)^3 also x = y
- Abzählbarkeit
	- endliche Mengen -> gleich viele Elemente
	- Wie ist das bei unendlichen mengen zu zeigen?
		-  Natürliche und Ganze Zahlen -> gleich viele Elemente
	- Endliche Menge:
		- Mengen Durchnummerieren
			- 2 Mengen -> beide Elemente abzählen durch nummerieren
			- jedem Buchstaben eine Zahl zuordnen -> bijektive Abbildung
			- endliche Menge -> wenn Abbildungen bijektiv sind -> gleiche Anzahl der Elemente
	- Unendliche Mengen
		- durchnummerieren?
			- ja anscheinend schon
				- für Z -> 0, -1, +1, -2, +2,.... jeder Zahl eine Natürliche zuweisen N -> 1, 2, 3, 4, 5, ....
				- f: N -> Z 
					- n {n/z, falls n gerade, -n-1/z, falls n ungerade
						- bijektive Abbildung
			- nicht gleich groß -> sondern gleich mächtig, wenn es eine bijektive Abbildung zwischen den beiden gibt
			- Abzählbar -> wenn Menge gleich mächtig zur Menge N der Natürlichen Zahlen ist
				- Natürlichen sind, id: N -> N mit id(n):=n -> bijektiv
				- Z ist abzählbar -> beispiel eben
			- höchstens Abzählbar -> wenn Menge endlich oder abzählbar ist
			- überabzählbar -> Menge weder endlich noch abzählbar
			- ist Menge Abzählbar, so ist Potenzmenge überabzählbar
				- Satz von Cantor
					- Menge und f: A -> Potenzmenge(A) -> f ist nicht surjektiv
					- Beweis:
						- Widerspruchsbeweis
							- gibt doch eine surjektive Abbildung o.O
							- Menge M := {a aus A und a ist aus f(a)} aus Potenzmenge(A)
								- f ist jetzt surjektiv
								- muss also von einem Element, x aus A, sodass f(xM) = M ist
								- liegt jetzt entweder in M oder in A\M
									- Angenommen x aus M = f(xM) -> geht nicht durch Definition von M
									- Angenommen ist in A\M -> muss gelten
										- x nicht aus M = f(xM)
										- wegen Potenzmengen Definition also Abbildung -> geht nicht
						- Kann keine surjektive Abbildung geben
			- Kriterien zur Abzählbarkeit(für komplizierte beweise)
				- Teilmenge einer Abzählbaren menge -> immer abzählbar oder endlich
				- gibt entweder eine injektive Abbildung f: X->N oder eine surjektive Abbildung f: N->X -> so ist X abzählbar  
				- Abzählbarkeit -> immer unendliche Mengen
				- N x N ist abzählbar -> Cantorsche Paarungsfunktion
		- Übungen:
			- a) Cantorsche Paarfunktion -> das gleiche wie bei N 
			- b) A U B -> G -> N -> Abzählbar 0, 0-> 1, -1 -> Abbildung dafür erstellen f: A -> A U B und dann noch n abbilden -> n -> {a(index)(n+1)/2, falls n ungerade; a(index)n/2, falls a gerade -> sollte dann eine bijektive Abbildung sein -> kann aber auch nur surjektiv sein -> ist hierbei jetzt surjektiv -> abzählbar
		- Rationale Zahlen sind abzählbar -> ganze zahlen im Zähler, natürliche im Nenner -> Z x N -> Q, (z, n) -> z/n -> surjektiv (Korollar 159) -> reicht, ist bijektiv -> abzählbar
		- Beispiel:
			- menge P aller verfassbaren Programme ist abzählbar
				- man hat:
					- A -> Alphabet -> endliche Menge an Zeichen |A| = unendlich
					- p aus A^m = {(a1, ..., an)| aj aus A}
					- Menge aller sinnvollen Programme P ist Teilmenge von unendlich Vereinigung M = 0 A^m =: A* -> ist abzählbar
						- |A^m| = |A|^m
						- A^0 = {P0}, A^1 = {P1, ..., P|A|}, A^2 = {P|A|+1,...., P|A|+|A|^2},...
						- Phi: N -> A*, n-> Pn-1 -> ist surjektiv -> ist sogar bijektiv :D -> also abzählbar
						- |P| = unendlich
		- Beispiel: Überabzählbare Menge
			- Menge der Reellen Zahlen ist eine überabzählbare Menge
				- Muss zeigen dass Teilmenge überabzählbar existiert
					- I -> Menge I = ]0; 1\[ := {x aus R| 0 < x < 1}
					- Behauptung: überabzählbar
					- Widerspruchsannahme:
						- doch abzählbar
						- Dann lässt I schreiben als {x1, x2, x3, ....} = I
							- X1 = 0, **a11**, a21, a31, a41...
							- x2=  0, a12, **a22**, a32, a42...
							- x3 =  0, a13, a23, **a33**, a43...
							- ... 
								-  hier wird auf diagonalen geachtet
								- jetzt wird element Konstruiert, was in I liegt, aebr keine der schon erstellten zahlen ist
								- y aus I, sodass y != xk  für alle k aus N
									- y = 0, y1,y2,y3,y4, ... -> jetzt yk -> yk!= akk mit k = 1, 2, 3 -> nicht alle yk = 0
									- y in I -> 0 < y < 1
									- kann keine der Diagonalen Zahlen sein -> somit kann auch nicht x1, ..., xn sein
									- aber {x1, ..., xn} soll doch abzählbar sein -> Wiederspruch >:D -> somit ist Menge Reeller Zahlen überabzählbar
							- Das mit reellen Zahlen hat konsequenz für info
							- Computer können nicht Nachkommastellen ausgeben
							- 
# Analysis (Lehre vom Ungleichheitszeichen)
## Eigenschaften der reellen Zahlen
- Wie präzise sind Computerrechnungen?
- Wichtig:
	- Bernoulli Ungleichung
		- Sei n aus N0 und delta >= -1 -> (1+delta)^n >= 1+n* delta
			- spezialfall x>= -1 und n aus N:
				- (1+(x/n))^n >= 1+x 
	- Archimedisches Axiom
		- Seien 0<x, 0<y, dann gibt es n aus N mit nx >y -> alo hier n definiert als aufrunden(y/x)+1
		- zu jeder beliebigen reellen Zahl Epsilon > 0 gibt es eine natürlich Zahll n aus N sodass 
			- 1/n < Epsilon (Epsilon ist sehr klein)
		- Sei b > 1, dann gibt es zu jedem R > 0 ein n= nR aus N mit b^n > R
		- Epsilon := b-1 > 0, b +1 = Epsilon
			- Daann ist b^n = (1+Epsilon)^n >=(Wegen bernoulli) 1+n* Epsilon > R für n hinreichend Groß
		- Sei 0 < b < 1 dann gibt es zu jedem Epsilon  > 0 ein n = nEpsilon aus N mit 0 < b^n < Epsilon -> (Wie corona sich verbreitet)
	- Rationale Zahlen liegen dicht in den Reellen Zahlen 
		- Seien x,y aus R mit x < y. Dann gibt es eine Zahl q aus Q mit x < q < y
	- gibt in Q die beschränkte Mengen, deren Supremum nicht mehr in Q liegt, z.B. sup{x aus Q; x^2 < 2} != Wurzel(2) nicht aus Q
	- **Sei x >= 0 eine reelle Zahl mit der Eigenschaft, dass x <= Epsilon ist für jedes Epsilon > 0, dann ist x = 0**
		- Konvergenz -> Zahlen annähern ->Folgen -> Zahlenfolgen -> ausrechenen nähern sich einem gewissen wert an -> |an - a| an 0 annähert -> nähert sich an an a an -> 0<= |an-a| <= Epsilon
	- Intervalle
		- Definition: Hat keine Löcher ->Einen nicht leere Teilmenge J von R heißt Intervall wenn für alle a, b aus J mit a <= b gilt: a<= x <= b => x aus J
		- 
## Metrische Räume und Konvergenz(wichtig alles was drunter steht hat damit zu tun)
- Wird Pacman von Geistern gegessen oder nicht?
- Abstand/ Distanz d(x, y) zweier Reellen zahlen x,y aus Z ist definiert als Absolutbetrag der Differenz von x und y -> dR(x, y) := |x-y|
- bei Komplexen Zahlen ist der Absolutbetrag schon definiert
## Eigenschaften die eine Abstandsmessung sinnvollerweise erfüllen muss
- Abstannd zu sich selbst ist Null -> d(x, x) = 0
- Abstand ist immer Positiv -> d(x, y) > 0 -> wenn y != x -> reflexivität
- Abstand von x nach y sollte gleich sein wie y nach x -> d(x, y) = d(y, x) -> symmetrie
- Abstand von y nach y ist höchstens so groß zu dem abstand von x nach z + z nach y  -> d(x, y) <= d(x, z) + d(z, y) -> Transitivität
- **Metrischer Raum** 
	- nicht leere Menge X, eine Funktion f: X x X -> R -> heißt Abstand, Distanz oder Metrik
	- wenn oben genannte Eigenschaften gelten
- **Normierter Vektorraum**
	- Abstand -> Länge des vektors von y nach x 
	- Norm -> länge des Vektors, Norm auf einem Vektorraum:
		- V ein K-Vektorraum, Abbildung ||.||: V -> R
		- mit folgenden eigenschaften
			- für alle x aus V ist ||x||>=0 und es gilt ||x|| = 0 wenn x =0
			- Für alle x aus V und alle Lambda aus K gilt ||Lambda * x|| = |Lambda| * ||x||
			- Für alle x, y aus V gilt die Dreiecksgleichung ||x-y|| <= ||x|| +||y||
		- Kann mehrere Normen auf demselben vektorraum geben -> da Norm nur auf abstrakte Eigenschaften aufbaut
		- Im R^n -> ||x||2: K^n -> R : Wurzel(n Sigma i = 1 |xi|^2) -> **Euklidische Norm** - bekommt ||.||2 den index 2 mit
		- **Maximum Norm** -> ||.||unendlich: K ^n -> R : x ,> n max k =1 |xk| -> größter Absolutbetrag der einzelnen Komponenten
		- Wurzel(2+4+1) ->Max = 2
	- Sei (V, ||.||) ein normierter vektorraum -> d: V xV -> R: (x,y) -> || x - y|| eine normierte Metrik auf V
	- Euklidische Metrik -> d2(x, y)= Wurzel(n Sigma k = 1 |xk -yk|^2) -> 25 -> 5
	- Maximummetrik -> dunendlich(x, y) = n max k=1 | xk - yk| -> 4
- Übungen:
	- a)
	- b)kann unter laufbedingung extra bedingungen schreiben
		- aus der summe den max rausholen und damit zeigen, dass der rest da drauf addiert größer ist, beim letzten ding einfach sagen, dass summe aus zahlen, die alle max sind ausklammern, sodass n * Max ist und weil hier noch klammer, heißt dass Wurzel(n) * max ist Ungleichungskette ||x||unendlich <= ||x||2 <= Wurzel(n)* ||x||unendlich
- Seien (X, d) ein metrischer Raum und A Teillmenge X
	- diam (A) := sup{d(x, y) | x, y aus A} aus R vereinigt {unendlich}
	- heißt durchmesser(diameter) von A bzgl. d
	- A heißt beschränkt, wenn diam(A) < unendlich ist, ansonsten unbeschränkt
		- durchmesser aller intervalle a,b beträgt jeweils \[a-b]
		- durchmesser von R und C ist unendlich
		- durchmesser der Menge {z aus C; |Re z| <= 1, 0<= Im z<=1} ist Wurzel(5)

## Folge
- Rekursive Folge -> jedem wert n aus N0 wird eine zahl xn aus Q zugeordnet
- Was ist allgemein eine Folge
	- kan in beliebigen mengen definiert werden
	- ist abbildung der Natürlichen Zahlen in X rein
	- X ist nichtleere menge
	- Nullfolge -> was mit epsilon und 0 und ein wert dazwischen, welcher sich mit größer werdendem n an null annähert
	- Schreibweise
		- (an(Folgenglieder))n aus N(indexmenge)
	- Sei (X, d) metrsicher Raum (an) eine Folge in X und a aus X 
		- a heißt beschränkt, wenn die Wertemenge {an |n aus} beschränkt ist
## Konvergenz(Wichtig!!!!!)
Übung
- 1.
	-  wenn x = y -> d(x,x) -> 0
	- wenn x != y -> < 0 -> ist nämlich definiert als 1
- 2.
	- wenn x= y -> lassen sich ja einfach umdrehen ist ja das deslbe
	- d(x, y) = 1 = d(y, x) 
- 3. 
	- wenn x = y -> ist das + kann nicht negativ sein -> deswegen eh >= 0
	- sei x, y, z aus R und alle ungleich -> d(x, z) +d(z,y) >= d(x, y)
	- wenn z = y -> 1 >= 0 + 1
	- wenn x = z -> 1>= 1 + 0
		- Handelt sich um eine Metrik
- **Konvergenz und Divergenz** (Wichtigste Definition dieses Semesters, hat alles damit zu tun(wenn auch verschlungen))
	- (an) heißt Konvergenz mit Grenzwerden a, in Zeichen 
		- lim n -> unendlich an = a
		- wenn gilt:
			- zu jeder Zahl Epsilon >0 existiert ein Index N aus Nepsilon, sodass für alle n >= N gilt:
				- d(an, a) <= Epsilon
				- 
				  Dabei bedeutet die Schreibweise Nepsilon dass die Zahl Nepsilon vom Parameter Epsilon abhängen darf (aber nicht notwendigerweise muss)
		- Eine konvergente Folge mit Grenzwert Null heißt **Nullfolge**
		- Eine Folge die nicht konvergiert heißt **divergent**
	- Beispiel Konvergente Folge
		- In jedem Metrischen Raum (X, d) ist eine konstante Folge, d.h.  xn := x aus X für aööe n aus N konvergent mit Grenzwert x
		- Sei k aus N dann ist die durch an := 1/n^k definierte reelle Folge eine nullfolge bzgl. der Absolutenbetragsmetrik auf R
			- hier ist das mit x >= 0 die kleiner ist als Epsilon 
			- immer aauf 1/ n kommen 
			- irgendwie 
			- damit man sagen kann ja hier 1/n <= Epsilon -> n >= 1/ Epsilon und mdan dann mit Gaußklammern aufrunden -> sollte dann passen
		- Wenn nicht explizit anders erwähnt, meinen wir mit R und C immer die durch den Absolutbetrag definierte Metrik -> |folgen - Grenzwert|
		- wie beweisen, dass es keinen grenzwert gibt
			- Widerspruchsbeweis
				- Angenommen es gibt Grenzwert a, d.h. für alle Epsilon > 0 gibt es ein Nepsilon aus N : d(an, a) <= Epsilon
				- speziell müsste d2 für Epsilon:=1/2 gelten -> könnte auch Epsilon 1/3 setzen -> Epsilon muss größer als 0 aber kleiner als 1 sein
				- d(an, a) <= 1/2 für alle n >= N1/2
				- Nach definition von dtrivial ist nur für an = a für alle n >= N1/2
				- d.h. 1/n -> konstante für alle n -> 1/n = a für alle n >= N1/2
- **auffrischung**
	- a)
		- man teilt auf -> n Sigma k = 0 1/k! => (1/n+1!)+(n Sigma k=0 1/k!)
	- b)
		- wie in a, das kleinste n in sn einsetzen und dann zeigen, dass eine monoton wachsende folge ist ->also wie in a -> 5/2 =< s2 + 1/3! +.....
		- ffür sn < 3 -> also erst für k=2 -> dann reihen nebeneinander schreiben -> sieht man dass bei 1/k! -> die werte immer 2,3,....n ist und bei 1/2^k-1 -> ist immer 2, ...., 2 -> also bei 1/k! wird größer, 1/2^k-1 bleibt gleich -> also 1/k! <= 1/2^k-1
		- jetzt nach oben abschätzen -> also für 1/k! ersetzen durch 1/2^k-1 -> jetzt indexverschiebung bei der summenformel -> damit wir geometrische summenformel haben -> sozusagen hiermit dann gezeigt dass das ganze ding 5/2 + sn>2 nciht an 3 dran kommen kann
- **Konvergente Folgen sind Beschränkt**
	- ist an eine konvergente Folge im metrischen Raum (X,d) so ist (an) beschränkt
- **rechenregeln für konvergente folgen**
	- c(C) := {(an)aus Abb(N,C)| (an) konvergiert}
	- dann gilt c(C) ist ein C-Unterraum von Abb(N,C) und die Abbildung  L:c(C) -> C : (an) -> lim n -> unendlich an ist linear
		- Konkret beeutet dies folgendes sind (an) und (bn) konvergente Folgen in C mit Grenzwerten a und b und ist lambda aus C eine beliebige Zahl, dann sind auch die Folgen (an)+(bn) und lambda* (an) konvergent und es gilt lim n -> unenedlich (an +bn) = a+b und lim n-> unendlich (lambda* an) = lambda * a
		- kann man in getrente päckchen packen
	- wenn zwei funktionen mit Eigenschaft lim n-> unenedlich f(n)/g(n) = 1 -> nähern sich asymptotisch an
	- **Üben**
	- Seien (an)n aus N, (bn)n aus N konvergente Folgen in C und Grenzwerten a und b
		- Zeigen sie dass dann auch die FOlge (an, bn) konvergiert mit lim n -> unendlich anbn= ab
		- Zeigen sie: Gilt obendrein b != 0 ist auch die Folge(an/bn) naus N konvergent mit Grenzwerte a/b
		- Folgern sie aus b dass lim  n-> unendlich  nteWurzel(a)= 1 auch für 0 < a < 1 gilt (vgl. beispiel 193)
- **monotone Folge**
	- Eine Folge (an) in R heißt monoton wachsend, wenn für alle n aus N gilt, dass an <= an+1
	- monoton Fallend wenn für alle n aus N gilt, dass an >= an+1
	- gilt in den beiden fällen stets < bzw > dann nennt man (an) monoton wachsend/fallend
	- fallend kann man zeigen, indem man den quozienten beider folgen bilden -> wenn das dann <= 1 ist, dann ist monoton fallen, vice versa bei monoton steigend
	- sei (an) eine reelle Folge
		- ist (an) monoton wachsend und nach oben beschränkt dann ist (an) konvergent und es gilt lim n -> unendlich = sup n aus n {an}
		- ist (an) monoton fallend und nach unten beschränkt dann ist (an) konvergent und es gilt lim n -> unendlich = inf n aus n {an}
- **rekursive Folgen umgehen**
	- bisher gabs explizite folgen->rekurission kommt aber oft vor
	- wie aber rekursive folgen?
		- schritt 1: Zeige dass (xn) nach unten beschränkte ist
		- Schritt 2: Zeige dass (xn) monoton fallend ist
		- Schritt 3: Zeige das lim n -> unendlich = Wurzel(2) ist
	- **übung**
	- x0=1
	- x1= 2/4 -> 1/2
	- x2 =3/2 * 1/4 -> 3/8
	- x3 =11/8 * 1/4 -> 11/32
		- rücken näher an den wert 1/3 heran
		- für monotonie
			- fallend -> differenz von xn+1 - xn <= 0
			- klar ist: xn > 0 für alle n aus N0
			- vollständige induktion -> xn + 1 -4xn /4 = -3n +1/4 <= wann? -> xn >= 1/3
			- behauptung xn ist immer >= 1/3
				- Anfang -> n=0 -> 1 > 1/3
				- vorraussetzung xn-1 >= 1/3
				- I.S
					- xn = xn-1 +1/4 >= (1/3)+1/4 -> 4/12 -> 1/3 passt :D
					- Es gibt einen Grenzwert
						- x= lim n -> unendlich xn existiert x >= 1/3
			- jetzt grenzwerte bestimmen
			- xn = x(n-1) +1 /4 -> xn -> x, x(n-1)+1/4 -> x +1 /4 -> und das passt dann für 1/3
- **unendliche reihen**
## Reihen
- spezielle Folgen
	- Sei (an) eine Folge in C und sei sn:= n Sigma k=1 ak
	- dann heißt die Folge (sn)n aus N (unendliche) Reihe
	- s heißt die Partialsumme der Reihe. man benutzt die schreibweise: unendlich Sigma k = 1 ak
		- für die unendliche Reihe mit Partailsumme sn
		- konvergiert die Reihe so wierd ihr grenzwert ebenfalls so bezeichnet 
			- unendlich Sigma k = 1 ak = lim n -> unendlich n Sigma k= 1 ak
			- Geometrische reihe als beispiel -> geometrosche summe 
- Grenzwert berechnen 
	- Reihen unenedlich Sigma k =1 (1/k(k+1))
	- auf (1/k(k+1)) -> (k+1-k/k(k+1)) -> (k+1/k(k+1))-(k/k(k+1)) -> 1/k + (1/k+1)
		- unenedlich Sigma k =1 (1/k(k+1)) = unenedlich Sigma k =1 1/k(jetzt als cx) + (1/k+1)(jetzt als cy) -> c1-c2+c2-c3+...+cn - cn1 -> c1 + cn+1 -> 1/1 +1/n+1 -> 1 + 1/n+1 ->**Teleskopsummen** -> man muss erkennen können
- **Partialbruchzerlegung**
- **Unendliche Dezimalbruchentwicklung** -> (an)nausN eine Folge, {0, 1, ..., 9} dann ist Reihen unendlich Sigma k = 1 ak* 10^-k
	- konvergent mit dem Wert <=1 -> **das ist super wichtig!!!!** -> ist beschreibung der Dezimalzahlen 0, a1, a2, a3, ...
	- n Sigma k = 1 ak* 10^-k <= n Sigma k = 1 9* 10^-k -> 9* n Sigma k = 1 10^-k -> 9* n Sigma k = 1 (1/10)^k ->geometrische summenform ->9* (-1 + n Sigma k = 0 (1/10)^k) -> hier diese dumme sumenformel anwenden -> 9* (-1 + (1-(1/10)^n+1/1-(1/10)) (hier muss ich das n weg bekommen also mach ich das n einfach weg und dann ein kleiner gleich weil ergebnis ist dann ja größer) <= 9 * (-1 + 1/1-(1/10)) = 9 * (1/9) = 1
- **Harmonische Reihe** -> unendlich Sigma k=1 1/k -> divergiert -> ist eine reihe die divergiert obwohl eine nullfolge ist
- BITTE NOCH IN NOTIZBLOCK GUCKEN
- **Majorante**
- **minorante**
- **Leibnitz**
- **Cauchy-Produk**
# Wichtige Funktionen
- Wie messe ich die Effizienz von Algorithmen
-  **Polynome** -> ganzrationale Funktonen 
- Rationalefuktion -> ganzrationale Funktone durch ganzrationale funktion geteilt
	- **Monome** -> seien n aus N, k1, ..., kn aus N0 und K aus {R,C}
		- Eine Funktion der Form 
			- m: K^n -> K: (x1,...xn) -> x1^k1* ... * xn^kn
			- heißt reelles oder komplexes Monom in den Variablen x1,..., xn
	- Die Zahl deg m := k1+...+kn
		- nennt man Grad des Monoms 
	- Linearkombinationen von Monomen -> endliche summe der Form:
		- p(x1, ..., xn) = Summe im skript ist sehr kompliziert
		- mit koeffizienten ak1,...kn aus K heißt Polynom in den Variablen x1, ..., x2 
		- schreibweise meint fast alle dass nur eindlich viele der Koeffizienten ak1,..., kn von Null verschieden sind sodass es sich nur um eine summe mit endlich vielen Summanden handelt
	- Der Grad von p ist definiert als der maximale Grad der in p als Summand vorkommenden monome 
		- Handelt es sich um das Nullpolynom, d.h. alle Koeffizienten dinf gleich Null wird definiert -> deg(0):= -uenendlich
	- Grad ist sozusagen alle exponenten addiert und der höchste gewinnt
	- Monome sind zb bei f(x,y) = x^3* y^2+... dann ist ein einzelner wert ein monom also jeweils x und y
	- Polynom ist Komutativer Ring -> kann man addieren und kommt polynom raus und multiplizieren und kommt polynom raus
	- **Gradformel**: sind p1, p2 aus K\[x] zwei Polynome, dann ist deg(p1,p2) = deg(p1)+deg(p2)
	- **Polynomzerlegung** -> seien p aus K\[x] mit n := degp >=1und c aus K ein beliebiges Element dann gibt es ein Polynom q aus K\[x] vo Grad 0 <= deg q <= n-1 und eine Zahl b aus K sodass gilt:
		- p(x) = q(x) (x-c)+k
	- **Linearfaktor abspaltung**
		- Sei p aus K\[x]  -> noch anschauen was mit nuellstellen
	- **Linearfaktorzerlegung**
		- Seien 1 <= k <= n und p aus K\[x] ein Polynom vom Grad n >=1 mit nullstellen c1, ...,c2 dann gibt es ein Polynom q aus K\[x] ohne Nullstellen in K mit p(x) = q(x) * kProduktzeichen j =1 (x - cj) -> ist eine andere möglichkeit polynomdivision zu machen
	- **Merken**: 
		- bei Potenzreihen unenedlich Sigma k = 0 (z^k /k!) -> kovergiert für jedes komplexe z absolut, abs konvergenzreihe lässt sich für jedes z mit dem Quotientenkriterium nachweisen, stellt in ganzen komplexen ebenen eine Funktion dar, und dann ganz lange funktion
		- Wie macht man Nulstellen? -> in jedem term steckte y drin -> wenn y also null ist ->unendlich nullstellen -> sind aaber mehr als der grad angibt
		- wie viele reelle Linearfaktoren hat das Folgende Polynom x^4 -4? -> kann auch (x^2+2) * (x^2 -2) -> +-Wurzel(2)
	- **Rechenauswand zum Auswerten von Polynomen**
		- Sigma n, k=0, ak x^k -> für x^k braucht man k Multiplikationen, das für alle k = 0,...,n -> für Sigma benötigt n Additionen zur auswertung
	- **Effizienter Algorithmus zur Auswertung von p(x)**
		- p(x) = a0 + a1x + ...+ an x^n -> jetzt ausklammern
				- = a0 + x(a1 + a2x + ... + anx^n-1) -> damit kann man immer weiter machen -> iteration dieses Prozesses führt auf eine Darstellung -> Horner Schema
				- = a0 + x(a1+ x(a2 +..... + an x))
		- mit dem Horner Schema -> ein Polynom mit Grad n -> n additionen und n Multiplikation als Rechenaufwand8
	- **Horner schema als Algorithmus**
		- Sei p(x) = a0+ a1x+...+anx^n
			- vom grad n>= 1 
				- Wert p(x) lässt sich durch rekursiven Algorithmus berechnen
					- y0 = an, yk = yk-1 x+an-k für k = 1, ..., n
					- Dann ist yn = p(x) und die berechnung von yn benötigt n Additionen und n multiplikationen also insgesamt 2n rechenoperationen
		- Beispiel: p(x) = 2x^3 + x -1 -> n = 3, a3 = 2, a2 = 0, a1 = 0, a0 = -1
			- y0 = 2, y1 = 2x+0, y2 = (2x)x+1 = ... -> kommt wieder das polynom 
- **Exponentialfunktion und Logarithmus**
	- Ging über die Exponentialreihe
		- Potenzreihe Sigma unendlich, n=0, z^n /n! für jedes z aus C
	- Die Exponentialfunktion exp erfüllt für alle z, w aus C die Funktionalgleichung 
	- Beschränken wir die Exponentialfunktion auf die reellen Zahlen, ist die Funktionalgleichung für das starke Anwachsen der Funktionswerte verantwortlich
	- **Anwendung der Exponentialfunktion**
		- Mit (reeller)Exponentialfunktion lassen sich viele Wachstumsprozesse in der realen welt modelieren
			- Kapitalverzinsung
			- Ausbreitung von vViren in Epi/Pandemi
			- Wachstum biologischer Kulturen
			- Radioaktiver Zerfall von Isotopen
			- Entwicklung von Population (Räuber-Beute-Modelle) -> dinge beeinflussen sich -> wenn eine mehr, dann andere weniger
			- In informatik -> aufwandsanalyse von Algorithmen -> Algorithmen und Datenstrukturen, Informationssicherheit
		- **Eulerische Zahl**
			- exp(1) oder sowas ist e
			- Approximation von exp(z) 
				- Exaktes Ausrechnen von Sigma unendlich, k=0 z^k /k! ist schwierig, per Computer sogar unmöglich
				- Ausrechnen endlicher Teilsumme Sigma N, k= 0 z^k /k! ist einfach und mit dem Hornerschema auch effizient
				- Aber! wie gut ist die Annäherung -> wenn wir ersten N Summanden addieren und rest ignorieren
				- **Restglied Abschätzung**
					- Approximation von exp(z) durch die N-te Partialsumme
						- Für N aus N0 sei r(N+1) (z) := Sigma unendlich, n=0 z^n /n" - Sigma N, n=0 z^n/n!
							- Dann gilt für alle z mit |z| <= (N+2)/2
							- |rN+1(z)| <= 2 |z|^N+1/(N+1)!
						- Genauen Dezimalwert von e kennen wir nicht
							- Mittels restgliedabschätzung  -> wie gut ist approximation
							- Wenn von der Zahl e sN abziehe -> ist größer gleich null -> ist höchstens noch so groß wie (2/N+1)!
						- Hier kann man mit rechnen -> N = 5 ->2,71666666... <= e <= 2,7194444444444 -> ersten 2 nachkommastellen ist approximiert
						- bei dreiecksungleichung -> mit einem Kleiner gleich kann Betragsstricke auch in summe
						- Exponentialfunktion konvergiert gegen 1 -> wir werden noch über stetigkeit redenn 
## Exponentialfunktion
- streng monoton wachsend -> injektiv -> gibt umkehrfunktion
- exp(z) =!0 für alle z aus C -> ist anscheiennd e^z
	- exp(0) = 1 = exp(z-z) = exp(z) * exp(-z), also exp(z) =!0
		- Funktionalgleichung
- exp(-z) = 1/exp(z)
	- asu dem ersten umformen 
		- geht weil keines der werte null werden kann
			- 1 = exp(z) * exp(-z)
				- 1 / exp(z) = exp(-z)
- n aus Z, exp(n) = e^n
	- exp(0) = 1 = e^0
	- exp(1) = e
	- exp(n) = Produktzeichen k=1, exp(1)
		- innen summe, außen produkt
	- Für n < 0 
		- nimmt man sich ergebnis aus b
			- und kann dann bisschen umformen
- exp(konj(z)) = konj(exp(z))
- Alle x aus R , |exp( i* x )| = 1
	- Generell: |z| = Wurzel((Re z)^2 + (Im z)^2) = Wurzel(z * konj(z))
		- z = i * x: |exp(i* x)| = (exp(ix) * (konj(exp(ix))))^1/2 = (exp(ix) * exp(konj(ix)))^1/2 = (exp(ix) * exp(-ix))^1/2 = exp(ix-ix)^1/2 = exp(0)^1/2 = 1

- ln(xy) = ln(x) + ln(y) -> merken!!!! -> über umwege dinge machen (hier umkehrfunktion)
	- ln -> produkt rein, summe raus
	- exp -> summe rein, produkt raus
- ln 1 = 0, ln e = 1
- Für n aus N ist ln (x^n) = n * ln (x)
- ln(x/y) = ln x - ln y
- ln: J -> R ist streng monoton wachsend

- WIchtig:
	- Logarithmus gilt nur für reelle Exponentialfunktion
	- komplexe ist nicht injektiv, damit nicht umkehrbar

## Basiswechsel bei Exponentialfunktion
- Statt zur basis e kann man auch eine andere Basis a< 0 eine Exponentialfunktion definieren
	- a = e^ln a = exp(ln a)
	- also für jedes x aus R : a^x := exp(ln (a) * x)
		- hat die gleichen eigenschaften
	- weitere rechenregen:
		- Für alle x und y aus R gilt a^xy = (a^x)^y
			- a^xy = e^(ln a) xy = e^((lna)x)y = e^(ln e^(ln a)x)y = e^(ln a^x)y ) (a^x)^y
		- Sind a und b > 0, dann ist (ab)^x = a^x * b^x
			- übung das zu beweisen
	- weil Exponentialfunktion zur Basis a > 0 injektiv ist -> gibt umkehrfunktion, Logarithmus zur Basis a
		- log a x
			- a^log a x = x
		- Rechenregeln von Logarithmus zur basis e sind erfüllt
		- es gilt log e x = ln x -> e^log e x = x = e^ln x
	- Umrechnungsformel:
		- seien a, b und x > 0
			- log a x = log a b * log b x
				- a^log a x = x = b^logb x und b = a^log a b
	- wachstum der Exponentialfunktion -> ist wichtig für informatik
		- wächst stärker als polynom
		- effizienzanalysen -> ist dann aber blöd, außer in der security -> symmetrische Kryptografie
		
- Für eine beliebige reelle Zahl gilt:
$$
|e^{ix}| = 1,\ \mathrm{Re}(e^{ix}) \leq{1},\ \mathrm{Im}(e^{ix}) \leq{1},\ (\mathrm{Re}(e^{ix})^2 + \mathrm{Im}(e^{ix})^2) = 1
$$
- Für die Euler'sche Zahl gilt:
$$
 \sum_{k = 0}^{\infty} \frac{1}{k!} = e
$$
- Seien x und y nicht negative reelle Zahlen, so gilt:
$$
\sqrt{x+y} = \sqrt{x}+\sqrt{y};\ nur,\ wenn\ xy=0
$$

# Trigonometrische Funktionen
## Geometrische Interpretation von e^ix
![[Pasted image 20250627101819.png]]
## Sinus und Cosinus
- Definition Sinus und Cosinus:
$$
\sin : \mathbb{R} \to [-1,1]:x\mapsto \mathrm{Im}\ e^{ix},\
\cos : \mathbb{R} \to [-1,1]:x\mapsto \mathrm{Re}\ e^{ix}
$$
	- Die Formeln sind unabhängig vom Radius
	-  Sin und Cos sind eine Schwingungsform
		- -> sind Modelle für alle Arten von Schwingungsphänomenen
- Die Euler Identität:
$$
e^{xi} = \cos x + i \sin x
$$
## Satz von Pythagoras (Spezialfall)
$$
1 = |e^{ix}|^2 = (\cos x + i \sin x)(\cos x - i \sin  x) = \cos^2 x + \sin^2 x
$$
- wann immer cos^2 und sin^2 in einer Formel ist, ist die Formel = 1
## Potenzreihendarstellung von sin und cos
- Sinus und Cosinus haben auf ganz ℝ **absolut konvergente** Potenzreihendarstellung
	 $$\cos x = \sum_{n=0}^{\infty} (-1)^n \frac{x^{2n}}{(2n)!},\ \sin x = \sum_{n=0}^{\infty} (-1)^n \frac{x^{2n+1}}{(2n+1)!}$$
	- Beweis:
$$
\sum_{n=0}^{\infty} \frac{(ix)^n}{n!} = e^{ix} = \cos x + i \sin x
$$
	- Schaut man sich jetzt das (ix)^n an:
$$
(ix)^n = i^n x^n,\ i^0 = 1 , i^1 = i , i^2 = -1 , i^3 = -i ,
i^4 = 1 
$$
$$i^n = { 1,\ n\ mod\ 4 = 0\ ; i,\ n\ mod\ 4 = 1;\ -1,\ n\ mod\ 4=2; -i,\ n\ mod\ 4 =3}$$
$$
i^nx^n = (-1)^n x^{2n}+(-1)^n i x^{2n+1}
$$
	- Also gilt: $$e^{ix} = \sum_{n=0}^{\infty} \frac{(ix)^n}{n!} = \sum_{n=0}^{\infty} (-1)^n {\frac{x^{2n}}{(2n)!} + i \sum_{n=0}^{\infty}(-1)^n \frac{x^{2n+1}}{(2n+1)!}}$$
## Symmetrieeigenschaften
- Sinus und Cosinus haben eine Symmetrie Eigenschaft
	- es ist egal, ob es x oder -x  ist
		- der Exponent bei Cosinus ist immer gerade
		- der Exponent bei Sinus ist immer ungerade
			- Cosinus ist eine gerade Funktion, Sinus ist eine ungerade Funktion
$$
\cos (-x) = \cos x
$$
$$
\sin(-x) = -\sin x
$$
	- Das folgt aus den Potenzreihendarstellungen
	- Beweis: 
- Für cos x:$$(-x)^{2n} = (-1)^{2n} x^{2n}=x^{2n}$$
	- Cosinus ist eine gerade Funktion
		- der Funktionsgraph ist symmetrisch zur y-Achse
- Für sin x:$$ (-x)^{2n+1} = (-1)^{2n+1} x^{2n+1}=-x^{2n+1} $$
	- Sinus ist eine ungerade Funktion
		- der Funktionsgraph ist symmetrisch zum Nullpunkt
## Graphen von sin und cos
![[Pasted image 20250627104345.png]]
## Additionstheoreme
- Für alle x, y aus R gilt:
$$\cos(x+y)=\cos x \cos y - \sin x \sin y $$
$$\sin(x+y)=\cos x \sin y + \sin x \cos y $$
## Grad- und Bogenmaß
- Ein Vollkreis entspricht dem Winkel 360°
- Der Umfang des Einheitskreises beträgt 2π
- Der Bogenmaß eines Winkels beträgt:
$$******************\frac{2\pi x}{360}\ mit\ x \in [0,360]****************** $$
![[Pasted image 20250701200723.png]]
- Borgenmaß des Winkel x = Länge des Kreisbogen von 1 zu e^ix
- Wichtige Werte:![[Pasted image 20250701201902.png]]
## Periodizität
- Die Eigenschaft sich nach einem bestimmten Zyklus zu widerholen
$$\sin (x +2 \pi)=\sin x $$
$$\cos (x +2\pi)=\cos x $$
$$e^{i(x+2\pi)}=e^{ix} $$ 
- Speziell für die letzte Formel gilt:
$$ für\ x=0:\ e^{2\pi i}-1=0 $$
- Alle Werte, die Sinus und Cosinus entlang der reellen Achse annehmen, nehmen sie auch schon vollständig auf dem Intervall \[0,2π\[ an:
$$\cos([0,2\pi[)=\cos (\mathbb{R}) $$
$$\sin([0,2\pi[)=\sin (\mathbb{R})$$ 
## Wichtige Werte
- ![[Pasted image 20250701203429.png]]
## Tangens
- Die Tangensfunktion (Tangens) ist definiert als:
$$\tan: \mathbb{R}\left( \frac{\pi}{2}+\pi \mathbb{Z} \right) \to \mathbb{R} :x \mapsto  \frac{\sin x}{\cos x}  $$
![[Pasted image 20250701205729.png]]
## Polarkoordinaten
- ![[Pasted image 20250627111103.png]]![[Pasted image 20250703213759.png]]![[Pasted image 20250703213807.png]]![[Pasted image 20250703213831.png]]
- ![[Pasted image 20250627111351.png]]
- ![[Pasted image 20250627111704.png]]
- wenn zahl z -> |z|e^ix -> x ist gesucht
- ![[Pasted image 20250701200244.png]]
- ![[Pasted image 20250627111841.png]]
### Auffrischung
![[Pasted image 20250704100458.png]]
Geometrische vorrangehensweise: realteil ist gespiegelt -> 90 rotation an der y achse
Lösung:
$$
\sqrt{2}e^{i \frac 3 4 \pi}
$$

![[Pasted image 20250704100702.png]]
 multiplikation mit i -> 90 grad rotation auf der y achse
 ![[Pasted image 20250704100755.png]]
 ![[Pasted image 20250704100842.png]]
 - Für das berechnen aus der Vorlesung:
	 - ![[Pasted image 20250704101220.png]]
	 - hierbei jetzt ausrechen, für welches x das gilt
# Stetigkeit
- Wie löst ein Computer komplizierte Gleichungen
- Unterschied Heizung und Glühbirne
	- Licht geht sofort an, heiziung braucht um auf wunschtemeperatur zu kommen
	- ![[Pasted image 20250704101744.png]] Für glühbirne
	- ![[Pasted image 20250704101757.png]]
	- Waws ist das besondere an dem Punkt
		- annähern von rechter und linker seite
			- links:
				- ![[Pasted image 20250704101944.png]]
				- wenn folge der funktionswerte, dann grenzwert bilden, kommt was anderes raus, als wenn man andersherum rangeht
				- ![[Pasted image 20250704102052.png]]
- Verallgemeinert:
	- ![[Pasted image 20250704102202.png]]
	- unstetig an der stelle a, wenn reihe an zu a konvergeirt, aber f(an) nicht zu f(a) konvergiert
- Bei stetigkeit:
- ![[Pasted image 20250704102359.png]]
- kann für jeden punkt gelten -> stetig auf der ganzen menge, wen für jeden punkt gilt![[Pasted image 20250704102501.png]]
- wenn y bei C(X,Y) fehlt-> ist Y sofort = R
- ist Verneinung von Unstetigkeit

- Hilfssatz:
	- max norm kann auf matrizen gepackt werden
	- Max norm einer matrix
	- ![[Pasted image 20250704102731.png]]
	- ![[Pasted image 20250704102846.png]]
	- ![[Pasted image 20250704102934.png]]
	- k -> von matrix a die k-te zeile -> kte eintrag im ergebnis vektor
	- ![[Pasted image 20250704103031.png]]
	- ![[Pasted image 20250704103125.png]]
	- ![[Pasted image 20250704102857.png]]
	- Affin lineare Abbildung: Ax+b -> so was ähnliches
	- ![[Pasted image 20250704103226.png]]
	- ![[Pasted image 20250704103352.png]]
	- Was passiert mit f(xk)-> konvergiert gegen f(x)??
	- ![[Pasted image 20250704103430.png]]
	- ![[Pasted image 20250704103452.png]]
	- b kürzt sich weg
	- ![[Pasted image 20250704103528.png]] man A ausklammern, weil Linear
	- durch hilfssatz:
		- ![[Pasted image 20250704103608.png]]
		- n* || A|| unendlich ist konstant
			- xk konvergiert gegen x also xk -x konvergiert gegen 0 für k -> unenedlich
			- also: ist stetig
			- ![[Pasted image 20250704103710.png]]
			- ![[Pasted image 20250704103735.png]]
			- weil wir x belibig gewählt haben ist f stetig auf dem ganzen -> für maxmetrik
			- ![[Pasted image 20250704103821.png]]
			- alle aussagen für max metrik ghilt auch für alle anderen, zb euklidische metrik
- Neues Beispiel: konkrete werte, Identische Abbildung:
	- ![[Pasted image 20250704103926.png]]
	- A ist einheitsmatrix, b ist nullvektor
	- Identische und konstante abbildung ist stetig -> lin abbildung ist stetig 
	- funktionen bleiben stetig, wenn auf kleine wertemenge auswerte:
	- ![[Pasted image 20250704104049.png]]
	- hier formaler wegen neue Funktion definieren, g ist Restriktion von f
	- ![[Pasted image 20250704104204.png]]
	- ![[Pasted image 20250704104259.png]]
	- ![[Pasted image 20250704104313.png]] gilt weil matrix vektor multiplikation gilt
	- ![[Pasted image 20250704104503.png]] mit vektor, bei dem k-ter wert 1 und rest 0 ist -> vektor matrix multiplikation > stetig
## Rechenregeln
 - alle rechenregeln bei konvergenten folgen auch hier übertragen
 - ![[Pasted image 20250704104816.png]]
 - Wenn ausgansgsumme stetig, dann auch addition 
 - ![[Pasted image 20250704105042.png]] -> produkt
 - ![[Pasted image 20250704105106.png]]-> Quotient
 - ![[Pasted image 20250704105123.png]] ist umformulierung der rechenregeln von konvergente folgen![[Pasted image 20250704105159.png]]
 - ![[Pasted image 20250704105248.png]] Multiplikation ist stetig
 - rechenregel von eben: stetige funktionen multiplizieren -> wieder stetig
	 - ![[Pasted image 20250704105339.png]] -> hat n faktoren siehe das ding mit an kter stelle 1 und sonst 0
	- Monome stetig?????
	- ![[Pasted image 20250704105451.png]] -> hat n faktoren wenn k = 1, hat mehr, wenn k > 1 ist
	- ![[Pasted image 20250704105804.png]] produkt ist einfach länger geworden
	- ![[Pasted image 20250704105825.png]]
	- Polynome stetig:
	- ![[Pasted image 20250704105842.png]]
	- ja
	- rationale funktionen stetig
	- ![[Pasted image 20250704105906.png]]
	- ja, wegen quotienten regel
	- ![[Pasted image 20250704110141.png]]
	- Fehlerdenken:
		- ![[Pasted image 20250704110009.png]]funktion ist an der stelle garnicht definiert, deswegen sit sie da weder stetig noch unstetig **das kann als frage in der prüfuing kommen**
		- gilt für reelle sowie komplexe quotienten

	- ![[Pasted image 20250704110201.png]]
	- nur wenn beide stetig sind ist sicher, sonst nachrechnen
	- ![[Pasted image 20250704110329.png]]
	- ![[Pasted image 20250704110447.png]]reduktionsprinzip anwenden
	- ![[Pasted image 20250704110624.png]]Konvergenzradius -> definiert ist er schon aber nicoht benannt -> konvergenzbereich hat radius, da wo die potenzreiehe konvergiert stellt sie eine stetige funktion dar
	- alle funktionen, von den wir wissen, das sie ko0nvergente potenzreihen haben ist sie stetig
	- ![[Pasted image 20250704110938.png]]
	- ja, cos sin und e ist stetig, dann verkettung wegen e und sin und quotient wegen dem und cos
	- gibt keine nullstelle, weil exp keine nullstellen hat

# Differenzialrechnung
- Wie berechne ich optimale Lösungen für ein Problem

- Auffrischung 26.09:![[Pasted image 20250926095919.png]]
- g ist differenzierbar und stetig
- Frage 1: ist h(x) differenzierbar -> wenn ja, was sit h'(a)
- also zuerst ableiten -> hier ist spezialfall -> quotientenregel-Spezialfall
- also: (1/g(x))' = (0* g(x) - 1* g'(x))/(g(x))^2
	- das wird zu h'(x) = -(g'(x)/(g(x))^2)
	- ![[Pasted image 20250926101023.png]] definiton der differenzierbarkeit oder sowas![[Pasted image 20250926101245.png]]
	- ![[Pasted image 20250926101253.png]]
- Ist Funktion f im Punkt a differenzierbar, so ist f in a auch stetig![[Pasted image 20250926101357.png]]
- ![[Pasted image 20250926101644.png]] #klausur ![[Pasted image 20250926101918.png]]
- #klausur aus differenzierbarkeit folgt stetigkeit aber aus stegikeit keine differenzierbarkeit
- ![[Pasted image 20250926102418.png]]![[Pasted image 20250926102513.png]]
- #übung ![[Pasted image 20250926102801.png]]![[Pasted image 20250926102846.png]]![[Pasted image 20250926103122.png]]![[Pasted image 20250926103550.png]]
- ![[Pasted image 20250926103836.png]]![[Pasted image 20250926104238.png]]
- Reihe der Exponentialfunktion -> e^x = unendllich Sigma n= 0 x^n/n! ableiten: erst zähler ableiten -> n* x ^n-1 und n! bleibt so  -> n* (x^n-1)/n! -> x^n-1/(n-1)! -> index um 1 zurück schieben, weil bei summe n = 1 -> und dadurch ist dann x^n /n!
- ![[Pasted image 20250926104758.png]]
- ![[Pasted image 20250926105113.png]]
- hier kann quotientenregel angewandt werden
- ![[Pasted image 20250926105132.png]]
- ![[Pasted image 20250926105221.png]]![[Pasted image 20250926105430.png]]![[Pasted image 20250926105622.png]]
- ![[Pasted image 20250926105757.png]]
- ![[Pasted image 20250926110028.png]]![[Pasted image 20250926110152.png]]![[Pasted image 20250926110253.png]]![[Pasted image 20250926110335.png]]
- ![[Pasted image 20250926110412.png]]
- #übung ![[Pasted image 20250926110500.png]]![[Pasted image 20250926110714.png]]
- ![[Pasted image 20250926111055.png]]
- ![[Pasted image 20250926111213.png]]![[Pasted image 20250926111304.png]]
- #übung![[Pasted image 20250926111559.png]]
- ![[Pasted image 20251010100616.png]]aus differenzierbar und nciht differenzierbar -> differenzierbar
- ![[Pasted image 20251010100749.png]]aus differenzierbar und nicht differenzierbar -> nicht differenzierbar
- ![[Pasted image 20251010100814.png]]aus nicht differenzierbar und nicht differenzierbar ->  differenzierbar

- Eine im Punkt a differenzierbare Funktion ist dort stetig
- L'hopital -> 
- f* g ist im Punkt a je nach Wahl von f und g mal differenzierbar, mal nicht, siehe Bilder
- Dafür, dass eine differenzierbare Funktion in einem Punkt a ein lokales Minimum oder Maximum hat, ist die Bedingung f'(a) = 0 notwendig

## Lokale Extrema
### Extremwertprobleme der realen Welt
- Welche Abmessung hat eine optimale Dose
- absolute extrema -> im gesamten graphen die extrema
- lokale extrema -> in bestimmten bereichen maxima und minima![[Pasted image 20251010102353.png]]
- ![[Pasted image 20251010102714.png]]
- ![[Pasted image 20251010102914.png]]
- nicht differenzierbare funktionen können auch extrem werte haben ->|x| #klausur 
- ![[Pasted image 20251010103550.png]]
- ![[Pasted image 20251010103838.png]]
- ![[Pasted image 20251010104101.png]]
- ![[Pasted image 20251010104229.png]]![[Pasted image 20251010104415.png]]![[Pasted image 20251010104528.png]]
- ![[Pasted image 20251010104723.png]]
- ![[Pasted image 20251010104737.png]]
- ![[Pasted image 20251010105153.png]]
- ![[Pasted image 20251010110058.png]]![[Pasted image 20251010110212.png]]![[Pasted image 20251010110335.png]]![[Pasted image 20251010110552.png]]![[Pasted image 20251010110953.png]]
- Monotonie dürfen wir jetzt auch bei folgen benutzen![[Pasted image 20251010111755.png]]
- ![[Pasted image 20251017094931.png]]![[Pasted image 20251017101316.png]]![[Pasted image 20251017101441.png]]![[Pasted image 20251017101756.png]]![[Pasted image 20251017102211.png]]
# Integralrechnung
- Wie kommt Musik in den Computer
- ![[Pasted image 20251017105523.png]]
- ![[Pasted image 20251017105800.png]]![[Pasted image 20251017110054.png]]![[Pasted image 20251017110350.png]]teleskopsumme
- ![[Pasted image 20251017110610.png]]
- ![[Pasted image 20251017110739.png]]![[Pasted image 20251017111145.png]]
- ![[Pasted image 20251017111244.png]]
- ![[Pasted image 20251017111531.png]]