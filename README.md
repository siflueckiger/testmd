## Einleitung

Die Schnittstelle «XLSX: AKJB» wird verwendet, um gegenüber dem Amt für Kind, Jugend und Behindertenangebote (AKJB) in Basel erbrachte SPF-Leistungen in Rechnung zu stellen. Dabei werden die Leistungen für die vorgegebenen Leistungstypen detailliert in einer Excel-Datei ausgewiesen:

- Facharbeit im Direktkontakt
- Facharbeit im Direktkontakt Online
- Facharbeit ohne Direktkontakte
- Kurzfristige Terminabsage
- Reisekostenpauschale
- Zusatzleistung
- Zusatzleistung 2

## Konfiguration und Inbetriebnahme

### Konfiguration

Damit die Schnittstelle «XLSX: AKJB» verwendet werden kann, sind folgende Konfigurationen vorzunehmen:

- Leistungs-Gruppen erstellen
- Leistungsarten erstellen
- Allgemeine Tarife erstellen
- Rechnungsvorlage erstellen
- Schnittstelle aktivieren
- Kostengutsprache bei Klient:innen-Dossiers hinterlegen
- Rechnungskonfigurationen bei Klient:innen-Dossiers hinterlegen

**Hinweis – Individuelle Konfiguration**

Die jeweilige Konfiguration muss mit der Institution abgesprochen werden. Informationen wie Namen der Leistungs-Gruppen, Leistungsarten, Tarif (Gruppe) und Preise müssen von der Institution definiert werden.

### Leistungs-Gruppen

Pfad: `Einstellungen > Kassabuch & Leistungen > Leistungs-Gruppen`

Es werden zwei Leistungs-Gruppen benötigt. Eine für tarifbasierte Leistungen und eine für Leistungen zum individuellen Einzelpreis. Der Name der Leistungsgruppen kann individuell gewählt werden.

| Name der Leistungsgruppe | Berechnungsgrundlage | Kosten-Art der Kostengutsprache | Bemerkung |
|---|---|---|---|
| SPF | Tarifbasierte Kosten | Stunden: Anzahl Stunden – werden direkt nach der Leistungserfassung abgezogen. Betrag: Geldbetrag – wird erst nach Fakturierung der Leistungen abgezogen. | Für alle Leistungsarten, welche nach einem fixen Tarif verrechnet werden. |
| zusätzliche Kosten | Individuelle Einzelpreise | Je nach Art der Kostengutsprache. In der Regel «Betrag». | Für alle Leistungsarten, welche zu individuellen Preisen verrechnet werden. |

### Leistungsarten

Pfad: `Einstellungen > Kassabuch & Leistungen > Leistungsarten`

Nachfolgend eine Übersicht über die Leistungsarten, welche in socialweb konfiguriert werden müssen.

**Hinweis – Verknüpfung mit Zeiterfassung**

Ist das Modul Zeiterfassung lizenziert, können Leistungsarten mit den passenden Arbeitsarten verknüpft werden. So werden Leistungen über die Zeiterfassung der Fachmitarbeitenden automatisch erstellt. Im Modul Leistungen müssen nur noch jene Leistungen erfasst werden, die nicht über die Zeiterfassung erfasst werden können.

| Leistungsart | Leistungs-Gruppe | Hinweis zur Erfassung |
|---|---|---|
| Facharbeit mit Direktkontakt | SPF | Werden als Stunden von – bis erfasst |
| Facharbeit mit Direktkontakt online | SPF | Werden als Stunden von – bis erfasst |
| Facharbeit ohne Direktkontakt | SPF | Werden als Stunden von – bis erfasst |
| Kurzfristige Terminabsage | SPF | Wird als Leistung mit der Anzahl 1 erfasst |
| Reisekostenpauschale | SPF | Wird als Leistung mit der Anzahl 1 erfasst |
| Zusätzliche Kosten | zusätzliche Kosten | Wird als einzelnes Objekt mit der entsprechenden Anzahl und dem Einzelpreis erfasst |

### Tarif (Gruppe)

Pfad: `Einstellungen > Rechnungen > Allgemeine Tarife`

Nachfolgend eine Übersicht über die Tarife (Gruppen), welche in socialweb konfiguriert werden müssen. Die Namen der Tarif (Gruppen) dienen als Beispiel und müssen mit der Institution definiert werden.

**Hinweis – Unterschiedliche Tarife für unterschiedliche Kantone**

Da die Tarife für Facharbeit je Kanton unterschiedlich festgelegt werden, empfiehlt es sich, pro Kanton eine Tarifgruppe zu erstellen. Auch für die Reisekostenpauschalen empfiehlt es sich, eigene Tarifgruppen pro Pauschale zu verwenden. Werden für Kantone und Reisekostenpauschalen separate Tarifgruppen eingesetzt, können diese in der Rechnungskonfiguration pro Klient:innen-Dossier einfach ausgewählt werden.

| Name | Bemerkung |
|---|---|
| SPF Kanton Basel Stadt | – |
| SPF Kanton Basel Land | – |
| Reisekostenpauschale CHF 90 | – |
| Reisekostenpauschale CHF 120 | – |
| … | |

#### Tarifkonfigurationen innerhalb der Tarife (Gruppe)

Pfad: `Einstellungen > Rechnungen > Allgemeine Tarife > [innerhalb der jeweiligen Gruppe] > Tarif`

Nachfolgend eine Übersicht über die Tarifkonfigurationen innerhalb der Tarife (Gruppen), welche in socialweb konfiguriert werden müssen.

| Tarif (Gruppe) | Leistungsarten | Verrechnungsmodus pro Monat | Einzelpreis |
|---|---|---|---|
| SPF Kanton Basel Stadt | Facharbeit mit Direktkontakt, Facharbeit mit Direktkontakt online, Facharbeit ohne Direktkontakt | Alle Leistungen zum Einzelpreis | Preis, zu welchem diese drei Leistungen verrechnet werden sollen |
| SPF Kanton Basel Stadt | Kurzfristige Terminabsage | Alle Leistungen zum Einzelpreis | Preis, zu welchem diese Leistung verrechnet werden soll |
| SPF Kanton Basel Land | Facharbeit mit Direktkontakt, Facharbeit mit Direktkontakt online, Facharbeit ohne Direktkontakt | Alle Leistungen zum Einzelpreis | Preis, zu welchem diese drei Leistungen verrechnet werden sollen |
| SPF Kanton Basel Land | Kurzfristige Terminabsage | Alle Leistungen zum Einzelpreis | Preis, zu welchem diese Leistung verrechnet werden soll |
| Reisekostenpauschale CHF 90 | Reisekostenpauschale | Alle Leistungen zum Einzelpreis | Preis, zu welchem diese Leistung verrechnet werden soll |
| Reisekostenpauschale CHF 120 | Reisekostenpauschale | Alle Leistungen zum Einzelpreis | Preis, zu welchem diese Leistung verrechnet werden soll |
| … | | | |

### Kostengutsprachen pro Klient:innen-Dossier

Pfad: `Leistungen > Kostengutsprache > [Gewünschtes Dossier]`

Damit in der AKJB-Excel in den Spalten «Beginn der KÜG» und «Ende der KÜG» ein Datum erscheint, muss pro Klient:in und KÜG eine entsprechende Kostengutsprache in socialweb erfasst sein.

### Rechnungskonfiguration

Pfad: `Rechnungen > Konfiguration > [Gewünschtes Dossier] > [Gewünschte Rechnungskonfiguration] > Registerkarte Optionen`

Damit das Beginn- und Enddatum der jeweiligen Kostengutsprache verwendet wird, muss in der jeweiligen Rechnungskonfiguration konfiguriert werden, dass die Referenznummer der Kostengutsprache auf die Rechnung übernommen wird, welche zu den Leistungen gehört, welche durch die Rechnungskonfiguration verarbeitet werden sollen.

Dies geschieht in der Lasche «Optionen» über den Punkt «Kostengutsprache», «Referenznummer übernehmen».

Fehlt bereits beim Vorbereiten einer Rechnung eine Kostengutsprache oder werden mehrere gültige Kostengutsprachen gefunden, so wird ein Fehler ausgegeben und die Rechnung wird nicht erstellt.

### Schnittstelle aktivieren

Pfad: `Einstellungen > Globale Einstellungen > Schnittstellen > Abschnitt Leistungen`

Wähle im Feld Export die Schnittstelle «XLSX: AKJB».

Die benötigten Felder für die Schnittstelle «XLSX: AKJB» werden nun angezeigt. Die Inhalte der Felder sind mit der Person abzustimmen, welche innerhalb der Institution für die Leistungsabrechnung mit dem Kanton zuständig ist.

Nachfolgend eine Übersicht über die Felder, welche konfiguriert werden können:

| Feld | Typ | Beschreibung |
|---|---|---|
| Sozialversicherungsnummer | Pflichtfeld | Stammdatenvariable, welche auf dem Kontakt der Klient:innen-Dossiers geführt wird. Enthält die Sozialversicherungsnummer der Klient:in. |
| Leistungsart | Pflichtfeld | Achtung: Dies ist KEINE in socialweb konfigurierte Leistungsart, sondern ein Text, welcher vom Kanton vorgegeben wird. Beispiel: «Sozialpädagogische Familienbegleitung» |
| Facharbeit im Direktkontakt | Pflichtfeld | Eine oder mehrere Leistungsarten, welche im Excel-Export in der Spalte «Facharbeit im Direktkontakt in Std.» ausgegeben werden. |
| Facharbeit im Direktkontakt Online | Pflichtfeld | Eine oder mehrere Leistungsarten, welche im Excel-Export in der Spalte «Facharbeit im Direktkontakt Online in Std.» ausgegeben werden. |
| Facharbeit ohne Direktkontakt | Pflichtfeld | Eine oder mehrere Leistungsarten, welche im Excel-Export in der Spalte «Facharbeit ohne Direktkontakte in Std.» ausgegeben werden. |
| Kurzfristige Terminabsage | Pflichtfeld | Eine oder mehrere Leistungsarten, welche im Excel-Export in der Spalte «Kurzfristige Terminabsage» ausgegeben werden. |
| Reisekostenpauschale | Pflichtfeld | Eine oder mehrere Leistungsarten, welche im Excel-Export in der Spalte «Reisekostenpauschale» ausgegeben werden. |
| Zusatzleistung | Pflichtfeld | Eine oder mehrere Leistungsarten, welche im Excel-Export in der Spalte «Zusatzleistung» ausgegeben werden. |
| Zusatzleistung 2 | Optional | Eine oder mehrere Leistungsarten, welche im Excel-Export in der Spalte «Zusatzleistung2» ausgegeben werden. |

## Test zur Inbetriebnahme

### Bevor du beginnst

Bevor du mit dem Test beginnst, solltest du:

- Arbeitsarten, Leistungsgruppen & Leistungsarten, Tarifgruppen, Rechnungskonfigurationen eingerichtet haben
- Die Schnittstelle aktiviert und entsprechend mit den Leistungsarten etc. konfiguriert haben

### Testfall «Neue Rechnung»

1. Erfasse eine Kostengutsprache in einem Klient:innen-Dossier
2. Erfasse Leistungen passend zur Kostengutsprache aus dem vorherigen Schritt
3. Erstelle eine Rechnung (Vorbereiten und Fakturieren) in socialweb
4. Gehe wieder zurück ins Modul «Leistungen», öffne die Ansicht «Liste» und klicke auf «XLSX: AKJB»
5. Prüfe den Inhalt des AKJB-Excel-Exports
6. Validiere zusammen mit dem Kanton, ob der Export so in Ordnung ist
7. Die Rechnung wieder stornieren und die Leistungen löschen
