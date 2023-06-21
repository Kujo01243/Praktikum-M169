# Praktikum-M169
## Ziel des Projekts
Ziel des Projekts ist es, die Containerisierung mit Docker zu verstehen und selbst anzuwenden, indem mehrere Container miteinander arbeiten und gemonitort werden. In diesem Repository sind alle Files, die benötigt werden, um die kleine Umgebung zu starten und auch zu verändern. Hier sind also alle Dockerfiles und Configs in ihrem Zustand, wo man sie noch nach seinen Wünschen verändern kann.
## Anleitung zur Verwendung
### Hinweis:
Das Docker Compose startet NICHT die Container aus den Ordnern und kann komplett ALLEINSTEHEND verwendet werden, weil die Container schon gebuildet wurden und in die Github Container registry hochgeladen wurden. Um die Container bei sich auszuführen muss man also allein das Docker Compose starten. Es werden keine lokalen Files in Container gemountet oder als Volume angehängt.

### Installation
1.) Docker und Docker Compose installieren.

2.) Docker Compose File an einem geeigneten Ort lokal abspeichern.

3.) Eine Befehlszeile am selbigen Ort öffnen.

4.) Befehl "docker compose up -d" oder, wenn es nicht geht, "docker-compose up -d" eingeben.

5.) Hostfile anpassen, sodass folgende Subdomänen auf "127.0.0.1" zeigen:

- m169.theil.es
- m169-2.theil.es
- grafana.theil.es
- prometheus.theil.es


6.) Jede Subdomäne in einem eigenen Tab öffnen.
