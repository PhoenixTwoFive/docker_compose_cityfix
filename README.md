## Erklärung:
Dieses Repository enthält die Docker-Einrichtung für das Cityfix-Projekt. Diese müssen auf GitHub vorhanden sein, damit der Build-Service des [Docker Hub](https://hub.docker.com/) die in den Dockerfiles definierten Container automatisiert bauen kann, was die Einbindung in das Gitlab-CI stark vereinfacht.

## Inhalte der Ordner:
|Ordnername|Erläuterung|
|----------|-----------|
|`cityfix_apache`|Container, welcher Apache,PHP, und die bezogenen Entwicklungsplugins für PHP enthält|
|`cityfix_apache`|Container, welcher eine Version des obigen Containers ohne Entwicklungsbezogene Software, zur Nutzung in der Auslieferung enthalten wird. **Noch nicht vollständig!**|
|`cityfix_api`|Container, welcher PHP, PHPUnit, composer und das `lumen`-Kommandozeilenwerkzeug enthält. `backend-terminal.sh` nutzt diesen Container.|
|`cityfix_elastic`| Würde Container mit Elasticsearch enthalten, ersetzt durch den [Offiziellen ES-Container](https://www.docker.elastic.co/)|
|`cityfix_frontend`|Enthält alle Werkzeuge welche sich auf die Frontend-Entwicklung beziehen. Analog zum bisherigen `frontendtools`-Container. `frontend-terminal.sh` nutzt diesen Container.|

## Kurzanleitung zur Nutzung:
1. Variablen in `up.sh` mit den entsprechenden Ordnern ausfüllen.
2. `up.sh` starten, die App ist jetzt unter `http://localhost:4200` aufrufbar, das Backend unter `http://localhost:4200/api/` erreichbar.
3. falls gewünscht, `backend-terminal.sh` für Terminal im `cityfix_api` Container starten.
4. falls gewünscht, `frontend-terminal.sh` für Terminal im `cityfix_frontend` Container starten.