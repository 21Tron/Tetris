# TRON GAMES – Tetris

![Version](https://img.shields.io/badge/version-1.0-22d3ee)
![HTML5](https://img.shields.io/badge/HTML5-Canvas-fb923c)
![Dependencies](https://img.shields.io/badge/dependencies-keine-34d399)
![Plattform](https://img.shields.io/badge/Desktop%20%2B%20Mobil-a78bfa)

Ein Tetris im Neon-Look, das komplett in **einer einzigen HTML-Datei** steckt. Kein Build, kein Framework: Datei öffnen und spielen. Mit Manifest, Icons und Service Worker lässt es sich zusätzlich als Web-App installieren. Es läuft am Desktop mit der Tastatur und am Handy mit Touch-Steuerung.

<!-- Screenshot einfügen: docs/screenshot.png
![Screenshot](docs/screenshot.png)
-->

**Live-Demo:** `https://<dein-benutzername>.github.io/<dein-repo>/` (nach dem Aktivieren von GitHub Pages, siehe unten)

---

## Funktionen

**Spielmechanik nach dem modernen Standard**

- Spielfeld 10 × 20, Steine aus dem **7er-Beutel** (jeder Stein kommt in jeder Runde genau einmal)
- **SRS-Drehung** mit Wall-Kicks, Drehen in beide Richtungen
- **Hold**, **Schattenstein** (Ghost) und Vorschau der nächsten drei Steine
- **Lock-Delay** von 0,5 Sekunden mit bis zu 15 Resets, damit Steine auch am Boden noch verschoben werden können
- **T-Spins**, **Kombos**, **Back-to-Back**-Bonus und **Perfect Clear**
- Level steigt alle 10 Linien, die Fallgeschwindigkeit wächst mit jedem Level

**Bedienung**

- Tastatur mit Auto-Repeat (DAS/ARR) für flüssiges Verschieben
- Touch-Buttons und Wischgesten für das Handy
- Die Buttons fühlen sich wie echte Tasten an: sie sinken beim Drücken ein, vibrieren kurz (Android) und machen einen leisen Klick
- Präzises Platzieren: ein kurzes Antippen von ↓ bewegt den Stein genau eine Reihe, erst längeres Halten beschleunigt den Fall

**Optik und Sound**

- Neon-Look mit Glas-Panels, Partikeln, Zeilen-Animation, Bildschirmwackeln und Popups wie „TETRIS!“ oder „T-SPIN DOUBLE“
- Die Farbwelt wechselt mit jedem Level
- Der Rand des Spielfelds pulsiert rot, wenn der Turm gefährlich hoch wird
- Synthesizer-Musik und Soundeffekte mit der Web Audio API, komplett ohne Audiodateien
- Musik und Effekte lassen sich getrennt stummschalten
- Vibration bei Linien und Game Over (auf unterstützten Handys)
- Respektiert die Systemeinstellung „Bewegung reduzieren“ (kein Wackeln)

**Sprachen**

- Oben rechts auf dem Titelbildschirm wechseln die Buttons **DE** und **EN** zwischen Deutsch und Englisch. Die Wahl wird gespeichert, beim ersten Start richtet sie sich nach der Browsersprache

**Als Web-App aufs Handy**

- Oben links auf dem Titelbildschirm sitzt der Button **Teilen / Installieren**. Er kopiert den Link in die Zwischenablage und öffnet eine Schritt-für-Schritt-Anleitung für **iPhone** und **Android**
- Eigenes **App-Symbol**, Web-App-Manifest und Service Worker: nach dem ersten Laden läuft das Spiel auch **offline**
- Gestartet vom Home-Bildschirm läuft das Spiel im Vollbild ohne Browserleiste, der Button wird dann ausgeblendet

**Rangliste**

- Alle gespielten Runden werden lokal gespeichert und nach Punkten sortiert angezeigt (Level, Linien, Datum und Uhrzeit)
- Die letzte Runde ist hervorgehoben, auf dem Game-Over-Bildschirm steht dein Platz
- Die Liste lässt sich mit einer Sicherheitsabfrage leeren

---

## Spielen

### Lokal

1. ZIP entpacken
2. `index.html` im Browser öffnen (Doppelklick genügt). Installation und Offline-Betrieb brauchen dagegen eine Webadresse, siehe unten

### Mit GitHub Pages veröffentlichen

1. Den **Inhalt** der entpackten ZIP (nicht den Ordner selbst) in ein neues GitHub-Repository hochladen: **Add file → Upload files**
2. Auf GitHub: **Settings → Pages**
3. Unter **Build and deployment** die Quelle **Deploy from a branch** wählen, den Branch `main` und den Ordner `/ (root)`
4. Speichern. Nach kurzer Zeit ist das Spiel unter `https://<benutzername>.github.io/<repo>/` erreichbar

### Als Web-App auf dem Handy speichern

Im Spiel auf **Teilen / Installieren** tippen (oben links auf dem Titelbildschirm). Der Link wird kopiert und die Anleitung erscheint. Von Hand geht es so:

**iPhone (Safari)**

1. Die Seite in Safari öffnen
2. Unten auf **Teilen** tippen (Quadrat mit Pfeil nach oben)
3. Nach unten scrollen und **Zum Home-Bildschirm** wählen
4. Oben rechts auf **Hinzufügen** tippen

**Android (Chrome)**

1. Die Seite in Chrome öffnen
2. Oben rechts das Menü **⋮** antippen
3. **App installieren** oder **Zum Startbildschirm hinzufügen** wählen
4. Bestätigen

Die Seite muss dafür unter ihrer eigenen Adresse laufen, zum Beispiel über GitHub Pages (HTTPS). Eine lokal geöffnete Datei lässt sich nicht als App speichern.

---

## Steuerung

### Tastatur

| Taste | Aktion |
| --- | --- |
| `←` `→` oder `A` `D` | Stein bewegen (gedrückt halten wiederholt) |
| `↓` oder `S` | Eine Reihe nach unten, gedrückt halten fällt schneller |
| `↑`, `X` oder `W` | Im Uhrzeigersinn drehen |
| `Z` oder `Strg` | Gegen den Uhrzeigersinn drehen |
| `Leertaste` | Hard Drop (sofort fallen lassen) |
| `C` oder `Shift` | Stein halten (Hold) |
| `P` oder `Esc` | Pause |
| `Enter` | Spiel starten (im Menü und nach Game Over) |

### Touch

| Geste / Button | Aktion |
| --- | --- |
| Tippen auf das Spielfeld | Drehen |
| Horizontal wischen | Stein bewegen |
| Langsam nach unten ziehen | Stein folgt dem Finger Reihe für Reihe |
| Schnell nach unten wischen | Hard Drop |
| Schnell nach oben wischen | Hold |
| Buttons unter dem Spielfeld | Hold, Drehen, Drop, ◀ ▼ ▶ |

Auf Geräten mit Maus und Tastatur werden die Touch-Buttons ausgeblendet.

---

## Punktesystem

Alle Linien-Punkte werden mit dem aktuellen **Level** multipliziert.

| Aktion | Punkte |
| --- | --- |
| 1 Linie | 100 |
| 2 Linien | 300 |
| 3 Linien | 500 |
| 4 Linien (Tetris) | 800 |
| T-Spin ohne Linie | 400 |
| T-Spin mit 1 / 2 / 3 Linien | 800 / 1200 / 1600 |
| Back-to-Back (Tetris oder T-Spin direkt nach dem vorherigen) | × 1,5 |
| Kombo | + 50 × Kombo-Zähler |
| Perfect Clear (Feld komplett leer) | + 1000 |
| Soft Drop | 1 pro Reihe |
| Hard Drop | 2 pro Reihe |

Soft Drop und Hard Drop werden nicht mit dem Level multipliziert.

**Fallgeschwindigkeit:** Sekunden pro Reihe = `(0,8 − (Level − 1) × 0,007) ^ (Level − 1)`, mindestens 4 Millisekunden.

---

## Technik

- **Rendering:** HTML5 Canvas 2D, scharf auf Retina-Displays (Device-Pixel-Ratio)
- **Audio:** Web Audio API (Oszillatoren), Musik mit Look-ahead-Scheduler, Tempo steigt mit dem Level
- **Eingabe:** Pointer Events für Touch und Maus, eigener Repeat-Mechanismus für Tasten und Buttons
- **Web-App:** `manifest.json` (Vollbild, Hochformat), PNG-Icons in `icons/` (192, 512, maskierbar 512 und Apple-Touch-Icon 180) und `sw.js`. Der Service Worker legt die Spieldateien im Cache ab: Seiten werden zuerst online geladen, ohne Verbindung kommt die gespeicherte Version
- **Speicher:** `localStorage`, alles bleibt auf deinem Gerät

| Schlüssel | Inhalt |
| --- | --- |
| `tetris_kremlin_highscore` | Rekord |
| `tk_games` | Liste der gespielten Runden (die letzten 200) |
| `tk_m`, `tk_s` | Musik und Soundeffekte stumm geschaltet |

Das Spiel funktioniert auch, wenn `localStorage` gesperrt ist, nur ohne dauerhaftes Speichern.

**Browser:** aktuelle Versionen von Chrome, Edge, Firefox und Safari (für `CanvasRenderingContext2D.roundRect` wird Chrome 99, Firefox 112 oder Safari 16 oder neuer benötigt).

### Datenschutz

Das Spiel sendet keine Daten an Server und nutzt keine Tracker. Die einzige externe Anfrage ist die Schriftart **Orbitron** von Google Fonts. Ohne diese Zeile im `<head>` läuft das Spiel mit einer Ersatzschrift weiter.

### Projektstruktur

```
.
├── index.html        # das komplette Spiel (HTML, CSS und JavaScript)
├── manifest.json     # Web-App-Manifest
├── sw.js             # Service Worker (Offline-Cache)
├── favicon.ico
├── .nojekyll         # GitHub Pages ohne Jekyll
├── icons/
│   ├── icon-192.png
│   ├── icon-512.png
│   ├── icon-maskable-512.png
│   ├── apple-touch-icon.png
│   └── favicon-32.png
└── README.md
```

Bei jeder neuen Version die Nummer `V` in `sw.js` erhöhen, damit installierte Apps den alten Cache verwerfen.

---

## Mitmachen

Fehler oder Ideen gern als Issue melden. Pull Requests sind willkommen. Da alles in einer Datei liegt, reicht zum Testen das Öffnen im Browser.

Ideen für später: Level-Auswahl zum Start, Sprint- und Ultra-Modus, weitere Farbthemen, eigene Tastenbelegung.

## Lizenz

Noch nicht festgelegt. Füge eine `LICENSE`-Datei hinzu (zum Beispiel MIT), bevor du das Projekt weitergibst.

## Hinweis

Dies ist ein nichtkommerzielles Fanprojekt. „Tetris“ ist eine eingetragene Marke von The Tetris Company. Das Projekt steht in keiner Verbindung zu den Markeninhabern.
