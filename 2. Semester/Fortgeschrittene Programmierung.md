- imperative, funktionale und Webprogrammierung
- Java, C, Javascript

- Java
	- 1. Sitzung: Exceptions - Ausnahmen
	- 2. Sitzung: Testen von Klassen (Unit Tests)
	- 6. Sitzung: Generische Datentypen (generics)
	- 7. Sitzung: Funktionale Elemente

- C
	- 3. Sitzung: Grundlagen
	- 4: Sitzung Arrays und Zeiger

- 5. Sitzung: Web
	- Hypertext Markup Language -> HTML
	- Cascading Style Sheet -> CSS
	- Javascript

**Klausurrelevanz:**
- Delegieren
	- einfach in dem catch block "throw e"
- Erzeugen und Werfen

## Exception Mechanismen
### Exceptions - Ausnahmen
- Pseudo code gegeben -> beinhaltet Fehler/Unschönheiten
	- verschachtelt
	- Fehelrcodes sind keine Norm
	- gibt Mechanismus um besser zu machen
### Klassenhierarchie Ausnahmen
- Oberklasse "Throwable"
	- Unterklasse "Exception" -> können zur Laufzeit behoben werden
		- checked exceptions
		- Unterklasse "RuntimeException"
			- unchecked exceptions
	- Unterklasse "Error" -> können nicht behoben werden
		- uncheckt exceptions

### Optionen im Exception Handling
- Erzeugen (**new**)
	- Werfen (**throw/throws**) *Programmabbruch*
		- Fangen (**try/catch**) -> unbedingter Sprung (gibt keine Bedingung, Springt ohne Bedingung)
			- Verarbeiten ( **( )** )
			- Delegieren (**throw/throws**) (in der Aufruffunktion verarbeiten)
			- Erzeugen & Werfen (**new, throw, throws**) (nicht weitergeben, aber andere Exception(neues Fehlerobjekt) erzeugen (Rekursion) -> kann günstiger sein)
				- **finally** -> wird immer durchlaufen
- *Programmabbruch*

## Codierung
- Im fehlerfall werden Ausnahmen(Exceptions) geworfen
	- Beispiel:
	- int arr\[] = { 1 };
		- Fehler durch Bereichsüberschreitung
	- arr\[1]++
		- Innerhalb der Array-Implementation erfolgt das Werfen der Ausnahme
- Instanz einer Ausnahmeklasse(Throwable) wird in Laufzeitumgebung übergeben
- häufig in bereits bestehenden Bibliotheksfunktionen

### Ablaufkontrolle
- reguläre Programmablauf wird unterbrochen
- nachfolgende Code wird nicht erreicht (unbedingter Sprung)
- Ohne Vorkehrungen wird Methode verlassen -> Rücksprung zum Aufrufpunkt -> macht nicht weiter -> guckt ob er dort verarbeitet wird
- kaskadierend bis zur main-Methode
- (reziprob(rückwärts))

### Fehlerobjekt
- Instanzen der Exception-Klassse
- in der Regel durch Konstruktoren erzeugt
- Kontruktor ist mehrfach überladen
- Aktualparameter sind u.a. Meldungen (String) und andere Exceptions(Throwable)
- kann getMessage und toString verwenden
- Beachte: erzeugen eines Fehlerobjektes löst noch keinen Fehler aus

### Auslösender Fall
- ausgelöst durch Werfen der Exception Instanz
- throw -> Kontrollflussanweisung
- bisherige Kontrollfluss wird in Exception-mechanismus umgeleitet
- Statement ist in der Bibliothek häufig vorprogrammiert

### Fangen der Exception
- Weiterverarbeitung wird fangen genannt (catch)
- catch ist mit try verbunden (try-catch-Block)
- try ist dafür da, dass der catch wirkt -> nur hier kann man Exceptions fangen (sozusagen hier kann was passieren)
- Exception Instanz wird an catch übergeben

### Finaler Code Block
- try-catch kann um final erweitert werden
- finally als Programmiermittel
- Kontrollfluss wird nach try und ggf. catch-Block unbedingt fortgesetzt
- unabhängig vom weiteren Programmverhalten den Programmstatus zu kontrollieren
### Fehlerspezifische Exceptions
- Adressierung spezifischer Fehelrursachen
- Beispiele
	- NullPointerException
	- ArrayIndexOutOfBoundsException
	- IOException
	- ArithmeticException
- allgemeine Exceptions fängt auch spezifische Exceptions, nicht andersrum

### Checked und Unchecked Exceptions
- Checked -> müssen gefangen werden
	- Beispiele
		- ClassNotFoundException
		- UnknownHostException
		- IOException
		- SQLException
- Unchecked -> können gefangen werden 
	- Beispiele:
		- ClassCastException
		- NullPointerException

### Code
- Signatur für Methoden:
	- setWert(int wert) throws Exception{}

## Tests
### Test Arten
### Aufbau Tests
### Unittests
- Währungsklasse erstellen -> umrechnen, wert +  wechselkurs
- Neue Klasse erstellen -> testklasse Test+ "Name" -> JUnit5
- Sachen importen
- Annotationen
	- @BeforeAll -> wird beim Initialisieren des Programms ausgeführt
	- @BeforeEach -> vor jedem Test ausgeführt
	- @AfterEach -> nach jedem Test ausgeführt
	- @Test -> zeigt das das eine Test Methode ist
	- @DisplayName("Beispiel") -> gibt dem Test einen Namen
	- @RepeatedTest(n) -> wiederholt die Methode n mal
	- @ParameterizedTest | @ValueSorce(doubles//hier müssen datentypen immer mit s enden// = {Param1, Param2, Param3, ..., Paramn}) | TestMethode(Param) -> gibt n verschiedene Parameter mit dem das Programm ausgeführt wird
		- @MethodSource("//Package Name + Klassen Name + # + Methoden Name") -> 
	- FÜr klausur:
		- Blackbox whitebox tests
		- Abdeckung und Zusammenfassung vonn testfällen
		- Testdriven Devolpement -> testzyklus reproduzieren -> folie mit rot grün und refactor, Detailablauf von Testzyklen sind da drin
		- Regression-> ist wichtig -> fehler der durch das verändern bereits laufenden/bestehendem Codes besteht
			- Regressionstests -> testen nahc fehlern
			- refactory -> verbessern des tests

# C-Programmieren
- c-17
- ProgrammierParadigmen
	- universalsprache
	- für diverse kernels
	- ist Höchst effizient
		- ist maschinennah
- Prozedurale sprache -> also c
- gibt in c funktionen
- Aufbau eines C programms
	- kommentare gleich wie in java
	- \#include <stdio.h> -> ist eine Präprozessoranweisung
	- int main(void){ -> Funktionskopf
	- 
	- }
- Präprozessor ist eigenständiger Teil innerhalb des Compilers
- syntaktische Vorverarbeitung
- Typdeklaration
- Arithmetische Anweisungen -> Operationen, Operanden, Operatoren
- Kontrollanweisungen
- 8 bit 1 byte
- variable char_bit -> wie viele bits -> 8
- C programm ist menge an funktionen
	- deklarationen
	- ausdrücke
	- Kontrollstrukturen/kontrollanweisungen
	- Präprozessoranweisungen -> ist eigenständiges tool innerhalb compiler
		- schaut nach zeilen die mit "#" beginnen, ersetzt dort eingaben in anderen text um
	- Platzhalter sind in Strings %d
		- x =4, y =25
		- printf("Die Sume von %d und %d ist %d", x, y, x+y) -> Werte werden der Reihe nach eingesetzt -> %d ist für decimal, %f ist für float oder %lf für double
		- scanf("%d", &w)
		- Änderung des Speicherzustandes -> Nebeneffekt
		- Variable -> verweis auf eine Speicherstelle -> ist eine benamte Speicherstelle
		- inlining
- Arrays
	- DATENTYP BEZEICHNER\[DIMENSION] -> name ist speicheradresse
	- L-value -> repräsentiert eine Speicherstelle
	- erstellen mit:
		- int number\[3] = {1, 2, 3};
		- geht auch so:
			- int number\[] = {1, 2, 3};
		- String arrays -> text\[1] = 'O';
			- text\[x] = '\0' -> ASCII-Null -> ist ein Terminal symbol
		- Header datei -> .h -> ist nur der methoden kopf und wird überall eingebunden
		- C-Datei -> .c -> ist der Quellcode, wird nicht eingebunden
			- sonst kommt Fehler -> Multiple definition of ... -> wenn das nach ändern noch nicht weg ist, dann nochmal kompilieren lassen
		- sizeof(int) -> sagt wie groß der datentyp auf dem rechner ist -> mit sizeof(arr) -> wie groß der array ist in byte -> wie anzahl der elemente? -> sizeof(arr)/sizeof(int), sizeof(arr\[1]) -> gibt die größe des Array elements an -> in bit = größe
		- sizeof ist ein Operator -> hängt von der Bindungsstärke ab -> liefert Bytes des Argumentes
- Zeiger(Pointer)
	- in v = 4
	- int pv = &v -> gibt die adresse aus -> & adressoperator
	- adressvariable ist * -> int * pv = &v 
	- dereferenzierungsoperator -> * -> das sternchen hat mehrere bedeutungen -> Homonym -> kontext ist wichtig -> bei deklaration ist stern ein Pointer, wenn * wann anders benutzt wird ist ein operator
	- int w = * pv -> das ist dann v

## Hypertext Markup Language(HTML)
### Web Anwendungen
- verteiltes System -> ist System, in dem Hardware und Softwarekomponenten auf vernetzten Computern befindet und miteinander über den Austausch von Nachrichten kommunizieren
- Verteilte Anwendungen -> Software für verteilte Systeme
- Client und Server sind Software
- Aufbau webanwendung
	- Webclient -> Internet (Firewall) -> Webserver -> Anwendungsserver(Intranet)-> Datenbankserver
		- Schichten Architektur -> Stack -> haben sonst auch noch namen -> L(linux)A(apache)M(MySql)P(PhP)
		- Datenbanken sind meistens MySql
	- Ablauf/Systemteile WEB Anwendung -> nochmal richtig anschauen
	- HTML mini Überblick -> nochmal richtig anschauen
	- SGML -> nicht Klausur relevant
	- Tags kennzeichnen -> sind wichtig für weitere Verarbeitung -> rendert eine Sichtbare Darstellung im Browser
- Struktur -> 
	- \<!DOCTYPE html> Sprache/Version
	- \<html>  Dokumentenbeginn
	- \<head> Beginn Kopfteil \<title>"Dokumententitel - Hier steht der Titel \</title> \</head> Ende Kopfteil
	- \<body> Beginn Hauptteil - hier steht der Inhalt \</body> Ende Hauptteil
	- \</html>
- Formale darstellung 
	- ist ein Baum
	- Bäume stehen immer auf dem Kopf
	- Jeder Stricht bedeutet Ein Element ist im darüber liegenden enthalten
	- Oberste element ist Wurzel
	- Jede Seite repräsentiert immer genau einen Baum, kein Wald
### Head und Body
- Head -> erscheinen Meta Informationen -> Dinge die Daten beschreiben
	- \<title> muss vorkommen
	- Alle anderen Head-Angaben sind optional
		- Titel erscheint in Titelleiste 
		- Steht in der Liste der Lesezeichen
- Body
	- stehen für Benutzer sichtbare Inhalte
	- sind vor allem Text, audiovisuelle Medien, 2D/3D Graphiken
	- Alle eintragungen sind direkt sichtbar
	- jede Eintragung im tag stehen
	- Tags -> öffnend/schließend/selbst schließend
	- \<p> sichtbarer Text \</p>
	- \<img/>
	- \<canvas> \</canvas>
	- \<script> \</script>
	- Inhalte von Skript -Tags sind ebenfalls nicht sichtbar, verlässt aber vollständig "Welt" von HTML
- Attribute
	- Tags können damit erweitert werden
		- \<p **style** = "color:red">
		- **src und alt** bei bildern
		- **id, Width, height** bei canvas
		- **type** bei script
		- Syntax:
			- attribut = "attributwert"
		- Attribute legen Art verhalten oder Aussehen der Tags fest
		- nicht alle für jedes Tag zulässig
		- Für manche Tags sind Attribute notwendig, für andere nicht
### Darstellung
- Textauszeichnung
	- Absatzerzeugende Tags wie
		- \<p> Absatz
		- \<h1> bis \<h6> Überschrift
	- Fließtext (Inline-) Tags bilden keinen Absatz -> das ist CSS -> Tag selber macht nichts -> browser liefert standartmäßig die dinge mit -> semantik bei Tags
		- \<em> Hervorhebung 
		- \<strong> Verstärkung
	- Strukturierte Tags
		- \<div> Absatzübergreifender Bereich
		- \<span> Bereich innerhalb einer Zeile
- HTML ist zum Taggen und nicht zum Design
- Struktur des Bodys  
	- Zentrales Strukturierungsmittel ist das Tag \<div>
- Verweise
	- verweise (Links) bieten beste Möglichkeit zur Strukturierung eines Web Projekts
	- Verweise zur eigenen HTML Seit oder zu einer Stelle auf der gleichen HTML Seite oder auch zu anderen Homepages
	- Syntax für Verweise ist in beiden Fällen gleich mit Tag \<a> ... \</a> für Anchor
		- link für andere seite \<a href = "URL(also hier die url rein)">Hier Inhalte oder so \</a>
- Abbildungen
	- werden auf jeweiligen Zugriffsort referenziert
	- Erfahrungsgemäß eignet sich PNG am besten
	- bilder werden mit Selbsschließendem Tag \<img> eingebunden
	- Tag hat zwei erforderliche Attribute -> src (für ressource selbst) und alt(alternativv zu zeigende Ressource falls Ressource nicht gefunden)
	- Weitere Attribute (hight und Width) sind möglich
	- Abbildungen können auch mit verweis kombiniert werden
### Interaktion
- Formulare
	- dienen der Interaktion von Usern und Website
	- Abbildung des typischen Workflows
	- können alle Elemente beinhalten beid en User
		- Texteingabe machen kann
		- Optionen auswählen kann
		- Aktionen starten kann
	- Seiten reagieren in der Regel auf diese Eingaben/selektion/Aktionen unmittlebar
	- prozedurale Abarbeitung erfolgt meist erst Clientsided
	- über formulare wird aber auch eine Server kommunikation ausgelöst/gestartet werden
	- dialog mit benutzer erfolgt im wesentlichen durch Formulareleente 
	- Formularelementer werden zumeist durch das tag \<input> erzeugt
	- Definition der Art über das Attribut type bspw. mit text, button, radio, passwort, submit, etc.
		- Beispiele
			- \<input type = "text" value= "Nachname?"/>
			- \<input type="checkbox" checked="checked" value="1"/>
			- \<input type = "button" value="Nicht Klicken!"/>
### Aufgaben
## Cascading Style Sheet(CSS)(vielleicht auch nicht) -> guck ich mir selber an :D

## JavaScript (Js)
- Scripsprachen -> werden durch einen Interpreter ausgeführt
- Interpreter geht zeilenweise und unabhängig durch und übersetzt
- JS wird in HTML eingebettet
- Kennzeichnung durch \<Script>
	- Unterschied in HTML zu Javascript
	- HTML ist Markup (erzeugt Auszeichnungen)
	- Js ist eine Programmiersprache (erzeugt Ablauf)
- Frei stehender Js Code wird immer beim Laden der Seite ausgeführt
- Tag kann grundsätzlich an beliebigem Ort stehen
- wird Typischerweise im header eingetragen, wenn
	- eine freistehende Anweisung unabhängig vom Inhalt beim Laden ausgeführt werden soll
	- eine Funktion definiert werden soll
- Event abhängiger Code muss direkt an den HTML Elementen stehen die das Event auslösen

- Auslagern von JAvascript in eigenen Dateien
	- Tag entfällt ddort
	- Code kann in HTML datei eingebunden werden
	- verwendet dasnn src im tag script
	- Verwendung von Funktionen
		- stehen global zur verfügung
		- einbindung sollte im Header der seite erfolgen
	- Einfache Interaktionoptionen
		- Meldung/Kommentarfenster ist eine einfache Kommunikation mit einer Seite möglich
		- in produktiven Websites sehr sparsam verwenden
		- sind Modal -> pop up fenster -> verbleiben im hintergrunf bis zum schließen
		- Funktion für diese Fenster sind im Standartobjekt window bereits implementiert
			- window.alert(TEXT)
			- window.confirm(TEXT)
			- window.promt(TEXT)
		- gibt in HTML kein Int String etc -> muss in Js getyped werden
	- neue inhalte können direkt in eine HTML seite geschrieben werden
	- Verwende den befehl document.write("TEXT")
	- TEXT wird unmittelbar an diese Stelle im HTML dokument geschrieben
	- Konsequenz: TEXT muss selbst immer eine Form vonn HTML sein
	- Ganze ist nur beim aufbau der Seite möglich
- Funktionen
	- function -> ist wie man eine funktion definiert
	- call by reference -> referenz -> ist speicherstelle -> referenz auf speicheradresse
	- referenzvariable -> variable die Referenzen aufnimmt -> in c ist das ein Pointer#
	- call by value
- Documentation Objet Model (DOM)
	- DOM ist Norm mit der Skriptsprache auf Elemente einer Auszeichnungssprache zugreifen können
	- Verwendung in der Sprache ermöglicht DOM-API
	- definiert **Objekte Eigenschaften und Methoden**
	- Wird von allen gängigen Browsern verstanden, gibt aber mehrere Standatisierungen (Level 0, level 1, Level 2, ...)
	- Level 0 wird als **W3C-DOM** bezeichnet
- Übersetzung der Dynamik Seite
	- Website wird Vollständig **geparsed**
	- Alle Elemente werden in Js Objekte umgewandelt werden
	- Bibliotheksmethoden erlauben Zugriff auf diese Objekte (DOM-API)
	- zugriff ist wahlfrei (random access)
	- auch **manipulation** der Elemente ist möglich
- Zugriff auf einzelne Elemente kann auf verschiedenen Wegen erfolgen
	- window.document.getElementById(STRING) da kann man noch .style oder .textContent; -> die Inhalte zwischne zwei Korrispondierenden Tags -> wenn noch tags dazwischen stehen werden die erst ausgeführt -> das kann man auch zum zuweisen verwenden 
	- window.document.getElementsByName(STRING) -> kann dem Elementen auch noch namen geben -> ist dann aber nicht eindeutig
	- window.document.getElementsByTagName(STRING)
	- indow.document.forms\[INDEX].elements\[INDEX]
- Benutzerdialog
	- Ziel ist js aktionen nach dem Laden der Seite auszuführen
	- Attribute von HTML elementen (Handler) wie: onclick, onchange, onmouseover, etc., .... können Funktionen(Listener) registrieren
	- bei eintritt des zugehörigen Ereignisses(Events) erfolgt ein Aufruf der jeweils registrierten Funktion(en)
	- über den Parameter event kann dem Aufruf ein Informationsobjekt im Kontext des Ergebnisses mitgegeben werden kann
	- callback funktion >:( -> registriere eine Funktion die bei event ausgeführt wird

# Generics
- Prinzip: Innerhalb einer Datenstruktur gibt es für Datentypen platzhalter -> Parameter
Ersetzung der Parameter durch konkrete Datentypen erfolgt
Parameter können nur durch Klassen etc. konkretisiert werden, nicht durch Basisdatentypen
public class Klasse<T> {
private String attribut1
private String attribut2
private T generischesAttribut
public Klasse(String pAttribut1, String pAttribut2, T pGenerischesAttribut){
this.attribut1 = pAttribut1
this.attribut2 = pAttribut2
this.generischesAttribut = pGenerischesAttribut}
public String getAttribut1(){
return this.attribut1;}
public void setAttribut1(pAttribut1){
this.attribut1 = pAttribut1;}
public String getAttribut2(){
return this.attribut2;}
public void setAttribut2(pAttribut2){
this.attribut2 = pAttribut2;}
public T getGenerischesAttribut(){
return this.generischesAttribut;}
public void setGenerischesAttribut(pGenerischesAttribut){
this.generischesAttribut = pGenerischesAttribut;}}
Jetzt eine Klasse erstellen:
String attribut1 = "";
String attribut2 = "";
Datentyp generischesAttribut = new Datentyp();
AndererDatentyp generischesAttribut2 = new AndererDatentyp();
Klasse<Datentyp> klasse = new Klasse<Datentyp>(attribut1, attribut2, generischesAttribut);
Klasse<AndererDatentyp> klasse2 = new Klasse<AndererDatentyp>(attribut1, attribut2, generischesAttribut2);
klasse2.getGenerischesAttribut(); -> gibt normal denm Generischen Datentypen T wieder, da es aber sdchon konkeretisiert ist wird AndererDatentyp wiedergegeben
Wenn alle Klassen konkretisiert wurden, gibt es nichts generisches mehr
jetzt Neue Klasse wo generisches Objekt erzeugt wird:
public class OberKlasse<T>{
private Klasse<T> klasse; -> jetzt ist generisch, man muss jetzt nicht auch in dem Klassenkopf konkretisieren, nur bei instanziierung        
public Klasse<T> getKlasse() {
return klasse;}
public void setKlasse(Klasse<T> pKlasse){
this.klasse = pKlasse;}}   
Damit gewährleistet ist, dass OberKlasse auch T von Klasse wiedergibt brauchen wir inteface
public OberKlasseInterface<T> implements Gewaehrleistet<T> { -> kann das interface verwenden, und auch schon konkretisieren
private Klasse<T> klasse;
public T getGenerischesAttribut(){
return klasse.getGenerischesAttribut();}}
public interface Gewaehrleistet<T> {
abstract public T getGenerischesAttribut(); -> Methoden in Interfaces sind (fast) immer public und abstrakt, public -> muss ja implementiert werden, deswegen geht private und protected nicht}
jetzt zwei generische Datentypen:
public class Klasse2<T,U> implements Gewaehrleistet<T>{
private T generischesAttribut;
private U generischesAttribut2;
@Override
public T getGenerischesAttribut(){
return this.generischesAttribut;}
public void setGenerischesAttribut(pGenerischesAttribut){
this.generischesAttribut = pGenerischesAttribut;}
public U getGenerischesAttribut2(){
return this.generischesAttribut2;}
public void setGenerischesAttribut2(pGenerischesAttribut2){
this.generischesAttribut2 = pGenerischesAttribut2;}}

## Interfaces und Abstrakte Klassen
### Interface
- Müssen bestimmte Methoden implementiert bekommen
- Klasse muss "extends Interface" haben um von interface die Sachen zu bekommen
- Alle Methoden im Interface müssen implementiert werden
- statt class interface
- abstract als key word, muss nicht, aber kann
- @Override benutzen um zu schauen ob es richtig ist, muss aber nicht