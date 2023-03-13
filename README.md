# Ansible Playbook für Webserver und Jenkins Installation
Dieses Repository enthält ein Ansible Playbook, um einen Webserver und eine Jenkins-Installation auf einem Ubuntu-Server zu konfigurieren. Die Konfiguration erfolgt über SSH und erfordert einen Benutzer mit Root-Rechten.

### Anforderungen
. Ein Ubuntu-Server mit SSH-Zugang
. Ansible auf dem Steuerungsrechner installiert
### Verwendung
1.Erstellen Sie eine Inventar-Datei mit den Hostnamen und IP-Adressen der Server, die konfiguriert werden sollen.

[webserver]
www.personalverwaltungssystem.com ansible_host=20.107.39.83

[jenkins]
techstarter.ddns.net ansible_host=20.107.39.99

2. Ändern Sie im Playbook die Variablen **ansible_user** und **ansible_ssh_private_key_file**, um den Benutzernamen und den Pfad zur SSH-Schlüsseldatei anzupassen.

3. Führen Sie das Playbook aus:
- ansible-playbook -i hosts.yml playbook-configure.yml

### Inhalt des Playbooks
Das Playbook besteht aus drei Aufgaben:

1. Upgrade und Installation von Tools (NGINX, Docker, CURL, Default JRE) auf allen Servern.
2. Einrichtung eines Benutzers mit Docker-Gruppenberechtigungen und Einrichtung der SSH-Schlüsselauthentifizierung auf dem Webserver.
3. Installation und Konfiguration von Jenkins auf dem Jenkins-Server und Einrichtung eines Reverse-Proxy für den Zugriff auf Jenkins über NGINX.
### Hinweise zur Konfiguration
- Das Playbook wurde auf Ubuntu 20.04 LTS getestet und sollte auf anderen Ubuntu-Versionen und Debian-basierten Systemen funktionieren.
Stellen Sie sicher, dass Sie über ausreichende Berechtigungen verfügen, um die Konfiguration durchzuführen.
Ändern Sie die Variablen und Aufgaben entsprechend Ihren Anforderungen.
Überprüfen Sie nach Abschluss des Playbooks, ob alles wie erwartet funktioniert.
