## Kontextfreie Sprachen
- Nicht jede Sprache regulär -> kann nicht durch regulären Ausdruck, einen DFA oder NFA oder eine reguläre Grammatik beschreiben werden


## CF-Grammatik

## CF-Grammatik für a^n b^n 
- 𝓛anbn = { a^n b^n | n >= 0} ist kontextfreie Sprache
	- V = {S}
	- T = {a, b}
	- S -> aSb | ε
- Ableitung des Wortes aabb
- ![[Pasted image 20250924083236.png]]

## Äquivalenz
- Zwei Grammatiken G1 und G2 heißen äquivalent, falls 𝓛(G1) = 𝓛(G2)
	- G1 = S -> S + S | 1
	- G2 = S -> S + 1 | 1
- G1 und G2 sind äquivalent: 𝓛(G1) = 1(\ + 1)* = 𝓛(G2)