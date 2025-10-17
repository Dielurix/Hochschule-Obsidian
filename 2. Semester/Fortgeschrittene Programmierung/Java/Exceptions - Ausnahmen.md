## Klassenhierarchie Ausnahmen
- Oberklasse "Throwable"
	- Unterklasse "Exception" -> können zur Laufzeit behoben werden
		- "checked exceptions" -> erweitern die Klasse "Exception", heißen so weil Compiler für die Übersetzungszeit try-catch-Mechanismus vom Programm einfordert
		- Unterklasse "RuntimeExceptions"
			-  "unchecked exceptions" -> erweitern die Klasse "RuntimeExceptions", heißen so weil Compiler für die Übersetzungszeit **keine** Überprüfung vornimmt
	- Unterklasse "Error" -> können nicht behoben werden
		- "unchecked exceptions"-> erweitern die Klasse "Error", heißen so weil Compiler für die Übersetzungszeit **keine** Überprüfung vornimmt

## Optionen im Exception Handling
- Erzeugen - **new**
	- Werfen - **throw/throws** -> Progammabbruch
		- Fangen - **try/catch** -> unbedingter Sprung, gibt keine Bedingung, Springt unbedingt
			- Verarbeiten - { ... }
			- Delegieren - **throw/throws** -> in der Aufruffunktion verarbeiten
			- Erzeugen & Werfen - **new, throw, throws** -> nicht weitergegeben, aber andere Exception, neues Fehlerobjekt, erzeugen -> Rekursion, kann günstiger sein