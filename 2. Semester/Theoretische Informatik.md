- Automatentheorie
- Gramatiken
	- Begriffe 
	- Entscheidbarkeit
- Grundlagen der Berechenbarkeit
- Petri-Netze

- Theoretische Informatik -> Prof dr Heinz-Peter Gumm(Buch)
- ![[Band 3 Informatik.pdf]]
### Aufgabe
- (positive) Integerzahlen auf verschiedene Art und Weise notieren
	- Zahl mit Symbol/Zeichen 0 -> wird nicht als Dezimalzahl interpretiert -> also hier eine der anderen beiden nehmen
	- zwischen zwei Ziffern, beliebig viele Unterstriche
- In Oktardarstellung 
	- beginnt mit 0
	- Enthält nur 0, ..., 7
- In Hexadarstellung
	- Beginnen mit 0x
	- dürfen neben 0, ..., 9 auch a, ..., f und  A, ..., F enthalten
## Alphabete, Worte, Sprache
-  Alphabet **Sigma** -> Endliche Menge
	- Elemente dieser Menge sind Symbole oder Zeichen
	- Alphabete werden mit Griechischen Zeichen bennant
		- Beispiele
			- unäre Alphabet -> Sigma unär = {1}
			- morse Alphabet -> Sigma morse = {lang, kurz, pause}
			- 
- Ein Wort über einem Alphabet (Sigma) ist eine endliche Folge von Symbolen aus Sigma
	- leere Wort -> Epsilon
	- Worte sind induktiv aufgebaut
	- Menge aller Worte mit Zeichen aus dem Alphabet Sigma heißt **Sigma Stern** -> Potenzmenge
	- jedes nicht-leere Wort w aus Sigma* lässt sich eindeutig darstellen als w = a.u (a gefolgt von u)
		- mit a aus Sigma und u aus Sigma*
	- kleinste Menge und Gleichheit anschauen
	- Wie schreibt man worte auf
		- zwei Methoden, nicht leere Worte angebene
			- Angabe aller endlichen Folge aller Zeichen
			- Als w = a.u 
				- a das erste Symbol des Wortes ist (a aus Sigma)
				- u das Rest-wort (u aus Sigma*)
- Was ist eine Sprache
	- Eine (formale) Sprache über dem Alphabet Sigma ist eine Menge von Worten aus Sigma*
		- Jede Teilmenge (Wierdes L) Teilmenge Sigma ist eine (formale) Sprache
		- alles was man Programmiert ist eine Sprache
- Länge eines Wortes |w| 
	- |Epsilon| = 0
	- |a.u| = 1 + |u|
- Konkatenieren
	- Epsilon ° u = u
	- (a.v) ° u = a.(v°u) 
		- Kringel meisten weglasse
		- in Programmen meistens +
		- Ist Assoziativ
		- Länge eines Konkatenierten Wortes ist Summe der Längen der ursprünglichen Worte
			- Formal beweisen -> vollständige Induktion  hab endlich verstanden :D zumindest für die summe
		- Kleene-Hülle = a*
### Entscheidbarkeit
- Eine Sprache heißt **entscheidbar**, wenn ein "**Algorithmus**" existiert der zu jedem Wort w entscheidet ob w in L oder w in Sigma*\L
- Eine Sprache heißt semi-entscheidbar wenn es einen "Algorithmus" gibt der zu jedem Wort e in Sigma* bestätigen kann falls w in L
- Ist eine Sprache entscheidbar <=> L und Sigma*\L sind semi-entscheidbar
- im Allgemeinen sind Sprachen nicht endlich -> nicht möglich für jede Sprache einen Algorithmus zu finden
- Wenn sprache entscheidbar -> auch semi entscheidbar ->

##  Reguläre Sprachen
### Formale Definition
- induktiv definiert
- reguläre sprachen sind:
	- leere Spreche -> leere Menge
	- {Epsilon} -> Sprachen welche nur das leere Wort enthält
	- {a} -> für jedes a in Sigma
- Wenn L = {0} und M={0} bereits reguläre Sprachen sind, dann auch
	- L|M -> L U M(L vereinigt M, manchmal auch L + M) -> {0} U {1} -> {0,1}
	- LM -> L°M (erst ein Wort aus L, dann ein Wort aus M) -> geht aber nur abwechselnd -> Cathesisches Produkt -> {01} ->anderes Beispiel: LM(L|M) -> {010,011}
	- L° -> L°L°... = LLL (beliebige (bestimmte) Aneinanderreihung von L, auch keinmal) -> {w| w aus Sigma* und w enthält keine 1} **-> ist das Kleene-Hülle von L**
- reguläre sprachen können durch reguläre Ausdrücke beschrieben werden
- r.S. sind formale Konstrukte und r.A. eine Deklarationssprache
- ALphabet selbst ist Regulär -> kann man in mengen aufteilen: {a1} U {a2} U ... U {an}
- Menge aller Worte im Alphabet auch regulär -> Konkatination von w
- L+ -> L*\\{Epsilon}

### Syntaxreguläre ausdrücke
- a|b -> Alternativen ->a oder b
- a°b -> Konkatination
- ab* -> beliebig viele b an ein a
- a? -> a und das leere wort
	- 001|1? -> 001, 1, Epsilon
- a+ -> a kommt mindestens einmal vor
	- (01+)|0 ->{01,0}
- \[] -> Menge an zulässigen Zeichen ->\[^a] -> negation
- a{x} -> a muss exact x mal vor
- a{x,}-> a kommt min. x mal vor -> a+-> a{1,}
- a{x, x+ 2} -> a kommt min x mal, aber maximal x+1 mal vor
- a{,x} -> a kommt max x mal vor

### Kurzformen und Sonderzeichen
- "." -> beliebiges Zeichen
- "s" -> beliebiges Whitespace
- "\\"-> Sonderbedeutung des nachfolgenden Zeichens-> wenn klammern beinhalten soll -> "\\(\\)"
- \\t -> Tabulator 

### Grenzen der Regulären sprachen
Man kann:
- bestimmte länge der worte
- die mit "(" anfangen und ")" enden
- mindestens ein "f" vorkommt
Mann kann nicht:
- mehr "A" als "B"
- gleichviele "A" und "B" 
- in den Klammern Paarweise auftreten

### Übungen
1.
a)
L= leereMenge* ->{w | w aus }
1* -> L {Epsilon, 1, 11, 111}
Leeremenge* -> L= {Epsilon, ∅, ∅∅, ∅∅∅, ...} -> {Epsilon}

Sigma = 1 -> Sigma* = Kleene-Hülle(1) bzw. 1*

b)
L2 = {}

c)
Epsilon -> leeres Wort -> länge 0, jedem Sigma* enthalten -> zeichenfolge die keine Zeichen enthält, gibt reihenfolge, kann elemente wiederholen
{} -> Leere Menge -> menge in der nichts enthalten ist, enthält keine elemente -> keine reihenfolge zwischen elemente,  hier können sich keine elemente wiederholen
{{}} -> Leere Menge mit leerer Menge -> menge enthält leere menge

2.
a) Sigma = {0,1}, L = {0}, L' ={1}
 L°L =L -> gilt nicht weil -> 0°0 = 00 

 b)
 L°L' = L'°L -> geht nicht weil -> 0°1=01 != 10 = 1°0

3.


4.
a)
.* 010 .*

b)
1*(0 1* 0)* 1* 0 1*

c)
1* (0|11+)*


## Deterministische Automaten
- DEA -> DFA
- interner Zustand
- liest prüfendes Wort symbolweise
- Zustand kann sich verändern
	- stehts nur das nächste Zeichen eingelesen werden
- kommt DFA am wortende an, prüft er ob der zustand akzeptierend ist oder nicht akzeptierend ist
- akzeptierende haben doppelringe

### Aufbau Automat
- 5-Tupel
- Q -> endliche Menge an Zuständen
- Transitionsfunktion
- Anfangszustand
- akzeptierende Zustände -> oder Endzustand

- graphische Notation
	- Zustände sind Knoten im Graph
	- Anfangszustand q0 aus Q
	- Zustandsübergänge Delta -> beschriftete Kanten im Graph -> eigenschleife/eigenkante -> wenn kante auf den selben zustand wieder übergeht
	- akzeptierende Zustände sind Knoten mit doppeltem kreis

- Weg ist definiert durch Transitionsfunktion Delta
- Zustand heißt erreichbar, wenn es min ein Wort gibt welches den zustand erreicht
- leere Wort ist teil der Sprache, wenn q0 akzeptierend ist
- nicht erreichbare Zustände können ohne Problem entfernt werden

### Konstruktion Automat
- erst unvollständigen Automaten für die worte die in der Sprache liegen
- nicht bestehende Übergänge hinzufügen
- kann auch Tabelle machen
- gibt zu jedem DFA einen Komplement Automat
	- alle zustände die Akzeptierend war sind nicht mehr akzeptierend

- Produkt Automaten -> das mit der Tabelle -> sind zwei Automaten an einander -> Infonotizen aus der Schule helfen da besser als seine Dinger
- Summenautomat -> min eines der beiden automaten muss das wort akzeptieren -> also akzeptierende zustände bei allen die die anderen auch haben

- Minimal automaten
	- alle nciht verwendeten zustände löschen
	- alle die sich ähnlich verhalten kompakter schreiben -> zu einem zusammenfassen
		- zustände sind trennbar, wenn es ein wort gibt, dass ???
	- verhaltensgleich oder ununterscheidbar, wenn sie nicht trennbar sind -> p~q

- Faktorautomaten
	- alle zustände sind paarweise trennbar

- nerode Lemma
	- L eine Sprache -> gibt n worte die Paarweise L-trennbar sind, so hat jeder Automat der L kennt min n Zustände
	- definiert untere Schranke
	- WIe beweis:
		- versucht unendlich viele paarweise L trennbare worte zu finden -> unendlich viele zustände haben -> kann kein dfa sein -> dfa sind endlich und regulär -> sprache kann nicht regulär sein
		- muss erkenntnis haben -> worte raussuchen -> sahce dranhängen -> ist in der sprache? 

- zwei worte -> L trennbar
	- suffix an wort -> eine wort in sprache, andere nciht
		- wenn 1, 0 -> 10 -> gültig, 00 -> ungültig

- Nicht jede sprache regulär -> Beispiel: L ={a^n b^n| n aus N0} -> hätte unendlich viele Zustände
- DFA weiß in welchem Zustand er ist
- DFA erinnert sich nicht warum er dort ist
- kann nicht zählen -> weiß nicht wie viele a er schon hatte
	- andere Beispiele:
		- L = {a^i b^k| i != k }
		- Dyck-Sprache -> Menge aller wohlgeformter Klammerausdrücke
		- L = {a^n* n}
		- hier wieder nerode Lemma -> brauch min n Zustände für L-trennbare Worte -> Die tablle nochmal anschauen

- Pumping Lemma:
	- A -> DFA mit k Zuständen -> jeder lauf hat ein 'langes' wort |w| >= k irgendwo mindestens einen Zyklus
		- Weil wort mit k Symbolen Länge k + 1 Zustände im DFA besucht
		- DFA hat nur k Zustände, muss also min ein Zustand mehrfach besucht werden
		- kann man nutzen bie zb: {a^n b^n| n aus N0} , oder {a^m!| m >= 3}
- Wie wählt man verfahren?
	- beide kann man nutzen, außer wenn man explizit gefragt wird
	- bei {a^n b^m} -> pumpinglemma schwer (muss wort treffen, wo n=m) -> lieber nerode lemma
	- kann auch dritte machen -> zwei automaten vereinigen und dann sehen "ja das ist nicht regulär"

- AUtomaten mit Ausgaben
	- Akzeptoren -> Automaten, die schauen ob worte in Sprache sind
	- Transducer -> Automaten mit komplexen ausgaben, durch Ausgabe alphabet
		- erweitern Akzeptoren um:
			- Ausgabealphabet wierdes Griechisches r
			- Ausgabefunktion gamma
		- Beispiele:
			- Moore-Automat -> erzeugt in jedem Zustand ein Symbol des Ausgabe worts
			- Mealy-Automat -> erzeugt in jeder Transition ein Symbol des Ausgabeworts
		- werden verwendet bei ampeln
			- oder scannern
- Übungen
	- a) L = {w aus Sigma* | es gibt ein l <= m <= n: w = a^l b^n a^m}
		- angenommen L ist regulär -> endlich viele zustände
			- gibt jetzt die menge der worte {a^n b^n |n aus N0} -> dazu a -> aba -> ist drin
			- aabba -> nicht drin -> aaabbba -> nicht drin
			- zusammenfassen als ^{l > m > n: w = a^l b^n a^m} -> nicht regulär -> weil unendlich viele zustände
		- Hier lieber a als anfang nehmen und (b^n a^m dran zu hängen)
	- b)gibt x, y, z -> x = ab, y = bb, z = ba -> ist regulär -> kann mit y aufgepumpt werden  x+0* y + z = abba -> ist drin
	- x,1* y, z -> abbbba -> ist drin
	- x,2* y, z -> abbbbbba -> ist drin
	- x,n* y, z -> ab(n*(bb))ba -> ist drin -> bb ist an sich auch ein palindrom -> regulär aber aber nur für  x = z^-1 und y = 2* a|b
		- Pumpinglemma nochmal anschauen :D

- Sprachen für DEAs entwickeln
	- DEA für Sprache zu spezifizieren kann schwer sein
	- muss schauen, welche worte passen
	- NEA -> nichtdeterministischer endlicher Automat
		- NEA -> Alphabet A ist ein 5-Tupel (Q, Sigma, Delta, q0, F)
			- Q -> endliche menge an zustäden
			- delta -> Transitionsfunktion
		- Sprache NEA -> muss nur ein akzeptierendes wort finden
		- jeder dfa ist nfa
		- dfa sagt ich brauche min ein übergang
		- jeder dfa erfüllt kriterien vom Nfa
		- nfa ist schwer zu konstruieren
		- wenn nfa n zustände hat kann dfa bis zu 2^n(mächitgkeit der Potenzmenge) Zustände haben
		- Gleichzeitig konstruieren
		- Potenzmengenautomat -> ist DFA der äquivalent zu einem NFA ist
- Sprachen durch Gramatik definieren -> Chomsky Hirarchie
- Grammatiken
	- Quatupel
		- V -> Nichtterminale -> Variablen -> Menge
		- T -> Terminale -> Token
		- P -> Produktionen (Regeln)
		- S aus V -> Startvariable
		- jeder schritt eine ableitung
			- wort -> wenn nur terminale
			- Satzform -> mischung aus Variablen und Terminalen
			- auch notizen aus der schule 
			- Wann zwei gramatiken Äquivalent
				- Wenn sie die selben worte Beschreiben
				- Chomsky normalform
					- wird benutzt um gleichheit zu zeigen
					- als auch -> wortproblem lösung
						- A -> a genau ein terminal
						- A -> BC -> genau zwei variablen
						- S -> Epsilon
					- Terminierende variable -> kann von hier irgendeine Satzform bilden
					- nichtterminierende Variable -> du kannst die entfernen ohne das was sich was an der sprache ändert
					- kollabierende Variable -> ist irgendwie möglich von a nur auf das leere wort zu kommen -> muss produktion geben -> also nicht nur wenn Epsilonregel gilt
						- wie entfernt man epsilon regel
							- fügt bei der Vorherigan variable 
					- Epsilon Freiheit
						- keine Regel der Form A -> Epsilon
						- oder S -> Epsilon  ist einzige Epsilon Regel -> S wird in keiner Anderen regel verwendet
					- 1-Variable Regeln
						- JEde Variable muss min excakt 1 Teminal oder excakt 2 Variablen abbilden
					- CYK algorithmus - >anschauen -> ist diese wierde pyramide
					- 