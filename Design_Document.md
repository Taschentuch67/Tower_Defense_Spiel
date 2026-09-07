Design Doc
Frameworks:
Main.py
settings.py
Models/
	player.py
	enemy.py
	tower.py
	projecticle.py
Managers/
	level.py
	game.py

Logik:
Wellen-Start: Der Level-Manager generiert Gegner (z. B. Erdbeeren) am Startpunkt der Map.
Bewegung: Jedes Frame ruft die game.py für jeden aktiven Gegner die move()-Methode auf. Erreicht eine Frucht das Ende des Pfads, verliert der Player Leben (player.lose_hp()) und die Frucht wird gelöscht.
Erfassung & Angriff: Jeder platzierte Tower prüft in seinem update()-Zyklus, welche Gegner in seiner range sind. Findet er einen, feuert er ein Projectile ab.
Treffer & Belohnung: Das Projectile fliegt zum Gegner. Sobald es ihn trifft, wird enemy.take_damage() aufgerufen. Sinkt die HP der Frucht auf 0, stirbt sie, der Player erhält Gold (player.add_money()) und die Frucht wird aus der Gegner-Liste entfernt.
Upgrades: Klickt der Spieler auf einen Turm, öffnet sich ein UI-Fenster. Ein Klick auf "Upgrade Pfad A" prüft, ob der Spieler genug Geld hat und ob die Regel path_a_level + path_b_level < 4 und path_a_level < 3 erfüllt ist. Wenn ja, steigen die Werte des Turms.
Wellen-Start: Der Level-Manager generiert Gegner (z. B. Erdbeeren) am Startpunkt der Map.
Bewegung: Jedes Frame ruft die game.py für jeden aktiven Gegner die move()-Methode auf. Erreicht eine Frucht das Ende des Pfads, verliert der Player Leben (player.lose_hp()) und die Frucht wird gelöscht.
Erfassung & Angriff: Jeder platzierte Tower prüft in seinem update()-Zyklus, welche Gegner in seiner range sind. Findet er einen, feuert er ein Projectile ab.
Treffer & Belohnung: Das Projectile fliegt zum Gegner. Sobald es ihn trifft, wird enemy.take_damage() aufgerufen. Sinkt die HP der Frucht auf 0, stirbt sie, der Player erhält Gold (player.add_money()) und die Frucht wird aus der Gegner-Liste entfernt.
Upgrades: Klickt der Spieler auf einen Turm, öffnet sich ein UI-Fenster. Ein Klick auf "Upgrade Pfad A" prüft, ob der Spieler genug Geld hat und ob die Regel path_a_level + path_b_level < 4 und path_a_level < 3 erfüllt ist. Wenn ja, steigen die Werte des Turms.

GameLoop:
Event-Processing
Update(Zustände berechnen)
Render(alles auf dem Bildschirm zeichnen)

Klassen: Player, Enemy, Tower, Projectile, Level
