## TCP Header-Felder – Übersicht

| Feld                  | Größe (Bit) | Bedeutung                                                                 |
|-----------------------|-------------|---------------------------------------------------------------------------|
| **Source Port**       | 16          | Port des sendenden Prozesses                                              |
| **Destination Port**  | 16          | Zielport beim empfangenden Host                                           |
| **Sequence Number**   | 32          | Nummer des ersten Bytes im Segment – wichtig für Reihenfolge              |
| **Acknowledgment Number** | 32     | Bestätigung: nächstes erwartetes Byte vom Partner                         |
| **Data Offset**       | 4           | Headerlänge in 32-Bit-Wörtern (mind. 5 = 20 Byte)                         |
| **Reserved**          | 3           | Für zukünftige Verwendung – immer 0                                       |
| **Flags**             | 9           | Steuerbits: SYN, ACK, FIN, RST, PSH, URG, ECE, CWR, NS                    |
| **Window Size**       | 16          | Wie viele Bytes kann Empfänger aktuell verarbeiten? (Flow Control)       |
| **Checksum**          | 16          | Prüfsumme für Header + Daten                                              |
| **Urgent Pointer**    | 16          | Gibt Position von dringenden Daten an (nur bei URG-Flag relevant)         |
| **Options (optional)**| variabel    | z. B. MSS, Timestamps, Window Scaling                                     |
| **Padding**           | variabel    | Auffüllen auf 32-Bit-Grenzen                                              |

> Hinweis: Diese Struktur ist für **klassisches IPv4-TCP**. Bei IPv6 oder TCP-Optionen (z. B. Fast Open) können Zusatzfelder auftreten.

## TCP Flags – Übersicht

| Flag | Name       | Bedeutung                                                                 |
|------|------------|---------------------------------------------------------------------------|
| URG  | Urgent     | Markiert Daten als dringend, `Urgent Pointer`-Feld wird interpretiert     |
| ACK  | Acknowledge| Bestätigt den Empfang vorheriger Daten                                    |
| PSH  | Push       | Daten sollen sofort an die Anwendung übergeben werden                     |
| RST  | Reset      | Verbindungsabbruch, z. B. bei Fehler oder unerwartetem Paket               |
| SYN  | Synchronize| Aufbau einer Verbindung (Start des 3-Wege-Handshake)                      |
| FIN  | Finish     | Beendet eine bestehende TCP-Verbindung                                    |
| ECE  | ECN Echo   | ECN-Unterstützung signalisieren (für Congestion Control)                  |
| CWR  | Congestion Window Reduced | Signalisiert reduzierte Fenstergröße (nach ECN)         |
| NS   | Nonce Sum  | Erweiterung zur Integritätssicherung (selten verwendet)                   |
