# Formkant – statische Website (formkant.de)

Reines HTML5 + CSS. Kein JavaScript, keine Cookies, keine externen Ressourcen.
Gehostet mit **GitHub Pages** (Repository `Johann-11/formkant`), Domain `formkant.de` bei **GoDaddy**.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Startseite |
| `impressum.html` | Impressum (§ 5 DDG) |
| `datenschutz.html` | Datenschutzerklärung (eRecht24-Generator) |
| `datenschutz-social-media.html` | Datenschutzerklärung für die Profile bei Instagram und TikTok (selbst formuliert) – im Profil-Bio verlinken |
| `404.html` | Fehlerseite (nutzt absolute Pfade, wirkt daher nur auf dem Server gestylt) |
| `css/style.css` | gemeinsames Stylesheet |
| `img/logo.svg`, `img/favicon.svg` | Logo und Favicon |
| `.htaccess` | Nur für Apache-Hosting. Wird von GitHub Pages ignoriert (HTTPS, www-Umleitung und 404 erledigt GitHub selbst) |
| `robots.txt` | erlaubt Indexierung |
| `.gitignore` | hält Arbeitsdateien (`formkant_*.png`) aus dem Repository |

## Änderungen veröffentlichen

1. In VS Code speichern.
2. Quellcodeverwaltung öffnen (`Strg+Shift+G`), kurze Notiz eingeben, **Commit** klicken.
3. **Sync Changes** klicken. Nach ca. einer Minute ist die Änderung online.

## Einrichtung GitHub Pages + GoDaddy (einmalig)

1. GitHub → Repository → **Settings → Pages**: Source „Deploy from a branch“, Branch `main`, Ordner `/ (root)`.
2. **Custom domain**: `formkant.de`.
3. GoDaddy → formkant.de → **DNS**:
   - A-Einträge `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (alte `@`-A- und AAAA-Einträge löschen)
   - CNAME `www` → `Johann-11.github.io`
4. Nach „DNS check successful“: **Enforce HTTPS** aktivieren.
5. Prüfen: `http://formkant.de`, `http://www.formkant.de`, `https://www.formkant.de` führen auf `https://formkant.de`; eine nicht existierende Adresse zeigt die 404-Seite.

## Prüfliste

- [x] Platzhalter in Impressum und Datenschutz ersetzt
- [x] Datenschutzerklärung aus Generator eingebaut (Hoster GitHub)
- [x] Datenschutz: Abschnitte zu USA-Übermittlung (GitHub), Gmail und Etsy/Instagram-Links ergänzt (selbst formuliert, im Code markiert)
- [x] Wirtschafts-Identifikationsnummer im Impressum
- [x] Hosting-Absatz angepasst (kein AV-Vertrag mit GitHub)
- [x] Datenschutzerklärung für Social-Media-Profile angelegt und im Footer verlinkt
- [ ] Impressum und Social-Media-Datenschutz in den Profilen bei Instagram und TikTok verlinken
- [ ] Die selbst ergänzten bzw. selbst formulierten Texte bei Gelegenheit prüfen lassen
- [ ] Bei Änderungen (anderer Hoster, eigene E-Mail-Adresse, neue Dienste) Datenschutzerklärung neu generieren
- [ ] W3C-Validator und Lighthouse auf der Live-Seite ausführen

## Offene Punkte

| Datei | Punkt | Beschreibung |
|---|---|---|
| `impressum.html` | Telefon | Bewusst weggelassen (keine private Nummer). Für Fernabsatz über Etsy eine Zweitnummer besorgen und dort bzw. hier eintragen |
| `datenschutz.html` | Ergänzte Abschnitte | USA-Übermittlung, Gmail, Etsy/Instagram-Links, Hosting-Satz selbst formuliert – prüfen lassen |
| `datenschutz-social-media.html` | Ganze Seite | Selbst formuliert – prüfen lassen. TikTok: Profil-Link ergänzen, sobald vorhanden |
| `index.html` | `<!-- TODO: Produktfoto … -->` | Produktfoto `img/caesar.jpg` mit alt-Text, Breite 100 %, `loading="lazy"` |
