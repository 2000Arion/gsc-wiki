---
title: Mods installieren
description: Hier erfährst du, wie du Mods auf deinem Fabric oder Forge Server installieren kannst.
published: true
date: 2026-01-30T20:20:20.308Z
tags: upload, troubleshooting, minecraft, mods
editor: markdown
dateCreated: 2025-12-20T11:13:39.999Z
---

# 🔍 Wo finde ich Mods, die ich installieren kann?

Du kannst alle Mods installieren, die du möchtest. Wichtig ist nur, dass die Mod **als `.jar`-Datei vorliegt** und **mit deiner Minecraft-Version kompatibel ist**.  

Wenn du nach passenden Mods suchst, schau doch mal auf **[Modrinth](https://modrinth.com/discover/mods)** oder **[CurseForge](https://www.curseforge.com/minecraft)** vorbei.

---

# ⚙️ Mods auf dem Gameserver installieren

## 🧩 Schritt 1: Mod herunterladen

Lade die `.jar`-Datei der Mod auf deinen Computer herunter. Achte ggf. darauf, ob der Autor der Mod angegeben hat, dass andere Mods als Abhängigkeit benötigt werden und zusätzlich installiert werden müssen.

## 📁 Schritt 2: Mods-Ordner öffnen

1. Melde dich im [Panel](https://panel.arion2000.xyz) an.  
2. Wähle den gewünschten Server aus.  
3. Navigiere zum Tab **Files**.  
4. Klicke auf den Ordner **`mods`**.  
5. Klicke oben rechts auf den blauen Button **Upload** und lade deine Mod-Datei(en) hoch.  
6. Wechsle anschließend zum Tab **Console** und starte den Server neu.

> 💡 **Tipp:** Falls du Mods lieber mit einem SFTP-Client hochladen möchtest, kannst du das genauso machen. [Weitere Informationen zu SFTP findest du hier.](https://wiki.arion2000.xyz/de/user-interface/verbindung-mit-sftp-herstellen)
{.is-info}

> **Wichtig:** Einige Mods erstellen nach dem Starten des Servers eine Konfigurationsdatei (bei Fabric meistens im `config`-Ordner), wo Einstellungen für die Mod angepasst werden können/müssen. Informiere dich in so einem Fall am besten über Tutorials oder die Dokumentation des Mod-Autors darüber, welche Einstellungen was bewirken.
{.is-warning}

---

# 🧰 Was tun bei Fehlern?

Keine Panik – Fehler bei der Verwendung von Mods kommen häufig vor und lassen sich in den meisten Fällen schnell beheben.

## 🔎 Schritt 1: Die Konsole prüfen

Wenn dein Server nicht startet oder abstürzt, findest du den Grund fast immer in der **Konsole**.  
Achte auf Zeilen mit Schlüsselwörtern wie:

- `Error`, `Exception` oder `Caused by`  
- `Mod resolution failed` (Fabric) oder `Found mismatching mod versions`  
- `Missing Mod: xyz` oder `NoClassDefFoundError`  
- `Mixin apply failed` (besonders bei Fabric)  
- `Unable to load registry` oder `Mod has failed class loading` (Forge)

>  Mit <kbd>STRG</kbd> + <kbd>F</kbd> kannst du in der Konsole suchen.
{.is-info}


Solche Zeilen erscheinen meist im Zusammenhang mit der betreffenden Mod und verraten, wo das Problem liegt.

### Beispielhafte Fehlermeldung bei **Fabric**:

```
[main/WARN]: Incompatible mod set! Some mods are not supported on this Minecraft version:
- examplemod requires Minecraft 1.21.1
```

### Beispielhafte Fehlermeldung bei **Forge**:

```
net.minecraftforge.fml.loading.moddiscovery.ModResolutionException:
Mod ‘examplemod’ requires version 1.20.1 but server is running 1.19.4
```

## 🧾 Schritt 2: Häufige Ursachen und Lösungen

| Problemtyp                                    | Beschreibung                                                                           | Lösung                                                                                                         |
|-----------------------------------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| ❌ **Falsche Minecraft-Version**              | Die Mod wurde für eine andere Version entwickelt.                                      | Lade eine Version der Mod herunter, die zu deiner Minecraft-Version passt oder ändere deine Minecraft-Version. |
| 🔄 **Fehlende Abhängigkeit**                  | Eine zweite Mod wird benötigt (z. B. Fabric API, Architectury, GeckoLib).              | Lies die Modbeschreibung auf Modrinth/CurseForge und installiere alle angegebenen Dependencies.                 |
| ⚔️ **Mod-Konflikt**                           | Zwei Mods verändern denselben Codebereich oder Hook.                                   | Entferne testweise eine der Mods, um zu untersuchen, ob es anschließend funktioniert.                          |
| 🧪 **Falscher Modloader (z.B. Fabric/Forge)** | Zum Beispiel wurde eine Fabric-Mod auf einem Forge-Server installiert oder umgekehrt.  | Verwende die zur Server-Software passende Mod-Variante.                                                        |
| ⚙️ **Fehlerhafte .jar-Datei**                 | Upload war unvollständig oder Datei wurde beschädigt.                                  | Lade die Mod erneut herunter und ersetze die alte `.jar`-Datei. Achte auf eine stabile Internetverbindung.     |

## 🔁 Schritt 3: Nach der Korrektur

1. Entferne oder ersetze die problematische Mod.  
2. Starte den Server neu und prüfe die Konsole erneut.  
3. Wiederhole den Vorgang, bis keine Fehler mehr auftauchen.  
4. Optional: Wenn du viele Mods nutzt, füge sie **schrittweise** hinzu, um Konflikte schneller zu erkennen.

---

# 💬 Noch Fragen?

Wenn du trotz allem nicht weiterkommst, kannst du den **Fehlertext aus der Konsole** (insbesondere die letzten 20–30 Zeilen) kopieren und unserem <a href="#" id="open-chat">Support eine Nachricht schreiben</a>.  
Wir helfen dir gerne bei der Lösung des Problems!