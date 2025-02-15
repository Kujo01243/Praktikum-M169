# This is an archive!
As said in https://github.com/Kujo01243/Praktikum-M169/issues/1 you cannot run the code anymore. There is a missing Container.
# Praktikum-M169
## Ziel des Projekts
Ziel des Projekts ist es, die Containerisierung mit Docker zu verstehen und selbst anzuwenden, indem mehrere Container miteinander arbeiten und gemonitort werden. In diesem Repository sind alle Files, die benötigt werden, um die kleine Umgebung zu starten und auch zu verändern. Hier sind also alle Dockerfiles und Configs in ihrem Zustand, wo man sie noch nach seinen Wünschen verändern kann.
## Anleitung zur Verwendung
### Hinweis:
Das Docker Compose-File startet NICHT die Container aus den Ordnern und kann komplett ALLEINSTEHEND verwendet werden, weil die Container schon gebuildet wurden und in die GitHub Container registry hochgeladen wurden. Um die Container bei sich auszuführen, muss man also allein das Docker Compose starten. Es werden keine lokalen Files in Container gemountet oder als Volume angehängt.

### Installation:
1.) Docker und Docker Compose installieren.

2.) Docker Compose File an einem geeigneten Ort lokal abspeichern.

3.) Eine Befehlszeile am gleichen Ort öffnen.

4.) Befehl "docker compose up -d" oder, wenn es nicht geht, "docker-compose up -d" eingeben (je nach Host System).

5.) Hostfile anpassen, sodass folgende Subdomänen auf "127.0.0.1" zeigen:

6.) Jede Subdomäne in einem eigenen Tab öffnen:


http://m169.theil.es

http://m169-2.theil.es

http://grafana.theil.es

http://prometheus.theil.es

### Login Grafana
Der Login Name und das Passwort für Grafana (admin, Passwort123) sind im Docker-Compose File festgelegt und können auch dort nach Belieben angepasst werden. Ein Dashboard ist bereits erstellt.

### Hostfile
Warum braucht es eine Anpassung am Hostfile? Eine Anpassung am Hostfile braucht es, weil alle Services über den Reverse Proxy laufen. Woher soll also der Reverse Proxy wissen, auf welchen Service man zugreift? Denn dieser läuft auf einer IP und auch nur auf einem Port. 
Der Proxy kann anhand der Domain, welche man im Browser eingibt, herausfinden, auf welchen Service man zugreifen will und dementsprechend weiterleiten. 
Da die Domains, die von uns gewählt wurden, aber auf unsere Cloud Maschine verweisen und nicht auf die lokale VM oder die lokale IP derjenigen Person, welche die Container bei sich ausführt, muss auf dem Endgerät, von welchem man auf die Services zugreifen will, die Einträge im Hostfile so einstellen, dass die Domains auf die IP zeigen, wo der Reverse Proxy läuft. Alternativ, wenn man einen DNS-Server im Netz hat, könnte man die Einträge auch dort vornehmen.
