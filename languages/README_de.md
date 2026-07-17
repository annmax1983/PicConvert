# ImageConv
[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | Deutsch | [日本語](README_ja.md) | [Français](README_fr.md)
Eine leichtgewichtige Browser-Erweiterung, die Bilder zwischen PNG, JPG, WEBP und AVIF konvertiert — vollständig lokal, ohne Datenupload.

> Chromium-basiert · Manifest V3 · Kein Tracking · Vollständig im Browser verarbeitet

[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | Deutsch | [日本語](README_ja.md) | [Français](README_fr.md)

---

## Warum ImageConv?

Die meisten Bildkonvertierungstools erfordern das Hochladen Ihrer Dateien auf einen Remote-Server. ImageConv erledigt alles in Ihrem Browser mit der Canvas-API — Ihre Daten verlassen niemals Ihr Gerät.

| Vorteil | Beschreibung |
|---------|-------------|
| 🔒 **Privatsphäre** | Alle Verarbeitung erfolgt im Speicher Ihres Browsers. Keine Server, keine Uploads, kein Tracking. |
| ⚡ **Sofortige Konvertierung** | Bilder ≤5MB werden in unter 500ms konvertiert. Keine Wartezeiten auf Server-Antworten. |
| 🎯 **Null Abhängigkeiten** | Gebaut mit Vanilla JavaScript und nativen Chrome-APIs. Keine Frameworks, kein Bloat. |
| 🌍 **6 Sprachen** | Erkennt automatisch Ihre Browsersprache — Englisch, Spanisch, Deutsch, Japanisch, Französisch, Chinesisch. |
| 📋 **Kopieren & Speichern** | Rechtsklick auf ein Bild zum Speichern als Datei ODER direkt in die Zwischenablage kopieren. |
| 📁 **Drag & Drop** | Lokale Bilder per Drag & Drop auf das Popup ziehen für schnelle Konvertierung. |

---

## Funktionen

| Funktion | Beschreibung |
|----------|-------------|
| 🖼️ **4 Formate** | Konvertieren zu PNG (verlustfrei), JPG (hohe Qualität), WEBP (kompakt) oder AVIF (beste Komprimierung) |
| 📋 **In Zwischenablage kopieren** | Rechtsklick → Kopieren als PNG/JPG/WEBP/AVIF — direkt in E-Mails, Chats, Dokumente einfügen |
| 📊 **Dateigrößenvergleich** | Toast-Benachrichtigung zeigt Original- vs. konvertierte Größe mit Einsparungsprozentsatz |
| 🎚️ **Anpassbare Qualität** | Feineinstellung der Exportqualität für JPG, WEBP und AVIF über Schieberegler im Popup |
| 🔗 **Intelligente Link-Bereinigung** | Entfernt CDN-Tracking-Parameter (`w=`, `h=`, `format=`, `watermark=`, etc.) für Originalbilder |
| 📁 **Drag & Drop** | Lokale Bilddateien per Drag & Drop auf das Popup ziehen ohne Rechtsklick |
| 🌐 **Cross-Origin-Unterstützung** | Ruft Bilder von jeder Website über Service Worker ab — verarbeitet Cross-Origin-Ressourcen intern |
| 🔤 **6-Sprach-i18n** | Kontextmenü und UI passen sich automatisch an Ihre Browsersprache an (EN/ES/DE/JA/FR/ZH-CN) |
| 🛡️ **JPG-Weißfüllung** | Füllt automatisch transparente Hintergründe mit Weiß bei PNG → JPG Konvertierung |
| ⏱️ **Duplikatschutz** | Ignoriert wiederholte Klicks auf dasselbe Bild innerhalb von 2 Sekunden |
| 📦 **Große Bildverarbeitung** | Bilder >20MB zeigen einen asynchronen Verarbeitungsindikator an, anstatt die UI einzufrieren |

---

## Vorschau

<!-- Ersetzen Sie durch tatsächliche Screenshots -->
<p align="center">
  <img src="screenshots/popup.png" alt="ImageConv Popup" width="360">
</p>

<p align="center">
  <img src="screenshots/context-menu.png" alt="ImageConv Kontextmenü">
</p>

---

## Unterstützte Browser

| Browser | Status |
|---------|--------|
| Google Chrome | ✅ Vollständig unterstützt |
| Microsoft Edge | ✅ Vollständig unterstützt |
| Brave | ✅ Unterstützt |
| Opera | ✅ Unterstützt |
| Vivaldi | ✅ Unterstützt |
| Jeder Chromium-basierte Browser | ✅ Unterstützt (Manifest V3) |

---

## Installation

### Aus Quellcode (Entwicklermodus)

1. Öffnen Sie die Erweiterungsseite Ihres Browsers:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Aktivieren Sie den **Entwicklermodus** (Schalter oben rechts)
3. Klicken Sie auf **Entpackte Erweiterung laden** und wählen Sie den `pic-convert` Ordner
4. Das ✨ ImageConv-Symbol erscheint in Ihrer Symbolleiste

---

## Verwendung

### Rechtsklick-Konvertierung

1. Rechtsklicken Sie auf ein Bild auf einer Webseite
2. Wählen Sie **ImageConv** aus dem Kontextmenü
3. Wählen Sie **Speichern unter** oder **Kopieren als**
4. Wählen Sie Ihr Format: PNG, JPG, WEBP oder AVIF
5. Fertig — die Datei wird sofort heruntergeladen oder das Bild in die Zwischenablage kopiert

### Drag & Drop

1. Klicken Sie auf das ImageConv-Symbol in Ihrer Symbolleiste, um das Popup zu öffnen
2. Ziehen Sie eine lokale Bilddatei auf die Drop-Zone
3. Wählen Sie Ihr Zielformat
4. Die konvertierte Datei wird automatisch heruntergeladen

### Qualitätseinstellungen

Öffnen Sie das Popup, um die Exportqualität für JPG, WEBP und AVIF über die Schieberegler anzupassen. PNG ist immer verlustfrei. Einstellungen werden automatisch gespeichert.

---

## Kontextmenü-Struktur

```
ImageConv
├── Speichern unter PNG (Verlustfrei)
├── Speichern unter JPG (Hohe Qualität)
├── Speichern unter WEBP (Kompakt)
├── Speichern unter AVIF (Beste Komprimierung)
├── Kopieren als PNG (Verlustfrei)
├── Kopieren als JPG (Hohe Qualität)
├── Kopieren als WEBP (Kompakt)
└── Kopieren als AVIF (Beste Komprimierung)
```

Die **Kopieren als** und **Speichern unter** Menüs erscheinen nur bei Rechtsklick auf Bilder oder Links, die auf Bilddateien zeigen (`.png`, `.jpg`, `.jpeg`, `.webp`, `.avif`, `.gif`, `.bmp`, `.jfif`, `.svg`).

---

## Datenschutz

ImageConv wurde mit Datenschutz als Kernprinzip gebaut:

- ✅ **Kein Datenupload** — Alle Bildverarbeitung erfolgt im Speicher Ihres Browsers
- ✅ **Keine Analyse** — Kein Tracking, keine Telemetrie, keine Remote-Aufrufe
- ✅ **Keine Cookies** — Kein Lesen oder Schreiben von Browser-Cookies
- ✅ **Kein Browserverlauf** — Kein Zugriff auf Ihre Browserdaten
- ✅ **Nur temporärer Speicher** — Bilder existieren während der Konvertierung im Speicher und werden danach sofort gelöscht
- ✅ **Minimale Berechtigungen** — Fordert nur das strikt Notwendige an: `contextMenus`, `downloads`, `offscreen`, `storage`, `clipboardWrite`

---

## So funktioniert es

```
Rechtsklick auf Bild
       ↓
Service Worker holt Bild-Blob (Cross-Origin-Verarbeitung)
       ↓
Sendet Blob an Offscreen-Dokument (verstecktes DOM mit Canvas-Zugriff)
       ↓
Canvas zeichnet Bild in nativer Auflösung
       ↓
Exportiert als Zielformat mit angegebener Qualität
       ↓
Gibt Daten-URL zurück → löst Download aus oder kopiert in Zwischenablage
       ↓
Zerstört alle temporären Ressourcen (Blob, Canvas, Bildelement)
```

> **Warum Offscreen?** Chromes Manifest V3 führt den Hintergrund als Service Worker aus, der keinen DOM-Zugriff hat. Die Canvas-API benötigt ein DOM, daher verwenden wir Chromes Offscreen-API, um ein verstecktes Dokument für die Bildverarbeitung zu erstellen.

---

## Standard-Exportqualität

| Format | Qualität | Anmerkungen |
|--------|----------|-------------|
| PNG | Verlustfrei | Keine Qualitätseinstellung — erhält immer volle Qualität und Transparenz |
| JPG | 92 | Hohe Qualität, gute Balance zwischen Größe und Klarheit |
| WEBP | 90 | Modernes Format, ~25-35% kleiner als JPG bei gleicher Qualität |
| AVIF | 70 | Nächstes Format, ~20-30% kleiner als WEBP, am besten für Web-Lieferung |

Alle Qualitätswerte sind über Schieberegler im Popup anpassbar (Bereich: 10–100).

---

## Urheberrechtlicher Haftungsausschluss

Diese Erweiterung bietet nur lokale Bildformatkonvertierung für die persönliche Offline-Verarbeitung des Benutzers. Alle Bilder, Fotos und Grafikressourcen auf Webseiten unterliegen dem Urheberrecht des ursprünglichen Rechtsinhabers. Konvertierte Bilder dürfen nicht für kommerzielle Vervielfältigung, unbefugte Verbreitung oder andere urheberrechtsverletzende Handlungen verwendet werden.

## Hinweis zu Cross-Origin-Bildern

Die Cross-Origin-Bildabrufoption dient nur zum Abrufen von Bildressourcen für die lokale Formatkonvertierung. Das massenhafte Crawling von Website-Bildressourcen mit dieser Funktion ist untersagt.

---

## Lizenz

Copyright © 2026 ImageConv. Alle Rechte vorbehalten.

---

## ❤️ Unterstützen

Wenn Ihnen ImageConv hilft, erwägen Sie bitte, das Projekt zu unterstützen!

<!-- Fügen Sie Ihren Unterstützungslink hier ein -->
**[👉 ImageConv unterstützen](https://annmax1983.github.io/ImageConv/)**

---

