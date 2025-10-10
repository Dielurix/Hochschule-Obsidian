- Verfahren zur nullstellen Bestimmung basiert auf Theorem 266 -> für stetige funktionen gibt es immer eine stelle x0 für  a und b 
- Auch intervallhalbierungsverfahren
	- Wieso brauche ich Stetigkeit
	- Stetigkeit nicht notwendig

- Scheidemann mag algorithmen #klausur
	- den für bisektionsverfahren merken
	- Terminiert algorithmus?
- Foliue 319 -> nochmal anschauen
- basiert dadrauf das intervall suksessive halbieren -> n mal machen ist lösungspunkt maximal (b-a) /2^n
- in jeder iteration wird die länge des intervalls halbiert

- bestimmen nullstelle von f(x) = x^3 - x - 2 im intervall \[1,2] mit bisektionsverfahren und epsilon = 0,1
1. f ist stetig
2. gibt vorzeichenwechsel -> intervallgrenzen einsetzen -> f(1) = -2 < 0, f(2) = 4 >0
	1. x1 = 1,5 -> mitte des intervalls, f(1,5) = -0,125 < 0 -> neues intervall ist also: I1 \[1,5;2] -> den nehmen weil kleiner null
	2. wieder hälfte -> x2 = 1,75, f(1,75) = 1,609.. > 0 -> neues intervall -> I2 = \[1,5;1,75]
	3. wieder hälfte -> x3 = 1,625, f(1,625) = 0,66602 > 0 -> I3 = \[1,5;1,625]
- Grund Idee: ![[Pasted image 20250918181658.png]]
- durch epsilon = 0,1 -> will das ergebniss weniger entfernt ist als 0,1 -> hierbei 7 schritt x7 = 1,5234... f(x7) = 0,012
- Ist für PC gemacht, Taschenrechner macht kein spass

Aufgaben: ![[Pasted image 20250918181951.png]]
#klausur ![[Pasted image 20250918182005.png]]
- Mündliche prüfung als situation vor augen führen

stetigkeit nachweisen -> alle sind stetig
#klausur hinreichend nicht notwendig -> wenn stetig dann ist prima, sonst aber auch nicht schlimm, warum braucht man stetigkeit -> minute 30 -> ergiebige erklärung -> folgenkonvergenz braucht man stetigkeit 
Frage 5 -> nicht schlimm, haben halt dann gezeigt das der direkt drauf liegt -> ist dann perfekt, weil wir dann auf keine toleranz sein

Frage 2 -> funktion Stetig im intervall, Vorzeichenwechsel
frage 3 -> nicht notwendig aber hinreichend -> mus snur im intervall stetig sein 
Frage 4 ->
![[Pasted image 20250918184509.png]]
frage 6 -> wenn funktionswert gleich null also wenn y = 0 also wenn f(x) = 0


bei 3 einfach umformen -> 3^x = 6 -> intervall ausdenken -> da schauen das ganze zahlen und jeweils ein f(x) < 0 und eins > 0 -> hier jetzt \[1,2] -> dann Bisektion  
![[Pasted image 20250918192158.png]]

Frage 7 -> Eigenschaft einer Funktion ohne Unterbrechung oder Sprünge zu sein -> hier Glühbirne und Heizung