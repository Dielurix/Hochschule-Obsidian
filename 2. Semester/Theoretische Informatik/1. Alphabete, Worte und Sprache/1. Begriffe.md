## Alphabete
- **Alphabet Σ** -> endliche Menge
- Elemente von Σ heißen **Symbole/ Zeichen**
- Alphabete werden mit großen griechischen Buchstaben benannt
- Beispiel:
	- Σ_unär = {1}
	- Σ_binary = {0, 1}
	- Σ_Morse = {lang, kurz, Pause}

## Worte
- **Wort** über einem Alphabet Σ -> endliche Folge von Symbolen aus Σ
- Worte sind induktiv aufgebaut
- Spezialfall:
	- **leeres Wort ε** -> leere Folge von Symbolen
		- in Code: ""
- Beispiele:
	- Worte über {1, 0} -> ε, 0, 1, 01, 1001, etc.
	- Worte über {a - z} -> ε, a, anno, bell, etc.

## Menge aller Worte über Σ
- Menge aller Worte mit Zeichen aus Σ -> Σ*
	- * -> Kleene-Hülle
- Beispiele:
	- {1}* = {ε, 1, 11, 111, etc.}
	- {a - z}* = {ε, a, b, etc., aa, ab, ba, etc.}
- Σ* ist kleinste Menge mit:
	- ε ϵ Σ
	- ∀a ϵ Σ, ∀u ϵ Σ* : a.u ϵ Σ*
- Gleichheit:
	- ∀u, v ϵ Σ*: u = v: ⇔ u = ε = v oder u = a.u' und v = a.v' und u' = v'
- Jedes nicht-leere Wort w ϵ Σ* lässt sich **eindeutig darstellen** als:
	- w = a.u mit a  ϵ Σ und u ϵ Σ*

## Wort-Darstellung
- gibt zwei Methoden, nicht-leere Worte anzugeben
1. Angabe der endlichen Folge aller Zeichen:
	- anno, bell, etc. 
2. Als w = a.u, wobei:
	- a -> erste Symbol des Wortes (a ϵ Σ)
	- u -> Rest-Wort (u ϵ Σ*)
	- Beispiel:
		- anno = a.nno = a.(n.no) = a.(n.(n.o)) = a.(n.(n.(o.ε)))
			- auf die Klammern kann verzichtet werden

## Formale Sprache
- (formale) Sprache über Alphabet Σ -> **Menge von Worten aus Σ\***
- Jede Teilmenge 𝓛 ⊆ Σ* ist eine (formale) Sprache
	- Alles was man Programmiert ist eine Sprache
- Gilt auch für:
	- Menge aller Worte -> Σ*
	- leere Menge -> ∅ = {}
	- Menge, welche das leere Wort enthält -> {ε}
	- jede einelementige Menge Menge mit einem Wort der Länge 1-> {a} für alle a ϵ Σ*

## Typische Operationen auf Worte
- Länge |w| (Anzahl der Zeichen in w)
	1. |ε| = 0
	2. |a.v| = 1 + |v|
-  Konkatenieren (Aneinanderhängen) zweier Worte u ∘ v = uv
	1. ε ∘ v = v
	2. (a.u) ∘ v = a.(u ∘ v)
- ∘ -> wird meistens weg gelassen
- identifizieren das **Zeichen a** mit **Wort a.ε** (Länge 1)
- Für a ϵ Σ und u ϵ Σ* gilt also au statt (a.ε) ∘ u = a.u
- Konkatenation mittels ∘ ist assoziativ
	- ∀u, v, w ϵ Σ* : (u ∘ v) ∘ w = u ∘ (v ∘ w)
- Länge eines konkatenierten Wortes ist Summe der Länge der ursprünglichen Worte
	- ∀u, v ϵ Σ* : |u ∘ v| = |u| + |v|


