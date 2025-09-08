# Backlog – Paketplattform
Version 1.0  
Architektur: React 19 + Next.js App Router + pnpm + TypeScript strict + Stripe + MapLibre  
Framework: HVD (Holistic Value Dynamics) → jede Story ist mindestens einem Vektor zugeordnet (V1–V6).  
Rollen: Shopper, Host, Admin.  
Ziel: Intuitiv für Grundschüler und Senioren, gleichzeitig skalierbar.  

---

## Epics

### Epic A – Core Shopper Journey
Ziel: Adressbuchung so einfach machen, dass jeder User sie versteht.  
HVD-Bezug: Value (Nutzererlebnis), Ressourcen (Zeitersparnis).

1. **Story A1 – Projekt-Setup**  
   - Next.js, React 19, pnpm, TypeScript strict, GitHub Actions.  
   - CI/CD Pipeline lauffähig.  

2. **Story A2 – Design-System**  
   - Storybook aufsetzen.  
   - Komponenten: Button, Input, PrimaryCTA, CardAddress, WizardLayout.  

3. **Story A3 – Home-Screen**  
   - Zwei große Kacheln: „Paket empfangen lassen“ | „Adresse anbieten“.  

4. **Story A4 – Suche**  
   - Eingabe PLZ/Ort oder Standort nutzen.  
   - Ergebnisliste + Karte. Filter: Preis, Entfernung, Bewertung.  

5. **Story A5 – Adress-Detailseite**  
   - Bild, Öffnungszeiten, Preisübersicht, Bewertungen, „Buchen“-Button.  

6. **Story A6 – Größen-Assistent**  
   - 4 Icons (Schuhe, Laptop, Kleidung, Sonstiges).  
   - Ausgabe S/M/L + Beispielbilder.  

7. **Story A7 – Slot-Picker**  
   - Kalender-UI. Nur freie Slots auswählbar.  

8. **Story A8 – Checkout**  
   - Ident light (SMS + Foto-Upload).  
   - Stripe Test-Payment.  
   - Gebühren transparent.  

9. **Story A9 – Bestätigung mit QR**  
   - QR-Code generieren + PIN.  
   - „Zu Wallet hinzufügen“. Offline verfügbar.  

10. **Story A10 – Meine Buchungen**  
    - Liste mit Status: offen, bestätigt, abgeschlossen.  

---

### Epic B – Core Host Journey
Ziel: Adress-Anbieter können ohne Friktion starten.  
HVD-Bezug: Ressourcen (Kapazität), Relation (Vertrauen), Culture (Transparenz).

1. **Story B1 – Host-Onboarding Wizard**  
   - 5 Schritte: Adresse, Öffnungszeiten, Kapazität, Preis, Ident.  

2. **Story B2 – Host-Kalender**  
   - Urlaub blocken, Slots freigeben.  

3. **Story B3 – Paket-Annahme**  
   - Barcode scannen oder manuell erfassen. Status = „eingelagert“.  

4. **Story B4 – Paket-Ausgabe**  
   - QR scannen oder PIN + Ausweis prüfen. Foto optional.  

5. **Story B5 – Host-Auszahlungen**  
   - Stripe Connect Testmode. Übersicht letzte 30 Tage.  

---

### Epic C – Admin Panel
Ziel: Betriebssicherheit und Betrugsprävention.  
HVD-Bezug: Communication (Monitoring), Resources (Controlling).

1. **Story C1 – Admin-Dashboard**  
   - Live KPIs: Buchungen, SLA, Disputes, KYC-Status.  

2. **Story C2 – KYC/KYH Queue**  
   - Hosts und Shopper verifizieren, Freigabe/Block.  

3. **Story C3 – Dispute-Management**  
   - Fälle anlegen, SLA-Timer, Status ändern.  

4. **Story C4 – Gebührenmatrix**  
   - Provision dynamisch anpassen.  

---

### Epic D – Wachstum & Botschafter
Ziel: Nutzer in aktive Akquisiteure verwandeln.  
HVD-Bezug: Vision (Wachstum), Relation (Netzwerk), Value (Incentives).

1. **Story D1 – Referral-Programm**  
   - Jeder Nutzer bekommt einen persönlichen Einladungslink.  
   - Bonus: Guthaben oder Gratis-Buchung.  

2. **Story D2 – Badge-System**  
   - Hosts & Shopper erhalten Abzeichen: „Top-Host“, „Power-Shopper“.  
   - Sichtbar in Profilen.  

3. **Story D3 – Social Sharing**  
   - Nach erfolgreicher Buchung: „Teilen auf WhatsApp/Facebook“.  
   - Mit Referral-Link verknüpft.  

4. **Story D4 – Botschafter-Dashboard**  
   - Übersicht: geworbene Nutzer, Provisionen, Status.  

5. **Story D5 – HVD-Wachstumsvektor Tracking**  
   - KPIs: Referral-Quote, Organisches Wachstum, Netzwerkeffekte.  
   - Visualisierung im Admin-Panel.  

---

### Epic E – HVD-Integration
Ziel: Daten erfassen, um die Plattform entlang der 6 Dimensionen zu steuern.  
HVD-Bezug: Alle 6 Vektoren.  

1. **Story E1 – Event Tracking**  
   - Events: `search_started`, `address_selected`, `size_chosen`, `slot_confirmed`, `checkout_completed`, `referral_shared`, `host_onboarded`.  

2. **Story E2 – Vektor-Berechnung**  
   - Mapping:  
     - V1 Value → Conversion-Rate  
     - V2 Vision → Referral-Quote  
     - V3 Culture → Dispute-Rate  
     - V4 Communication → SLA-Antwortzeiten  
     - V5 Relation → Host-Retention  
     - V6 Resources → Kapazitätsnutzung  

3. **Story E3 – Normalisierung**  
   - Alle KPIs zwischen 0 und 1. Speicherung in DB.  

4. **Story E4 – Admin-HVD-View**  
   - Dashboard: Radar-Chart mit V1–V6.  

---

### Epic F – Support & Barrierefreiheit
Ziel: Zugänglichkeit für Senioren und Kinder.  
HVD-Bezug: Culture (Inklusion), Value (Einfachheit).

1. **Story F1 – Hilfe-Center**  
   - FAQ, 5 Kurzvideos.  

2. **Story F2 – Accessibility**  
   - Screenreader-Labels, Kontrast ≥4.5:1, „Text vergrößern“.  

3. **Story F3 – Mehrsprachigkeit**  
   - DE, EN, FR, IT.  

---

# Abnahme-Kriterien
- Senior (70+) kann Adresse buchen ohne Hilfe.  
- Kind (8–10) kann QR-Code abrufen.  
- Referral-Link funktioniert.  
- Admin sieht HVD-Vektor-Dashboard.  
- E2E-Tests grün (Shopper-Flow, Host-Flow, Referral-Flow).  

---
