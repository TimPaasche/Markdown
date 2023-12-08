# Themen Bonuspunkte Prüfung Secruity

**Inhaltsverzeichnis:**
- [BSI-ICS - Vorsätzliche Handlungen](#bsi-ics---vorsätzliche-handlungen)
- [Profinet/Profibus](#profinetprofibus)
  - [Profinet (Process Field Network)](#profinet-process-field-network)
  - [Profibus:](#profibus)
- [Firewalls / HW Firewall / IDS Systeme](#firewalls--hw-firewall--ids-systeme)
- [Diverse Angriffsvektoren und besprochene Maßnahmen zur Vermeidung, s. BSI Top 10 Threads zur Vorbereitung](#diverse-angriffsvektoren-und-besprochene-maßnahmen-zur-vermeidung-s-bsi-top-10-threads-zur-vorbereitung)
- [Unterschied Safety und Security in Automation](#unterschied-safety-und-security-in-automation)
- [Malware Klassen und Merkmale: Trojaner, Viren, Würmer](#malware-klassen-und-merkmale-trojaner-viren-würmer)
  - [Virus](#virus)
  - [Trojaner / Trojanisches Pferd](#trojaner--trojanisches-pferd)
  - [Computerwurm:](#computerwurm)
- [Angriffsformen DDOS, Phishing, Spoofing , Man in the Middle](#angriffsformen-ddos-phishing-spoofing--man-in-the-middle)
  - [Spoofing](#spoofing)
  - [Phishing](#phishing)
  - [(Distributed) Denial of Services (D)DoS](#distributed-denial-of-services-ddos)
  - [Man-in-the-middle](#man-in-the-middle)
- [Architektur/Konzept der Angriffsmodelle: Time/Logic Bomb , Makroviren, ARP Spoofing, XML Injection](#architekturkonzept-der-angriffsmodelle-timelogic-bomb--makroviren-arp-spoofing-xml-injection)
- [VIV Modell](#viv-modell)
- [Kommunikation: OPC , OPC UA , IPSec](#kommunikation-opc--opc-ua--ipsec)
  - [OPC](#opc)
  - [OPC UA](#opc-ua)
  - [IPSec (Internet Protocol Security)](#ipsec-internet-protocol-security)
- [Router NAT/PAT , ARP Spoofing](#router-natpat--arp-spoofing)
  - [NAT(Network Address Translation)](#natnetwork-address-translation)
  - [PAT (Port and Address Translation)](#pat-port-and-address-translation)
- [DMZ bzw. Automation Cells](#dmz-bzw-automation-cells)
----

## BSI-ICS - Vorsätzliche Handlungen

- Industrial Control Systems


## Profinet/Profibus

### Profinet (Process Field Network)
  - offener Industrial Ethernet-Standard 
  - nutzt TCP/IP und IT-Standards, ist Echtzeit-Ethernet-fähig und ermöglicht die Integration von Feldbus-Systemen
### Profibus:
  - PROFIBUS DP (Dezentrale Peripherie): Ansteuerung von Sensoren und Aktoren durch eine zentrale Steuerung in der Fertigungstechnik.
  - PROFIBUS PA (Prozess-Automation): Kommunikation zwischen Mess- und Prozessgeräten, Aktoren und Prozessleitsystem bzw. SPS/DCS in der Prozess- und Verfahrenstechnik

## Firewalls / HW Firewall / IDS Systeme

- Eine Firewall ist ein Sicherungssystem, das ein Rechnernetz oder einen einzelnen Computer vor unerwünschten Netzwerkzugriffen schützt und ist weiter gefasst auch ein wichtiger Teilaspekt eines Netzwerk-Sicherheitskonzepts.
- Jedes Firewall-Sicherungssystem basiert auf einer Softwarekomponente.
- Sie überwacht den durch die Firewall laufenden Datenverkehr und entscheidet anhand festgelegter Regeln, ob bestimmte Netzwerkpakete durchgelassen werden oder nicht.
- Für das Aufspüren von Angriffen sind sogenannte IDS-Module (Intrusion Detection System) zuständig.
- Personal Firewall: lokales zu schützendes Gerät
- External Firewall: seperates Gerät z.B. von WAN (Wide Area Network) auf LAN (Local Area Network)
- Firewall Regeln: 
    - Methode basiert auf Mandatory Access Control
    - Die Regeln werden für jedes Paket der Reihe nach geprüft, und die erste zutreffende Regel wird angewendet
- IDS (Intrusion Detection System):
    - Erkennung von Angriffen, die gegen ein Computersystem oder Computernetz
    - kann eine Firewall ergänzen oder auch direkt auf dem zu überwachenden Computersystem laufen

## Diverse Angriffsvektoren und besprochene Maßnahmen zur Vermeidung, s. BSI Top 10 Threads zur Vorbereitung

| Rang | Bedrohung/Trend                                     | Beschreibung                                             |
|------|-----------------------------------------------------|---------------------------------------------------------|
| 1    | Einschleusen von Schadsoftware über Wechseldatenträger und mobile Systeme | Diese Bedrohung bezieht sich auf die Verbreitung von bösartiger Software über externe Speichermedien wie USB-Sticks und mobile Geräte wie Smartphones. Angreifer nutzen oft diese Wege, um Malware in Netzwerke einzuschleusen. |
| 2    | Infektion mit Schadsoftware über Internet und Intranet | Angriffe durch Schadsoftware über das Internet oder interne Netzwerke sind weit verbreitet. Dies umfasst beispielsweise den Download von schädlichen Dateien, die sich über das Netzwerk verbreiten und Systeme infizieren. |
| 3    | Menschliches Fehlverhalten und Sabotage              | Sicherheitsrisiken entstehen durch Fehler oder böswilliges Verhalten von Mitarbeitern. Dies kann unbeabsichtigte Datenlecks, unsichere Passwörter oder Sabotageakte einschließen. Schulung und Bewusstseinsbildung sind entscheidend, um diese Bedrohung zu minimieren. |
| 4    | Kompromittierung von Extranet und Cloud-Komponenten | Angreifer richten ihre Aufmerksamkeit vermehrt auf externe Netzwerke und Cloud-Dienste, um Zugriff auf sensible Daten zu erhalten oder Dienste zu beeinträchtigen. Die Sicherheit von Cloud-Komponenten muss besonders beachtet werden. |
| 5    | Social Engineering und Phishing                      | Social Engineering zielt darauf ab, Menschen zu täuschen, um an vertrauliche Informationen zu gelangen. Phishing, eine Form von Social Engineering, verwendet gefälschte Kommunikation, um Benutzer zur Preisgabe von Passwörtern oder persönlichen Daten zu verleiten. |
| 6    | (D)DoS Angriffe                                      | Distributed Denial of Service (DDoS)-Angriffe zielen darauf ab, Netzwerke, Dienste oder Websites durch Überlastung lahmzulegen. Dies kann zu erheblichen Ausfallzeiten und Serviceunterbrechungen führen. |
| 7    | Internet-verbundene Steuerungskomponenten            | Die zunehmende Vernetzung von industriellen Steuerungssystemen birgt Risiken. Angriffe auf diese Systeme können zu schwerwiegenden Konsequenzen führen, von Produktionsausfällen bis hin zu physischen Gefahren. |
| 8    | Einbruch über Fernwartungszugänge                    | Fernwartungszugänge bieten bequeme Möglichkeiten zur Wartung von Systemen, sind jedoch auch Einfallstore für unautorisierte Zugriffe. Schwachstellen in der Konfiguration können zu unerlaubten Zugriffen führen. |
| 9    | Technisches Fehlverhalten und höhere Gewalt          | Technische Fehler oder Naturkatastrophen können zu Ausfällen und Störungen führen. Die Planung für solche Ereignisse und die Implementierung von Notfallwiederherstellungsplänen sind entscheidend. |
| 10   | Soft- und Hardwareschwachstellen in der Lieferkette  | Sicherheitslücken in Software- und Hardwarekomponenten, die von Lieferanten bereitgestellt werden, können von Angreifern ausgenutzt werden. Eine sorgfältige Überprüfung der Lieferkette ist wichtig, um diese Schwachstellen zu minimieren. |




## Unterschied Safety und Security in Automation

- Security in Automation: Schutz vor Eindringen, Angriffen und Übernahme einer Industrieanlage
- Gewährleistung eines Sicherheitszustandes und eines reibungslosen Produktionsprozess
=> Security in Automation dient dem Schutz vor Gefahren bzw. Bedrohungen, der Vermeidung von Schäden und der Minimierung von Risiken im Produktionsprozess. 


## Malware Klassen und Merkmale: Trojaner, Viren, Würmer

### Virus 

  - Ein Computervirus ist ein sich selbst verbreitendes Computerprogramm, welches sich in andere Computerprogramme einschleust und sich damit reproduziert.
  - Einmal gestartet, kann es vom Anwender nicht kontrollierbare Veränderungen am Status der Hardware, am Betriebssystem oder an der Software vornehmen.
  - Zur Verbreitung eines Viruses muss die infizierte Datei ausgeführt werden.

### Trojaner / Trojanisches Pferd

  - Als Trojanisches Pferd bezeichnet man ein Computerprogramm, das als nützliche Anwendung getarnt ist, im Hintergrund aber ohne Wissen des Anwenders eine andere Funktion erfüllt.
  - Viele Trojanische Pferde installieren während ihrer Ausführung auf dem Computer heimlich ein Schadprogramm.  So können u. a. eigenständige Spionageprogramme auf den Rechner gelangen (z. B. Sniffer oder Komponenten, die Tastatureingaben aufzeichnen, sogenannte Keylogger).
  - Auch die heimliche Installation eines Backdoorprogramms ist möglich, dies gestattet, den Computer unbemerkt über ein Netzwerk (z. B. das Internet) fernzusteuern.

### Computerwurm: 

  - Würmer verbreiten sich autonom über Netzwerke oder über Wechselmedien wie USB-Sticks.
  - Dafür benötigen sie gewöhnlich ein Hilfsprogramm wie einen Netzwerkdienst oder eine Anwendungssoftware als Schnittstelle zum Netz.
  - Würmer können sich eigenständig reproduzieren.

## Angriffsformen DDOS, Phishing, Spoofing , Man in the Middle

### Spoofing

  - Spoofing umfasst alle Methoden, mit denen sich Authentifizierungs- und Identifikationsverfahren untergraben lassen, welche auf der Verwendung vertrauenswürdiger Adressen oder Hostnamen in Netzwerkprotokollen beruhen

### Phishing

  - Anzeigen von „gefälschten“ Web-Seiten, die täuschend ähnlich den Original-Web-Seiten nachgebaut sind.
  - iele des Phishings sind im Wesentlichen, der Diebstahl von Bank-Kreditkarteninformation in den Internet-Bezahlsystemen. 

### (Distributed) Denial of Services (D)DoS

  - Überlastung von Infrastruktursystemen (bspw. Server, Rechner) durch einen Angriff, mit der Absicht, einen oder mehrere bereitgestellte Dienste „arbeitsunfähig“ zu machen.
  - Im Unterschied zu anderen Angriffen will der Angreifer beim DoS-Angriff normalerweise nicht in den Computer eindringen und benötigt deshalb keine Passwörter oder Ähnliches vom Zielrechner.

### Man-in-the-middle

  - Ziel:
      - Der Angreifer platziert sich zwischen zwei Kommunikationsparteien, um den Datenverkehr abzufangen oder zu manipulieren.
  - Methoden:
      - Abhören von unverschlüsseltem Datenverkehr
      - Entschlüsseln von verschlüsselten Daten
      - Spoofing von Netzwerken, um den Datenverkehr umzuleiten
      - Einschleusen von bösartigem Code oder Inhalten
  - Wo:
      - Kann in drahtlosen Netzwerken, öffentlichen Hotspots, unsicheren Websites oder internen Netzwerken auftreten.

## Architektur/Konzept der Angriffsmodelle: Time/Logic Bomb , Makroviren, ARP Spoofing, XML Injection

- Time/Logic Bomb:
    - Programme, die aufgrund eines bestimmten Triggers , z.B. Datum/Uhrzeit, Einlogvorgang eine Aktion auslösen (z.B: Manueller Diebstahl/Zerstörung von Daten/Programme oder Einspielung eines „schadhaften/böswilligen Computerprogrammes auf ein Datensystem)

## VIV Modell

**Verfügbarkeit:**
  - Falls Daten, aus welchen Gründen auch immer, nicht verfügbar sind, fährt die Produktionsanlage „blind“ unter Umständen „ungesteuert“ was zu gravierenden Problemen führen kann.
  - Verschiedene Gründe können zur „Unverfügbarkeit“ des Netzwerks/Daten führen, u.a.:
      - Ein Anwender- oder Softwarefehler führt zu einem Absturz des Systems
      - Das System ist von einem Computer Virus befallen#
      - Das System wurde „gehacked“ von einem internen oder außenstehenden Benutzer.
      - Stromausfall bzw. Backup Generator nicht verfügbar
      - Physikalischer Schaden (Feuer, Erdbeben) am Netzwerk/Computerraum

**Integrität (Daten/ Hardware und Software):**
  - Daten: Sicherstellung, dass die erfassten, gespeicherten und dargestellten Daten, den Daten des tatsächlichen reellen Systems entsprechen und korrekt wiedergegeben werden (e.g. Füllstand in einem Kessel, Temperatur eines Reaktors).
  - Hardware/Software: korrekten Hardware – Firmware- und Softwareversionen im Prozess befinden und nur autorisierte Änderungen oder Aktualisierungen (Updates) vorgenommen werden können

**Vertraulichkeit:**
  - Zugang zu den Daten nur für Menschen und Systeme, die dazu autorisiert sind, um diese Daten einzusehen, zu verändern, zu archivieren oder zu versenden. 

## Kommunikation: OPC , OPC UA , IPSec

### OPC

- standardisierte Software-Schnittstellen, die den Datenaustausch zwischen Anwendungen unterschiedlichster Hersteller in der Automatisierungstechnik ermöglicht (SCADA)
- benutzt die DCOM Technologie von Mircosoft (Windows Propitär)
- Was kann OPC classic:
    - (OPC-DA) Daten auslesen
    - (OPC-HDA) Historische Daten auslesen+
    - (OPC-A&E) Alarme & Events
- flache Datenhierarchie in der Datenübertragen

### OPC UA

- plattformunabhängige, sichere und erweiterbare Technologie
<img src="https://raw.githubusercontent.com/TimPaasche/PublicNotes/main/Security/image-1.png" width="600">

### IPSec (Internet Protocol Security)

  - Teil des IPv6-Protokolls
  - arbeitet direkt auf der Internetschicht (Internet layer) des TCP/IP-Protokollstapels.
  - Verschlüsselung und die Überprüfung der Authentizität von IP-Paketen

##  Router NAT/PAT , ARP Spoofing

### NAT(Network Address Translation)

- Adressen eines privaten Netzes über Tabellen öffentlich registrierten IP-Adressen zugeordnen (Eins-zu-Eins-Zuordnung)
- Die interne Struktur des Firmennetzwerkes bleibt nach außen verborgen.

### PAT (Port and Address Translation)

- alle Adressen eines privaten Netzwerkes auf eine einzelne öffentliche (dynamische) IP-Adress
- nicht nur die IP-Adressen, sondern auch Port-Nummern umgeschriebe
- Nachteil: Die Rechner im privaten Netzwerk können nicht aus dem Internet angewählt werden

## DMZ bzw. Automation Cells

**DMZ:**
- Definition: Eine DMZ ist ein isolierter Netzwerkbereich zwischen dem internen Netzwerk (LAN) und dem externen Netzwerk (normalerweise das Internet).
- Zweck: Die DMZ dient dazu, externe Dienste, wie Webserver, E-Mail-Server oder FTP-Server, zu hosten, ohne das interne Netzwerk direkt zu gefährden.
- Sicherheit: Die DMZ fungiert als Pufferzone, die das interne Netzwerk vor direkten Angriffen aus dem Internet schützt. Gleichzeitig erlaubt sie den sicheren Betrieb von öffentlich zugänglichen Diensten.