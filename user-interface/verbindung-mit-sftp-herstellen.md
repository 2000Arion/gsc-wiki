---
title: Verbindung mit SFTP herstellen
description: Hier erfährst du, wie du dich mit SFTP auf deinen Server verbindest, um Dateien hochzuladen, herunterzuladen oder zu bearbeiten.
published: true
date: 2026-01-01T18:26:55.153Z
tags: filezilla, management, sftp, ssh-keys, upload, winscp
editor: markdown
dateCreated: 2025-02-02T13:35:02.091Z
---

# 📋 Voraussetzungen

- FTP-Client (z. B. [WinSCP](https://winscp.net "Klicke hier, um winscp.net zu öffnen"), [FileZilla](https://filezilla-project.org "Klicke hier, um filezilla-project.org zu öffnen"), etc.)
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

# 🔌 Schritt 2: Verbindung mit einem SFTP-Client herstellen

## Tabs {.tabset}

### ⚙️ Verbinden mit WinSCP

1. Öffne **WinSCP**.
2. Klicke auf **Neues Verbindungsziel**.
3. Wähle das Protokoll **SFTP** aus.
4. Gib die folgenden Informationen ein:
   - **Serveradresse:** Serveradresse (z.B. `example.com`)
   - **Portnummer:** `2022`
   - **Benutzername:** Der Benutzername, der im Panel angezeigt wird
   - **Passwort:** Dein Panel-Passwort
5. Klicke auf **Anmelden**.

![Anmeldemaske im WinSCP-Client](/_assets/user-interface/verbindung-mit-sftp-herstellen/winscp-anmeldung.png)

### ⚡ Verbinden im FileZilla

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

Beantworte die Fragen oder bestätige mit <kbd>Enter</kbd>, um die Standardantwort in den Klammern zu verwenden.

Anschließend wird dir angezeigt, wo das Schlüsselpaar gespeichert wurde.

## Schritt 2: Public Key im Panel hinterlegen

1. Rufe folgende Seite auf: <https://panel.arion2000.xyz/account/ssh>
2. Trage folgende Daten ein:
   - **SSH Key Name:** Wähle einen Namen deiner Wahl, um den SSH-Key in Zukunft eindeutig identifizieren zu können.
   - **Public Key:** Trage hier den Inhalt deiner _Public_ Key-Datei ein. Diese findest du standardmäßig in deinem Benutzerverzeichnis im `.ssh`-Ordner.
   > - Unter Windows kannst du im Explorer den Pfad `%userprofile%\.ssh` eingeben, um dorthin zu gelangen.
   > - Die Datei hat die Endung `.pub`.
   > - Falls Windows die Datei standardmäßig in einem Programm wie z.B. Microsoft 365 Publisher öffnet, mache einen Rechtsklick auf die Datei, wähle **Öffnen mit > Editor** aus und kopiere dann den kompletten Inhalt der Datei.
   <!-- {blockquote:.is-info} -->
3. Klicke auf **Save**.

## Schritt 3: SSH-Key bei der Anmeldung verwenden {.tabset}

### WinSCP

1. Gib die **Serveradresse**, die **Portnummer** und deinen **Benutzernamen** in WinSCP ein.
2. Klicke auf **Erweitert**.
3. Wähle aus der Liste auf der linken Seite unter SSH den Menüpunkt **Authentifizierung** aus.
4. Trage in das Textfeld **Datei mit privatem Schlüssel** den privaten Schlüssel ein.
> - Der Private Key befindet sich standardmäßig in der Datei ohne Dateiendung (z.B. `id_rsa`).
> - WinSCP muss die Datei, falls noch nicht geschehen, zuerst in eine **`.ppk`-Datei** konvertieren. Bestätige den Vorgang mit **OK**.
>
> ℹ️ Lasse das Feld für das Passwort leer, wenn du einen SSH-Key verwenden möchtest.
<!-- {blockquote:.is-info} -->
5. Klicke auf **OK**.
6. Verbinde dich mit **Anmelden**.

### FileZilla

1. Gehe zum Menü **Datei > Servermanager**.
2. Gib die **Serveradresse**, den **Port** und deinen **Benutzernamen** ein.
3. Ändere die **Verbindungsart** zu **Schlüsseldatei**.
4. Trage in das Textfeld **Schlüsseldatei** den privaten Schlüssel ein.
> Der Private Key befindet sich standardmäßig in der Datei ohne Dateiendung (z.B. `id_rsa`).
>
> ℹ️ Lasse das Feld für das Passwort leer, wenn du einen SSH-Key verwenden möchtest.
{.is-info}
5. Klicke auf **Verbinden**.

---

# 🛠️ Häufige Probleme und Lösungen

## ❌ Fehler: "Verbindung fehlgeschlagen"

**Lösung:** Überprüfe:
- Die Richtigkeit der Serveradresse und des Ports
- Die Richtigkeit deines Benutzernamen und Passworts
- Ob deine Firewall SFTP-Verbindungen zulässt
- Schaue auf unserer [Status-Seite](https://status.arion2000.xyz "Klicke hier, um die arion2000.xyz Statuspage zu öffnen") nach, ob es aktuelle Störungen gibt

## 🐧 Anmeldung unter Linux mithilfe des `sftp`-Commands

Stelle sicher, den Benutzernamen und die Serveradresse immer im Format `username.a1b2c3d4@example.com` anzugeben und nicht anders. Ein häufig auftretender Fehler ist die Separierung der Serveradresse und des Benutzernamens oder die Verwendung von Großbuchstaben. Beispielsweise sollte `example.com username.a1b2c3d4` oder `Username.A1B2C3D4@example.com` vermieden werden.

Vergiss nicht, den richtigen Port mithilfe von `-P 2022` anzugeben.

## ⚠️ Zertifikatswarnung

**Lösung:** Diese Warnung kommt in der Regel bei der ersten Verbindung mit einem neuen Server. Du kannst die Verbindung normalerweise trotzdem fortsetzen. Stelle sicher, dass du die richtige Serveradresse verwendest.

---

# 📚 Weitere Ressourcen

- [WinSCP-Dokumentation](https://winscp.net/eng/docs/start "Klicke hier, um https://winscp.net/eng/docs/start zu öffnen")
- [FileZilla-Dokumentation](https://wiki.filezilla-project.org/Documentation "Klicke hier, um https://wiki.filezilla-project.org/Documentation zu öffnen")