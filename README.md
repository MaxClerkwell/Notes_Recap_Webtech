# Netzwerke & Betriebssysteme – Ein Recap für Webtechnologie 2

## Einführung & Motivation
- **Zentrale Frage:** Wie kommunizieren Computer miteinander?
- **Analogie:** Postsystem – MAC als Absender, IP als Empfänger
- Ziel: Grundlegendes Verständnis für Netzwerk- und Betriebssystemmechanismen schaffen

## MAC & IP
- **MAC-Adresse**
  - Hardware-Adresse der Netzwerkkarte (z. B. `00:1A:2B:3C:4D:5E`)
  - Weltweit eindeutig, fest einprogrammiert
- **IP-Adresse**
  - Logische Netzwerkadresse (z. B. `192.168.0.12`)
  - Je nach Netz dynamisch oder statisch vergeben
- **ARP:** Zuordnung von IP zu MAC-Adresse
- **DHCP:** Automatische Vergabe von IP-Adressen
- **Subnetting:** Aufteilung in Netzwerk- und Hostanteile (z. B. `192.168.0.0/24`)

## Routing & NAT
- **Default Gateway:** Standard-Route für fremde Netze
- **Routing-Tabelle:** Anzeigen mit `ip route`
- **NAT (Network Address Translation)**
  - Unterscheidung zwischen privaten und öffentlichen IP-Adressen
  - Port-Zuordnung durch NAT-Tabelle

## Ports & Protokolle
- **Transportprotokolle:** TCP (verbindungsorientiert), UDP (verbindungslos)
- **Standardports:** z. B. 80 (HTTP), 22 (SSH), 443 (HTTPS)
- **Werkzeuge:** `netstat`, `ss`, `lsof -i`, `nmap`

## TCP/IP Headerstruktur
- **Wichtige TCP-Felder:**
  - Source/Destination Port
  - Sequence & Acknowledgment Number
  - Flags: SYN, ACK, FIN, RST, PSH, URG
- **3-Wege-Handshake** zur Verbindungsinitialisierung
- **Segmentierung** und Wiederherstellung der Reihenfolge

## Shell & Syscalls
- **Shells:** Bash, Zsh, Fish – Pipes, Umleitungen, Skripting
- **System Calls:** `read`, `write`, `open`, `close`, `fork`, `exec`, `wait`
- **Analyse-Tools:** `strace`, `ltrace`

## SSH & sichere Kommunikation
- **Prinzip:** Verschlüsselte Verbindung & Authentifizierung per Public/Private Key
- **Tools:** `ssh`, `scp`, `ssh-copy-id`, `sshd`
- **Konfig-Dateien:** `~/.ssh/config`, `/etc/ssh/sshd_config`

## Unix Permissions
- **Rechtekonzept:** Nutzer, Gruppen, Andere – `rwx`
- **Werkzeuge:** `chmod`, `chown`, `umask`
- **Sonderbits:** `setuid`, `setgid`, `sticky`
- **Beispiele:** `ls -l`, `chmod 755 file`

## Webserver & HTTP
- **Modell:** Client ↔ Server
- **HTTP-Mechanismus:** Request → Response
- **Tools:** `curl`, `wget`, `python3 -m http.server`
- **Logs:** `access.log`, `error.log`

## Recap & Ausblick
- Vom ARP bis zur HTTP-Antwort
- Überblick über das Zusammenspiel der Konzepte
- Ausblick auf: Web-Apps, REST, Sockets, Security

---

## 📚 Inhaltsverzeichnis

1. [Einführung & Motivation](./chapters/01_intro.md)
2. [MAC & IP](./chapters/02_mac_and_ip.md)
3. [Routing & NAT](./chapters/03_routing_and_nat.md)
4. [Ports & Protokolle](./chapters/04_ports_and_protocols.md)
5. [TCP/IP Headerstruktur](./chapters/05_tcp_ip_header.md)
6. [Shell & Syscalls](./chapters/06_shell_and_syscalls.md)
7. [SSH & sichere Kommunikation](./chapters/07_ssh_and_security.md)
8. [Unix Permissions](./chapters/08_unix_permissions.md)
9. [Webserver & HTTP](./chapters/09_webserver_http.md)