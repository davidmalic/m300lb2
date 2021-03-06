M300 - LB2
======

Diese Repository behandelt die Umsetzung von der LB2.

## Einleitung
Diese Dokumentation wurde von David Malic im Rahmen des Moduls M300 (Plattformübergreifende Dienste in ein Netzwerk integrieren)
erarbeitet und zeigt alle Schritte auf, die es braucht um die LB2-Kriterien zu erfüllen.

## Inhaltsverzeichnis

* K1
  * VirtualBox
  * Vagrant
  * Visualstudio-Code
* K2
  * Persönlicher Wissenstand
  * Wichtige Lernschritte sind dokumentiert
* K3
  * Bestehenden Docker-Dontainer kombinieren
  * Bestehende Container als Backend, Desktop-App als Frontend einsetzen
  * Volumes zur persistenten Datenablage eingerichtet
  * Kennt die Docker spezifischen Befehle
  * Eingerichtete Umgebung ist dokumentiert (Umgebungs-Variablen, Netzwerkplan gezeichnet, Schichtenmodell, Sicherheitsaspekte)
  * Funktionsweise getestet inkl. Dokumentation der Testfälle
  * Projekt mit Git und Mark Down dokumentiert
* K4
  * Sicherheitsaspekte
  * Testfall
* K5
  * Vergleich Vorwissen - Wissenzuwachs
  * Reflexion
* K6
  * Kubernetes

___

K1
======

## Virtualbox

Nun widmen wir uns der Virtualisierung von Computersystemen. Für den Betrieb von solchen Maschinen bzw. Computern stehen zahlreiche Virtualisierungsanwendungen zur Verfügung. Eine davon ist VirtualBox. In diesem Kapitel richten wir eine einfache VM (Virtuelle Maschine) mit VirtualBox ein. Also ganz traditionell und wie sich im späteren Verlauf zeigt, auch eine sehr aufwendige Arbeit.                                                     
## Vagrant

Vagrant sollte uns zeigen, dass das Bereitstellen virtueller Systeme in der konventionellen Art lange dauert und umständlich sein kann.
Abhilfe bietet hier Vagrant. Vagrant ist eine freie Ruby-Anwendung zur Erstellung und Verwaltung virtueller Maschinen und ermöglicht einfache Softwareverteilung.

## Visual Studio Code

Bis hierhin haben wir soweit alles aufgesetzt und installiert. Nun möchten wir für effizienteres Arbeiten eine "Entwicklungsumgebung" aufbauen, die es uns ermöglicht, alle lokalen Repositories an einem Ort zu verwalten und die dazugehörigen Dateien zu bearbeiten. Die Lösung hierzu ist: Visual Studio Code 
Dieser freie Quelltext-Editor von Microsoft, ermöglicht uns, unsere Workflows besser zu gestalten und damit die Arbeit um einiges leichter zu machen.

K2
======

## Persönlicher Wissenstand

- Docker / Container:
  Ich habe zwar schon von Docker und Containern gehört mich aber leider nie mit diesem Thema befasst.

- Microservices: 
  Von Microservices habe ich ebenfalls schon öfters gehört und kenne es nur ein bisschen aus der Theorie. In der Praxis habe ich es nie angewandt und kenne mich deswegen auch nicht sehr gut aus.



## Kennt die Docker spezifischen Befehle

| Befehl       | Beschreibung                                       |
| ------------ | -------------------------------------------------- |
| docker run   | Führt ein Befehl in einem neuen Container aus      |
| docker start | Startet einen oder mehrere gestoppte Container     |
| docker stop  | Stoppt einen oder mehrere laufende ontainer        |
| docker build | Erstellt ein Image aus einem Docker-File           |
| docker pull  | Ladet ein Image aus der Registry                   |
| docker push  | Ladet ein Image in die Registry hoch               |
| docker exec  | Führ einen Befehl in einem laufenden Container aus |
| docker ps | Überblick über die aktuellen Container, wie z.B. Namen, IDs und Status
| docker images | Liste lokaler Images aus, wobei Informationen zu Repository-Namen, Tag-Namen und Grösse enthalten sind
| docker rm | Entfernt einen oder mehrere Container. Gibt die Namen oder IDs erfolgreich gelöschter Container zurück
| docker rmi | Löscht das oder die angegebenen Images. Diese werden durch ihre ID oder Repository- und Tag-Namen spezifiziert
| docker logs | Gibt die "Logs" für einen Container aus. Dabei handelt es sich einfach um alles, was innerhalb des Containers nach STDERR oder STDOUT geschrieben wurde.



K4
======

## Sicherheitsaspekte

-   Nur der Port 80 ist freigegeben
-   Container laufen auf einem sicheren PC.
-   Die verwendeten Images definieren einen Benutzer und laufen nicht direkt als root

## Testfall

| Testfall                                                                                                                               | Resultat                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Vom Client (192.168.55.1) auf localhost:8080 zugreifen                                                                          | Funktioniert. Die Homepage des Webservers wird angezeigt                                                               |


K5
======

## Vergleich Vorwissen / Wissenszuwachs

Mein Wissen vor dem Projekt bez. Docker etc. war sehr beschränkt. Ich habe von Docker nur ab und zu gehört sonst auch nicht mehr. Durch dieses Projekt konnte ich lernen wie man Docker richtig anwendet und wie wichtig es ist. Generell habe ich mein Wissen im Docker und Container Bereich sehr erweitern können.

## Reflexion

Dieses Projekt war sehr lehrreich. Ich hatte gegen den Schluss ein bisschen Zeitdruck da ich die Zeit nicht optimal geplant habe. Mit dem Endresultat bin ich aber trotzdem zufrieden. Ich habe auch gemerkt wie wichtig Docker ist und das es bestimmt in Zukunft noch viel wichter sein wird. 


K6
======

## Kubernetes 

Kubernetes fasst Container-Images, ihre Konfiguration und die Anzahl der benötigten Instanzen in Deployments zusammen, so der Sprachgebrauch des Orchestrierungssystems. Die Parameter eines Deployments überwacht Kubernetes selbsttätig. Das Tool sorgt dafür, dass die gewünschte Anzahl von Containern jederzeit läuft. Änderungen an der Software oder der Konfiguration verteilt Kubernetes mit einem Rollout. Dieser Prozess lässt sich pausieren, fortsetzen und rückgängig machen (Rollback).

Optimierung der Nutzung der Computer-Ressourcen
Kubernetes setzt die Container eines Deployments selbständig dort ein, wo entsprechende Ressourcen frei sind. Der Anwender kann Mindest- und Höchstwerte der Ressourcennutzung (Rechenzeit, Speicherplatz) für die Container festlegen, um dem Orchestrierungstool einen Rahmen vorzugeben.

Zahlreiche Optionen für dauerhafte Datenspeicherung (Persistent Storage)

Container sind zustandslos. Für die dauerhafte Speicherung von Konfigurations- und Nutzerdaten bietet Kubernetes Schnittstellen zu zahlreichen Diensten wie zum Beispiel EBS von Amazon Web Services oder Google Cloud Platform.

