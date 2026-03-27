# Lernperiode 9

Ich habe in **Godot** ein Spiel programmiert. Jetzt möchte ich das mit einer datenbank verbinden, so das ich ganz einfach Spielstände speichern kann. Ich hatte drei Datenbanken zur verfügung.(**PostgreSQL**, **SQLAlchemy**, **MongoDB**, **SQLite**) Ich habe mich nach lanem überlegen für die Datenbank SQLite entschieden. Danach habe ich lange Tutorials gesucht die mir dabei helfen können SQLite herunter zu laden. Problem war das ich keines gefunden habe. Am Schluss habe ich es mit Hilfe von ChatGPT heruntergeladen.

Ich habe eine Idee gehabt, das ich einen Timer einfüge in mein Spiel und jedes mal wenn ich starte wird die Zeit gemessen.Die wird gespeichert und die besten 5 plätze ausgegeben. Ich muss aber dafür mein Godot Projekt nochmal optimieren und später mithilfe der Datenbank alles speichern.

Mein aktuelles Problem ist das ich meine Datenbank nicht verbinden kann, da ich nicht herausgefunden habe wie dies Funktioniert. Das muss ich nächste Woche mit meinem Lehrer anschauen. 

## 27.2
- [ ] Datenbank verbinden
- [ ] Eine Ziellinie in Godot erstellen
- [ ] Timer in Godot hinzufügen.

## 06.03

- [x] Ziellinie im Level erstellt  
- [x] Timer eingebaut, der beim ersten Bewegen startet  
- [x] Timer stoppt, wenn der Spieler die Ziellinie erreicht  
- [x] Zeit über dem Spieler im Spiel anzeigen  

Heute habe ich mein Spiel weiter verbessert. Ich habe eine **Ziellinie mit Area2D und CollisionShape2D** erstellt, die erkennt, wenn der Spieler das Ziel erreicht. Zusätzlich habe ich einen **Timer programmiert**, der automatisch startet, sobald sich der Spieler bewegt, und stoppt, wenn die Ziellinie berührt wird. Die gemessene Zeit wird nun mit einem **Label direkt über dem Spieler im Spiel angezeigt**. **Wichtig:** Ich konnte denn Code nicht hochladen, da er zu gross ist.

## 13.03

- [x] SQLite-Datenbank mit dem Godot-Projekt verbunden  
- [x] Tabelle für Bestzeiten in der Datenbank erstellt  
- [x] Spielzeit beim Erreichen der Ziellinie in der Datenbank gespeichert  
- [ ] Top 3 Bestzeiten im Spiel anzeigen  

Heute habe ich mein Spiel weiterentwickelt und eine **SQLite-Datenbank mit meinem Godot-Projekt verbunden**. Anschliessend habe ich eine **Tabelle für Bestzeiten erstellt**, in der die Spielzeiten gespeichert werden können. Zusätzlich habe ich die Ziellogik erweitert, sodass die **gemessene Zeit automatisch in der Datenbank gespeichert wird**, sobald der Spieler die Ziellinie erreicht.

## 20.03

- [x] Top 3 Bestzeiten aus der Datenbank auslesen  
- [x] Top 3 Zeiten im Spiel anzeigen  
- [X] Map vergrössern und schwerer machen 
- [ ] Spielrunde neu starten können, um Bestzeiten zu schlagen

Heute habe ich mein Spiel weiter ausgebaut und verbessert. Ich habe die **Top 3 Bestzeiten aus der Datenbank ausgelesen** und diese anschliessend direkt im Spiel angezeigt, sodass man seine Leistungen vergleichen kann. Zusätzlich habe ich die **Map vergrössert und den Schwierigkeitsgrad erhöht**, indem ich neue Plattformen hinzugefügt und das Level anspruchsvoller gestaltet habe.

## 27.03
- [ ] Spielrunde neu starten können, um Bestzeiten zu schlagen
- [ ] animationen hinzufügen

