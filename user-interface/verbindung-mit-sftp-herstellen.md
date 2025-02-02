---
title: Verbindung mit SFTP herstellen
description: Hier erfährst du, wie du dich mit SFTP auf deinen Server verbindest, um Dateien hochzuladen, herunterzuladen oder zu bearbeiten.
published: false
date: 2025-02-02T13:53:34.770Z
tags: sftp, upload, management, winscp, filezilla
editor: markdown
dateCreated: 2025-02-02T13:35:02.091Z
---

# 📋 Voraussetzungen

- SFTP-Client (z. B. [WinSCP](https://winscp.net "Klicke hier, um winscp.net zu öffnen"), [FileZilla](https://filezilla-project.org "Klicke hier, um filezilla-project.org zu öffnen"), etc.)
- Server-Zugangsdaten aus dem Panel

---

# 🔍 Schritt 1: SFTP-Zugangsdaten im Panel abrufen

1. Melde dich im [Panel](https://panel.arion2000.xyz "Klicke hier, um das Panel zu öffnen") an.
2. Wähle den gewünschten Server aus.
3. Navigiere zum Tab **Settings**.
4. Kopiere die folgenden Informationen:
   - **Server Adress:** (z.B. `sftp://example.com:2022`)
   - **Username:** Dein spezifischer Benutzername (oft Server-bezogen, z.B. `username.a1b2c3d4`)
   - **Passwort:** Verwende das Passwort deines Panel-Kontos

> Falls dein Browser und Betriebssystem die Funktion unterstützen, kannst du auch direkt den **Launch SFTP**-Button verwenden, um die Sitzung in deinem Standard-SFTP-Programm zu starten.
{.is-success}

---

# 🔌 Schritt 2: Verbindung mit einem SFTP-Client herstellen {.tabset}

## ⚙️ Verbinden mit WinSCP

1. Öffne **WinSCP**.
2. Wähle das Protokoll **SFTP** aus.
3. Gib die folgenden Informationen ein:
   - **Serveradresse:** Serveradresse (z.B. `example.com`)
   - **Portnummer:** `2022`
   - **Benutzername:** Der Benutzername, der im Panel angezeigt wird
   - **Passwort:** Dein Panel-Passwort
4. Klicke auf **Anmelden**.

![Anmeldemaske im WinSCP-Client](/_assets/user-interface/verbindung-mit-sftp-herstellen/winscp-anmeldung.png)

## ⚡ Verbinden im FileZilla

1. Öffne **FileZilla**.
2. Gehe zum Menü **Datei > Servermanager**, klicke auf **Neuer Server** und gib diesem einen Namen deiner Wahl.
3. Trage folgende Daten ein:
   - **Protokoll:** SFTP - SSH File Transfer Protocol
   - **Server:** Serveradresse (z.B. `example.com`)
   - **Port:** `2022`
   - **Verbindungsart:** Normal
   - **Benutzername:** Der Benutzername, der im Panel angezeigt wird
   - **Passwort:** Dein Panel-Passwort
4. Klicke auf **Verbinden**.

![Anmeldemaske im FileZilla-Client](/_assets/user-interface/verbindung-mit-sftp-herstellen/filezilla-anmeldung.png)

# ✅ Schritt 3: Dateien verwalten

Nach erfolgreicher Verbindung kannst du:

- Dateien auf den Server hochladen
- Dateien vom Server herunterladen
- Dateien und Ordner verwalten

---

# 🔑 Extra: SSH-Keys statt Passwort verwenden

SSH-Keys sind eine sicherere Alternative zu Passwörten, mit denen man sich bei der Anmeldung am Server authentifizieren kann.

## Schritt 1: SSH-Keys erstellen

SSH-Keys sind genau genommen zwei Dateien auf dem eigenen Computer: eine Datei enthält einen öffentlichen Schlüssel und die andere einen privaten Schlüssel.

> Den **privaten Schlüssel** solltest du **niemals** mit anderen teilen!
{.is-warning}

Öffne das Terminal/die Konsole (unter Windows "Eingabeaufforderung") und gib folgenden Befehl ein, um ein neues SSH-Schlüsselpaar zu generieren:

```bash
ssh-keygen
```

---

# 🛠️ Häufige Probleme und Lösungen

## ❌ Fehler: "Verbindung fehlgeschlagen"

**Lösung:** Überprüfe:
- Die Richtigkeit des Hostnamens und Ports
- Ob deine Firewall SFTP-Verbindungen zulässt
- Schaue auf unserer [Status-Seite](https://status.arion2000.xyz "Klicke hier, um die arion2000.xyz Statuspage zu öffnen") nach, ob es aktuelle Störungen gibt

## ⚠️ Zertifikatswarnung

**Lösung:** Du kannst die Verbindung normalerweise trotzdem fortsetzen. Stelle sicher, dass du die richtige Serveradresse verwendest.

---

# 📚 Weitere Ressourcen

- [WinSCP-Dokumentation](https://winscp.net/eng/docs/start "Klicke hier, um https://winscp.net/eng/docs/start zu öffnen")
- [FileZilla-Dokumentation](https://wiki.filezilla-project.org/Documentation "Klicke hier, um https://wiki.filezilla-project.org/Documentation zu öffnen")