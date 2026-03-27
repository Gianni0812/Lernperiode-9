---
title: Mein Tutorial
---

# Goal

In diesem Tutorial lernst du, wie man eine **SQLite-Datenbank in Godot integriert**, um Daten dauerhaft zu speichern und zu verwalten. Dabei wird gezeigt, wie man eine Datenbank erstellt, Tabellen definiert und Daten mithilfe von SQL-Befehlen speichert, ausliest und löscht. Dieses Wissen ist besonders wichtig, um Spielstände, Highscores oder andere Informationen langfristig im Projekt zu sichern.

# Previous Knowledge

Für dieses Tutorial solltest du die grundlegende Bedienung von Godot kennen. Dazu gehört das Erstellen von Szenen, das Hinzufügen und Verwalten von Nodes sowie das Schreiben einfacher GDScript-Skripte. Grundkenntnisse in Programmierung wie Variablen, Funktionen, Bedingungen und einfache Logik sind hilfreich. Zudem ist es von Vorteil, wenn du bereits einfache Projekte in Godot umgesetzt hast.

# What you'll learn

In diesem Tutorial lernst du:

- Eine SQLite-Datenbank in Godot einzubinden  
- Eine Datenbankdatei zu erstellen und zu öffnen  
- Eine Tabelle mit Spalten und Datentypen zu definieren  
- Daten mithilfe von SQL-Befehlen in die Datenbank zu speichern  
- Daten aus der Datenbank auszulesen und zu verarbeiten  
- Daten gezielt zu sortieren und zu begrenzen  
- Daten aus der Datenbank zu löschen  
- Grundlegende SQL-Befehle zu verstehen und anzuwenden 

# Tutorial
Zuerst installieren wir das **SQLite-Plugin** über die Godot Asset Library und aktivieren es anschliessend in den Project Settings unter „Plugins“. Dieses Plugin ermöglicht es, direkt aus dem GDScript heraus mit einer SQLite-Datenbank zu arbeiten.

Danach erstellen wir im Script eine Verbindung zur Datenbank:

```csharp
var db

func _ready():
	db = SQLite.new()
	db.path = "user://database.db"

	if db.open_db():
		print("Datenbank verbunden")
	else:
		print("Fehler beim Verbinden")
```
Die Datenbankdatei wird automatisch erstellt, falls sie noch nicht existiert. Der Pfad user:// ist ein spezieller Godot-Pfad, der für lokale Speicherung verwendet wird.

Anschliessend erstellen wir eine Tabelle in der Datenbank:

```csharp
func create_table():
	var sql = "CREATE TABLE IF NOT EXISTS data (id INTEGER PRIMARY KEY AUTOINCREMENT, value REAL)"
	db.query(sql)
```
Hier wird eine Tabelle mit zwei Spalten erstellt:

id: eine automatisch hochzählende eindeutige Nummer
value: ein Zahlenwert (z. B. eine Zeit oder ein Punktestand)

Der Zusatz IF NOT EXISTS verhindert, dass die Tabelle mehrfach erstellt wir

Nun können wir Daten speichern:
```csharp
func save_data(value):
	var sql = "INSERT INTO data (value) VALUES (%f)" % value
	db.query(sql)
```
Dieser SQL-Befehl fügt einen neuen Eintrag in die Tabelle ein. Der Platzhalter %f wird dabei durch den übergebenen Wert ersetzt.

Um Daten auszulesen, verwenden wir eine SELECT-Abfrage:
```csharp
func load_data():
	var sql = "SELECT value FROM data ORDER BY value ASC"
	db.query(sql)

	var result = db.query_result

	for i in range(result.size()):
		print(str(i + 1) + ": " + str(result[i]["value"]))
```
Dabei passiert Folgendes:

SELECT holt die Daten aus der Tabelle
ORDER BY value ASC sortiert die Werte aufsteigend
query_result enthält die Ergebnisse der Abfrage

Optional kann man die Anzahl der Ergebnisse begrenzen:
```csharp
var sql = "SELECT value FROM data ORDER BY value ASC LIMIT 3"
```
Damit werden nur die ersten drei Einträge zurückgegeben.

Zusätzlich kann man alle Daten löschen:
```csharp
func clear_data():
	db.query("DELETE FROM data;")
```
Dieser Befehl entfernt alle Einträge aus der Tabelle, ohne die Struktur der Tabelle zu löschen. Man sollte jedoch aufpassen, da man die Daten sonst immer wieder löscht. Dies dient nur zum Testen.

# Result

# What could go wrong?
