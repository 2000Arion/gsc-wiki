---
title: Welt hochladen
description: Eine Anleitung, wie du eine bestehende Welt auf deinen Server hochladen kannst.
published: true
date: 2026-01-30T20:20:14.479Z
tags: 
editor: markdown
dateCreated: 2025-12-29T12:12:29.375Z
---

Falls du bereits eine Singleplayer-Welt oder eine Welt von einem anderen Server hast, die du auf deinem eigenen Server verwenden möchtest, kannst du sie ganz einfach hochladen. Auf dieser Seite wird dir Schritt für Schritt erklärt, wie du dabei vorgehst.

# 🌍 Welt auf Vanilla- oder Fabric-Server hochladen

1. Öffne den Datei-Explorer und wechsle in das Verzeichnis deiner Minecraft-Installation auf deinem Computer. Standardmäßig ist dies unter Windows `%appdata%/.minecraft`.

2. Öffne den Ordner `saves` und suche die Welt heraus, die du auf den Server hochladen möchtest.

##### Tabs {.tabset}

###### 🖥️ Über das Panel hochladen

3. Da das Panel derzeit noch kein Hochladen kompletter Ordner unterstützt, musst du den **Weltenordner zunächst in eine ZIP-Datei komprimieren**.

4. Wechsle im Panel in den Tab **Files**.

![Im Bild ist der „Files“-Tab in der Navigation des Gameservercloud-Panels durch ein rotes Quadrat markiert.](/_assets/minecraft/marked-file-tab-d3d479fabff413cccb4977d185868769.png =572x100)

5. Lade die ZIP-Datei über den **Upload**-Button hoch.

![Der „Upload“-Button befindet sich zwischen den Buttons „Create Directory“ und „New File“ und ist im Bild durch ein rotes Quadrat gekennzeichnet.](/_assets/minecraft/marked-upload-button-253f763f180594147408759bba61fb4c.png =461x100)

6. Mache einen Rechtsklick auf die hochgeladene ZIP-Datei und klicke auf **Unarchive**.

7. Nachdem der Weltenordner auf dem Server entpackt wurde, kannst du die ZIP-Datei wieder löschen.

8. Falls der Name des Weltenordners **nicht** `world` lautet, hast du zwei Möglichkeiten:
	- Mache einen Rechtsklick auf den Weltenordner und wähle **Rename** aus, um den Ordner in `world` umzubenennen.
  	- Oder öffne die Datei `server.properties` und ändere in der Zeile `level-name` den Namen des Weltenordners (vergiss nicht zu speichern!):
  	```properties
  	level-name=Hier Ordnername eintragen
  	```

9. Falls nötig, starte deinen Server neu.

###### 🔐 Über einen FTP-Client hochladen

3. Falls du noch keinen FTP-Client installiert hast, solltest du zunächst einen installieren. Wir empfehlen [WinSCP](https://winscp.net/eng/download.php). <span style="color: #858585;">Weitere Informationen zu SFTP-Verbindungen findest du [hier](/user-interface/verbindung-mit-sftp-herstellen).</span>

4. Wechsle im Panel in den Tab **Settings** und klicke auf **Launch SFTP**. Falls dein Browser fragt, ob WinSCP automatisch geöffnet werden soll, kannst du dies bestätigen.

![Der „Launch SFTP“-Button ist in der unteren rechten Ecke des Bildes durch ein rotes Quadrat markiert.](/_assets/minecraft/marked-launch-sftp-button-9e45dd836f8a6c8beb738f677e2ca4cb.png =720x400)

5. WinSCP fragt dich nach einem Passwort. Dieses ist identisch mit dem Passwort, das du für die Anmeldung im Panel verwendest.

6. Sobald die Verbindung hergestellt ist, ziehe den Weltenordner einfach in das rechte Fenster von WinSCP. Der Ordner wird anschließend hochgeladen.

7. Falls der Name des Weltenordners **nicht** `world` lautet, hast du zwei Möglichkeiten:
	- Benenne den Ordner per Rechtsklick und **Umbenennen** in `world` um.
  	- Oder passe den Eintrag `level-name` in der Datei `server.properties` entsprechend an (nicht vergessen zu speichern!):
  	```properties
  	level-name=Hier Ordnername eintragen
  	```

8. Falls nötig, starte den Server neu.

<h5 style="visibility: hidden;"></h5>

✅ Jetzt sollte die neue Welt auf deinem Server verfügbar sein.
Falls es dennoch Probleme gibt, versuche, die Ordner `.cache` und `libraries` zu löschen und den Server anschließend neu zu starten, damit diese automatisch neu erstellt werden.

Alternativ kannst du dich jederzeit an <a href="#" id="open-chat">unseren Support</a> wenden.

# 📦 Welt auf Paper- oder Purpur-Server hochladen

1. Öffne den Datei-Explorer und wechsle in das Verzeichnis deiner Minecraft-Installation auf deinem Computer. Standardmäßig ist dies unter Windows `%appdata%/.minecraft`.

2. Öffne den Ordner `saves` und suche die Welt heraus, die du auf den Server hochladen möchtest.

3. Paper und Purpur verwenden eine etwas andere Ordnerstruktur als Vanilla-Minecraft. Daher musst du zusätzlich zum ursprünglichen Weltenordner zwei weitere Ordner anlegen:

| Version        | Overworld | Nether                | End                   |
|----------------|-----------|-----------------------|-----------------------|
| Vanilla        | `/world`  | `/world/DIM-1`        | `/world/DIM1`         |
| Paper & Purpur | `/world`  | `/world_nether/DIM-1` | `/world_the_end/DIM1` |

- Erstelle die Ordner `world_nether` und `world_the_end`.
- Verschiebe anschließend den Unterordner `DIM-1` aus dem ursprünglichen Weltenordner in `world_nether` sowie den Unterordner `DIM1` in `world_the_end`.

##### Tabs {.tabset}

###### 🖥️ Über das Panel hochladen

4. Da das Panel aktuell noch kein Hochladen kompletter Ordner unterstützt, musst du den **Weltenordner zuerst in eine ZIP-Datei komprimieren**.

5. Wechsle im Panel in den Tab **Files**.

![Im Bild ist der „Files“-Tab in der Navigation des Gameservercloud-Panels durch ein rotes Quadrat markiert.](/_assets/minecraft/marked-file-tab-d3d479fabff413cccb4977d185868769.png =572x100)

6. Lade die ZIP-Datei über den **Upload**-Button hoch.

![Der „Upload“-Button befindet sich zwischen den Buttons „Create Directory“ und „New File“ und ist im Bild durch ein rotes Quadrat gekennzeichnet.](/_assets/minecraft/marked-upload-button-253f763f180594147408759bba61fb4c.png =461x100)

7. Mache einen Rechtsklick auf die hochgeladene ZIP-Datei und klicke auf **Unarchive**.

8. Nachdem der Weltenordner entpackt wurde, kannst du die ZIP-Datei wieder löschen.

9. Falls der Name des Weltenordners **nicht** `world` lautet, hast du zwei Möglichkeiten:
	- Mache einen Rechtsklick auf den Weltenordner und wähle **Rename** aus, um den Ordner in `world` umzubenennen.
  	- Oder öffne die Datei `server.properties` und ändere in der Zeile `level-name` den Namen des Weltenordners (vergiss nicht zu speichern!):
  	```properties
  	level-name=Hier Ordnername eintragen
  	```

10. Falls nötig, starte deinen Server neu.

###### 🔐 Über einen FTP-Client hochladen

4. Falls du noch keinen FTP-Client installiert hast, solltest du zunächst einen installieren. Wir empfehlen [WinSCP](https://winscp.net/eng/download.php). <span style="color: #858585;">Weitere Informationen zu SFTP-Verbindungen findest du [hier](/user-interface/verbindung-mit-sftp-herstellen).</span>

5. Wechsle im Panel in den Tab **Settings** und klicke auf **Launch SFTP**. Falls dein Browser fragt, ob WinSCP automatisch geöffnet werden soll, kannst du dies bestätigen.

![Der „Launch SFTP“-Button ist in der unteren rechten Ecke des Bildes durch ein rotes Quadrat markiert.](/_assets/minecraft/marked-launch-sftp-button-9e45dd836f8a6c8beb738f677e2ca4cb.png =720x400)

6. WinSCP fragt dich nach einem Passwort. Dieses ist identisch mit dem Passwort, das du für die Anmeldung im Panel verwendest.

7. Sobald die Verbindung hergestellt ist, ziehe den Weltenordner einfach in das rechte Fenster von WinSCP. Der Ordner wird anschließend hochgeladen.

8. Falls der Name des Weltenordners **nicht** `world` lautet, hast du zwei Möglichkeiten:
	- Benenne den Ordner per Rechtsklick und **Umbenennen** in `world` um.
  	- Oder passe den Eintrag `level-name` in der Datei `server.properties` entsprechend an (nicht vergessen zu speichern!):
  	```properties
  	level-name=Hier Ordnername eintragen
  	```

9. Falls nötig, starte deinen Server neu.

<h5 style="visibility: hidden;"></h5>

✅ Jetzt sollte die neue Welt auf deinem Server verfügbar sein.
Falls es dennoch Probleme gibt, versuche, die Ordner `.cache` und `libraries` zu löschen und den Server anschließend neu zu starten, damit diese automatisch neu erstellt werden.

Alternativ kannst du dich jederzeit an <a href="#" id="open-chat">unseren Support</a> wenden.