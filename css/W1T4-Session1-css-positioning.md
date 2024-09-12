
static (default)

fixed
	- wird aus dem documentflow rausgenommen
	- Platz wird frei, alles andere rückt nach
	- bleibt dort, wo man die Position angegeben hat (z.B. top = 0 -> ganz oben) und bleibt im viewport
	- offset: ja, relativ zum Viewport (offset bedeutet Angaben wie top, bottom, left, right)
sticky
	- Platz bleibt im documentflow reserviert
	- offset: ja, dient zur Fixierung
	- bei offset z.B: top = 0 dann bleibt das Element erst dann kleben, wenn es an der Position angekommen ist


die beiden folgenden werden meistens in Kombi miteinander verwendet:


relative
	- ändert zunächst nichts
	- Documentflow wird nicht geändert, Platz wird nicht freigegeben
	- offset: ja, relativ zum Ursprung -> offset-Angaben beziehen sich auf die ursprüngliche Position des Elementes, nicht auf den viewport
	- dient als Anker für position: absolute


absolute
	- Position wird aus dem documentflow rausgenommen und absolut positioniert
	- offset: ja, relativ zum nächsten "non-static" Vorfahren


z-Index:

	- bestimmt die Ebene eines Elements
	- bei gleicher Zahl im z-index gilt: das später im css aufgeführte Element liegt eine Ebene über dem anderen