# Formkant – statische Website (formkant.de)

> **ENTWURF, vor Veröffentlichung durch den geprüften Text der IT-Recht Kanzlei oder eines Generators ersetzen**
> (gilt für `datenschutz.html`; auch die Angaben in `impressum.html` vor dem Livegang prüfen lassen)

Reines HTML5 + CSS. Kein JavaScript, keine Cookies, keine externen Ressourcen.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Startseite |
| `impressum.html` | Impressum (§ 5 DDG) |
| `datenschutz.html` | Datenschutzerklärung (Entwurf) |
| `404.html` | Fehlerseite (nutzt absolute Pfade, wirkt daher nur auf dem Server gestylt) |
| `css/style.css` | gemeinsames Stylesheet |
| `img/logo.svg`, `img/favicon.svg` | Logo und Favicon |
| `.htaccess` | HTTPS, www-Umleitung, 404-Seite, Sicherheits-Header |
| `robots.txt` | erlaubt Indexierung |

Nicht hochladen: `README.md` und die vorhandenen PNG-Dateien (`formkant_*.png`), die gehören nicht zur Website.

## Veröffentlichen bei GoDaddy

1. Im GoDaddy-Konto cPanel öffnen → **Dateimanager** (oder per FTP/SFTP verbinden).
2. In den Ordner `public_html` wechseln.
3. Die vorhandene Standard-Startseite von GoDaddy (z. B. `index.html`, `index.php`, `default.html`) löschen oder überschreiben.
4. Alle Website-Dateien inkl. der Ordner `css/` und `img/` hochladen. Achtung: `.htaccess` ist eine versteckte Datei – im Dateimanager unter „Einstellungen“ → „Versteckte Dateien anzeigen“ aktivieren.
5. **SSL** im GoDaddy-Konto für `formkant.de` und `www.formkant.de` aktivieren. Erst danach greifen die HTTPS-Umleitungen sauber.
6. Prüfen, dass alle vier Varianten mit **301** auf `https://formkant.de/` führen:
   - `http://formkant.de`
   - `http://www.formkant.de`
   - `https://www.formkant.de`
   - `https://formkant.de` (Ziel)
7. Eine nicht existierende Adresse aufrufen (z. B. `https://formkant.de/test`) → die eigene 404-Seite muss erscheinen.

**Kein Apache?** Läuft das Paket auf Windows-Hosting (IIS/Plesk), wird `.htaccess` ignoriert. Dann ist stattdessen eine `web.config` mit denselben Regeln nötig.

## Prüfliste vor dem Livegang

- [ ] Alle Platzhalter `[[…]]` ersetzt (Suche nach `[[` darf nichts mehr finden)
- [ ] Impressum und Datenschutzerklärung durch geprüfte Texte (IT-Recht Kanzlei/Generator) ersetzt
- [ ] Auftragsverarbeitung (AVV/DPA) mit GoDaddy geklärt
- [ ] Kontakt-E-Mail formkant@gmail.com (Google) im Datenschutz-Abschnitt „Kontaktaufnahme per E-Mail“ berücksichtigt; bei Wechsel auf eine eigene Domain-Adresse in index.html, impressum.html und datenschutz.html ersetzen
- [ ] Zuständige Aufsichtsbehörde (LDI NRW) und Anschrift **vor Veröffentlichung prüfen**
- [ ] SSL aktiv, Umleitungen (siehe oben) geprüft
- [ ] W3C-Validator und Lighthouse auf der Live-Seite ausgeführt

## Offene Punkte

| Datei | Platzhalter | Beschreibung |
|---|---|---|
| `impressum.html` | `<!-- PLATZHALTER: weitere Pflichtangaben … -->` | Weitere Pflichtangaben laut IT-Recht Kanzlei, z. B. Wirtschafts-Identifikationsnummer |
| `impressum.html` | Telefon | Bewusst weggelassen (keine private Nummer). Optional geschäftliche Nummer als zweiten Kontaktweg ergänzen – von Kanzlei prüfen lassen |
| `datenschutz.html` | gesamte Datei | **ENTWURF**, durch geprüften Text ersetzen |
| `datenschutz.html` | `[[GODADDY-VERTRAGSPARTNER UND ANSCHRIFT LAUT KONTO]]` | Vertragspartner aus dem GoDaddy-Konto/Vertrag |
| `datenschutz.html` | `[[SERVERSTANDORT]]` | Serverstandort laut GoDaddy |
| `datenschutz.html` | `<!-- PLATZHALTER: Hosting-Abschnitt … -->` | Vollständiger Hosting-Text inkl. ggf. Drittlandübermittlung |
| `datenschutz.html` | `[[TEXT KONTAKTAUFNAHME PER E-MAIL]]` | Text zur Kontaktaufnahme per E-Mail |
| `datenschutz.html` | `<!-- PLATZHALTER: Text zu externen Links … -->` | Ggf. ergänzender Text zu Etsy/Instagram-Links |
| `datenschutz.html` | `[[TEXT BETROFFENENRECHTE]]` | Betroffenenrechte (Art. 15–21 DSGVO) |
| `datenschutz.html` | `[[ANSCHRIFT AUFSICHTSBEHÖRDE]]` | Anschrift der LDI NRW – **vor Veröffentlichung prüfen** |
| `index.html` | `<!-- TODO: Produktfoto … -->` | Produktfoto `img/caesar.jpg` mit alt-Text, Breite 100 %, `loading="lazy"` |
