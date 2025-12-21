---
title: Plugins installieren
description: Hier erfährst du, wie du Plugins auf deinem Paper, Spigot, Purpur oder Bukkit Server installieren kannst.
published: true
date: 2025-12-21T18:22:26.836Z
tags: upload, troubleshooting, minecraft, plugins
editor: markdown
dateCreated: 2025-12-20T11:34:53.930Z
---

# 🔍 Wo finde ich Plugins, die ich installieren kann?

Du kannst beliebige Plugins installieren, die du möchtest. Wichtig ist nur, dass das Plugin **als `.jar`-Datei vorliegt** und **mit deiner Minecraft-Server-Software (z. B. Paper, Spigot, Purpur oder Bukkit) kompatibel ist**.

Wenn du nach passenden Plugins suchst, empfehlen wir dir, auf **[Modrinth](https://modrinth.com/discover/plugins)**, **[PaperMC Hangar](https://hangar.papermc.io/)**, [SpigotMC](https://www.spigotmc.org/resources/) oder [BukkitDev](https://dev.bukkit.org/bukkit-plugins) zu schauen.

---

# ⚙️ Plugins auf dem Gameserver installieren

## 🧩 Schritt 1: Plugin herunterladen

Lade die `.jar`-Datei des Plugins auf deinen Computer herunter. Achte darauf, ob der Autor des Plugins angibt, dass weitere Plugins als Abhängigkeit benötigt werden und zusätzlich installiert werden müssen.

## 📁 Schritt 2: Plugins-Ordner öffnen

1. Melde dich im [Panel](https://panel.arion2000.xyz) an.  
2. Wähle den gewünschten Server aus.  
3. Navigiere zum Tab **Files**.  
4. Klicke auf den Ordner **`plugins`**.  
5. Klicke oben rechts auf den blauen Button **Upload** und lade deine Plugin-Datei(en) hoch.  
6. Wechsle anschließend zum Tab **Console** und starte den Server neu.

> 💡 **Tipp:** Falls du Plugins lieber mit einem SFTP-Client hochladen möchtest, kannst du das genauso machen. [Weitere Informationen zu SFTP findest du hier.](https://wiki.arion2000.xyz/de/user-interface/verbindung-mit-sftp-herstellen)
{.is-info}

> **Wichtig:** Einige Plugins erstellen nach dem Starten des Servers eine Konfigurationsdatei, in welcher Einstellungen für das Plugin geändert werden können/müssen. Informiere dich in so einem Fall am besten über Tutorials oder die Dokumentation des Mod-Autors darüber, welche Einstellungen was bewirken.
{.is-warning}

---

# 🧰 Was tun bei Fehlern?

Keine Panik – Fehler bei der Verwendung von Plugins kommen häufig vor und lassen sich in den meisten Fällen schnell beheben.

## 🔎 Schritt 1: Die Konsole prüfen

Wenn dein Server nicht startet oder abstürzt, findest du den Grund fast immer in der **Konsole**.  
Achte auf Zeilen mit Schlüsselwörtern wie:

- `Error`, `Exception` oder `Caused by`  
- `Could not load plugin`  
- `Plugin failed to load`  
- `NoClassDefFoundError`  
- `Missing dependency`  
- `Plugin version mismatch`

> Mit <kbd>STRG</kbd> + <kbd>F</kbd> kannst du in der Konsole suchen.
{.is-info}

Solche Zeilen erscheinen meist im Zusammenhang mit dem betreffenden Plugin und verraten, wo das Problem liegt.

### Beispielhafte Fehlermeldung bei **Paper/Spigot/Purpur**:

```
[ERROR]: Could not load 'plugins/ExamplePlugin.jar' in folder 'plugins'
org.bukkit.plugin.InvalidPluginException: java.lang.UnsupportedClassVersionError
```

### Beispielhafte Fehlermeldung bei fehlender Abhängigkeit:

```
[ERROR]: Plugin 'ExamplePlugin' is missing dependency 'Vault'
```


## 🧾 Schritt 2: Häufige Ursachen und Lösungen

| Problemtyp                     | Beschreibung                                                                                                                                  | Lösung                                                                                     |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| ❌ **Falsche Server-Software** | Das Plugin wurde für eine andere Server-Software geschrieben oder es handelt sich nicht um ein Plugin, sondern um eine Mod (z.B. für Fabric). | Lade eine Version des Plugins herunter, die zu deiner Server-Software passt.               |
| 🔄 **Fehlende Abhängigkeit**   | Ein weiteres Plugin (z. B. Vault, ProtocolLib) wird benötigt.                                                                                  | Lies die Plugin-Beschreibung und installiere alle angegebenen Dependencies.               |
| ⚔️ **Plugin-Konflikt**         | Zwei Plugins greifen auf dieselbe Funktionalität zu oder verändern denselben Codebereich.                                                     | Entferne testweise eines der Plugins, um zu prüfen, ob das Problem behoben wird.           |
| ⚙️ **Fehlerhafte .jar-Datei**  | Upload war unvollständig oder Datei wurde beschädigt.                                                                      | Lade das Plugin erneut herunter und ersetze die alte `.jar`-Datei. Achte auf eine stabile Internetverbindung. |

## 🔁 Schritt 3: Nach der Korrektur

1. Entferne oder ersetze das problematische Plugin.  
2. Starte den Server neu und prüfe die Konsole erneut.  
3. Wiederhole den Vorgang, bis keine Fehler mehr auftauchen.  
4. Optional: Wenn du viele Plugins nutzt, füge sie **schrittweise** hinzu, um Konflikte schneller zu erkennen.

---

# 💬 Noch Fragen?

Wenn du trotz allem nicht weiterkommst, kannst du den **Fehlertext aus der Konsole** (insbesondere die letzten 20–30 Zeilen) kopieren und unserem <a href="#" id="open-chat">Support eine Nachricht schreiben</a>.  
Wir helfen dir gerne bei der Lösung des Problems!