# Richtlinie für KI-Nutzung, Code-Quality & Human Testing

Für den Einsatz von KI gelten bei Langmeier Software GmbH die folgenden Grundsätze. Sie orientieren sich an der OWASP-Liste **„Top 10 Risks for LLM Applications“ (2025)**.

## 1. Verantwortung und Haftung des Software-Architekten

### 1.1 Verantwortung
Der Software-Architekt muss jede eingecheckte Zeile Code jederzeit erklären können. Die Verantwortung für den Code bleibt vollumfänglich beim Menschen, welcher als Software-Architekt agiert und für die von ihm getroffenen technologischen Entscheidungen verantwortlich ist.

### 1.2 Arbeitsrechtliche Haftung
Verstößt der Software-Architekt oder Entwickler vorsätzlich oder grob fahrlässig gegen die Vorgaben dieses Reglements – insbesondere, aber nicht beschränkt auf Lizenzprüfungen, Verstöße gegen Datenschutzbestimmungen oder die Nichteinhaltung des Überprüfungsgebots von KI-Code –, haftet er im Rahmen der gesetzlichen Bestimmungen (insb. Art. 321e OR) für die dem Unternehmen oder Dritten dadurch entstehenden Schäden.

## 2. KI-Nutzung, Sicherheits- und Compliance-Vorgaben

### 2.1 Allgemeines Überprüfungsgebot (Human Review Mandate)
Sämtlicher durch KI-Tools oder KI-Agenten generierte Output (Quellcode, Testfälle, Konfigurationen und Dokumentationen) unterliegt einem strikten manuellen Überprüfungsgebot. Kein KI-generierter Inhalt darf ohne vorherige inhaltliche, logische und sicherheitstechnische Prüfung durch den Software-Architekten oder Entwickler in die Versionsverwaltung (Repository) eingecheckt oder in Produktion übernommen werden.

### 2.2 Zugriffsverbot für KI-Agenten auf Produktivsysteme
KI-Agenten erhalten unter keinen Umständen Zugriff auf produktive Datenbanken und produktive Systeme.

### 2.3 Isolierung von Produktivzugängen und API-Schlüsseln
Produktive Zugangscodes und API-Schlüssel bleiben strikt ausserhalb des Scope von KI-Agenten.

### 2.4 Kopplung von Routen und Endpunkten an konkrete Use-Cases
API-Routen und Ajax-Endpunkte werden ausschliesslich für konkrete Anwendungsfälle (Use Cases) erstellt.

### 2.5 Zentrale Input-Validierung
Jede API-Route und jeder Ajax-Endpunkt prüft sämtliche Eingaben zuerst mit einer zentralen Engine zur Input-Validierung.

### 2.6 Verbot von freier Datenbank- und Dateisystem-Exposition
Es werden keine API-Routen oder Ajax-Endpunkte erstellt, die frei auf die Datenbank oder auf die Festplatte/den Speicher der Server zugreifen können, weder lesend noch schreibend.

### 2.7 Lizenzprüfung und Haftung bei Schutzrechtsverletzungen
KI-generierter Code wird vor dem Einchecken daraufhin geprüft, ob er Lizenzen und Rechte Dritter verletzt. Der Software-Architekt haftet persönlich für monetäre Ansprüche Dritter, wenn durch den von ihm eingecheckten Code Lizenzen oder Rechte von Dritten verletzt werden, oder wenn diese Ansprüche oder Nutzungsentgelte geltend machen.

### 2.8 Bring Your Own AI (BYOAI)
Der Software-Architekt bezahlt für die von ihm verwendeten KI-Tools selbst.

### 2.9 Datenschutz, Vertraulichkeit und Schutz von Betriebsgeheimnissen

#### Verbot vertraulicher Datenübermittlung
Es ist strikt untersagt, personenbezogene Daten (z. B. Kunden-, Mitarbeiter- oder Lieferantendaten), Zugangsdaten, Passwörter, Geschäftsgeheimnisse oder geschützte interne Quellcodes in externe oder öffentliche KI-Modelle einzugeben oder als Prompt/Context hochzuladen.

#### Vorgaben für BYOAI-Tools (Commercial Use & Data Privacy)
Bei der Nutzung von „Bring Your Own AI“ (BYOAI) dürfen ausschließlich KI-Tools und Tarife genutzt werden, deren Nutzungsbedingungen (Terms of Service) explizit garantieren, dass eingegebene Daten und Prompts nicht zum Training der KI-Modelle verwendet und nicht dauerhaft durch den Anbieter gespeichert werden (z. B. Business/Enterprise-Tiers mit Opt-out für Model Training). Die Nutzung kostenloser Consumer-Varianten ohne Datenschutzgarantien ist für geschäftliche Zwecke untersagt.

### 2.10 Urheberrecht und Schöpferhöhe bei KI-Einsatz
Sämtliche Rechte an KI-unterstützt erstelltem Code, Testfällen und Dokumentationen stehen uneingeschränkt dem Unternehmen zu, unabhängig davon, ob diese während oder außerhalb der regulären Arbeitszeit erstellt wurden. Rein KI-generierter Code erfüllt nach internationalen Standards nicht die Voraussetzungen für einen Urheberrechtsschutz (Copyright) und darf nicht eingecheckt werden.

Der Software-Architekt sowie die beteiligten Entwickler haben durch aktives, menschliches und wertschöpfendes Zutun (z. B. substanzielle Überarbeitung, individuelle Anpassung oder Erweiterung) sicherzustellen, dass der Code die erforderliche Schöpferhöhe erreicht, um rechtlichen Schutz für das Unternehmen zu gewährleisten.

### 2.11 Qualität und Prüfung von Code-Kommentaren
Von KI-Agenten generierte Kommentare dürfen nicht ungeprüft übernommen werden. Sämtliche Kommentare müssen vom Entwickler auf Richtigkeit, Prägnanz und Mehrwert geprüft und gegebenenfalls manuell überarbeitet oder gekürzt werden. Redundante, generische oder unverständliche KI-Erklärungen sind vor dem Einchecken zu entfernen.

### 2.12 Bestandsschutz von Kernkomponenten und Engines
Bestehende Kernkomponenten und Engines (z. B. API-Architektur, Payment-Gateways, Template- oder Form-Engines, hauseigene Code- & Funktions-Bibliotheken) dürfen nicht durch KI-generierten Code, Refactorings oder automatistische KI-Versionsupdates ersetzt, umgangen oder in ihrer Funktionsweise grundlegend verändert werden. Ausnahmen erfordern eine vorherige schriftliche Zustimmung der Geschäftsleitung.

### 2.13 Kennzeichnungspflicht und EU AI Act Compliance

#### Transparenz gegenüber Endkunden
Sofern in Produkten der Langmeier Software GmbH KI-generierte Inhalte (Texte, Bildmaterial, Code) oder interaktive KI-Systeme (z. B. Chatbots) zum Einsatz kommen, sind diese gemäß den Vorgaben des EU AI Act (Künstliche Intelligenz-Verordnung) für den Endnutzer klar und unzweideutig als KI-generiert bzw. KI-gestützt zu kennzeichnen.

#### Verbot von Risikoklassen
Der Einsatz von KI-Systemen, die unter das Verbot des EU AI Act fallen (z. B. unzulässige Verhaltensbeeinflussung oder Biometrie-Scoring), ist im gesamten Unternehmen ausnahmslos untersagt.

### 2.14 Sicherheit von KI-Komponenten im Produkt (Prompt Injection & System Prompts)

#### Schutz vor Prompt Injection (OWASP LLM01)
Sofern KI-Agenten oder LLM-Schnittstellen direkt in Produkte oder Services der Langmeier Software GmbH integriert werden, sind geeignete technische und organisatorische Maßnahmen zum Schutz vor direkter und indirekter Prompt Injection umzusetzen. Nicht vertrauenswürdige Benutzer- und Fremdinhalte dürfen nicht ungeprüft als vertrauenswürdige Instruktionen verarbeitet werden. Insbesondere sind eine klare Trennung von Systeminstruktionen und nicht vertrauenswürdigen Inhalten, serverseitige Autorisierungs- und Validierungsprüfungen für Tool- und Funktionsaufrufe sowie das Prinzip der geringstmöglichen Berechtigungen sicherzustellen.

#### Absicherung von System-Prompts (OWASP LLM02 / LLM06)
System-Prompts, Instruction-Sets und interne Agenten-Logiken sind als vertrauliche Systemkomponenten zu behandeln. Sie müssen gegen Information Leakage und Exfiltration durch Manipulationstechniken (z. B. „Ignore previous instructions“) abgesichert werden.

#### Human-in-the-Loop & Agency-Begrenzung (OWASP LLM08)
KI-Agenten dürfen keine eigenständigen, unumkehrbaren Aktionen (wie das Löschen von Daten, das Ausführen von Finanztransaktionen oder das Ändern von Systemkonfigurationen) ohne explizite, manuelle Freigabe durch einen menschlichen Nutzer oder Operator durchführen.

## 3. Human Testing & Usability-Standards
Kein automatisierter oder maschineller Test ersetzt die echte menschliche Nutzung. Jede Softwarekomponente muss vor der Freigabe durch manuelle Tests auf fachliche Korrektheit, Nutzbarkeit und Einhaltung moderner UX/UI-Industriestandards geprüft werden.

### 3.1 Fachlogik und Grundlagen
- **Korrekte Fachlogik:** Die Software muss von Menschen gründlich auf die korrekte und vollständige Abbildung der fachlichen Geschäftsprozesse und Sonderfälle durchgetestet werden.
- **Sicherheitsprüfungen:** Manuelle Tests und Penetrationstests zur Schwachstellenfindung werden bevorzugt auf Test- oder Staging-Umgebungen durchgeführt.

### 3.2 Usability- und UI/UX-Industriestandards
Beim manuellen Testing wird die Anwendung zwingend auf folgende Usability-Kriterien überprüft:

- **Verständliche Empty States:** Wo keine Daten vorhanden sind (z. B. leere Tabellen, neue Accounts), müssen verständliche Hilfeseiten oder Hinweistexte inklusive Handlungsanweisung angezeigt werden.
- **Barrierefreiheit (Barrier-freeness):** Die Oberfläche muss barrierearm gestaltet sein (z. B. ausreichende Farbkontraste, Tastaturbedienbarkeit, lesbare Schriftgrössen).
- **Kontextuelle Orientierung:** Der Nutzer muss in jedem Schritt der Anwendung genau wissen, wo er sich befindet, woher er kommt und was als Nächstes zu tun ist.
- **Saubere & klare Informationsarchitektur:** Logische Strukturierung von Menüs, Inhalten und Funktionen ohne unnötige Verschachtelung.
- **Klare Nutzer-Handlungsaufforderungen & Wording:** Buttons und Interaktionselemente tragen eindeutige, verständliche Bezeichnungen (z. B. „Speichern“ oder „Kostenpflichtig bestellen“ statt unklarer Beschriftungen). Die Sprache ist durchgängig präzise und frei von Fach-Jargon.

#### Dynamische Datenaktualisierung & Server-Driven HTML (htmx)
- **Standard:** Bei einfachen Input/Output-Anwendungsfällen (z. B. klassische Formular-Übermittlungen mit vollständigem Seitenaufruf) sind reguläre Seitenaufrufe (Page Refreshes) zulässig.
- **Dynamische Updates:** Bei Teildaten-Updates (z. B. Statusänderungen, Tabellen-Reloads, Push-Benachrichtigungen) darf kein manueller Komplett-Refresh der Seite erforderlich sein. Hierfür ist die jeweilige Region dynamisch über das zugelassene Framework htmx (Server-Driven HTML Hot-Reload) zu aktualisieren.
- **Verbotene Client-Frameworks:** Zur Vermeidung unnötiger Komplexität, Sicherheitsrisiken und Wartungsaufwände ist der Einsatz von JavaScript-Heavy-SPA-Frameworks (z. B. React, Angular, Vue) sowie veralteten Ajax-Bibliotheken (z. B. jQuery) strikt untersagt.

- **Nützliche Go-Back-Pfade:** Es sind klare und verlässliche Wege zur Rückkehr enthalten (z. B. Breadcrumbs, funktionierende Zurück-Buttons), ohne dass der Zustand der Anwendung verloren geht.
- **Nutzung von UI-Standard-Elementen:** Verwendung etablierter UI-Komponenten und Design-Patterns, damit sich Nutzer ohne Einarbeitung sofort zurechtfinden.
- **Responsiveness für Mobile Devices:** Die Benutzeroberfläche muss auf mobilen Geräten und unterschiedlichen Bildschirmgrössen ohne Darstellungs- oder Funktionsfehler bedienbar sein.

## 4. Inkrafttreten und Revision
Dieses Reglement tritt mit der Unterschrift der Geschäftsleitung in Kraft. Die Geschäftsleitung überprüft es mindestens einmal jährlich und passt es bei wesentlichen betrieblichen Änderungen an. Jede Änderung erfasst die Geschäftsleitung mit Versionsnummer, Datum und Änderungsgrund in der Versionstabelle am Anfang dieses Dokuments.

Name: _____________________  
Funktion: _____________________  
Datum: _____________________  
Ort: _____________________  
Unterschrift: _____________________
