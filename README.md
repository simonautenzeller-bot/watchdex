# Watchdex

Film- & Serientracker als installierbare PWA. Kein Backend, keine Cloud – alle Daten liegen lokal im Browser (`localStorage`).

## Features

- Status pro Eintrag: **Will ich sehen**, **Laufend** (nur Serien), **Gesehen** (Filme) / **Abgeschlossen** (Serien), **Abgebrochen**
- Filme: Titel, Jahr, Genre, Regisseur, Haupt-Darsteller, Länge, Bewertung
- Serien: zusätzlich Staffel-/Episoden-Tracking (geschaut/gesamt pro Staffel)
- Statistik: Filme gesehen, Episoden geschaut, Gesamtzeit, Top-Genres, Top-bewertet
- TMDB-Anbindung: Suche beim Anlegen füllt Felder automatisch (Jahr, Genre, Regie, Cast, Länge, Poster)
- Moviebreak-Import: Massenimport mit automatischer TMDB-Anreicherung

## Lokal starten

```bash
node server.js
```

Dann `http://localhost:5173` öffnen. Für die Service-Worker-/PWA-Features braucht es http(s), nicht `file://`.

## TMDB-Key einrichten

Kostenloser Account auf [themoviedb.org](https://www.themoviedb.org) → Einstellungen → API → "API-Schlüssel" (v3, **nicht** das "API-Token für Lesezugriff"). In der App unter Einstellungen → TMDB-Anbindung eintragen. Bleibt nur in deinem Browser (`localStorage`), wird nie sonst irgendwohin geschickt.

## Daten

`data/` enthält persönliche Exporte (moviebreak-Verlauf, Bibliotheks-Backups) und ist bewusst in `.gitignore` – das ist dein privater Sehverlauf, kein Teil des Codes.


## Wochen-Backup

Die App sichert einmal pro Woche (beim Öffnen) ein Backup außerhalb des Browsers, denn gelöschte Browser-Daten nehmen sonst auch die App-Daten mit. Am Computer (Chrome/Edge) schreibt sie automatisch in einen gewählten Ordner, z. B. im OneDrive-Ordner; am Handy lädt sie nach einmaliger Einrichtung direkt in dein privates OneDrive oder erinnert dich, die Datei per „Teilen“ abzulegen. Fehlen beim Start alle Daten, bietet die App direkt das Einspielen eines Backups an. Einstellungen und Einrichtung der Microsoft-Anmeldung: **Einstellungen → Wochen-Backup**. Weiterleitungs-URI für die Microsoft-App-Registrierung: `https://simonautenzeller-bot.github.io/watchdex/`. Ausführliche Anleitung: README von alltagplus. Die Logik steckt in `backup.js` (eine Kopie in jeder App).
