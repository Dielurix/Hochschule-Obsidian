# Grundelemente der Programmierung
## Strukturierungselemente
- **Ablauf eines Programms**
![[Ablauf_eines_Programms_GdI.png]]
- **Strukturierungsmechanismen**
	- Programmiersprache dient als Rahmen in welchem Ideen über die Problemdomäne organisiert werden können
	- gibt drei  Mechanismen um Prozessideen zu strukturieren
		- **Primitive Ausdrücke**
			- Repräsentieren die einfachste Einheit der Sprache
		- **Kombinationsmittel**
			- Zusammengesetzte Elemente werden aus einfachen Einheiten konstruiert
		- **Abstraktionsmittel**
			- Zusammengesetzte Elemente können benannt und weiter als Einheit manipuliert werden
			- Black-Box-Abstraktion
				- zusammengesetzte Ausdrücke werden nach dem Benennen wie primitive Ausdrücke verwendet
- **Sprachelemente - Die Primitiven**
	- **Zahlen**
		- z.B. 42, -36
		- sind Werte der Ziffern
		- sind selbstauswertend
	- **Boolesche Werte**
		- true (wahr) und false (falsch)
		- sind selbstauswertend
	- **Namen für eingebaute Funktionen/ Prozeduren**
		- Bsp. +, -, *, /, =, …
			- Der Wert von + ist eine Funktion, die Zahlen addiert
			- Der Wert von - ist eine Funktion, die Zahlen subtrahiert
			- …
		- Auswertung
			- Nachschlag des dem Namen zugewiesenen Werts
- **Besonderheiten bei Zahlen**
	- **DrRacket rechnet immer genau, wenn möglich**
		- Ganze Zahlen, endliche Dezimalzahlen “wie üblich”
		- Brüche mit periodischem Ergebnis
			- Darstellung in Text
				- als Bruch, etwa 7/3
			- direkt im Fenster
				-  als Periode, etwa 2,3333333 (mit dem Strich oben drauf)
	- **Nicht jede Zahl kann exakt dargestellt werden**
		- Beschränkung durch Verwendung des Binärsystems
			- mehr Dezimalstellen → mehr Probleme
		- Zahlen unendlicher Länge ohne Periode
			- (Raute)i “inexakt”
				- e: (Raute)i2.718281828459045
				- pi: (Raute)i3.141592653589793
				- √2: (Raute)i1.4142135623730951
	- **Mit Brüchen oder “inexakten” Zahlen kann normal gerechnet werden - das Ergebnis ist aber ggf. wieder “inexakt”**
		- (√2)^2 = (Raute)i2.0000000000000004
- **Sprachelemente - Kombinationen**
	- **Zusammengesetztes Element**
		- Sequenz von Ausdrücken, in Klammern
		- Ausdrücke sind primitiv oder erneut zusammengesetzt 
		- Bsp:
			- Ausdrücke können mit anderen Ausdrücken kombiniert werden, repräsentieren primitive Funktionen (+, -, …)
				- erstellen so einen zusammengesetzten Ausdruck
					- (+ 2 3)
						- öffnende Klammer
						- drei Ausdrücke
						- schließende Klammer
						- Notationen
							- Präfixnotation (wird in Racket verwendet)
								- Rechenzeichen werden vor die Werte geschrieben
									- + 2 3
							- Infixnotation
								- Rechenzeichen werden zwischen die Werte geschrieben
									- 2 + 3
							- Portfixnotation
								- Rechenzeichen werden hinter die Werte geschrieben 
									- 2!
		- Kombinationen können verschachtelt werden
			- Regeln rekursiv anwenden
				- (+ 4 (* 2 3)) 
					- 4 + (2 * 3) = 10
				- (* (+ 3 4) (- 8 2))
					- (3 +4) * (8 - 2) = 42
		- Kombination → Anwendung einer Funktion
			- Klammern können nicht eingefügt oder weggelassen werden
				- verändern die Bedeutung des Ausdrücks
- **Sprachelemente - Abstraktion**
	- Erstelle ein komplexe Sache aus primitiven Sachen
	- Benenne sie
	- Behandele sie als eine primitive Sache
		- einfachstes Abstraktionsmittel
			- define
				- (define score (+ 27 3))
					- score = 27 + 3
				- (define roughlyPI 3.14)
					- roughlyPI = 3.14
- **Sonderformen**
	- geklammerte Ausdrücke, die mit HtDP-TL-Schlüsselwörtern starten
		- z.B. define
			- Wert an einen Namen binden
				- (define score (+ 27 3))
			- wertet den zweiten Ausdruck nicht aus (im Bsp. score)
			- assoziiert den Namen mit dem Wert des dritten Ausdrucks in einer Umgebung
			- Wert von Namen nicht neu definierbar/ nicht löschbar
			- man hat Umgebung in der Werte gespeichert werden (wie eine Tabelle)
## Namen, Umgebung, Auswertung, Fehler
- **Namensgebung und Umgebungen**
	-  wichtiger Aspekt → Werte über Namen referenzieren
		- Name identifiziert einen bestimmten Wert
	- Umgebung → Verwaltung der Name-Wert Paare
		- ist eine Art Speicher, welche vom Interpreter unterhalten wird
		- assoziiert Werte mit Namen
		- Werte können später über Namen geholt werden
	- um Wert auszurechnen, der durch Namen repräsentiert ist, reicht es ihn in der Umgebung aufzulösen
		- Bsp. Evaluierung von score ist 30
	- ist (implizit) für die Symbole der arithmetischen Operatoren gemacht
		- d.h. Wert erhalten, welcher durch den Namen referenziert wird
		![[Umgebung_GdI.png]]
- **Auswertungsregeln**
	- Selbstauswertend
		- gibt den Wert zurück
			- Werte der Ziffern sind Zahlen, die sie bezeichnen
	- Eingebaute Operatoren
		- gibt Sequenz der Maschineninstruktionen zurück
		- führen entsprechende Operationen durch
	- Name
		- gibt Wert zurück, der in der Umgebung mit diesem Namen assoziiert wurde
	- Sonderformen
		- mache etwas besonderes
	- Kombinationen
		- Wertet die Unterausdrücke (in beliebiger Reihenfolge) aus
		- Wende die Prozedur, die der Werte des am wenigsten links liegenden Unterausdruckes ist (der Operator), auf Argumente an
			- Werte des restlichen Unterausdrücke (Operanden)
	- Auswertung ist rekursiv
		- bei Kombination ruft Regel sich selbst auf
		- jedes Element muss ausgewertet werden, bevor Gesamtauswertung einer Kombination abgeschlossen werden kann
- **Lesen-Auswerten-Ausgeben-Schleife des Intepreters**
		![[Lesen-Auswerten-Ausgeben-Schleife_GdI.png]]
		![[Lesen-Auswerten-Ausgeben-Schleife_mit_Pi_GdI.png]]
- **Finden gemeinsamer Muster**
	- gibt es Gemeinsamkeiten?
		- (* 3.14 (* 5 5))
		- (* 3.14 (* 23.2 23.2))
		- (* 3.14 (* r r))
	- sind alles Beispiele einer Kreisflächenberechnung
- **Definition neuer Funktionen**
	- um wiederkehrende Muster festzuhalten verwendet man Funktionen
		- werden auch Prozedur genannt
		- Analog zu einer Funktionsdefinition in der Mathematik
	- define-Sonderform wird hierbei verwendet um neue Funktion zu erstellen/definieren
		- (define (area-of-disk r) (* 3.14 (* r r)))
			- area-of-disk → Name der Funktion
			- r → Parameter
	- sobald Funktion definiert wurde kann sie wie primitive Funktion verwendet werden
		- Kreisfläche
			- (area-of-disk 5)
				- ergibt 78.5
		- Fläche eines Rings
			- (- (area-of-disk 5) (area-of-disk 3))
				- ergibt 78.5 - 28.6 = 50.24
	- schon definierte Funktionen können zu mächtigeren Funktionen kombiniert werden
		- Berechnung der Fläche eines Rings
			- (define (area-of-ring outer inner) (- (area-of-disk outer) (area-of-disk inner)))
		- Anwendung der neuen Funktion
			- (area-of-ring 5 3)
				- (- (area-of-disk 5) (area-of-disk 3))
					- (- (* 3.14 (* 5 5)) (* 3.14 (* 3 3)))
				- ...
			- ergibt 50.24
- **Informelle Beschreibung**
	- Typische Programmspezifikation
		- Üblicherweise nicht in Form mathematischer Ausdrücke, die in Programme umzuwandeln sind
			- sind in informelle Problembeschreibungen umzuwandeln
				- enthalten irrelevante/mehrdeutige Informationen
		- Bsp.:
			- Firma XYZ bezahlt Angestellte 12€ pro Stunde
			- Angestellter arbeitet zwischen 20 und 65 Stunden pro Woche
			- Entwickeln sie ein Programm, welches den Lohn eines Angestellten aus der Anzahl der Arbeitsstunden berechnet
				- Problemanalyse
					- (define (lohn stundenanzahl) (* 12 stundenanzahl))
- **Fehler**
	- Programme werden Fehler enthalten
		- ist nichts schlimmes
		- nicht verwirren/entmutigen lassen
	- Mögliche Fehler
		- keine Korrekte Klammerung
			- (* 3 (5))
		- Operator eines Funktionsaufrufs ist keine Funktion
			- (10), (10 + 20)
		- Typfehler und andere Laufzeitfehler
			- (+ 3 true), (/ 3 0)
	- Ausprobieren, was bei fehlerhaften Eingaben passiert und versuchen Fehlermeldung zu verstehen
## Design von Programmen
- **Design von Programmen**
	- Design von Programmen ist nicht trivial
	- folgendes soll helfen Programme zu schreiben
		- Schritt-für-Schritt Beschreibung
		- später wird verfeinert
	- Jede Programmentwicklung besteht aus mindestens vier Aktivitäten
		1. Verstehen, was der Zweck ist
		2. Programmbeispiele ausdenken
		3. Programmkörper implementieren
		4. Testen
	- Verstehen was der Zweck ist
		- Berechnung der Fläche eines Ringes
		- Berechnung der Fläche eines Ringes mit einem äußeren Radius 'outer' und einem inneren Radius 'inner'
		- Berechnen kann man das durch die Fläche des Kreises mit dem Radius 'outer' minus der Fläche des Kreises mit Radius 'inner'
		- ...
		- Vergabe eines sinnvollen Namens
		- Definition eines Vertrags
			- Welche Daten werden konsumiert und produziert
		- Formulierung einer kurzen Beschreibung des Sinns des Programms
		- Hinzufügen des Programmkopfes
		- Bsp.
			- ; area-of-ring: number number → number
			- ; Berechnet die Fläche eines Rings
			- ; mit Radius 'outer', dessen Loch den Radius 'inner' hat
			- (define (area-of-ring outer inner) ... )
				- ; → Zeichen für Kommentare
	- Programmbeispiele ausdenken
		- Hilft Ein-/Ausgaberelation zu charakterisieren
		- ist oft einfacher, Abstraktes anhand von Beispielen zu verstehen
		- Beispiele helfen...
			- Berechnungsprozess zu verstehen und logische Fehler zu entdecken
			- Spezialfälle und Grenzfälle zu erkennen
		- Im Beispiel
			- ; Beispiel: (area-of-ring 5 2) ergibt 65.94
	- Programmkörper implementieren
		- Ersetzung des Platzhalters '...' mit einem Ausdruck 
		- Ist Eingabe-Ausgabe-Relation eine mathematische Formel kann man diese meist direkt übersetzen
		- bei informeller Beschreibung muss der Berechnungsprozess klargemacht werden
			- Beispiele aus Schritt 2 können helfen
		- Im Beispiel
			- (define (area-of-ring outer inner) (- (area-of-disk outer) (area-of-disk inner)))
	- Testen
		- eingebaute Prozedur der HtDP-TL (How to Design Programms) nutzen
		- (check-expect test expected)
			- Vergleicht "Test"-Wert mit "Expected"-Wert
			- Gleitkommazahlen ist problematisch, da Ergebnis nicht unbedingt exakt ist
				- (check-expect (* 2 2) 4)
		- (check-within test expected delta)
			- Prüft ob Testwert(meist Gleitkommzahlen) korrekt ist mit Abweichung +/- delta, etwa delta = 0.0001
				- (check-within (area-of-ring 5 2) 65.9 0.5)
		- (check-error test message)
			- Prüft ob Aufruf die erwartete Fehlermeldung liefert
			- Fehler in Funktion durch (error "message") auslösen
		- Fehlgeschlagene Test werden in einem separaten Fenster von DrRacket angezeigt
- **Hilfsprozeduren**
	- sind sozusagen Hilfsfunktionen
	- können aus einem schlechten Programmdesign:
	![[schlechtesProgrammdesign_GdI.png]]
	- ein gutes/wartbares Programmdesign machen:
	![[GutesProgrammdesign_GdI.png]]
- **Prozedur als Black Box-Abstraktion**
	- Abstraktion = Verstecken von Komplexität
	- Details, die nicht zum Verständnis des Sachverhaltes beitragen, werden versteckt (hängt vom Betrachter ab)
	- Prozedurale Abstraktion ist eine von vielen Abstraktionen#
		- z.B. area-of-ring berechnet die Fläche eines Rings
			- Benutzer muss nicht mehr Details von area-of-ring wissen und sich nicht drum kümmern
	- Berechnungsprobleme werden oft in natürliche, kleine Teilprobleme aufgeteilt
		- Bsp. Ringfläche -> zweifache Berechnung einer Kreisfläche
		- Für Teilproblem werden Prozeduren geschrieben
			- area-of-disk, ... , primitive Prozeduren, ...
	- Prozedur attendees kann als "Black Box" betrachtet werden
		- soll Anzahl der Teilnehmer berechnen
		- wollen nicht wissen wie
			- Die Details können vernachlässigt werden
	- attendees ist prozedurale Abstraktion für revenue und cost
	- benutzerdefinierte Prozedur wird über Namen aufgerufen
		- ähnlich zu primitiven Prozeduren
	- wie Prozeduren arbeiten bleibt versteckt
- **Konstantendefinition**
	- Richtlinie für Namensdefinition
		- Taucht eine Konstante häufig in einem Programm auf, sollten wir ihr einen Namen geben
			- Bessere Lesbarkeit
			- Bessere Wartbarkeit
				- bei Änderung muss nur an einer Stelle etwas geändert werden
## Bedingung und Symbole
- **Bedingte Ausdrücke: if**
	- (if 'test' 'then-expr' 'else-expr')
- **Bedingte Ausdrücke: cond**
	- (cond [ 'test1' 'expr1']
			[ 'test2' 'expr2'])
			...
			[else 'last-expr']
- **Boolsche Funktionen**
	- (and 'expr_1' 'expr_2' ... 'expr_N')
		- werden in der Reihenfolge 'expr_i' (i = 1 ... N) ausgewertet
		- false, wenn Ausdruck als falsch ausgewertet werden
			- ansonsten true
		- wenn Auswertung weder false noch true so gibt Fehler
		- Shortcut-Regel
			- manche Werte werden nicht ausgegeben
				- wenn z.B false am Anfang
	- (or 'expr_1' 'expr_2' ... 'expr_N')
		- wieder Reihenfolge von and
		- true nach dem ersten Wert der True ist
		- false wenn alle Werte false sind
		- wenn Wert ausgewertet wird, der weder true noch false, so Fehler
	- (boolean=? 'expr_1' 'expr_2')
		- werden in Reihenfolge ausgewertet
		- wird true, wenn beide gleich sind -> entweder true oder false
		- false wenn unterschiedlicher booleschen Wert
		- wenn weder true noch false so Fehler
	- (not 'expr')
	- true, wenn 'expr' false
	- flase, wenn 'expr' true
	- Fehler, wenn weder true noch false
- **Beachten**
	- Überflüssigen Code vermeiden
		- (if (< x 0) true false) -> ist auch -> (< x 0)
	- auch bei "umgekehrter Logik" 
		- (if (>= x 0) false true) -> ist auch -> (< x 0) -> ansonsten auch (not ...)
- **Design konditionaler Prozeduren**
	- Wie ändert sich Designprozess
		- Programmentwicklung besteht aus wenigstens vier Aktivitäten
			- Zweck des Programms verstehen
			- Programmbeispiele ausdenken
			- Programmkörper Implementieren
			- Testen
		- Kennt man schon
		- Neue Phase: Datenanalyse
			- unterschiedliche Situationen?
		- Beispiele
			- min. eins für jede Situation
		- Implementierung des Programmkörpers
			- Erst Skelett der cond/if-Ausdrücke definieren, dann einzelfälle implementieren
		- Testen
			- Tests sollen Situationen abdecken
- **Symbole**
	- ist Sequenz von Zeichen angeführt von einem einfachen Anführungszeichen
		- Bsp. 'dog 'ate 'a 'cat!, etc.
	- nicht alle Zeichen sind erlaubt (z.B. keine Leer)
	- nur symbol=? auf den Datentypen
		- (symbol=? 'Hallo 'Hallo) -> true
	- sind atomar
		- können nicht zerlegt werden
- **Symbole vs. String**
	- sind voneinander zu unterscheiden
	- Symbole 
		- symbolische Namen
		- Atomar
		- keine Manipulation
		- sehr effizienter Vergleich
		- Gewisse Einschränkungen, welche Zeichen dargestellt werden können
	- Strings
		- für Textdaten benutzt
		- Manipulation möglich (suchen, zusammensetzen, etc.)
		- Vergleiche sind teuer
		- Beliebige Zeichen(kette) darstellbar
	- Strings sind auch in HtDP-TL verfügbar
		- erzeugen mit doppelten Anführungszeichen
		- mit string=? vergleichen
	- Strings werden bei uns ignoriert :( 
		- außer bei (error ...)
## Substitutionsmodell und Auswertungsreihenfolge
- **Auswertungsregeln erweitern**
	- Auswertungsregeln für Funktionen
		- Prozedur ist primitive Funktion
			- entsprechende Maschineninstruktionen ausführen
		- Funktion ist selbst-definierte Funktion
			- Werte Rumpf der Funktion aus
			- jeder formale Parameter mit entsprechend aktuellen Parameterwert ersetzen
				- aktueller Parameterwert wird bei der Anwendung angegeben
			- (define (f x) (* x x)) -> (f 5)
- **Das Substitutionsmodell**
	- Fiktive Namen (formale Parameter)
		- Definition von allgemeinen Prozeduren
			- können in unterschiedlichen Situationen wieder verwendet werden
		- effektive Werte müssen an fiktive Namen gebunden werden
			- dann kann Prozedur ausgewertet werden
	- z.B. arithmetische Formeln 
		- f(a, b) -> Deklaration der formalen Parameter
		- a^2 + b^2 -> Definition der Funktion mit Hilfe von formalen Parametern
		- f(3, 2) -> Benutzung der allgemeinen Funktion, um ein Spezialproblem zu lösen
	- Substitution der fiktiven Variablen mit effektiven Werten
		- Aufrufumgebung
			- (define b 2) ... (f 3 2) ... (f b 8) ...
		- Prozedurumgebung für f
			- (define (f a b) (+ (* a a) (* b b)))
		- Jetzt kann man hier Werte einsetzen
	- Substitutionsmodell soll helfen über Semantik nachzudenken
		- keine Auskunft über Arbeit des Interpreters
		- wertet typischerweise nicht den Prozedurabruf durch textuelle Manipulation des Rumpfes aus
	- Einfaches Modell um formal über den Auswertungsprozess nachzudenken
		- erlaubt ein Programm auf Papier auszuführen
- **Applikative vs. normale Auswertungsreihenfolge**
	- Applikativ
		- Erst Operator und alle Operanden auswerten, dann substituieren
	- Normal
		- Operator Auswerten, die (unausgewerteten) Operanden für formale Argumente des Operators substituieren
	- Wichtige nicht-triviale Eigenschaft
		- Ergebnis hängt nicht von der Auswertungsreihenfolge ab(Konfluenz)
		- kann sein, dass bei ungeschickter Auswertungsreihenfolge, Auswertung nicht terminiert
		- gibt Sprachfeatures (Zuweisung, Ein-/Ausgabe) die die Eigenschaft zerstören
		- Strategien können sich erheblich in der Anzahl der benötigten Schritte unterscheiden
			- Argument wird nicht benötigt -> normale Reihenfolge besser
			- Argumente wird mehrfach benötigt -> applikative Reihenfolge besser
## Rückblick: Die Sprache HtDP-TL
- **Dinge die ein HtDP-TL ausmachen**
	- selbst auswertende Werte -> 23, true, false
	- Namen -> +, roughlyPI, pi
	- Kombinationen -> (+2 3), (* pi 4)
	- Sonderformen -> (define PI 3.14)
- **Syntax** 
	- Kombination
		- (operator-expression other-expressions ...)
	- Sonderformen
		- besonderes Schlüsselwort als erster Unterausdruck
- **Semantik**
	- Kombinationen
		- Werte Unterausdrücke in beliebiger Reihenfolge aus
		- Wende den Operator auf die Operanden an; substituiere bei benutzerdefinierten Prozeduren
	- Sonderformen
		- Jede hat eine eigene Semantik
# Datenrepräsentation
## Datenkodierung
## Zahlensysteme
## Binärarithmetik
## Fließkommazahlen
## Zeichenkodierung
# Strukturierte Datentypen
## Strukturen
## Datenabstraktion
## Heterogene Daten
# Rekursive Datentypen und strukturelle Rekursion
## Listen (= Heterogenität + Rekursion)
## Verarbeitung rekursiver Datentypen
## Design von Hilfsfunktionen
## Funktionen mit mehreren rekursiven Argumenten
## Erste eigene Programmiersprache
# Lexikalisches Scoping und Auswertungsreihenfolge
## Vertiefung: Applikative vs. Normale Auswertungsreihenfolge
## Lokale Definition
## Lexikalisches Scoping
# Abstraktion
# Schnelleinstieg Python
# Aufgaben
## Computer Quartett
### Nr. 1

; get-category: playcard symbol -> number
; Ist die Hilfsfunktion compare-by-category
; nimmt sich symbol, vergleicht das mit den Kategorie auf der Karte
; nimmt sich dann den Wert in der Kategorie

Hilfsfunktion:
(define (get-category playcard symbol) 
	(cond [ (symbol=? symbol 'cpu) (playcard-cpu playcard)]
			[ (symbol=? symbol 'ram) (playcard-ram playcard)]
			[ (symbol=? symbol 'storage) (playcard-storage playcard)]
			[ (symbol=? symbol 'gpu) (playcard-gpu playcard)] 
			[ (symbol=? symbol 'rgb)
			(cond [(playcard-rgb playcard) 1] 
				[else 0] )]
	)
)

; compare-by-category : playcard playcard symbol -> number
; vergleicht die beiden gegebenen Karten anhand des Symbols
(define (compare-by-category playcard01 playcard02 symbol)
		(cond [(> (get-category playcard01 symbol) (get-category playcard02 symbol)) 1]
			[else -1]
	)
)

;Bsp.:
; Zwei Karten -> omen-45L, alienware-r14 
; Kategorie: CPU
; Test
(check-expect (compare-by-category (omen-45L alienware-r14 'cpu) 1) 

### Klausur
- genug platz für aufgaben auf den Klausur Blätern
- 104 Punkte insgesamt -> nicht nach Schwierigkeit -> sondern nach Zeit
- Note <=> Textmenge -> nichts schreiben & viel aber nicht präzise schreiben -> schlechte Note, wenig schreiben, aber präzise -> gute Note