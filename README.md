# FeedLab 4.1 – THE LIFESTYLE EDIT

10 neue Musikgrafiken, 10 Captions mit Emojis, 5 Call-to-Actions in Captions, je 5 Hashtags und je 10 fiktive Kommentare. Die übrigen Kategorien bleiben unverändert.

# FeedLab 3.9 – KI und Schule

10 neue AI UNLOCKED-Grafiken, individuelle Captions, je fünf Hashtags, je zehn fiktive Kommentare. Kategorie KI und Schule ersetzt die bisherige Lernkategorie. Sonstige Beiträge unverändert.

## Vorherige Updates
# FeedLab 3.8 – Kino-Update

12 neue KI-Filmplakate, fiktive Filmhandlungen, fünf Hashtags je Beitrag und je zwölf simulierte Rezensionen und Kommentare. Alle übrigen Themen bleiben unverändert.

# FeedLab 3.7 – Umweltbilder- und Captions-Update

Die 12 früheren Umweltbilder wurden durch die 12 neuen Nutzerbilder ersetzt; Captions, Kommentarfragen, Hashtags und Unterthemen wurden aktualisiert. **Beitrag 11** zeigt Baumrinde und erklärt Borkenkäfer sowie Waldstress; **Beitrag 12** zeigt einen Lagerfeuerabend und thematisiert Naturverbundenheit statt Pfandsystem. Die übrigen Themenbereiche und die Empfehlungssimulation sind unverändert. Für die konkreten Zuordnungen siehe `Umwelt_Bildzuordnung_und_Captions.json`.

# FeedLab 3.6 – Du trainierst deinen Feed

**Interaktive Unterrichts-Webanwendung für Schüler*innen ab 15 Jahren.** Instagram-inspirierte Gestaltung, ohne Verbindung zu Instagram/Meta. Alle Konten und Interaktionen sind fiktiv. Der Empfehlungsalgorithmus ist bewusst vereinfacht.

## Starten und auf GitHub Pages veröffentlichen

Die App besteht aus statischen Dateien; ein Server, Datenbankdienst, Node.js oder Build-Schritt ist **nicht erforderlich**.

1. Inhalt dieses Ordners entpackt ins **Hauptverzeichnis** eines GitHub-Repositories hochladen. Insbesondere `index.html`, `app.js`, `styles.css`, `.nojekyll` und den vollständigen Ordner `assets/` übernehmen.
2. Im Repository **Settings → Pages → Build and deployment → Deploy from a branch** wählen.
3. Als Branch `main`, als Verzeichnis `/ (root)` auswählen und speichern.
4. Die veröffentlichte Website öffnen, z. B. `https://BENUTZERNAME.github.io/feedlab/` (Repo-Name ggf. anpassen).

*Wichtig:* Nicht die ZIP-Datei selbst ins Repository stellen, sondern ihren entpackten Inhalt. `index.html` liegt auf oberster Ebene.

## Lernprozess: vier aufeinander aufbauende Level

| Level | Aufgabe der Schüler*innen | Ablauf |
|---|---|---|
| **1 – Feed erkunden** | Scrollen und auf authentisch wirkende Beiträge reagieren | **30** gemischte Startbeiträge mit **3–4 Beiträgen aus jedem der 8 Oberthemen**, danach **18** personalisierte Beiträge, automatisch in **3 Gruppen zu 6** geladen; **48 Beiträge insgesamt**. Keine Schaltfläche für weitere Beiträge. |
| **2 – Beobachten** | Vor Einsicht in Daten die eigene Wahrnehmung beurteilen | Auswahl „Veränderung bemerkt / unsicher / kaum Veränderung“; eine konkrete Beobachtung in einem Satz. |
| **3 – Auswerten** | Eigene Beobachtung mit den Themenanteilen vergleichen | Nach oben animierte Säulen: **30 Startbeiträge gegen 18 personalisierte Empfehlungen**, dazu Nutzersignale, gewichtete Interessen und Unterinteressen. |
| **4 – Forschen** | Eine Vermutung mit einer Handlung prüfen | Thema und Handlung wählen, erwartete Richtung festhalten und zwei Runden mit je zwölf Beiträgen vergleichen. Anschließend die Vermutung anhand der Zahlen beurteilen, den Unterschied zwischen Interessenwert und Beitragszahl erklären und das Ergebnis auf echte Feeds übertragen. Beide Runden nutzen denselben vollständigen Beitragspool, dieselbe Auswahlregel und dieselbe Zufallsfolge. |

Die **94 verschiedenen Posts** sind ausschließlich der **Inhaltspool**. Eine Schülerin oder ein Schüler muss **nicht alle 94** ansehen. Pro regulärem Feed-Durchlauf sind **48 einzigartige Beiträge** vorgesehen. Für das Experiment in Level 4 werden zwei eigene Vergleichsrunden mit je zwölf Beiträgen berechnet.

### Grundprinzip der Personalisierung

1. **30 Startposts:** Die Zusammensetzung wird unabhängig vom Verhaltensprofil ausgewogen zusammengestellt. Die Reihenfolge variiert. Dabei sammelt das System bereits Signale, die **Auswahl der ersten 30** wird jedoch nicht durch die Signale verändert.
2. **18 personalisierte Posts:** Beim Weiterrollen entsteht ohne Tastendruck ein kurz sichtbares Ladesymbol. Es werden nacheinander **3 × 6** bisher ungesehene Posts angehängt. Jeder neue Sechserblock nutzt die **bis zu diesem Moment** gemessenen Signale.
3. In jedem personalisierten Sechserblock werden **5 Beiträge mit individuell gewichteter Zufallsauswahl** gezogen. **Ein Beitrag** stammt bewusst aus schwächer gewichteten Themen. Dieser Anteil sorgt für Perspektivenvielfalt (ca. 83 % gewichtete und 17 % explorative Auswahl). Die fünf gewichteten Beiträge können aufgrund der Zufallsauswahl ebenfalls unterschiedliche Themen betreffen.
4. Nach 48 geladenen Beiträgen endet das automatische Nachladen. Sobald die Endmarke unter dem letzten Beitrag sichtbar wird, zeigt die App **„Level 1 abgeschlossen“** und gibt Level 2 frei.

Eine stärkere Gewichtung steigert die Wahrscheinlichkeit eines Inhalts, garantiert ihn aber nicht. Hat ein Thema keine ungesehenen Beiträge mehr, stehen andere Themen weiter zur Verfügung. **Es werden in Level 1 keine Bilder wiederholt.**

### Welche Signale verarbeitet der Lernalgorithmus?

| Gemessene Handlung | Punkte |
|---|---:|
| Bildfläche unter 3 Sekunden sichtbar | 0 |
| Bildfläche insgesamt mindestens 3 Sekunden sichtbar | +1 |
| Bildfläche insgesamt mindestens 5 Sekunden sichtbar | +2 **gesamt** (nicht +1 und +2) |
| Bereits länger betrachteten Beitrag erneut mindestens 1,5 Sekunden ansehen | +2 einmalig |
| Like | +3 |
| Speichern | +4 |
| Teilen (nur Simulation) | +3 |
| „Weniger davon“ | −3 |
| Kommentare mindestens 3 Sekunden geöffnet | +1 |
| Kommentare mindestens 5 Sekunden geöffnet | +2 **gesamt** |
| In Level 4 ein neues Thema bewusst entdecken | +3 (einmalig) |
| In Level 4 einen Entdeckungsbeitrag öffnen | +2 (einmalig) |

Die Zeitmessung setzt voraus, dass mindestens **55 % der Bildfläche** sichtbar sind und der Tab aktiv ist. Beim Kommentarfenster wird dessen **Öffnungszeit** gemessen: Eine tatsächliche Blickrichtung oder ob jemand liest, kann die App nicht prüfen. Alle Punkte und Zeitgrenzen sind **didaktische Simulationswerte, keine veröffentlichten Instagram-Parameter**.

## Datenschutz

- Keine Anmeldung und keine Abfrage von Namen, Identitäten oder privaten Angaben.
- Keine Übermittlung von Verhaltenssignalen an einen eigenen Server; keine Datenbank, Cookies, `localStorage` oder `sessionStorage`.
- Die persönlichen Variablen bleiben ausschließlich im **JavaScript-Arbeitsspeicher der geöffneten Seite**. **Neuladen oder Schließen** setzt das Profil und die Beobachtungsnotiz zurück.
- Bei der statischen Auslieferung durch GitHub Pages können unabhängig von der App **technische Hosting-Zugriffsprotokolle** entstehen.

## Dateistruktur

```text
index.html                         Startseite mit Navigation
styles.css                         Layout, Animationen, Mobilansicht
app.js                             94 fiktive Posts, Algorithmus, Tracking, Lernlevel
assets/beitrag-*.webp              94 individuelle KI-generierte Beitragsbilder
.nojekyll                          Direkte statische Veröffentlichung
README.md                          Diese Anleitung
Projektbeschreibung_und_Pruefbericht.md   Pädagogische und technische Dokumentation
```

Alle 94 Bilddateien tragen ein sichtbares **AI GENERATED**. Die 36 überarbeiteten Bilder zu KI und Schule, Sport und Kino sind in der Bildsammlung enthalten. Einzelne Motive sind aus KI-Collagen zugeschnitten und besitzen nicht alle die gleiche originale Detailauflösung. Die beiden Turmspring-Motive sind illustrativ, nicht fotorealistisch.

## Qualitätssicherung – Version 3.6 (20. November 2026)

Automatisierte Chromium-Browsertests mit **Desktop-Bildschirm (1366 × 900)** und **Smartphone-Viewport (390 × 844)** ergaben:

- 94 Bilddateien vorhanden und untereinander verschieden; keine fehlenden eingebundenen Dateien.
- Startfeed genau 30 eindeutige Beiträge; jedes Thema erscheint 3 oder 4 Mal; unterschiedliche Reihenfolge bei neuen Sitzungen.
- Während der ersten 30 Beiträge keine Neuzusammenstellung durch Likes oder sonstige Signale.
- Drei automatische Ergänzungen: 30 → 36 → 42 → 48, jeweils ohne erneuten Klick und ohne Wiederholungen.
- Nach 48 Beiträgen kein weiteres automatisches Nachladen.
- Beobachtungsfrage vor Level-3-Auswertung; individuelle Daten für Diagramme 30 versus 18.
- Level-4-Mission nur nach Abschluss der vorherigen Lernschritte; Hypothesenprüfung, zusätzlicher Vergleich und Freigabe der Code-Auflösung funktionieren.
- Keine JavaScript-Laufzeitfehler oder fehlenden Bilder in diesen Prüfungen.

Dies ist eine **Funktionsprüfung der beiden Browser-Ansichtsgrößen**, kein Nachweis für fehlerfreien Betrieb auf jedem Gerät und keine Prüfung der späteren tatsächlichen GitHub-Veröffentlichung.

## Sportbilder-Update (20. November 2026)

Zwölf Sportfotos wurden durch neue quadratische, als „AI GENERATED“ gekennzeichnete Bilder ersetzt. Die jeweiligen Posts enthalten neu formulierte sportartspezifische Captions, Rückfragen und jeweils **fünf passende Hashtags**. Die Kommentarverläufe für **alle 14** Sportposts sind individuell auf die jeweilige Abbildung und Sportart abgestimmt. Die ursprünglichen Posts `beitrag-sport-01.webp` (Skateboard) und `beitrag-sport-02.webp` (Turmspringen) bleiben als zwei weitere, inhaltlich passende Sportbeiträge bestehen, damit alle 94 Posts und alle 94 individuellen Bilder erhalten bleiben. Eine genaue Übersicht steht in `Sportbilder_Update_12_Beitraege.json`. Am Empfehlungs- und Phasenmodell (30 + 18) wurde nichts verändert.

## Gaming- und Tierbilder-Update (20. November 2026)

Alle zwölf Gamingbeiträge wurden mit jeweils genau einem Spielmotiv, einer dazu passenden eigenständigen Caption, einem CTA, **genau fünf Hashtags (darunter der konkrete Spieletitel)** und 11/17/28 spielbezogenen Kommentaren aktualisiert. Die sechzehn Tierbeiträge wurden jeweils mit eigenem Tierbild, neuer Caption, CTA, genau fünf Hashtags und warmherzigen, auf das Bild bezogenen Kommentaren versehen. Die Bilder tragen im rechten unteren Eck die sichtbare Kennzeichnung „AI GENERATED“. Die vorherige Aktualisierung der zwölf Sportbeiträge bleibt erhalten. Die restlichen Themen, alle 94 Beitrags-IDs und die Feed-Mechanik mit 30 gemischten + 18 personalisierten Beiträgen bleiben unverändert.

Die genaue Zuordnung aller neu ersetzten Beiträge samt Bildquellen und Captions steht in `Gaming_Tiere_Update_28_Beitraege.json` sowie `Bildzuordnung.json`.


## Lifestyle-Update 4.1
8 neue Bilder, 4 CTAs, 5 Hashtags pro Beitrag, 96 fiktive Kommentare.

## Lizenz und Datenschutz

FeedLab steht unter [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/), soweit die Projektverantwortliche über die entsprechenden Rechte verfügt. Rechte Dritter und Markenrechte bleiben unberührt. Kontakt, Projektkontext und Datenschutz stehen im [Impressum](impressum.html).
