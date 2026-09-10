# Druk Yul — Das Quiz

Interaktives Bhutan-Quiz für einen Infostand. Ausgelegt für ein iPad, das
den ganzen Tag am Stand steht: wählbare Rundenlänge, große Tippflächen,
sofortige Rückmeldung mit einer kurzen Erklärung zu jeder Frage, und ein
automatischer Rücksprung zum Startbildschirm nach 90 Sekunden ohne
Berührung, damit der nächste Besucher ein frisches Quiz vorfindet.

## Inhalt

26 Fragen aus der Vorlage, in vier Kapiteln:

| Kapitel | Fragen |
|---|---|
| Schule | 3 |
| Geografie | 6 |
| Geschichte und Politik | 3 |
| Religion, Kultur und Essen | 14 |

Die Antwortmöglichkeiten werden bei jedem Durchlauf neu gemischt, damit sich
keine Position einprägt. Die Frage nach den Nachbarländern erwartet zwei
Antworten (Indien und China) und wird mit „Antwort prüfen“ bestätigt.

## Rundenlänge

Vor dem Start lässt sich wählen, wie viele Fragen die Runde umfasst: **3, 5,
10, 15 oder alle 26**. Voreingestellt sind 10 — zu ändern über `DEFAULT_LEN`
in `index.html`; die Auswahl selbst steht in `LENGTHS` direkt darüber.

Die Fragen werden bei jeder Runde neu gezogen und in zufälliger Reihenfolge
gestellt. Gezogen wird dabei **reihum aus den vier Kapiteln** (`drawOrder`),
damit eine kurze Runde nicht zufällig nur aus Essensfragen besteht — bei drei
Fragen kommen so immer drei verschiedene Kapitel vor, ab fünf Fragen alle
vier. Wer stattdessen rein zufällig ziehen möchte, ersetzt den Rumpf von
`drawOrder` durch ein `shuffle` über alle Fragenindizes.

Die Auswertung am Ende zeigt nur die Kapitel, die in der Runde tatsächlich
vorkamen. Die gewählte Länge bleibt erhalten — auch nach „Noch einmal“ und
nach dem automatischen Rücksprung —, sodass sie sich für den Standtag einmal
einstellen lässt.

## Gestaltung

Die Farben stammen vom **Kemar-Band**, dem ockerroten Streifen mit
Messingscheiben, der an jeder Dzong-Mauer umläuft — er bildet den
Seitenhintergrund und die Oberkante jeder Karte. Die vier Kapitel tragen vier
der fünf **Gebetsfahnen-Farben** (Wasser, Himmel, Luft, Erde); die fünfte,
das Feuerrot, ist der Grund der Seite. Das Ergebnis wird als
**Bruttonationalglück** ausgegeben, Bhutans eigenem Wohlstandsmaß.

Schriften: *Eczar* für Überschriften und *Mukta* für den Fließtext — beide
sind Devanagari-Latein-Familien aus der Region.

Bewusst einfarbig gestaltet (kein Hell/Dunkel-Wechsel): Das Display am Stand
soll unabhängig von der iPad-Einstellung immer gleich aussehen.

## Betrieb am Stand

`index.html` ist eine einzelne Datei ohne Abhängigkeiten außer den Schriften
von Google Fonts. Zum Aufstellen im Safari öffnen und über
**Teilen → „Zum Home-Bildschirm“** ablegen; von dort startet die Seite im
Vollbild ohne Browserleiste. Für den Dauerbetrieb empfiehlt sich zusätzlich
*Einstellungen → Anzeige & Helligkeit → Automatische Sperre → Nie* sowie der
geführte Zugriff (*Bedienungshilfen → Geführter Zugriff*), damit niemand aus
dem Quiz herausnavigiert.
