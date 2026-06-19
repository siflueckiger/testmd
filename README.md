## Einleitung

Die Schnittstelle «XLSX: AKJB» wird verwendet, um gegenüber dem Amt für Kind, Jugend und Behindertenangebote (AKJB) in Basel erbrachte SPF-Leistungen in Rechnung zu stellen. Die Leistungen werden detailliert in einer Excel-Datei ausgewiesen.

**Leistungstypen:**
- Facharbeit im Direktkontakt
- Facharbeit im Direktkontakt Online
- Facharbeit ohne Direktkontakte
- Kurzfristige Terminabsage
- Reisekostenpauschale
- Zusatzleistung / Zusatzleistung 2

---

## Konfiguration

> **Hinweis:** Die Konfiguration muss individuell mit der Institution abgesprochen werden (Namen, Tarife, Preise).

### 1. Leistungs-Gruppen erstellen
Pfad: `Einstellungen > Kassabuch & Leistungen > Leistungs-Gruppen`

Es werden zwei Gruppen benötigt:

| Name | Berechnungsgrundlage | Verwendung |
|---|---|---|
| SPF | Tarifbasiert (Stunden oder Betrag) | Alle Leistungsarten mit fixem Tarif |
| zusätzliche Kosten | Individuelle Einzelpreise | Leistungsarten mit individuellen Preisen |

### 2. Leistungsarten erstellen
Pfad: `Einstellungen > Kassabuch & Leistungen > Leistungsarten`

> **Tipp:** Leistungsarten können mit Arbeitsarten der Zeiterfassung verknüpft werden, damit Leistungen automatisch erstellt werden.

| Leistungsart | Gruppe | Erfassung |
|---|---|---|
| Facharbeit mit Direktkontakt | SPF | Stunden von–bis |
| Facharbeit mit Direktkontakt Online | SPF | Stunden von–bis |
| Facharbeit ohne Direktkontakt | SPF | Stunden von–bis |
| Kurzfristige Terminabsage | SPF | Anzahl 1 |
| Reisekostenpauschale | SPF | Anzahl 1 |
| Zusätzliche Kosten | zusätzliche Kosten | Anzahl + Einzelpreis |

### 3. Allgemeine Tarife erstellen
Pfad: `Einstellungen > Rechnungen > Allgemeine Tarife`

> **Empfehlung:** Pro Kanton eine eigene Tarifgruppe erstellen; ebenso separate Gruppen für Reisekostenpauschalen.

Beispiel Tarifgruppen:

| Name | Bemerkung |
|---|---|
| SPF Kanton Basel Stadt | |
| SPF Kanton Basel Land | |
| Reisekostenpauschale CHF 90 | |
| Reisekostenpauschale CHF 120 | |

Tarifkonfiguration innerhalb der Gruppen (`Verrechnungsmodus: Alle Leistungen zum Einzelpreis`):

| Tarif (Gruppe) | Leistungsarten |
|---|---|
| SPF Kanton Basel Stadt/Land | Facharbeit mit/ohne Direktkontakt, Kurzfristige Terminabsage |
| Reisekostenpauschale CHF 90/120 | Reisekostenpauschale |

### 4. Rechnungsvorlage erstellen
Pfad: `Einstellungen > Rechnungen > Rechnungsvorlagen`

Vorlage für SPF-Rechnungen an den Kanton anlegen.

### 5. Schnittstelle aktivieren
Pfad: `Einstellungen > Globale Einstellungen > Schnittstellen > Abschnitt Leistungen`

Im Feld **Export** die Schnittstelle `XLSX: AKJB` wählen. Anschliessend alle Pflichtfelder konfigurieren:

| Feld | Typ | Beschreibung |
|---|---|---|
| Sozialversicherungsnummer | Pflicht | Stammdatenvariable auf dem Klient:innen-Kontakt |
| Leistungsart | Pflicht | Vom Kanton vorgegebener Text, z.B. «Sozialpädagogische Familienbegleitung» |
| Facharbeit im Direktkontakt | Pflicht | Leistungsart(en) für diese Spalte im Excel |
| Facharbeit im Direktkontakt Online | Pflicht | Leistungsart(en) für diese Spalte im Excel |
| Facharbeit ohne Direktkontakt | Pflicht | Leistungsart(en) für diese Spalte im Excel |
| Kurzfristige Terminabsage | Pflicht | Leistungsart(en) für diese Spalte im Excel |
| Reisekostenpauschale | Pflicht | Leistungsart(en) für diese Spalte im Excel |
| Zusatzleistung | Pflicht | Leistungsart(en) für diese Spalte im Excel |
| Zusatzleistung 2 | Optional | Leistungsart(en) für diese Spalte im Excel |

### 6. Kostengutsprache bei Klient:innen-Dossiers hinterlegen
Pfad: `Leistungen > Kostengutsprache > [Gewünschtes Dossier]`

Pro Klient:in und KÜG eine Kostengutsprache erfassen, damit im Excel-Export die Spalten «Beginn der KÜG» und «Ende der KÜG» korrekt befüllt werden.

### 7. Rechnungskonfiguration bei Klient:innen-Dossiers hinterlegen
Pfad: `Rechnungen > Konfiguration > [Dossier] > [Rechnungskonfiguration] > Lasche Optionen`

Unter **Kostengutsprache** die Option **«Referenznummer übernehmen»** aktivieren.

> **Achtung:** Fehlt beim Vorbereiten einer Rechnung eine Kostengutsprache oder werden mehrere gültige gefunden, wird ein Fehler ausgegeben und die Rechnung nicht erstellt.

---

## Test zur Inbetriebnahme

**Voraussetzungen:** Arbeitsarten, Leistungsgruppen, Leistungsarten, Tarifgruppen, Rechnungskonfigurationen und Schnittstelle sind eingerichtet.

1. Kostengutsprache in einem Klient:innen-Dossier erfassen
2. Passende Leistungen zur Kostengutsprache erfassen
3. Rechnung in socialweb vorbereiten und fakturieren
4. Modul **Leistungen** öffnen → Ansicht **Liste** → **«XLSX: AKJB»** klicken
5. Inhalt des Excel-Exports prüfen
6. Export zusammen mit dem Kanton validieren
7. Rechnung stornieren und Leistungen löschen
