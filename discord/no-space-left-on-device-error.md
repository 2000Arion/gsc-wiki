---
title: [Python] Lösung von „No space left on device“-Fehlern
description: Python-Bots starten manchmal nicht, wenn zu viele Dependencies geladen werden müssen und der Host-Server nicht genug Speicheplatzr für den Container zur Verfügung stellt. Lerne hier, wie du mit diesem Problem umgehen kannst.
published: true
date: 2026-09-12T12:54:15.480Z
tags: troubleshooting, discord
editor: markdown
dateCreated: 2026-09-12T12:54:15.480Z
---

# Fehler beim Serverstart: "No space left on device" / ModuleNotFoundError

## Was du im Log siehst

Wenn dein Server nicht startet, kann es sein, dass du in der Konsole eine Fehlermeldung wie diese siehst:

```sh
OSError: [Errno 28] No space left on device
...
ModuleNotFoundError: No module named 'discord'
```

Keine Sorge: Das bedeutet nicht, dass dein zugewiesener Speicherplatz voll ist. Deine Disk-Auslastung im Panel kann dabei ganz normal aussehen, zum Beispiel nur wenige MiB belegt.

## Was hier eigentlich passiert

Beim Start deines Servers werden die in der `requirements.txt` definierten Python-Pakete automatisch heruntergeladen und installiert. Dafür wird intern ein kleiner, separat begrenzter temporärer Ordner genutzt, der unabhängig von deinem eigentlichen Server-Speicher ist. Wenn die zu installierenden Pakete zusammen mehr Platz brauchen, als dieser temporäre Ordner zulässt, bricht die Installation mit genau dieser Fehlermeldung ab. Da dadurch nicht alle benötigten Pakete installiert werden konnten, startet dein Bot anschließend nicht richtig und meldet ein fehlendes Modul (z. B. `discord`).

Du kannst hierfür nichts und kannst durch Löschen von Dateien im Panel auch nichts an diesem Problem ändern – die Ursache liegt an einer internen Systemeinstellung, die wir als Betreiber anpassen müssen.

## Was du tun kannst

Melde dich einfach bei uns per E-Mail an <gsc-support@arion2000.xyz> oder <a href="#" id="open-chat">nutze den Live-Chat</a>. Gib dabei auch deine Server-ID mit an *(zu finden auf der "Settings"-Seite)*, dann kümmern wir uns zeitnah darum und passen die entsprechende Einstellung an, damit dein Server wieder normal startet.
