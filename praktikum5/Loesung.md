CSP.01
	Variablen V:{ # Eine Variable für jede Kombination von Eigenschaft und Hausnummer
		Hausfarbe(1), Nationalität(1), Haustier(1), Getränk(1), Zigarettenmarke(1),
		Hausfarbe(2), [..]	
	}
	Domänen D:{ # X ist Platzhalter für die Hausnummern 1-5
		Hausfarbe(x) : {rot, grün, weiß, gelb, blau}
		Nationalität(x) : {England, Spanien, Ukraine, Norwegen, Japan}
		Haustier(x) : {Hund, Schnecke, Fuchs, Pferd, Zebra}
		Getränk(x) : {Kaffee, Tee, Milch, Orangensaft, Wasser}
		Zigarettenmarke(x) : {Old-Gold, Kools, Chesterfield, Lucky-Strike, Parliaments}
	}
	Constraints: {
		Keine zwei Häuser dürfen dieselbe Hausfarbe, Nationalität, Haustiere, Getränk oder Zigarettenmarke haben.
		Nationalität(x) = England <-> Hausfarbe(x) = Rot
		Nationalität(x) = Spanien <-> Haustier(x) = Hund
		Getränk(x) = Kaffee <-> Hausfarbe(x) = Grün
		Nationalität(x) = Ukraine <-> Getränk(x) = Tee
		Hausfarbe(x) = Weiss <-> Hausfarbe(x+1) = Grün		# X ist Hausnummer von links nach rechts, x+1 also das Haus rechts von x
		Zigarettenmarke = Old-Gold <-> Haustier = Schnecken
		Zigarettenmarke = Kools <-> Hausfarbe = Gelb
		Getränk(3) = Milch
		Nationalität(1) = Norwegen
		Zigarettenmarke(x) = Chesterfield <-> Haustier(x+1) = Fuchs OR Haustier(x-1) = Fuchs
		Zigarettenmarke(x) = Kools <-> Haustier(x+1) = Pferd OR Haustier(x-1) = Pferd
		Zigarettenmarke(x) = Lucky-Strike <-> Getränk(x) = Orangensaft
		Nationalität(x) = Japan <-> Zigarettenmarke(x) = Parliaments
		Nationalität(x) = Norwegen <-> Hausfarbe(x+1) = Blau OR Hausfarbe(x-1) = Blau
	}