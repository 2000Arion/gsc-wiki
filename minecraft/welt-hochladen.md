---
title: Welt hochladen
description: Eine Anleitung, wie du eine bestehende Welt auf deinen Server hochladen kannst.
published: true
date: 2025-12-29T12:28:17.786Z
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

![marked-file-tab-d3d479fabff413cccb4977d185868769.png](/_assets/minecraft/marked-file-tab-d3d479fabff413cccb4977d185868769.png)

5. Lade die ZIP-Datei über den **Upload**-Button hoch.

![marked-upload-button-253f763f180594147408759bba61fb4c.png](/_assets/minecraft/marked-upload-button-253f763f180594147408759bba61fb4c.png)

6. Mache einen Rechtsklick auf die hochgeladene ZIP-Datei und kliche auf **Unarchive**.

7. Nachdem der Weltenordner auf dem Server entpackt wurde, kannst du die ZIP-Datei wieder löschen.

8. Falls der Name des Weltenordners nicht `world` ist, hast du zwei Möglichkeiten:
	- Entweder machst du einen Rechtsklick auf den Weltenordner und wählst **Rename** aus, um den Ordner zu `world` umzubenennen.
  - Oder du öffnest die `server.properties`-Datei und änderst `level-name` zu dem Namen des Weltenordners (vergiss nicht, zu speichern!):
  ```
  