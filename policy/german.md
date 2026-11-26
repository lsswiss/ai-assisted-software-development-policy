# Richtlinie für KI-Nutzung, Code-Qualität & Human Testing

Für den Einsatz von KI gelten bei [Company] die folgenden Grundsätze. Sie orientieren sich an der OWASP-Liste **„Top 10 Risks for LLM Applications“ (2025)**.

## 1. Verantwortung und Rollenverständnis des Software-Architekten

### 1.1 Aufgabenbereich und Rollenverständnis
Der Unterzeichner nimmt im Rahmen seiner Tätigkeit für [Company] die Funktion eines Software-Architekten für Software und technologische Dienste wahr.

Sein Aufgabenbereich umfasst insbesondere die Konzeption, Architektur, Entwicklung, Implementierung, Integration, Prüfung und Weiterentwicklung von Softwarelösungen und technologischen Diensten. Dazu zählen unter anderem SaaS-Anwendungen, mobile Anwendungen, Web-Lösungen, Desktop-Software, API-Dienste, SOAP-Schnittstellen sowie sonstige softwarebasierte Systeme und Technologien.

Der Software-Architekt versteht sich ausdrücklich nicht als sogenannter Vibe Coder, der durch KI-Systeme oder automatisierte Werkzeuge generierten Code ungeprüft übernimmt oder integriert, ohne dessen Funktionsweise und technische Auswirkungen nachvollziehen zu können.

### 1.2 Eigenverantwortung und Code-Verständnis
Der Software-Architekt muss jederzeit in der Lage sein, den von ihm entwickelten, veränderten oder eingecheckten Code fachlich und technisch nachzuvollziehen und dessen wesentliche Funktionsweise zu erklären.

Er muss außerdem die zugrunde liegenden Architektur- und Technologieentscheidungen eigenständig begründen können.

Dies gilt unabhängig davon, ob der betreffende Code vollständig eigenständig entwickelt, mithilfe von KI-Systemen generiert oder durch andere automatisierte Werkzeuge erstellt beziehungsweise verändert wurde.

KI-generierter oder automatisiert erzeugter Code darf nicht ohne angemessene fachliche und technische Prüfung in ein Softwareprojekt integriert werden.

### 1.3 Abgrenzung der Verantwortung

Der Software-Architekt trägt im Rahmen seiner jeweiligen Funktion, Zuständigkeit und tatsächlichen Entscheidungsbefugnis Verantwortung für:

- die von ihm getroffenen Architektur- und Technologieentscheidungen;
- die fachliche und technische Nachvollziehbarkeit seiner eigenen Entwicklungsleistungen;
- die sorgfältige Prüfung und Integration von Codeänderungen;
- die Einhaltung der ihm zugewiesenen Qualitäts- und Sicherheitsanforderungen.

Die Verantwortung für übergeordnete Architekturvorgaben, technische Rahmenbedingungen sowie ausdrücklich durch andere zuständige Stellen getroffene Entscheidungen verbleibt bei den jeweils hierfür verantwortlichen Personen oder Organisationseinheiten.

Die persönliche Verantwortung des Software-Architekten erstreckt sich auf seinen jeweiligen Aufgaben- und Verantwortungsbereich und richtet sich nach den geltenden gesetzlichen Bestimmungen.

### 1.2 Arbeitsrechtliche Haftung
Der Software-Architekt oder Entwickler haftet für Schäden, die er dem Unternehmen oder Dritten durch eine schuldhafte Verletzung seiner arbeitsvertraglichen Pflichten verursacht, im Rahmen der gesetzlichen Bestimmungen, insbesondere nach Art. 321e OR.

Bei der Beurteilung einer allfälligen Haftung sind insbesondere die Art der Pflichtverletzung, der Grad des Verschuldens, das Berufsrisiko, die übertragenen Aufgaben, die tatsächlichen Entscheidungsbefugnisse sowie die vom Arbeitgeber bereitgestellten Arbeitsmittel und organisatorischen Rahmenbedingungen zu berücksichtigen.

Die vorsätzliche oder fahrlässige Missachtung verbindlicher Sicherheits-, Datenschutz-, Lizenzierungs- oder Überprüfungsvorgaben kann eine arbeitsvertragliche Pflichtverletzung darstellen. Ob daraus eine Schadenersatzpflicht entsteht, beurteilt sich nach den gesetzlichen Voraussetzungen.

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

### 2.7 Lizenzprüfungs-Pflicht & Wahrung von Rechten Dritter

KI-generierter Code wird vor dem Einchecken in die Repositories vom zuständigen Software-Architekten sorgfältig daraufhin geprüft, ob er Lizenzen, Urheberrechte oder sonstige Schutzrechte Dritter verletzt.

### 2.8 Bring Your Own AI (BYOAI)

Die Nutzung privater KI-Abonnements und eigener KI-Zugänge für geschäftliche Zwecke bedarf der vorgängigen schriftlichen Zustimmung der Geschäftsleitung. Die Genehmigungskompetenz liegt ausschliesslich bei der Geschäftsleitung oder einer von ihr ausdrücklich schriftlich bevollmächtigten Stelle.

Die Geschäftsleitung bestimmt, welche privaten KI-Werkzeuge und Tarifmodelle im Einzelfall für geschäftliche Zwecke zugelassen werden. Die private Finanzierung begründet keinen Anspruch auf Genehmigung oder auf Nutzung eines bestimmten KI-Werkzeugs.

Die Kenntnisnahme, Duldung oder unterlassene Intervention durch einzelne Vorgesetzte stellt für sich allein keine Genehmigung im Sinne dieser Bestimmung dar.

Mitarbeitende sind verpflichtet, nicht genehmigte private KI-Abonnements und KI-Zugänge nicht für geschäftliche Zwecke einzusetzen. Eine eigenmächtige Nutzung entgegen einer ausdrücklichen Weisung kann arbeitsrechtliche Konsequenzen haben.

### 2.9 Bereitstellung und Einschränkungen von KI-Werkzeugen

Das Unternehmen legt den Umfang der für geschäftliche Zwecke bereitgestellten KI-Werkzeuge und deren Nutzungskontingente fest. Es ist berechtigt, die Bereitstellung auf bestimmte Produktversionen, Tarifmodelle und Funktionsumfänge zu beschränken.

Wünschen Mitarbeitende darüber hinausgehende Funktionen oder höhere Nutzungskontingente, die für die Erfüllung ihrer zugewiesenen Aufgaben nicht erforderlich sind, können sie die daraus entstehenden Mehrkosten grundsätzlich selbst tragen. Voraussetzung für eine geschäftliche Nutzung bleibt die vorgängige schriftliche Genehmigung gemäss Ziffer 2.8.

Sind weitergehende Funktionen oder Nutzungskontingente für die Erfüllung einer zugewiesenen Aufgabe betrieblich erforderlich, entscheidet das Unternehmen über deren Bereitstellung und Kostenübernahme.

### 2.10 Datenschutz, Vertraulichkeit und Schutz von Betriebsgeheimnissen

#### Verbot vertraulicher Datenübermittlung
Es ist strikt untersagt, personenbezogene Daten (z. B. Kunden-, Mitarbeiter- oder Lieferantendaten), Zugangsdaten, Passwörter, Geschäftsgeheimnisse oder geschützte interne Quellcodes in externe oder öffentliche KI-Modelle einzugeben oder als Prompt/Context hochzuladen.

#### Vorgaben für BYOAI-Tools (Commercial Use & Data Privacy)
Bei der Nutzung von „Bring Your Own AI“ (BYOAI) dürfen ausschließlich KI-Tools und Tarife genutzt werden, deren Nutzungsbedingungen (Terms of Service) explizit garantieren, dass eingegebene Daten und Prompts nicht zum Training der KI-Modelle verwendet und nicht dauerhaft durch den Anbieter gespeichert werden (z. B. Business/Enterprise-Tiers mit Opt-out für Model Training). Die Nutzung kostenloser Consumer-Varianten ohne Datenschutzgarantien ist für geschäftliche Zwecke untersagt.

### 2.10 Urheberrecht und Schöpferhöhe bei KI-Einsatz
Rein KI-generierter Code erfüllt nach internationalen Standards nicht die Voraussetzungen für einen Urheberrechtsschutz (Copyright) und darf nicht ins Git-Repository eingeführt werden.

Der Software-Architekt hat durch aktives, menschliches und wertschöpfendes Zutun (z. B. substanzielle Überarbeitung, individuelle Anpassung oder Erweiterung) sicherzustellen, dass der Code die erforderliche Schöpferhöhe erreicht, um rechtlichen Schutz für das Unternehmen zu gewährleisten.

### 2.11 Qualität und Prüfung von Code-Kommentaren
Von KI-Agenten generierte Kommentare dürfen nicht ungeprüft übernommen werden. Sämtliche Kommentare müssen vom Entwickler auf Richtigkeit, Prägnanz und Mehrwert geprüft und gegebenenfalls manuell überarbeitet oder gekürzt werden. Redundante, generische oder unverständliche KI-Erklärungen sind vor dem Einchecken zu entfernen.

### 2.12 Bestandsschutz von Kernkomponenten und Engines
Bestehende Kernkomponenten und Engines (z. B. API-Architektur, Payment-Gateways, Template- oder Form-Engines, hauseigene Code- & Funktions-Bibliotheken) dürfen nicht durch KI-generierten Code, Refactorings oder automatistische KI-Versionsupdates ersetzt, umgangen oder in ihrer Funktionsweise grundlegend verändert werden. Ausnahmen erfordern eine vorherige schriftliche Zustimmung der Geschäftsleitung.

### 2.13 Kennzeichnungspflicht und EU AI Act Compliance

#### Transparenz gegenüber Endkunden
Sofern in Produkten der [Company] KI-generierte Inhalte (Texte, Bildmaterial, Code) oder interaktive KI-Systeme (z. B. Chatbots) zum Einsatz kommen, sind diese gemäß den Vorgaben des EU AI Act (Künstliche Intelligenz-Verordnung) für den Endnutzer klar und unzweideutig als KI-generiert bzw. KI-gestützt zu kennzeichnen.

#### Verbot von Risikoklassen
Der Einsatz von KI-Systemen, die unter das Verbot des EU AI Act fallen (z. B. unzulässige Verhaltensbeeinflussung oder Biometrie-Scoring), ist im gesamten Unternehmen ausnahmslos untersagt.

### 2.14 Sicherheit von KI-Komponenten im Produkt (Prompt Injection & System Prompts)

#### Schutz vor Prompt Injection (OWASP LLM01)
Sofern KI-Agenten oder LLM-Schnittstellen direkt in Produkte oder Services der [Company] integriert werden, sind geeignete technische und organisatorische Maßnahmen zum Schutz vor direkter und indirekter Prompt Injection umzusetzen. Nicht vertrauenswürdige Benutzer- und Fremdinhalte dürfen nicht ungeprüft als vertrauenswürdige Instruktionen verarbeitet werden. Insbesondere sind eine klare Trennung von Systeminstruktionen und nicht vertrauenswürdigen Inhalten, serverseitige Autorisierungs- und Validierungsprüfungen für Tool- und Funktionsaufrufe sowie das Prinzip der geringstmöglichen Berechtigungen sicherzustellen.

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

## 4. Geltung und Verbindlichkeit

Dieses Reglement bildet einen verbindlichen Bestandteil der bestehenden Vereinbarung zwischen der [company] und dem Unterzeichner.

Es tritt am [Datum] in Kraft und gilt für die gesamte Dauer des Vertragsverhältnisses, soweit es nicht durch eine schriftliche Vereinbarung geändert oder aufgehoben wird.

Mit seiner Unterschrift bestätigt der Unterzeichner, dieses Reglement vollständig gelesen und verstanden zu haben. Er verpflichtet sich, die darin festgelegten technischen, organisatorischen und sicherheitsbezogenen Vorgaben im Rahmen seiner Tätigkeit einzuhalten.

Die Unterzeichnung dieses Reglements begründet keine über die zwingenden und teilzwingenden gesetzlichen Bestimmungen hinausgehende Arbeitnehmerhaftung.

Änderungen und Ergänzungen dieses Reglements bedürfen der schriftlichen Vereinbarung zwischen den Vertragsparteien.


Erlassen durch die Geschäftsleitung:

Ort, Datum: ______________________

Unterschrift: ____________________


Gelesen, verstanden und als verbindlich anerkannt (Software-Architekt):

Name: ____________________________

Ort, Datum: ______________________

Unterschrift: ____________________


---
Source: github.com/lsswiss/ai-assisted-software-development-policy

Open Source Policy

This policy is published as an open-source framework under the CC BY 4.0 License and may be freely used, adapted and redistributed with appropriate attribution.
