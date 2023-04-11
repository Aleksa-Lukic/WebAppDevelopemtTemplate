# WebApp Template

Dieses Open-Source-WebApp-Vorlagenprojekt wurde entwickelt, um Ihnen den Einstieg in die Erstellung von Webanwendungen mit FastAPI, PostgreSQL und Docker zu erleichtern.

## Anforderungen

- Python 3.9 oder höher
- Docker und Docker Compose

## Installation

1. Klone das Repository oder lade es herunter.
2. Passe die pyproject.toml-Datei nach Belieben an.
3. Erstelle eine virtuelle Umgebung:

```python
py.exe -m venv env
```
## Für Windows
```powershell
cd ./env/Scripts/active
```
## Im Bearbeitungsmodus starten
Navigiere zum Hauptverzeichnis des Web-Templates und führe den folgenden Befehl aus:
```bash
pip install -e .
```

3. Erstelle eine `.env`-Datei im Hauptverzeichnis und passe die folgenden Informationen nach Belieben an:
 -    DB_USER=postgres
 -    DB_PASSWORD=password
 -    DB_NAME=postgres_database
 -  DB_SERVER=db
 -  DB_PORT=5432
 - PGADMIN_EMAIL=admin@admin.com
 - PGADMIN_PASSWORD=admin

4. # Initialisiere Docker-Compose:
-    docker-compose up --build 

5. # Starte im "detached mode":

-    wenn der docker container noch läuft 
 -    docker-compose down
 -    docker-compose up -d

6. 
-    Die Webanwendung ist nun unter http://localhost erreichbar, und pgAdmin ist unter http://localhost:5050 verfügbar.

## Projektstruktur

- `app`: Hauptanwendungsverzeichnis
  - `app/main.py`: Hauptdatei der FastAPI-Anwendung
  - `app/controlers/`: Hier ist platz für sämtliche CRUD Operationen.
  - `app/core/config.py`: Hier sind die Configurations Settings für die Postgreql Datenbankanbindung für SQLAlchemy.
  - `app/database/engine.py`: Hier ist die engine für SQL Alchemy mit der Datenbank URL von der `app/core/config.py`
  - `app/database/session.py`: Definiert Funktionen zum Aufbau einer asynchronen Datenbankverbindung `get_db()` und zum Erstellen von Tabellen für SQLModel-Modelle `create_db_and_tables()`.
  - `app/models/`: Hier werden Datenbank Modelle erstellt mit SQLModel.
    - `app/views/static`: Hier ist platz für die style.css etc....
    - `app/views/templates`: Hier werden die index.html etc angebunden
- `Dockerfile`: Docker-Datei zum Erstellen des Webanwendungs-Containers
- `docker-compose.yaml`: Docker Compose-Konfigurationsdatei zum Starten der Webanwendung und der zugehörigen Dienste
- `requirements.txt`: Liste der Python-Pakete, die für das Projekt erforderlich sind
- `pyproject.toml`: Konfigurationsdatei für das Projekt und seine Abhängigkeiten
- `.env`: Beispiel für eine `.env`-Datei zum Festlegen der Umgebungsvariablen für das Projekt

## Anpassen

Um dieses Template für deine eigenen Projekte anzupassen, kannst du die folgenden Schritte ausführen:

1. Ändere die Projektinformationen in der `pyproject.toml`-Datei, wie den Projektnamen und die Beschreibung.
2. Aktualisiere die `app/main.py`-Datei, um die gewünschte Funktionalität für deine Webanwendung und erstelle noch weite Directorys nach belieben im `./app/` Directory

