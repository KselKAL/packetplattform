Zielbild
	•	One-Task-per-Screen. Große Touch-Ziele. Klarer Primär-Call-to-Action.
	•	Zwei Modi: Einfach-Modus (Wizard, maximal 1 Entscheidung pro Schritt) und Pro-Modus (kompakt, Mehrfachaktionen).
	•	Drei Rollen: Shopper, Host, Admin.

Leitprinzipien
	•	WCAG 2.2 AA. 44×44 px Touch-Targets. Mindestschrift 16 px, bevorzugt 18–20 px.
	•	Plain Language. Kein Jargon in Nutzertexten.
	•	Fortschritt immer sichtbar: Schritt X von Y.
	•	Primäraktion unten fixiert. Sekundäraktionen oben.
	•	Fehlertoleranz: Undo, klare Recovery-Wege.

Personas
	•	Ruth, 72: Smartphone, Lesebrille, unsicher bei Online-Zahlung.
	•	Leo, 9: Liest einfache Sätze. Tippt schnell. Versteht Bilder besser als Text.
	•	Aylin, 34 Shopper Pro: Grenznah, viele Bestellungen.
	•	Marco, 41 Host Semi-Pro: Öffnungszeiten, Ferien, Kapazitäten.

Informationsarchitektur
	•	Home (Zwei Kacheln): „Paket empfangen lassen“ | „Adresse anbieten“
	•	Shopper-Flow: Suchen → Adresse wählen → Größen-Assistent → Datum/Zeiten → Ident/Bezahlung → Bestätigung + QR
	•	Host-Flow: Onboarding-Wizard → Kalender/Zeiten → Preise → Auszahlung → Verifizierung → Online
	•	Konto: Profil, Ident, Zahlungen, Belege, Hilfe
	•	Hilfe: FAQ, Kontakt, Schritt-Videos
	•	Admin: Monitoring, KYC/KYH, Disputes, Payouts, Pricing, Content

Kern-Journeys mit Akzeptanzkriterien

Shopper: „Adresse buchen“ (Einfach-Modus)
	1.	Standort wählen
Eingabe: PLZ/Ort oder „Standort nutzen“.
Kriterien: Ergebnisliste <800 ms, Karte + Liste, Filter: heute geöffnet, Preis, Bewertung, Entfernung.
	2.	Adresse antippen
Karte der Adresse, Öffnungszeiten als Ampel, Preis pro Paketgröße, Hinweise „So funktioniert’s“ (3 Bilder).
	3.	Größen-Assistent
Frage 1: „Was kommt?“ (Auswahlsymbole: Schuhe, Laptop, Kleidung, Sonstiges).
Frage 2: „Ungefähr wie groß?“ (S/M/L mit Beispiel-Fotos).
Ausgabe: Vorschlag + Preis + Lagerfrist.
Kriterium: Auswahl in ≤2 Taps.
	4.	Zeit & Abholung
Slot-Picker. Nur gültige Slots klickbar.
Kriterium: Slot bestätigt, ETA-Fenster angezeigt.
	5.	Sicherheit & Zahlung
Ident light: SMS-Code + Ausweisfoto oder verifizierte Payment-ID.
Zahlart: Karte, SEPA, Wallet.
Transparente Gebühren.
Kriterium: Checkout ≤60 s, Fehlerrate <1%.
	6.	Bestätigung
QR-Code + 6-stelliger Abhol-PIN. „Zu Wallet hinzufügen“.
Tracking-Eingabe optional.
Kriterium: Offline-Verfügbarkeit des QR.

Fehlerfälle: QR verloren → Login → „Code neu anzeigen“. Akku leer → PIN + Ausweis beim Host. Falscher Name auf Paket → Self-Service Dispute Button.

Host: „Adresse anbieten“
	1.	Onboarding-Wizard
Schritt 1 Adresse + Foto Eingangsbereich.
Schritt 2 Öffnungszeiten + Abholzeiten.
Schritt 3 Kapazität S/M/L (Schieberegler) + Sperrgut ja/nein.
Schritt 4 Preisvorschlag (dynamisch) + Provision sichtbar.
Schritt 5 Ident (IBAN/Konto + Ausweis).
Kriterium: Abschluss in <5 min.
	2.	Kalender
Urlaub blocken, Slots managen, Max-Paket-pro-Slot.
Kriterium: Drag-to-Block, klare Legende.
	3.	Check-in Paket
Aktion: „Paket annehmen“ → Scan Versand-Barcode → Name/Bestellnr. Auto-Parse → Status „eingelagert“.
Kriterium: <10 s pro Paket.
	4.	Ausgabe
Button „Paket ausgeben“ → Shopper QR scannen oder PIN + Ausweis prüfen → Foto-Beleg optional → „erfolgreich“.
Kriterium: Falsch-Abgabe verhindert durch Name-Match.

Admin: „Betrieb steuern“
	•	Live-Panels: aktive Buchungen, SLA Empfang/Abgabe, Disputes, KYC-Queue, Betrugsflags, Auszahlungen.
	•	Regeln: Sperrlisten, Limits, dynamische Preise, Gebührenmatrix.
	•	Audit-Trail: jede Statusänderung nachvollziehbar.

Screen-Inventar (Minimal)
	•	Home, Suche, Kartenliste, Adress-Detail, Größen-Assistent, Slot-Picker, Checkout, Bestätigung/QR, Meine Buchungen, Dispute erstellen, Host-Wizard 1-5, Host-Kalender, Host-Paket annehmen, Host-Ausgabe, Host-Auszahlungen, Profil, Ident, Zahlungen/Belege, Hilfe, Admin-Dashboard, Admin-KYC, Admin-Disputes.

Komponenten-Kit
	•	Header schlicht, Zurück-Pfeil links, Hilfe rechts.
	•	Bottom-Primary-CTA (100% Breite, max 1 CTA).
	•	Kartenliste mit großen Kacheln, 1 Bild, Sterne, Preis, Entfernung, „Heute offen bis…“.
	•	Wizard-Stepper: 1/5, 2/5 …
	•	Slot-Picker: horizontale Tage, vertikale Slots.
	•	QR-Card: groß, Kontrast hoch, „PIN anzeigen“.
	•	Empty States: Bild + 1 Satz + Primäraktion.
	•	Toasts statt Modals, außer rechtlich Relevantes.
	•	Help-Button persistent unten rechts.

Design-Tokens (CSS-Variablen)
	•	--space-2/4/8/12/16/24/32
	•	--radius-8/12/16
	•	--fg-1, --fg-2, --bg-1, --bg-alt, --brand-1, --ok, --warn, --error
	•	Typo: Inter/Roboto 400/600. H1 22–24, Body 18, Small 16.

Interaktionsregeln
	•	Fokuszustände klar sichtbar.
	•	Eingaben sofort validieren.
	•	Jede kritische Aktion mit kurzem Review-Screen.

Inhalte / Microcopy (Beispiele, DE)
	•	Größen-Assistent: „Wähle die ungefähre Größe. Du kannst dich nicht vertun.“
	•	Checkout: „Du zahlst erst, wenn die Adresse bestätigt ist.“
	•	Ausgabe: „Zeige QR oder nenne deinen PIN.“

Barrierefreiheit
	•	Screenreader-Labels für alle Bedienelemente.
	•	Kontrast ≥ 4.5:1.
	•	„Text vergrößern“ Schalter App-weit.
	•	Animations-Reduktion respektieren.

Internationalisierung
	•	DE, EN, FR, IT. Datums- und Währungsformat lokal.
	•	Alle Texte in i18n-Katalogen, keine Hardcodes.

Sicherheit & Datenschutz
	•	Datenminimierung. Adresse erst nach Buchung sichtbar.
	•	QR + kurzlebiger Abhol-Token. Offline-Fallback via PIN.
	•	KYC/KYH modular (Stripe Identity/Veriff o. ä.).
	•	DSGVO: Einwilligungen granular, Löschpfade im Konto.
	•	Logging mit PII-Redaktion.

Zahlungslogik
	•	Transparente Gebühren. Belege als PDF.
	•	Wallet-Integration. SEPA-Payouts für Hosts.
	•	Rückerstattungs-Flows klar.

Disputes
	•	Drei Kategorien: „Nicht angekommen“, „Beschädigt“, „Falsch ausgegeben“.
	•	Schritt-Wizard, Foto-Upload, Fristen sichtbar.
	•	SLA-Timer und Statusbadges.

Analytics & KPIs
	•	Events: search_started, search_result_viewed, address_selected, size_assisted, slot_confirmed, checkout_started, identity_passed, payment_succeeded, qr_viewed, package_checked_in, package_released, dispute_opened.
	•	KPIs: Aktivierung (Checkout/Adresse gewählt), Buchungs-Conversion, Host-Fill-Rate, Check-in-SLA, Abhol-SLA, Dispute-Rate, NPS.

Technische Umsetzungsanweisung für base44

Stack
	•	React 19 + TypeScript strict. Next.js App Router. pnpm Workspace.
	•	Zustand oder Redux Toolkit für globalen State. React Hook Form + Zod.
	•	i18next.
	•	MapLibre/Leaflet + Open-Data Tiles.
	•	PWA: Offline-Cache für QR/Belege. Push-Notifications.
	•	QR/Barcode: zxing-library. Wallet-Pass generieren.
	•	Zahlungen: Stripe o. ä. KYC modular.
	•	CI/CD: GitHub Actions, Preview per PR. Feature-Flags (Unleash/ConfigCat).

Routing (App Router)
	•	/ Home
	•	/find Suche + Liste + Karte
	•	/address/[id] Detail
	•	/book/size → /book/slot → /book/checkout → /book/done
	•	/me/bookings
	•	/host/onboarding/*
	•	/host/calendar /host/checkin /host/release /host/payouts
	•	/admin/* mit RBAC und IP-Allowlist

Zustände als State-Maschinen
	•	bookingMachine: idle → addressSelected → sizeChosen → slotChosen → identityOk → paid → confirmed.
	•	hostFlowMachine: onboarding → review → live.
	•	Fehler-Substates mit Recovery.

Komponentenlieferobjekte
	•	WizardLayout
	•	PrimaryCTA (sticky)
	•	CardAddress
	•	SizeAssistant
	•	SlotPicker
	•	CheckoutForm
	•	QrCard
	•	ScanButton (Kamera-Zugriff)
	•	EmptyState
	•	HelpFab

Performancebudgets
	•	LCP < 2.5 s, TTI < 3 s, Bundle < 250 KB initial.
	•	Bilder srcset, Lazy-Load.
	•	Form-Steps client-only, Suche server-rendered.

Tests
	•	Unit: Vitest.
	•	E2E: Playwright (kritische Pfade: Shopper-Buchung, Host-Check-in, Host-Ausgabe, Offline-QR).
	•	A11y: axe-core CI.
	•	Visual Regression: Chromatic/Storybook.

Telemetrie
	•	OpenTelemetry SDK. Logs ohne PII.
	•	SLOs: Fehlerquote <1%, API P95 <200 ms.

Rollout
	•	Staged Rollout per Feature-Flag:
	1.	Einfach-Modus.
	2.	Host-Kalender.
	3.	QR-Offline.
	4.	Disputes.
	5.	Pro-Modus.

Edge-Cases und Lösungen
	•	Kein Smartphone: QR per E-Mail drucken, PIN-Fallback.
	•	Akku leer: PIN + Ausweis.
	•	Falscher Name: Host-Warnung, Dispute anlegen.
	•	Paket zu groß: Host-UI stoppt Annahme, Alternativen vorschlagen.
	•	No-Show: Automatische Erinnerung, Fristablauf, Rückversand-Option.

Inhalte für Hilfe
	•	5 Kurzvideos: Suchen, Buchen, QR nutzen, Host Annahme, Host Ausgabe.
	•	FAQ mit Bildern.
	•	Kontakt: Chat, E-Mail, Telefon.

Abnahme-Checkliste (stichprobenfest)
	•	Senior-Test: 5 Nutzer 70+, Erfolgsquote >95% für Buchung.
	•	Kinder-Test: 5 Nutzer 8–10, Erfolgsquote >95% für QR anzeigen.
	•	Screenreader-Test: NVDA/VoiceOver bestehen.
	•	Offline-QR funktioniert Flugmodus.
	•	E2E grün auf CI.
	•	Datenschutz-Check: Einwilligungen erfassbar, Export/Löschung im Konto.

Deliverables für base44
	•	Design-System in Storybook mit allen oben genannten Komponenten.
	•	Flow-Diagramme als README in /docs/flows.
	•	Copy-Deck in /locales/{de,en,fr,it}.json.
	•	Event-Schema in /analytics/events.md.
	•	E2E-Skripte in /e2e/*.spec.ts.

Diese Spezifikation ist umsetzbar „as is“. Start mit Einfach-Modus und Shopper-Flow. Danach Host-Kalender und QR-Offline. Admin nur intern zugänglich mit RBAC und IP-Allowlist.
