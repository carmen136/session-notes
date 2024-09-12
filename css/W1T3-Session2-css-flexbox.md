flex-direction:
	row	-> horizontale Anordnung
	column	-> vertikale Anordnung

justify-content: (Anordnung horizontal oder vertikal, je nach direction)
	flex-start	-> items links 
	flex-end	-> items rechts
	center		-> mittig
	space-between	-> Platz verteilt, seitlich andockend
	space-evenly	-> gleicher Abstand überall
	space-around	-> gleicher Abstand zwischen items, seitlich halber Abstand


align-items: (Ausrichtung auf der Querachse)
	stretch		-> dehnen sich aus so viel Platz sie im Container haben
	flex-start	-> nur so viel Platz wie item braucht, Position oben
	flex-end	-> nur so viel Platz wie item braucht, Position unten
	center		-> nur so viel Platz wie item braucht, Position mittig

align-content: (Abstand zwischen mehreren Zeilen formatieren)
	flex-start	-> Zeilen oben im Container ausrichten
	flex-end	-> Zeilen unten im Container ausrichten
	center		-> mittig
	space-between	-> mit gleichmäßigem Innenabstand
	space-around	-> mit gleichmäßigem Außenabstand
	stretch		-> Zeilen strecken, um Container auszufüllen

gap: (erstellt Lücke)
	Größenangabe in px, rem, em
	rem (root Schriftgröße)


responsives Design

flex-wrap:
	wrap		-> items geraten in nächste Zeile wenn nebeneinander nicht genug Platz ist
	nowrap		-> items rücken nicht in nächste Zeile
	wrap-reverse


flex-direction und flex-wrap Kurzschreibweise:

flex-flow: z.B. row wrap;