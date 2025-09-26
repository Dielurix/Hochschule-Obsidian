## Chomsky-Hierarchie formaler Sprachen
![[Pasted image 20250924080628.png]]
- (N)PDA -> (Nicht deterministische) Push down Automaten

## Formale Grammatik
- Sprachen mittels Grammatik beschreiben
	- Grammatik beschreibt Syntax(Struktur), nicht Semantik(Bedeutung)
- Syntaktisch falscher Satz: gestohlen der. hat Gans Fuchs die
- Syntaktisch richtiger, aber semantisch falscher Satz: Die Ganz hat den Fuchs gestohlen.
- Syntaktisch und semantisch richtiger Satz: Der Fuchs hat die Gans gestohlen.
- Im Kontext formaler Sprachen befassen nur mit syntaktischer Beschreibung von Sprache

## Grammatik
- Grammatik ist ein Quadrupel -> G = (V, T, P, S) mit T ∩ V = ∅
	-  V -> Menge von **Variablen** (auch **Non-Terminale**)
	- T -> Alphabet aus **Terminalen** (auch **Token** genannt)
	- P ⊂ V x (T ∪ V)* -> **Produktionen** (auch **Regeln** genannt)
	- S ∈  V-> **Startvariable**
- Mit Hilfe einer Grammatik kann Worte einer Sprache **erzeugen** -> **Ableitung**
	- Alle mit Grammatik G ableitbaren Worte bilden Sprache L(G)
- Um prüfen, ob Wort zu Grammatik definierten Sprache gehört -> diese mithilfe der Grammatik zerlegen/ Struktur erkennen
	- Wort-Problem: w ∈ L(G) oder w ∉ L(G)

## Satzformen und Ableitungen
