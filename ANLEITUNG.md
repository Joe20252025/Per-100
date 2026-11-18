# Tabak-Preisvergleich – installierbare Android-PWA

Die App ist komplett statisch (HTML, JavaScript, Manifest und Service Worker).
Sie benötigt weder ein Backend noch zusätzliche Bibliotheken.

## Kostenlos über GitHub Pages veröffentlichen

1. Auf https://github.com/new ein neues **öffentliches** Repository anlegen, zum Beispiel `tabak-preisvergleich`.
2. Die ZIP-Datei lokal **entpacken** und den Inhalt des Ordners `tabak_preisvergleich_pwa` (nicht den übergeordneten Ordner) in die Wurzel des Repositories hochladen. Die `icons`-Unterordnerstruktur muss erhalten bleiben.
3. Unter `Settings` → `Pages` → `Build and deployment` die Quelle `Deploy from a branch` wählen.
4. Als Branch `main` und als Ordner `/(root)` wählen, danach `Save`.
5. Sobald GitHub Pages die Seite veröffentlicht hat, den dort angezeigten HTTPS-Link öffnen. Das ist üblicherweise `https://BENUTZERNAME.github.io/tabak-preisvergleich/`.

## Auf Android installieren

1. Den HTTPS-Link in **Google Chrome** auf Android öffnen.
2. Im Chrome-Menü `⋮` auf `App installieren` oder `Zum Startbildschirm hinzufügen` tippen.
3. Falls die App einen eigenen Button `App installieren` anzeigt, kann auch dieser benutzt werden.
4. Die App einmal vollständig laden lassen, damit der Offline-Cache angelegt wird.

Wichtig: Das Öffnen von `index.html` über eine `file://`-Adresse oder direkt aus dem Download-Ordner ist **keine installierbare PWA**. Der Browser braucht eine HTTPS-Adresse (oder `localhost` für Entwicklung).

## Datenschutz und Datenhaltung

- Alle eingegebenen Angebote werden nur im `localStorage` des Browsers auf dem eigenen Gerät gespeichert.
- Keine Anmeldung, Werbung, Tracking oder Preisabfrage im Internet.
- GitHub Pages veröffentlicht den **Quellcode**, aber nicht die lokalen Preiseinträge der Nutzer.
- Angebote aus der alten lokalen HTML-Datei werden nicht automatisch in die neue HTTPS-PWA übertragen. Falls wichtig, vorher notieren und nach Installation erneut eingeben.
- Das Löschen von Browser-/App-Daten kann die Einträge unwiderruflich entfernen.

## Technischer Test auf einem Computer

Im entpackten Ordner:

```bash
python -m http.server 8000
```

Dann `http://localhost:8000` aufrufen. `localhost` erlaubt die Registrierung des Service Workers, ist aber **nicht** die Adresse, die das Android-Handy normalerweise für die Installation verwenden kann.
