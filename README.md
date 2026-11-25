# Von der Kundenanfrage zum Auftrag

Interaktive Demo: Eine Kundenanfrage für ein Netzteil läuft durch fünf Schritte. Die Angaben werden aus dem Mailtext gelesen, die Anfrage wird qualifiziert, für passende Anfragen entsteht ein Entwurf für das ERP, danach folgen ein Blick auf Wartezeiten im Prozess und eine Bewertung möglicher KI-Ansätze.

**Demo öffnen:** https://rroessger.github.io/anfrage-auftrag-demo/

Erstellt im November 2026 von René Rößger für eine Bewerbung als Spezialist für KI und ERP-Prozesse. Dauer eines Durchlaufs: etwa 5 bis 10 Minuten.

## Was die Demo zeigt

1. **Eingang (Dokumentenverarbeitung):** Feste Regeln lesen Ausgangsspannung, Ausgangsstrom, Stückzahl, Zieltermin, Einsatzumfeld, Sonderwünsche und Normen aus dem Text. Treffer sind markiert, fehlende Felder als "nicht gefunden".
2. **Qualifizieren:** Vollständigkeit, Aufwand, Potenzial und Dringlichkeit ergeben eine Ampel mit Begründung: Rückfragen nötig (mit Entwurf der Rückfrage), Standardweg ohne Sonderanfertigung oder weiter an Technik und Arbeitsvorbereitung. Kein Kundenscore, kein CRM.
3. **Übergabe ans ERP (Vorschau):** Entwurf für Kundenauftrag, Artikel-Stammdaten und eine Aufgabe für die Arbeitsvorbereitung, als Felderliste und als JSON. Prüfregeln blockieren unplausible Werte, ein Mensch gibt frei. Generisches Datenmodell, kein bestimmtes ERP-Produkt.
4. **Prozess ansehen:** Bearbeitungszeit und Wartezeit je Schritt, Durchlaufzeit, Anteil Wartezeit und die acht Verschwendungsarten. Die Startwerte sind Beispielannahmen.
5. **KI-Chancen bewerten:** Vier Ansätze nach Nutzen, Aufwand, Risiko, Datenschutz, Geheimhaltung und EU-KI-Verordnung. Die Einschätzungen sind Hypothesen.

Drei erfundene Anfragen stehen zur Auswahl (vollständig, unvollständig, kein Fall für eine Sonderanfertigung). Eine eigene Anfrage lässt sich einfügen.

Je Schritt zeigt ein aufklappbarer Block "So entscheidet die Demo" die Regeln, Felder und Schwellenwerte. Er wird aus denselben Konstanten erzeugt, die auch die Logik nutzt.

## Was simuliert ist

- Alle Anfragen, Firmen und Zeiten sind erfunden. Der Hersteller "Beispiel Stromversorgung GmbH" ist fiktiv. Die Demo beschreibt keine internen Abläufe eines bestimmten Unternehmens.
- Die "KI-Schritte" sind feste Regeln (reguläre Ausdrücke und Schwellenwerte). Es ist kein Sprachmodell eingebaut. Ein freier Text kann deshalb unvollständig ausgewertet werden.
- Es gibt kein echtes ERP. Die Vorschau ist nur eine Anzeige, die Demo schreibt nirgends hin.
- Die Zahlen im Prozessschritt stammen aus Beispielannahmen und Ihren Eingaben. Sie zeigen die Methode, keine gemessene Wirkung.

## Datenschutz und Technik

- Eine einzelne Datei `index.html` mit HTML, CSS und JavaScript. Keine externen Bibliotheken, Schriften, Bilder oder Tracker, keine Cookies, kein Server, kein lokaler Speicher.
- Strikte Content-Security-Policy: Das Skript ist per SHA-256-Hash freigegeben, Anfragen an andere Adressen sind gesperrt.
- Eingaben bleiben im Browserfenster und sind nach dem Schließen weg.
- Die Datei funktioniert auch lokal ohne Internet: herunterladen und im Browser öffnen.
- Inhalte, Regeln und Schwellenwerte stehen als Konstanten am Anfang des Skripts (`CASES`, `R`, `TERMIN_REGELN`, `UMFELD_REGELN`, `SONDER_REGELN`, `Q`, `CHECK`, `PROZESS`, `ANSAETZE`). Wer das Skript ändert, muss den Hash in der Content-Security-Policy neu berechnen.

## Was eine echte Lösung bräuchte

Zugriff auf Postfach, Dokumente und ERP mit Rechteprüfung, eine Datenschutzprüfung, eine Einordnung nach EU-KI-Verordnung, die Einbindung von IT-Sicherheit und Betriebsrat und einen Pilot mit Anwendern und Messung des Ist-Zustands.

## Entstehung

Mit Claude Code gebaut (Agentic Coding). Geprüft durch automatische Durchläufe aller drei Fälle und einer eigenen Anfrage in Edge (Entscheidungen, Prüfregeln, Freigabe, keine Netzwerkanfragen, keine Cookies, kein lokaler Speicher, keine Konsolenfehler) sowie Sichtprüfung auf Handy- und Desktopbreite.

## Lizenz

MIT, siehe [LICENSE](LICENSE).
