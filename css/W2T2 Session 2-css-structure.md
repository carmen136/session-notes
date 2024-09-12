What happens if 2 rules target the same property?

- Specificity:
	More specific rules overrule less specific ones
	!important > inline-styling im html > id > class > element
- Order:
	Rulesets with same specificity are evaluated by position. Lower is better

- Inheritance:
	Standardmäßig: color, background-color, font-family
	ansonsten extra Befehl: inherit -> erbt das Styling des Elternelements


How to structure CSS in a meaningful way?


Stichwort: komponentenbasierte Struktur
	->	bedeutet, dass man einzelne css Dateien für verschiedene Komponenten erstellt 
		und diese in einem components Ordner speichert
	->	mit (z.B.) @import "./components/title.css" kann man die css Dateien in einer main.css Datei (nennt man styles.css) verlinken 


gute Ordnerstruktur:

css 	> components > komponentendateien.css
	> global.css
	> styles.css

Ziel soll sein, dass es in der styles.css nur noch @imports gibt
global.css: allgemeine Regeln (u.a. für *, *::before, *::after html, body, (Farb-)variablen, allgemeinere Designs)