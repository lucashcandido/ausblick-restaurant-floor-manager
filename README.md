# Ausblick – Salón (Floor-Manager für Restaurants)

Ein Bildschirm für Tische, Reservierungen, Zeit am Tisch und Bestellungen. Aufgebaut wie `ausblick-clientes` und `ausblick-shiftmanager`: eine einzige `index.html` auf GitHub Pages, Daten in einem privaten Repo, Zugang per 12-stelligem Code, Design Ausblick Sistemas (schwarz/weiß, Dunkelmodus invertiert). Die Schichtplanung aus der Präsentation ist bewusst **nicht** enthalten – dafür gibt es `ausblick-shiftmanager`.

## Funktionen

- **Salón (Live-Plan):**
  - Jeder Tisch zeigt seinen Status in Farbe: grün frei · blau reserviert · bernstein am Essen · rot Rechnung · grau gestrichelt abräumen.
  - Stoppuhr pro Tisch (seit wann besetzt, Personen / Plätze). Tische über der geplanten Zeit blinken rot mit „+11m“.
  - Reservierte Tische zeigen Uhrzeit und Name (ab „Mostrar mesa como reservada desde“, Standard 60 Min. vorher).
  - Oben: freie und besetzte Tische, Gäste heute, und **Hinweise** zum Antippen: Rechnung gewünscht, Tisch über der Zeit, Getränke seit X Min. nicht nachbestellt, lange Wartezeit, Reservierung kommt in 20 Min.
- **Etagen als Tabs:** Hat ein Lokal mehrere Räume oder Etagen (Salón, Terraza, Planta alta …), stehen sie wie Browser-Tabs über dem Plan. Jeder Tab zeigt klein in Grün, wie viele Tische frei sind (z. B. „3 libres“), ein roter Punkt heißt: dort möchte jemand zahlen oder ist über der Zeit. „+“ legt eine neue Etage an. Doppelklick auf einen Tab (oder ✎ im Bearbeiten-Modus): umbenennen, nach links/rechts verschieben, löschen (nur leer). Hinweise oben gelten für alle Etagen und springen beim Antippen auf die richtige. Reservierungen und Tischvorschläge gelten für das ganze Lokal; in der Tischauswahl steht die Etage dabei.
- **Plan bearbeiten:** runde, quadratische oder rechteckige Tische hinzufügen, ziehen, an der blauen Ecke Größe ändern (10er-Raster). Tisch antippen → Name, Mindest- und Höchstgruppe, Etage (verschiebt den Tisch dorthin), Form, Duplizieren, Löschen (mit Rückgängig; besetzte Tische lassen sich nicht löschen).
- **Tische zusammenstellen:** Rahmen über die Tische ziehen (oder einzeln antippen) → „Juntar“. Plätze und Gruppengrenzen zählen zusammen, im Plan gestrichelt umrahmt. Ein besetzter Tisch darf dazukommen (die Gruppe wächst). Im Tischfenster „Separar mesas“, mit Rückgängig.
- **Tischfenster:**
  - Frei: Reservierung platzieren, ohne Reservierung platzieren, nächste Reservierungen des Tisches.
  - Besetzt: Personen ±, Zeit am Tisch gegen geplant, „Se libera“ (geplante Freigabe), Notizen aus der Reservierung (Allergien, VIP, Geburtstag).
  - **Bestellung:** Karte nach Kategorie, pro Tisch oder pro Platz (P1, P2 …), Menge ±. „An Küche und Bar senden“, Status pro Position (zu senden · gesendet · serviert).
  - Summe, **teilen durch N** und Summe **pro Platz**. „Pidió la cuenta“, „Cambiar de mesa“, „Cerrar mesa“ (mit Rückgängig). Danach steht der Tisch auf „abräumen“, bis jemand „Mesa limpia“ tippt.
- **Reservas:**
  - Tagesliste mit Vor/Zurück. Pro Reservierung: Uhrzeit, Name, Personen, Tisch, Herkunft (Telefon, persönlich, online), Telefon, Etiketten „Große Gruppe“, Allergien, Anlässe, Anzahlung.
  - **Allergien als Tags:** die 14 Hauptallergene (Gluten/TACC, Milch, Ei, Erdnüsse, Schalenfrüchte, Fisch, Krebstiere, Weichtiere, Soja, Sesam, Senf, Sellerie, Sulfite, Lupinen) zum Antippen. Fehlt eine, unten unter „Otra alergia…“ eintragen; sie erscheint danach bei allen Reservierungen als eigener (gestrichelter) Tag. Wird z. B. „frutos secos“ eingetippt, erkennt die App den vorhandenen Tag. Die Allergien stehen rot in der Liste und im Tischfenster.
  - **Besondere Anlässe als Tags:** 🎂 Cumpleaños, 💍 Aniversario, ❤️ Cita romántica, 💐 Pedida de mano, 🎉 Celebración, 🎓 Graduación, 👋 Despedida, 💼 Negocios, ✨ Primera visita, 🏠 Cliente habitual, ⭐ VIP. Eigene Anlässe unter „Otra ocasión…“ eintragen; sie werden gemerkt und danach überall angeboten. Das Symbol erscheint auch auf dem Tisch im Saalplan (reserviert und während die Gäste sitzen) und im Tischfenster.
  - **Tisch wird automatisch vorgeschlagen:** der kleinste passende Tisch (oder zusammengestellte Tische), der zu der Zeit nicht reserviert oder besetzt ist. Man kann einen anderen wählen; bei Überschneidung warnt die App.
  - Schnellknöpfe „Sentar“ und „No vino“ (zählt in der Statistik als nicht erschienen).
  - **Warteliste:** Name, Personen, Telefon, Wartezeit. „Avisar“ öffnet eine fertige SMS oder WhatsApp („tu mesa está lista“). „Sentar“ schlägt einen freien Tisch vor.
- **Pedidos:** alle offenen Tische mit dem, was noch an Küche/Bar muss, und dem, was in Zubereitung ist, getrennt nach Küche und Bar. Getränke gehen an die Bar, der Rest an die Küche.
- **Estadísticas** (heute, 7 Tage, 30 Tage):
  - Umsatz, Ø pro Tisch, Ø pro Gast, Tischbelegungen, Gäste, Ø Zeit am Tisch, Quote der Nicht-Erschienenen.
  - **Stoßzeiten** als Skala von ruhig bis voll, mit „Pico: 21h, con 92 % de las mesas ocupadas“.
  - Meistverkaufte Gerichte, Personal (wer den Tisch geöffnet hat).
  - Bei mehreren Lokalen ein Vergleich aller Lokale. Export als CSV.
- **Ajustes y reglas:** Name des Restaurants, große Gruppe ab N, geplante Zeit am Tisch (normal / große Gruppe), Gruppen ohne Reservierung min/max (die App warnt, man kann trotzdem platzieren), Online-Reservierungen sperren und Höchstgröße online, Getränke- und Warte-Hinweise, Währung.
- **Carta:** Gerichte mit Preis in Vorspeisen, Hauptgerichte, Desserts, Getränke.
- **Locales:** mehrere Lokale mit eigenem Plan, eigenen Reservierungen und eigener Statistik; Regeln und Karte gelten für alle. Auswahl oben neben „+“. „Copiar plano de…“ übernimmt den Plan eines anderen Lokals samt Etagen.
- **Beispiel zum Vorführen:** „Probar con datos de ejemplo“ im Einrichtungsbildschirm. Lädt ein Restaurant mit Salón (14 Tische) und Terraza (7 Tische), Karte, offenen Tischen, Reservierungen, Warteliste und 30 Tagen Verlauf. Bleibt nur auf dem Gerät, ohne GitHub.
- Fenster speichern beim Schließen (daneben tippen, Escape, „Listo“); „Descartar“ verwirft. ES / EN / DE, offline-fähig, „Deshacer“ überall.

## Daten

`salon.json` im privaten Daten-Repo = `{ v: 1, c: { id → Eintrag } }`, Art `k`:

| k | Inhalt |
|---|---|
| `set` | Einstellungen (id `set`): `biz`, `big`, `online`, `onMax`, `wMin`, `wMax`, `dur`, `durBig`, `drink`, `wait`, `soon`, `cur` |
| `loc` | Lokal: `n`, `o` (ohne Einträge gibt es ein Lokal `main`) |
| `flr` | Etage (Tab über dem Plan): `loc`, `n`, `o`. Ohne Einträge hat das Lokal eine Etage |
| `tbl` | Tisch: `loc`, `fl` (Etage; leer oder unbekannt = erste Etage), `n`, `sh` (`round`/`sq`/`rect`), `x`, `y`, `w`, `h` (Plan = 1000 × 640), `min`, `max`, `j` (gleiches `j` = zusammengestellt) |
| `menu` | Gericht: `n`, `p`, `cat` (`ent`/`pri`/`pos`/`beb`), `o` |
| `res` | Reservierung oder Warteliste: `loc`, `d`, `a`, `n`, `p`, `tel`, `src`, `tb`, `dep`, `alg` (Liste: `a:gluten` … für die Hauptallergene, sonst freier Text), `note`, `tags` (Anlässe: `bday`, `anniv` … oder freier Text), `st` (`''`/`seated`/`noshow`/`cancel`/`wait`), `at`, `nt`, `v` |
| `visit` | Besetzter Tisch: `loc`, `tb` (Tisch-IDs), `p`, `n`, `res`, `a` (seit), `end`, `tot`, `cl` (abgeräumt), `bill`, `dk`, `note`, `by`, `it` (Positionen `{id → {m, n, p, q, seat, cat, s, t}}`) |

Alle Einträge haben `t` (letzte Änderung, neuere gewinnt) und ggf. `del: true`. Positionen einer Bestellung werden einzeln zusammengeführt, damit zwei Kellner gleichzeitig am selben Tisch bestellen können. Die App synchronisiert alle 20 Sekunden.

## Einrichtung (einmalig)

1. Privates, leeres Repo **`ausblick-restaurant-floor-manager-data`** anlegen.
2. Diese Dateien nach `ausblick-restaurant-floor-manager` pushen, Settings → Pages → Branch `main` / root.
3. Fine-grained Token, der **nur** das Daten-Repo erreicht (Contents: Read and write).
4. App öffnen → „Primera vez (token)“ → `access.json` herunterladen und in dieses Repo hochladen. Weitere Geräte brauchen dann nur Name + Code.

## Für einen Kunden übernehmen

1. `index.html` kopieren und **nur den Block `APP`** oben im Script ändern:
   ```js
   var APP = {
     repo: 'lucashcandido/<kunde>-salon',
     data: 'lucashcandido/<kunde>-salon-data',
     file: 'salon.json',
     prefix: '<kurz>'          // eigener Speicher-Präfix pro App
   };
   ```
2. Eigene Farbe: `--accent` in `:root` (hell und dunkel).
3. Einrichtung wie oben mit den Repos des Kunden, dann Plan, Karte und Regeln eintragen.

## Noch nicht drin (Hoja de ruta)

Öffentliche Reservierungsseite mit den Online-Regeln, automatische SMS-Erinnerungen und Anzahlungen per Zahlung, Küchenbildschirm, Lager und „ausverkauft“, Kundenbewertungen, Kassen-(POS-)Anbindung, QR-Bestellung am Tisch.
