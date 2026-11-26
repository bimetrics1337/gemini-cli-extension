# bimetrics für Google Gemini CLI

bimetrics ist die Agent-First-Buchhaltungssoftware für Selbstständige und Unternehmen in Deutschland: Web-App, REST-API und der offizielle Remote-MCP-Server (`https://app.bimetrics.de/mcp`) arbeiten auf demselben GoBD-Buchhaltungskern. Diese Extension verbindet die **Google Gemini CLI** direkt per OAuth 2.1 + PKCE mit deinem bimetrics-Account.

**Stand:** MCP-Version `2026-11-23` (**209–216 produktive MCP-Werkzeuge** plus **4 eingebaute Server-Prompts**). Die vollständige Übersicht steht in der [Tool-Übersicht](https://developer.bimetrics.de/mcp/tools) und im interaktiven [App-zu-MCP-Paritäts-Explorer](https://bimetrics.de/mcp#paritaets-matrix).

## Installation in der Gemini CLI

```sh
gemini extensions install https://github.com/bimetrics1337/gemini-cli-extension
```

Danach in einer Gemini-CLI-Sitzung anmelden:

```text
/mcp auth bimetrics
```

Die OAuth-2.1-Anmeldung mit PKCE öffnet bimetrics im Browser. Dort wählst du ausdrücklich die Unternehmen und Rechte (Lesen oder Lesen und ändern), die du freigeben möchtest. Du brauchst keinen API-Schlüssel und kein Client-Secret; mit `offline_access` bleibt die Verbindung bis zu 30 Tage aktiv und lässt sich jederzeit in bimetrics unter **Einstellungen › KI-Assistenten** widerrufen.

Du brauchst einen bimetrics-Account und ein Unternehmen mit freigeschaltetem MCP-Zugang (als Teammitglied vergibt der Inhaber das MCP-Recht in den Team-Einstellungen). Bei mehreren verbundenen Unternehmen nennst du im Auftrag einfach die gewünschte Firma.

## Warum bimetrics MCP? (App-Parität & GoBD-Beweis)

Im Gegensatz zu schmalen Rechnungs-Konnektoren deckt bimetrics über denselben Domain-Kern alle neun Buchhaltungsbereiche ab:

- **Volle Buchhaltungstiefe:** Belege & Belegpostfach, Bankumsätze & Zahlungsabgleich (inkl. Teil-/Sammelzahlung, Skonto, Fremdwährungs-Kursdifferenz, CSV/CAMT/MT940), Angebote, Auftragsbestätigungen & E-Rechnungen (ZUGFeRD/XRechnung), Mahnwesen & Offene Posten (OPOS), Anlagen & Abschreibungen (AfA), Kassenbuch & Z-Bons, Kostenstellen (`KOST1`), Automatisierungen, Summen- und Saldenliste (SuSa) sowie DATEV-Export-Vorbereitung.
- **Serverseitige System-Vorschau:** Vor dem Festschreiben einer Rechnung, eines Stornos oder einer Rechnungskorrektur, dem Ausstellen von Angebot/AB/Mahnung, dem E-Mail-Versand, dem Löschen von Belegen, dem Kassenmonatsabschluss und dem Start des DATEV-Exports erzwingt der Server eine aktuelle Vorschau und deine ausdrückliche Bestätigung.
- **Öffentliche GoBD-Prüfspur:** Jede MCP-Aktion wird mit Quelle, Verbindung und Person protokolliert und ist in der öffentlichen [Verfahrensbeschreibung (Fassung 13)](https://bimetrics.de/rechtliches/verfahrensbeschreibung) dokumentiert.
- **Ohne Funktions-Paywall:** In jedem bezahlten Tarif ab 9 € netto/Monat enthalten und in der 7-tägigen Testphase mit fairem Tageslimit nutzbar.

## Beispiele

- „Prüfe den letzten Monat vor dem DATEV-Export: fehlende Belege, Buchungsfehler und offene Bankumsätze. Ändere nichts.“
- „Zeige mir alle überfälligen offenen Rechnungen meines Unternehmens mit Betrag und Fälligkeit.“
- „Erstelle für diesen Kontakt einen Rechnungsentwurf und zeige mir vor dem Festschreiben die Vorschau.“
- „Ordne den Bankumsatz der Druckerei Hafenkante mit 2 % Skonto dem offenen Beleg zu und zeig mir das Ergebnis.“
- „Zeig mir die System-Vorschau für den DATEV-Export im letzten Monat. Noch nicht starten.“

## Änderungen, Vorschau und Grenzen

Mit Schreibrechten werden Änderungen an Kontakten, Entwürfen, Belegen, Zuordnungen, Mahnungen, Kassenbuch, Kostenstellen, Anlagen und Layouts direkt in bimetrics wirksam. Kritische Vorgänge (Festschreiben, Ausstellen, E-Mail-Versand, Beleg löschen, Kassenmonatsabschluss, DATEV-Export) laufen nur nach aktueller System-Vorschau und deinem ausdrücklichen Ja.

Die Extension reicht keine Steueranmeldungen (ELSTER) ein, löst keine Banküberweisungen aus und ersetzt keine Steuerberatung. Die fertige DATEV-Datei lädst du in der bimetrics-App unter **Einstellungen › Exporte** herunter.

## Hilfe, Nachweise und Lizenz

- [MCP & App-Paritäts-Explorer](https://bimetrics.de/mcp#paritaets-matrix)
- [Leitwerk: Agent-First-Buchhaltung](https://bimetrics.de/ratgeber/agent-first-buchhaltung)
- [DATEV & MCP für Steuerkanzleien](https://bimetrics.de/datev-mcp)
- [Öffentliche GoBD-Verfahrensbeschreibung (Fassung 13)](https://bimetrics.de/rechtliches/verfahrensbeschreibung)
- [Maschinenlesbares Faktenblatt (llms-full.txt)](https://bimetrics.de/llms-full.txt)
- [Entwicklerdoku zum MCP-Server](https://developer.bimetrics.de/mcp)
- [Support](mailto:support@bimetrics.de)

---

### Overview (EN)

Official **bimetrics** extension for **Google Gemini CLI** (`https://app.bimetrics.de/mcp`, MCP version `2026-11-23`), connecting via OAuth 2.1 + PKCE with zero API keys. Built on the exact same GoBD accounting domain core as the bimetrics Web App and REST API (**209–216 live tools + 4 built-in server prompts** across 9 domains: receipts, bank matching with cash discount & FX differences, ZUGFeRD/XRechnung e-invoices, dunning/OPOS, fixed assets/AfA, cash book/Z-Bon, cost centers `KOST1`, trial balance, and DATEV export). Protected by server-enforced preview gates (no bank transfers, no ELSTER filing). Included in every paid plan from 9 €/month net (plus 7-day free trial).

Diese Extension steht unter der [MIT-Lizenz](LICENSE). Die Lizenz betrifft die Dateien dieses Pakets. Sie erteilt keine Rechte am gehosteten bimetrics-Backend und ersetzt keine Vereinbarung für den bimetrics-Dienst.
