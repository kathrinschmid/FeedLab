# FeedLab 3.6 – Projektbeschreibung und technischer Prüfbericht

## Ausgangssituation und Ziel

FeedLab ist eine im Rahmen eines Vibe-Coding-Projekts entwickelte, Instagram-inspirierte Webanwendung für Schüler*innen einer 5. Klasse AHS. Sie vermittelt die Funktionsweise von Empfehlungsalgorithmen, Interaktionssignalen und möglichen Filterblasen durch eigene Erkundung. Die Entwicklung wurde durch sprachlich formulierte Anforderungen an Programmcode, Oberfläche, Benutzerinteraktion und pädagogischen Aufbau gesteuert und iterativ überprüft.

Die Schüler*innen sollen **nicht zuerst lesen, wie der Algorithmus funktioniert**. Sie sollen zunächst handeln, ihre Wahrnehmung festhalten, ihre personalisierte Auswertung untersuchen und erst anschließend ein gezieltes Experiment durchführen. Die programmierten Regeln werden erst nach diesem Prozess innerhalb der Anwendung offengelegt.

## Lernprozess

### Level 1 – Feed erkunden und unbemerkt trainieren

Die App beginnt mit **30 gemischten Feed-Beiträgen**. Alle acht Oberthemen kommen je drei- bis viermal vor; die Reihenfolge wird pro Sitzung neu zusammengestellt. Die Schüler*innen scrollen im Instagram-ähnlichen Feed und können liken, speichern, teilen (simuliert), „Weniger davon“ auswählen, Beiträge länger oder erneut ansehen sowie Kommentare öffnen und lesen.

Die App sammelt währenddessen Verhaltenssignale. **Die Auswahl der ersten 30 Posts bleibt jedoch unverändert.** Das ist wichtig, damit die Datenerhebung nicht schon durch einseitige Anfangsempfehlungen verzerrt wird. An das Ende dieses Abschnitts schließen sich **18 personalisierte Beiträge** an, die in **drei Sechsergruppen** ausschließlich durch Scrollen automatisch nachgeladen werden. Das Ladesymbol signalisiert die kurze Verzögerung. Es ist **kein Weiter-Button** erforderlich. Pro Sechsergruppe folgen fünf Empfehlungen gewichteten Interessen und eine weitere bringt bewusst ein schwächer vertretenes Thema ein. Nach genau 48 verschiedenen Beiträgen endet Level 1.

Die **94 vorhandenen Beiträge** sind ein Katalog für die Auswahl; sie müssen nicht vollständig gesehen werden. Die 48 im Durchlauf ausgewählten Bilder kommen nicht doppelt vor.

### Level 2 – Vor der Analyse beobachten

Die Schüler*innen entscheiden zunächst, ob sie subjektiv eine Veränderung des Feeds bemerkt haben. Sie können freiwillig notieren, welche Themen ihnen besonders aufgefallen sind. Die Datenanalyse ist bis zu dieser Beobachtungsentscheidung nicht freigeschaltet. Dadurch wird die **Eigenwahrnehmung von der anschließenden Dateninterpretation getrennt**.

### Level 3 – Eigene Daten untersuchen

Im persönlichen Algorithmus-Check werden ausschließlich die **Interaktionen derselben geöffneten Sitzung** ausgewertet. Animierte, nach oben wachsende Säulendiagramme stellen die Themenverteilung der **30 Startposts** der Themenverteilung der **18 empfohlenen Posts** gegenüber. Weitere Darstellungen zeigen erfasste Signale, Themen- und Unterthemenwerte sowie den zeitlichen Signalverlauf.

Wichtig: Der Algorithmus ermittelt **vermutete** Interessen anhand von Verhaltenssignalen. Die angezeigte Verteilung lässt keine verlässliche Aussage über tatsächliche Interessen oder die Persönlichkeit zu. Die Säulen bilden die **ausgewählten Inhalte** ab, nicht eine objektive Messung von Vorlieben.

### Level 4 – Forschen, überprüfen, offenlegen

Die Schüler*innen wählen ein wenig empfohlenes Thema und formulieren eine Hypothese, wie sie die Auswahl beeinflussen könnten. Sie müssen die vermutete Handlung tatsächlich ausprobieren und mindestens eine zweite Signalart zum Zielthema erzeugen. Erst dann dürfen sie eine zusätzliche Zwölfergruppe berechnen und mit der Ausgangslage vergleichen. Der interne Interessenwert wird ebenfalls gegenübergestellt, denn eine Gewichtungsänderung ist wegen der Zufallsauswahl nicht unbedingt sofort in den tatsächlichen Beitragszahlen sichtbar.

Vor der Auflösung beurteilen die Schüler*innen ihre Hypothese. Danach erhalten sie die konkreten Gewichtungen des eigenen Algorithmus, vereinfachten Pseudocode, Zugang zum JavaScript-Quellcode und den fachlichen Input zu Filterblasen sowie deren Risiken und Gegenstrategien.

## Technische Funktionsweise

Die GitHub-Pages-fähige App basiert ausschließlich auf **HTML, CSS und JavaScript**. Sie besitzt keine Nutzerkonten, Datenbank und kein Backend. JavaScript hält während einer Sitzung Interessenwerte für acht Oberthemen und zahlreiche Unterthemen. Punkte entstehen aus zeitbasierten und bewussten Interaktionen. Für eine Empfehlung bekommt jeder ungesehene Post anhand seiner Ober- und Unterthemen einen berechneten Gewichtungswert. Aus den verfügbaren Posts wird nach diesen Gewichten zufällig ausgewählt; je eine Empfehlung pro personalisierter Sechsergruppe erweitert die Perspektivenvielfalt.

Die dafür eingesetzten Werte (z. B. **3 s = +1, 5 s = +2 insgesamt, Like = +3, Speichern = +4, Kommentare 3 s = +1 und 5 s = +2 insgesamt**) sind didaktisch festgelegte **Simulationsparameter** und keine Rückschlüsse auf interne Instagram-Gewichtungen. Ein geöffnetes Kommentarfenster wird über seine Zeitdauer erfasst; die App kann nicht nachweisen, dass Kommentare wirklich gelesen wurden.

## Pädagogische Begründung

Der Aufbau unterstützt entdeckendes und forschendes Lernen in einer erkennbaren Lernprogression:

**Handeln → Vermuten/Beobachten → Daten analysieren → Hypothese testen → Ergebnisse bewerten → Programmregeln verstehen.**

Das vertraute Feed-Design und jugendnahe Themen ermöglichen einen lebensweltbezogenen Einstieg. Die Schüler*innen erzeugen selbst Daten, die anschließend zum Gegenstand einer kritischen Analyse werden. Dadurch verbinden sich informatische Grundbegriffe (Algorithmus, Daten, Gewichtung, Zufallsauswahl) mit Medienkompetenz (Personalisierung, Perspektivenvielfalt, Filterblase) und Datenschutz.

Insbesondere die Trennung zwischen subjektivem Eindruck und nachfolgendem Diagramm unterstützt eine differenzierte Reflexion: Die Schüler*innen sollen erkennen, dass das Modell lediglich **Signale interpretiert**, dabei Fehler machen kann und Verhaltensdaten nicht mit der Identität oder den tatsächlichen Interessen der Nutzer*innen gleichzusetzen sind.

## Datenschutz und Grenzen

Alle individuellen Experimentdaten, einschließlich der Beobachtungsnotiz, bleiben im JavaScript-Arbeitsspeicher des geöffneten Browser-Tabs. Weder `localStorage` noch `sessionStorage` oder eine Datenbank werden verwendet. **Beim Schließen oder Neuladen** sind diese Daten weg. GitHub Pages kann jedoch unabhängig davon technische Zugriffsprotokolle für die Auslieferung der Dateien führen.

Die Anwendung ist ein **regelbasiertes Lernmodell**, keine Nachbildung eines realen Instagram-Recommenders. Die Beispiele und Kommentare sind fiktiv; die KI-generierten Bilder sind sichtbar gekennzeichnet. In der Praxis können reale Plattformen komplexere Signale, weitere Geschäftsregeln und Datenquellen nutzen. Für den Unterricht muss klar bleiben, dass Personalisierung nicht immer und nicht zwangsläufig zu einer Filterblase führt.

## Prüfung vom 20. November 2026

Automatisierte Chromium-Tests wurden mit einem Desktop-Viewport (1366 × 900) sowie einem mobilen Viewport (390 × 844) ausgeführt. Prüfgegenstände und Ergebnisse:

- **Bild-/Dateiprüfung:** 94 individuelle Bilddateien verfügbar und geladen, keine fehlenden Ressourcen im Test.
- **Startfeed:** genau 30 verschiedene Posts; jedes der acht Themen 3–4 Mal vertreten; zunächst feste Zusammenstellung auch nach einem Like.
- **Personalisierter Feed:** drei Ladeereignisse mit je sechs neuen Posts, insgesamt 48 ohne Duplikate; kein automatisches Nachladen darüber hinaus.
- **Navigation:** Auswertung vor Abschluss von Level 1 gesperrt; Level 2 ist vor Level 3 zu bearbeiten.
- **Auswertung:** acht animierte Themen-Säulen und Vergleichsgrundlage 30 vs. 18.
- **Forschungsmission:** zwei Signalarten inklusive getesteter Hypothese nötig, anschließender Zwölfervergleich und Freigabe der Auflösung funktionieren.
- **Technischer Lauf:** Keine JavaScript-Laufzeitfehler in den automatisierten Tests auf beiden Ansichtsgrößen.

Die Prüfung beweist nicht Fehlerfreiheit auf allen Geräten und ersetzt nicht die Live-Kontrolle nach der späteren GitHub-Pages-Veröffentlichung.
