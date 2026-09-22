# Musiktest mit Supabase – Einrichtung

Enthalten:
- `index-supabase.html` – Schüler-Test
- `lehrer.html` – geschützter Lehrerbereich
- `config.js` – Supabase-Verbindung
- `supabase-setup.sql` – Tabelle + Sicherheitsregeln

## 1. Supabase-Projekt anlegen
Erstelle bei Supabase ein Projekt.

## 2. Datenbank einrichten
Öffne in Supabase den **SQL Editor**, füge den Inhalt von `supabase-setup.sql` ein und führe ihn einmal aus.

## 3. Lehrerkonto anlegen
Unter **Authentication → Users** ein Benutzerkonto für die Lehrkraft anlegen.
Wichtig: Gib Schülern kein Supabase-Login. Nur angemeldete Benutzer können die Ergebnisliste lesen.

## 4. config.js ausfüllen
Unter **Project Settings → API** die Project URL und den für Browser vorgesehenen anon/publishable Key kopieren.
In `config.js` einsetzen.

**Niemals einen `service_role`-/Secret-Key in GitHub hochladen.**

## 5. Auf GitHub hochladen
- Die bisherige `index.html` durch `index-supabase.html` ersetzen bzw. `index-supabase.html` vor dem Upload in `index.html` umbenennen.
- `lehrer.html` und `config.js` ebenfalls in das Hauptverzeichnis des Repositories hochladen.
- GitHub Pages bleibt auf `main` + `/(root)`.

Schüler öffnen die normale GitHub-Pages-Adresse.
Die Lehrkraft öffnet dieselbe Adresse mit `/lehrer.html` am Ende.

## Datenschutz
Die Anwendung speichert Namen, Testergebnis und Zeitpunkt bei Supabase. Für den schulischen Einsatz bitte die Vorgaben deiner Schule bzw. deines Schulträgers zum Datenschutz prüfen. Falls Klarnamen nicht zulässig sind, kann das Namensfeld leicht auf Kürzel/Pseudonyme umgestellt werden.

## Notenschlüssel
Aktuell:
- 90–100 % → 1
- 80–89 % → 2
- 65–79 % → 3
- 50–64 % → 4
- 30–49 % → 5
- 0–29 % → 6

Der Notenschlüssel ist sowohl in `index-supabase.html` als auch in der Datenbankprüfung in `supabase-setup.sql` hinterlegt. Bei Änderungen müssen beide Stellen angepasst werden.
