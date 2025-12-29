---
title: Welt hochladen
description: Eine Anleitung, wie du eine bestehende Welt auf deinen Server hochladen kannst.
published: true
date: 2025-12-29T12:55:21.898Z
tags: upload, minecraft, worldfolder
editor: markdown
dateCreated: 2025-12-29T12:12:29.375Z
---

Falls du bereits eine Singleplayer-Welt oder eine Welt von einem anderen Server hast, die du auf deinem Server verwenden möchtest, kannst du sie ganz einfach hochladen. Auf dieser Seite wird dir Schritt für Schritt erklärt, wie du das tun kannst.

# Welt auf Vanilla- oder Fabric-Server hochladen

1. Öffne den Datei-Explorer und wechsle in das Verzeichnis deiner Minecraft-Installation auf deinem Computer. Standardmäßig ist das unter Windows `%appdata%/.minecraft`

2. Öffne den `saves`-Ordner und finde die Welt, die du auf den Server hochladen möchtest.

## Tabs {.tabset}

### Über das Panel hochladen

3. Da das Panel das Hochladen von ganzen Ordnern aktuell noch nicht unterstützt, musst du den **Weltenordner zuerst in eine ZIP-Datei komprimieren**.

4. Wechsle im Panel in den Tab **Files**.

![Der "Files"-Tab ist in der Navigation des Gameservercloud-Panels durch ein rotes Quadrat gekennzeichnet.](/_assets/minecraft/marked-file-tab-d3d479fabff413cccb4977d185868769.png =572x100)

5. Lade die ZIP-Datei über den **Upload**-Button hoch.

![Der "Upload"-Button befindet sich zwischen den Buttons "Create Directory" auf der linken Seite und "New File" auf der rechten Seite und ist durch ein rotes Quadrat gekennzeichnet.](/_assets/minecraft/marked-upload-button-253f763f180594147408759bba61fb4c.png =461x100)

6. Mache einen Rechtsklick auf die hochgeladene ZIP-Datei und kliche auf **Unarchive**.

7. Nachdem der Weltenordner auf dem Server entpackt wurde, kannst du die ZIP-Datei wieder löschen.

8. Falls der Name des Weltenordners nicht `world` ist, hast du zwei Möglichkeiten:
	- Entweder machst du einen Rechtsklick auf den Weltenordner und wählst **Rename** aus, um den Ordner zu `world` umzubenennen.
  	- Oder du öffnest die `server.properties`-Datei und änderst in der Zeile `level-name` den Namen des Weltenordners (vergiss nicht, zu speichern!):
  	```properties title="server.properties"
  	level-name=Hier Ordnername eintragen
  	```

9. Falls nötig, starte deinen Server neu.

### Über einen FTP-Client hochladen

3. Falls du noch keinen FTP-Client installiert hast, solltest du einen installieren. Wir empfehlen [WinSCP](https://winscp.net/eng/download.php). <span style="color: #858585">Weitere Informationen zu SFTP-Verbindungen findest du [hier](/user-interface/verbindung-mit-sftp-herstellen).</span>

4. Wechsle im Panel in den Tab **Settings** und klicke auf **Launch SFTP**. Falls dein Browser fragt, ob WinSCP automatisch geöffnet werden soll, kannst du dem zustimmen.

![marked-launch-sftp-button-9e45dd836f8a6c8beb738f677e2ca4cb.png](/_assets/minecraft/marked-launch-sftp-button-9e45dd836f8a6c8beb738f677e2ca4cb.png =720x400)

<h2 style="visibility: hidden;"></h2>

Jetzt sollte die neue Welt auf deinem Server vorhanden sein. Falls es Probleme gibt, versuche die Ordner `.cache` und `libraries` zu löschen und den Server anschließend neu zu starten, damit diese Ordner neu generiert werden.

Alternativ kannst du auch <a href="#" id="open-chat">unseren Support</a> um Hilfe bitten.

