# StahlZähler

Zählt **Vierkant-Rohre, Rundstäbe, Sechskant, Flachstahl und Winkel/L** automatisch
aus einem Foto der Stirnfläche – oder **live** durch die Kamera. Läuft offline am Gerät,
Bildverarbeitung mit OpenCV.js. Verpackt als Android-App mit Capacitor.

## App-Code
Die komplette App steckt in **[`www/index.html`](www/index.html)** (UI + Logik in einer Datei),
dazu `www/opencv.js`, `www/sw.js` (Offline), `www/manifest.json`, `www/icon.svg`.

## APK bauen – automatisch in der Cloud
Bei jedem Push auf `main` baut **GitHub Actions** automatisch eine installierbare APK:

1. Reiter **Actions** → letzten Lauf **„Build APK"** öffnen.
2. Unten unter **Artifacts** → **`StahlZaehler-APK`** herunterladen (ZIP) und entpacken.
3. `StahlZaehler.apk` aufs Handy kopieren und installieren
   (einmalig „Installation aus unbekannten Quellen" erlauben).

Manuell starten: **Actions → Build APK → „Run workflow"**.

> Die APK ist debug-signiert (für interne Verteilung). Die **Kamera-Berechtigung**
> für den Live-Modus wird im Workflow automatisch ins Android-Manifest eingetragen.

## Lokal im Browser testen
Kleiner Static-Server (nur Node-Builtins): `node serve.js` → http://localhost:8848
