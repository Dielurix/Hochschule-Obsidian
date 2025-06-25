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
- Ändern
