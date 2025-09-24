## Chomsky Normalform (CNF)
- Zu jeder CF-Grammatik G gibt es eine äquivalente Grammatik G', deren Produktionen folgende Struktur hat:
	- A -> a: genau ein Terminal
	- A -> BC: genau zwei Variablen
	- S -> ε: ausschließlich wenn ε L(G), dann darf jedoch S in keiner Regel rechts vom Pfeil vorkommen

## Erreichbare Variablen
- Variable ist **erreichbar**, falls A in min. einer Satzform vorkommen, die ausgehend von S abgeleitet werden kann
	- 𝐴 erreichbar ⇔ 𝐴 = 𝑆 oder (E →𝛼𝐴𝛽) ∈𝑃 und 𝐸 erreichbar
- Nicht erreichbare Variablen können gelöscht werden -> Sprache ändert sich nicht

## Terminierende/produktive Variablen
- Variable A V heißt **terminierend/ produktiv**, falls aus A eine Satzform erzeugen kann, die nur Terminale enthalten: ∃𝑤 ∈ 𝑇* : 𝐴* ⇒ w
	- 𝐴 terminierend ⇔ (𝐴 → 𝑤) ∈ 𝑃 für ein 𝑤 ∈𝑇* oder (𝐴 → 𝛼) ∈ 𝑃 für ein 𝛼 ∈(𝑉\{𝐴}∪𝑇)* und alle Variablen in 𝛼 sind terminierend
- Nicht terminierende Variablen können gelöscht werden -> Sprache ändert sich nicht

## Kollabierende/ nulllable Variable und ε-Regeln
- 

## ε-Freiheit
- Grammatik heißt ε-Frei, falls
	- keine Regel der Form A -> ε vorkommt
	- S -> ε die einzige ε-Regel und S kommt in keiner Produktion rechts des Pfeils vor
- Zu jeder CF-Grammatik G gibt es eine äquivalente ε-Freie Grammatik
- G -> ursprüngliche Grammatik, G+ -> entstanden durch entfernen aller ε-Regeln aus G
	- G+ -> ε-frei

## 1-Variablen-Regeln

## Umwandeln einer CF-Grammatik in Chomsky-Normalform