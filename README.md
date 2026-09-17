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
