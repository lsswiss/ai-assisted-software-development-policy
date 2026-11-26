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

Die Übernahme einer Funktion als Software-Architekt begründet keine verschuldensunabhängige Erfolgshaftung für die technische, wirtschaftliche oder rechtliche Fehlerfreiheit sämtlicher Softwareprodukte und Systeme des Unternehmens. Eine persönliche Haftung setzt die Erfüllung der gesetzlichen Haftungsvoraussetzungen voraus und beschränkt sich auf Pflichtverletzungen innerhalb des individuell übertragenen Aufgaben- und Verantwortungsbereichs.

### 1.4 Arbeitsrechtliche Haftung
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

### 2.11 Urheberrecht und Schöpferhöhe bei KI-Einsatz
Rein KI-generierter Code erfüllt nach internationalen Standards nicht die Voraussetzungen für einen Urheberrechtsschutz (Copyright) und darf nicht ins Git-Repository eingeführt werden.

Der Software-Architekt hat durch aktives, menschliches und wertschöpfendes Zutun (z. B. substanzielle Überarbeitung, individuelle Anpassung oder Erweiterung) sicherzustellen, dass der Code die erforderliche Schöpferhöhe erreicht, um rechtlichen Schutz für das Unternehmen zu gewährleisten.

### 2.12 Qualität und Prüfung von Code-Kommentaren
Von KI-Agenten generierte Kommentare dürfen nicht ungeprüft übernommen werden. Sämtliche Kommentare müssen vom Entwickler auf Richtigkeit, Prägnanz und Mehrwert geprüft und gegebenenfalls manuell überarbeitet oder gekürzt werden. Redundante, generische oder unverständliche KI-Erklärungen sind vor dem Einchecken zu entfernen.

### 2.13 Bestandsschutz von Kernkomponenten und Engines
Bestehende Kernkomponenten und Engines (z. B. API-Architektur, Payment-Gateways, Template- oder Form-Engines, hauseigene Code- & Funktions-Bibliotheken) dürfen nicht durch KI-generierten Code, Refactorings oder automatistische KI-Versionsupdates ersetzt, umgangen oder in ihrer Funktionsweise grundlegend verändert werden. Ausnahmen erfordern eine vorherige schriftliche Zustimmung der Geschäftsleitung.

### 2.14 Kennzeichnungspflicht und EU AI Act Compliance

#### Transparenz gegenüber Endkunden
Die Nutzung und Bereitstellung von KI-Systemen hat unter Berücksichtigung der jeweils anwendbaren gesetzlichen Anforderungen zu erfolgen. Soweit der EU AI Act auf die Tätigkeit, Produkte oder Dienstleistungen des Unternehmens anwendbar ist, sind dessen einschlägige Transparenz-, Dokumentations- und Risikovorgaben einzuhalten. Verbotene KI-Praktiken gemäss Art. 5 EU AI Act sind untersagt.

#### Verbot von Risikoklassen
Der Einsatz von KI-Systemen, die unter das Verbot des EU AI Act fallen (z. B. unzulässige Verhaltensbeeinflussung oder Biometrie-Scoring), ist im gesamten Unternehmen ausnahmslos untersagt.

### 2.15 Sicherheit von KI-Komponenten im Produkt (Prompt Injection & System Prompts)

#### Schutz vor Prompt Injection (OWASP LLM01)
Sofern KI-Agenten oder LLM-Schnittstellen direkt in Produkte oder Services der [Company] integriert werden, sind geeignete technische und organisatorische Maßnahmen zum Schutz vor direkter und indirekter Prompt Injection umzusetzen. Nicht vertrauenswürdige Benutzer- und Fremdinhalte dürfen nicht ungeprüft als vertrauenswürdige Instruktionen verarbeitet werden. Insbesondere sind eine klare Trennung von Systeminstruktionen und nicht vertrauenswürdigen Inhalten, serverseitige Autorisierungs- und Validierungsprüfungen für Tool- und Funktionsaufrufe sowie das Prinzip der geringstmöglichen Berechtigungen sicherzustellen.

#### Absicherung von System-Prompts (OWASP LLM02 / LLM06)
System-Prompts, Instruction-Sets und interne Agenten-Logiken sind als vertrauliche Systemkomponenten zu behandeln. Sie müssen gegen Information Leakage und Exfiltration durch Manipulationstechniken (z. B. „Ignore previous instructions“) abgesichert werden.

#### Human-in-the-Loop & Agency-Begrenzung (OWASP LLM08)
KI-Agenten dürfen keine eigenständigen, unumkehrbaren oder sicherheitskritischen Aktionen ohne vorherige explizite, manuelle Freigabe durch einen menschlichen Nutzer oder Operator durchführen.

Hierzu zählen insbesondere:
- das Löschen oder unwiderrufliche Verändern von Daten;
- das Ausführen von Finanztransaktionen oder kostenpflichtigen Bestellungen;
- das Ändern von Systemkonfigurationen, Berechtigungen oder Sicherheitsrichtlinien;
- das Veröffentlichen oder externe Übermitteln vertraulicher oder geschäftsrelevanter Informationen;
- das Durchführen produktiver Deployments oder vergleichbarer Eingriffe in produktive Systeme.

Die Freigabe muss sich auf die konkret vorgesehene Aktion beziehen und vor deren Ausführung erfolgen. Eine nachträgliche Überprüfung ersetzt keine vorherige Freigabe.

### 2.16 Verbot autonomer Ausführungsmodi (YOLO-Modus) bei KI-Agenten
#### 2.16.1 Grundsatz und Definition
Der sogenannte YOLO-Modus (You Only Live Once) bezeichnet einen Ausführungsmodus von KI-Agenten, bei dem diese eigenständig und ohne vorherige manuelle Bestätigung einzelner Aktionen Befehle ausführen, Dateien verändern, Code generieren, löschen, installieren oder anderweitige Systemoperationen durchführen können.

Die Nutzung solcher autonomen Ausführungsmodi ist im Rahmen der geschäftlichen Tätigkeit grundsätzlich untersagt.

KI-Agenten dürfen ausschliesslich in solchen Ausführungsmodi verwendet werden, bei denen der Entwickler die Kontrolle über die auszuführenden Aktionen behält und sicherheitsrelevante Änderungen vor deren Ausführung angemessen prüfen und freigeben kann.

Das Verbot gilt unabhängig davon, ob sich die betreffende Umgebung auf einem lokalen Rechner, einem Entwicklungsserver, einem Testserver, einem Staging-System oder einem Produktivserver befindet.

#### 2.16.2 Beispiele zur Abgrenzung zulässiger und unzulässiger Nutzung

Die nachfolgende Tabelle dient der Konkretisierung des Verbots:

| Szenario | Gemäss Reglement |
| :--- | :---: |
| YOLO auf lokalem Entwicklungsserver | Verboten |
| YOLO auf isoliertem Testserver | Verboten |
| YOLO auf Staging | Verboten |
| YOLO mit SSH-Zugang zum Produktivserver | Verboten |
| YOLO mit produktiven Datenbankzugängen | Verboten |
| YOLO mit produktiven API-Keys | Verboten |

Das Verbot umfasst insbesondere die Aktivierung von Ausführungsmodi, bei denen KI-Agenten Shell-Befehle, Dateioperationen, Codeänderungen oder sonstige Systemoperationen ohne vorherige menschliche Freigabe selbstständig durchführen können.

#### 2.16.3 Zulässige KI-gestützte Entwicklungsarbeit
Die Verwendung von KI-Agenten zur Unterstützung der Softwareentwicklung bleibt ausdrücklich zulässig, sofern die Ausführung innerhalb eines kontrollierten Arbeitsablaufs erfolgt.

Insbesondere dürfen KI-Agenten:
- Quellcode analysieren und Verbesserungsvorschläge erstellen;
- Codeänderungen und Refactorings vorbereiten;
- neue Funktionen implementieren, sofern die erforderlichen Ausführungsschritte kontrolliert erfolgen;
- Testfälle und Dokumentationen generieren;
- Fehler analysieren und Lösungsvorschläge erarbeiten.
Der Entwickler muss die Kontrolle über die Ausführung behalten und sicherstellen, dass KI-generierte Änderungen vor ihrer Übernahme in die Versionsverwaltung fachlich, technisch und sicherheitstechnisch geprüft werden.

#### 2.16.4 Verantwortung und Einhaltung
Die eigenmächtige Aktivierung oder Verwendung eines untersagten autonomen Ausführungsmodus entgegen den vorstehenden Bestimmungen kann eine Verletzung arbeitsvertraglicher Pflichten darstellen.

Die Beurteilung allfälliger arbeitsrechtlicher Konsequenzen und einer daraus resultierenden Haftung richtet sich nach den geltenden gesetzlichen Bestimmungen und den konkreten Umständen des Einzelfalls.

### 2.17 Verbot der unnötigen Neuentwicklung bestehender Softwarekomponenten (Rewrite statt Bugfix)
Bestehende Softwarekomponenten, Module und Anwendungen sind grundsätzlich gezielt weiterzuentwickeln und instand zu halten. Fehler (Bugs), Fehlfunktionen und technische Unzulänglichkeiten sind vorrangig durch gezielte Korrekturen, Verbesserungen oder angemessene Refactorings innerhalb der bestehenden Architektur zu beheben.

Es ist untersagt, bestehende Softwarekomponenten, Module oder Anwendungen ohne sachlich und technisch begründete Notwendigkeit vollständig oder in wesentlichen Teilen durch KI-generierten Code neu entwickeln oder ersetzen zu lassen, wenn die bestehenden Funktionalitäten durch gezielte Fehlerbehebungen oder verhältnismässige Anpassungen erhalten und verbessert werden können.

Insbesondere ist es unzulässig, einen bestehenden Softwarebestand allein aus Gründen der einfacheren KI-generierten Implementierung, vermeintlich höheren Entwicklungsgeschwindigkeit oder persönlichen Präferenz des Entwicklers durch eine Neuentwicklung zu ersetzen.

Eine vollständige oder teilweise Neuentwicklung (Rewrite) ist nur zulässig, wenn hierfür nachvollziehbare technische, wirtschaftliche oder architektonische Gründe vorliegen und die Geschäftsleitung oder eine von ihr ausdrücklich schriftlich bevollmächtigte Person dem Vorhaben vor Beginn ausdrücklich zugestimmt hat.

Die schriftliche Zustimmung kann insbesondere per Brief, E-Mail oder über einen anderen dauerhaft dokumentierbaren elektronischen Kommunikationsweg erfolgen. Die Zustimmung muss eindeutig, ausdrücklich und der zuständigen entscheidungsberechtigten Person zuordenbar sein.

Bei einer genehmigten Neuentwicklung sind insbesondere die bestehenden Geschäftslogiken, Schnittstellen, Sicherheitsmechanismen, Datenstrukturen, Abhängigkeiten und funktionalen Anforderungen angemessen zu berücksichtigen.

Die Verantwortung für die Einhaltung bestehender Architekturvorgaben sowie für die technische Begründung vorgeschlagener Neuentwicklungen verbleibt beim zuständigen Software-Architekten beziehungsweise Entwickler im Rahmen seines jeweiligen Aufgaben- und Verantwortungsbereichs.

### 2.18 Kurzlebige Entwicklungs- und Testartefakte (Short-Living Test Artifacts)
Während der Entwicklung, Fehlerbehebung und Implementierung von Software dürfen Entwickler temporäre Testskripte, Testdaten, Debugging-Dateien, Hilfsprogramme und sonstige technische Testartefakte erstellen und verwenden.

Diese dienen ausschliesslich der unmittelbaren Entwicklungs- und Überprüfungsarbeit und sind grundsätzlich nicht dauerhaft in das produktive Repository zu übernehmen.

Nach erfolgreicher Überprüfung und Abschluss der jeweiligen Entwicklungsarbeit sind temporäre Testartefakte zu entfernen, sofern sie keinen dauerhaft begründeten technischen oder fachlichen Mehrwert für das Softwareprojekt bieten.

Insbesondere sollen keine zusätzlichen automatisierten Tests, Testframeworks, Testdatenbanken oder Testinfrastrukturen ausschliesslich deshalb in ein bestehendes Softwareprojekt integriert werden, um die vom Entwickler selbst vorgenommene Implementierung oder Fehlerbehebung nachträglich zu bestätigen.

Dauerhaft zu übernehmende automatisierte Tests müssen einen nachvollziehbaren, langfristigen Mehrwert für die Qualitätssicherung, Regressionserkennung oder Stabilität der Software bieten und in einem angemessenen Verhältnis zur Komplexität und zum Wartungsaufwand stehen.

Die Entscheidung über die dauerhafte Integration umfangreicher Testinfrastrukturen richtet sich nach den bestehenden Architekturvorgaben und Zuständigkeiten.

### 2.19 Auswertung von Datenbanklogs und produktionsnahen Daten
Müssen Datenbanklogs, Datenbankauszüge oder sonstige produktionsbezogene Datensätze zu Analyse-, Debugging-, Fehlerbehebungs- oder Entwicklungszwecken ausgewertet werden, hat dies grundsätzlich ausschliesslich anhand einer separaten Kopie der betreffenden Daten zu erfolgen.

Die hierfür benötigten Daten sind vor der Auswertung aus der produktiven Umgebung zu exportieren und in eine geeignete, vom Produktivsystem getrennte Analyse- oder Entwicklungsumgebung zu übertragen.

Eine direkte Auswertung durch KI-Agenten oder KI-Tools innerhalb produktiver Datenbanken oder Produktivsysteme ist untersagt.

Vor der Weitergabe an KI-Tools sind personenbezogene Daten, Zugangsdaten, Session-Tokens, Passwörter, API-Schlüssel sowie sonstige vertrauliche oder sicherheitsrelevante Informationen soweit technisch möglich zu entfernen oder zu anonymisieren.

Die Kopie muss unter angemessenen Sicherheitsvorkehrungen gespeichert, vor unbefugtem Zugriff geschützt und nach Wegfall des Analysezwecks gelöscht werden.

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
