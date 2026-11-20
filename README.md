# Simulator für endliche Automaten

Ein interaktiver Simulator für deterministische (DEA) und nichtdeterministische endliche Automaten (NEA) im
Browser. Er entstand für die Lehrveranstaltung **Grundlagen der Informatik (GdI)**. Der Automat wird über seine
Übergänge festgelegt. Der Simulator erkennt selbst, ob es ein DEA oder ein NEA ist, und zeigt den Ablauf im
Zustandsdiagramm und, bei NEAs, im Berechnungsbaum.

**Direkt ausprobieren:** [https://flennartz.github.io/gdi-endliche-Automaten/](https://flennartz.github.io/gdi-endliche-Automaten/)

## Funktionen

- **Zwei Ansichten zum Bearbeiten:** Die Übergangsliste hat die Spalten Zustand, Eingabe und Folgezustand. Die
  Zustandstabelle (δ-Matrix) hat Zeilen für die Zustände und Spalten für die Zeichen. Beide zeigen denselben
  Automaten, und man kann jederzeit umschalten.
- **Alphabet und Endzustände:** Σ wird explizit angegeben. Endzustände markiert man per Häkchen. Der Startzustand ist
  immer `s0`.
- **ε-Übergänge** für NEAs.
- **Automatische Einordnung:** DEA oder NEA, mit Begründung. Bei DEAs wird die Vollständigkeit geprüft, ein
  Fehlerzustand lässt sich per Knopf ergänzen. Nicht erreichbare Zustände werden gemeldet.
- **Simulation Zeichen für Zeichen:** Schritt, zurück, automatisch mit einstellbarem Tempo oder sofort bis zum Ende.
  Aktive Zustände pulsieren im Diagramm, zuletzt benutzte Übergänge werden markiert.
- **Berechnungsbaum für NEAs:** Er zeigt alle Rechenwege mit akzeptierenden (✓) und abgebrochenen oder abgelehnten
  (✗) Pfaden.
- **Mehrere Wörter auf einmal testen:** Eine Liste von Wörtern wird sofort mit „akzeptiert“ oder „nicht akzeptiert“
  ausgewertet.
- **NEA → DEA:** Potenzmengenkonstruktion (mit ε-Hülle). Das Ergebnis lässt sich als neuer Automat übernehmen.
- **DEA minimieren:** Tabellenfüllverfahren mit Dreieckstabelle, die zeigt, in welcher Runde und wegen welches Zeichens
  ein Paar markiert wurde. Danach werden die Klassen zusammengefasst.
- **Import und Export** als Markdown mit LaTeX-Notation.
- **Beispiele:**
  - DEA: gerade Anzahl a
  - DEA: endet auf ab (absichtlich nicht minimal)
  - NEA: drittletztes Zeichen ist a
  - NEA mit ε: aⁿbᵐ

## Textformat für den Import

```markdown
Σ = {a, b}
Endzustände: s3

| Zustand | Eingabe | Folgezustand |
| ------ | ------ | ------ |
| $`s_0`$ | a | $`s_0`$ |
| $`s_0`$ | a | $`s_1`$ |
| $`s_1`$ | $`\varepsilon`$ | $`s_2`$ |
```

Mehrere Folgezustände dürfen auch durch Komma getrennt in einer Zelle stehen, z. B. `s0, s1`. Ohne senkrechte Striche
genügt eine Zeile je Übergang, z. B. `s0 a s1`.

## Technik

- Eine einzige Datei `index.html` mit HTML, CSS und JavaScript, ohne externe Bibliotheken und ohne Build-Schritt
- Läuft vollständig im Browser; es werden keine Daten gespeichert oder übertragen

## In Moodle einbinden

Als iframe in einer Textseite (HTML-Quellcode-Ansicht):

```html
<iframe src="https://flennartz.github.io/gdi-endliche-Automaten/" width="100%" height="1800" style="border:0"></iframe>
```

Alternativ eine Aktivität **URL** mit der Darstellung „In neuem Fenster“ oder „Einbetten“ anlegen.

## Lizenz

Dieses Projekt ist gemeinfrei und steht unter [The Unlicense](https://unlicense.org). Es darf ohne Einschränkungen
verwendet, verändert und weitergegeben werden, auch ohne Namensnennung. Details stehen in der Datei `LICENSE`.
