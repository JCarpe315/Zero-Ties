# The Zero-Ties Car: A Complete Audit of Israeli Entanglement in the Connected Automobile

αΩ∞

*A fully-sourced investigation into the modern car — the phone's big sibling — its Israeli-built safety, security, and data layers, the documented hacking record from the university lab to Vault 7, and the realistic protections available to a driver, as of September 2026.*

---

## 1. Why the Car Is the Phone's Big Sibling

A modern car is a data center on wheels: dozens of computers networked together, a cellular modem, GPS, Bluetooth, Wi-Fi, cameras, microphones, radar, and — in connected models — a continuous uplink to the manufacturer. The average new car runs more lines of code than a fighter jet. And it sits in your driveway, unlocked by radio, updated over the air, and increasingly monetized as a data source. When WikiLeaks published the CIA's Vault 7 files in 2017, one passage chilled the automotive world: the agency's capabilities against vehicle systems would permit "**nearly undetectable assassinations**." That sentence is this document's starting point — not as a claim about any specific death, but as the standing proof that the car's attack surface was understood, at nation-state level, years before most drivers knew their car had an attack surface.

### How to read this document

- **Part 2** — the short answer. **Part 3** — orientation for non-specialists.
- **Parts 4–7** — the audit: silicon, the security backbone, the data layer, and the OEM ledger.
- **Part 8** — the documented hacking record. **Part 9** — EV charging. **Part 10** — privacy.
- **Part 11** — protections. **Part 12** — the minimum-entanglement configuration.
- **Parts 13–17** — method, open questions, key figures, glossary, conclusion.

---

## 2. The Short Answer

**No clean new car exists — the automotive safety, security, and data layers are structurally Israeli-built across every major brand.** Mobileye (Intel-owned, Israeli) supplies the driver-assistance eyes in a majority of the world's vehicles. Qualcomm's automotive silicon — designed across Israeli R&D centers running since 1993 — runs the dashboards and modems of much of the industry. The automotive-cybersecurity industry that guards it all is an Israeli cluster: Argus (acquired by Continental for $430 million, founded by three Unit 8200 veterans), Upstream, Karamba (General Motors' partner), C2A, GuardKnox, and Cymotive — Volkswagen's joint venture with former Israeli intelligence leadership. The connected-car data marketplace was built in Herzliya (Otonomo). And every major OEM either has documented military/settlement entanglement profiles (GM, Volkswagen, Toyota, Mercedes-Benz — per Who Profits) or Israeli venture operations (Hyundai's CRADEL Tel Aviv). The realistic answer for a driver is therefore **not elimination but minimization**: the simplest, least-connected vehicle that meets your needs, hardened keys, no data-sharing subscriptions, and awareness of the relay-theft epidemic that has made keyless cars the easiest property crime in the industrialized world.

## 3. A Thirty-Second Orientation

A car's computers are divided into domains: the **powertrain** (engine and brakes), the **infotainment head unit** (screen, radio, navigation), the **telematics control unit or TCU** (the cellular modem that phones home), and increasingly **ADAS** (driver assistance — cameras, radar, lane-keeping). These domains talk over internal networks (CAN bus). The security question is always the same: who can cross from the outside world (Bluetooth, cellular, key fob) into the safety-critical inside? Everything in Parts 4–10 is an answer to that question.

## 4. The Silicon Layer

- **Mobileye (Intel-owned, Jerusalem-founded; ~96.9% Intel voting control):** the ADAS leader — eyeQ chips and SuperVision in vehicles from dozens of brands; SuperVision builds on QNX. If your car has lane-keeping or automatic emergency braking, the odds are excellent the eyes are Israeli.
- **Qualcomm (Snapdragon Digital Chassis; Israeli R&D since 1993, ~700 Israel staff):** infotainment and TCU silicon across the industry. The automotive ledger includes **Autotalks** (V2X, ~$350–400 million, 2023), **Cellwize** ($350 million), **Wilocity** (~$300 million, 2014), **CSR's Israeli imaging unit** ($45 million). At CES 2026, Qualcomm and Google announced pre-integrated Android Automotive on Snapdragon — tightening the pairing of the two most entangled vendors.
- **Nvidia** (Mellanox-derived automotive networking) and **NXP** (its Yokne'am, Israel design center) supply supporting silicon.
- **The clean alternative at the OS layer:** **QNX (BlackBerry, Canadian)** hosts 235 million vehicles' safety systems at a 38.2% share with automotive's highest safety certification — Canadian-authored, clean at corporate level. Android Automotive (Google) is the entangled, fastest-growing rival (~18% by 2027 projected). Automotive Grade Linux (open) and Wind River (Aptiv-owned) sit between. Elektrobit — Continental's software arm — inherits the Argus tie below.

## 5. The Security Backbone — an Israeli Cluster

The industry that *guards* the connected car is, to a first approximation, Israeli:

- **Argus Cyber Security** (founded 2013 by three **Unit 8200** veterans plus Zohar Zisapel; renamed **PlaxidityX** in 2024): acquired by **Continental for ~$430 million in 2017**; Argus technology sits inside Continental's automotive software, which ships to most major OEMs; Argus also maintains a partnership with Check Point. Continental's entire connected-car security stack is Israeli-authored.
- **Upstream Security** (Herzliya, 2017): cloud automotive monitoring, a category leader.
- **Karamba Security:** ECU hardening; **partnered with General Motors** for vehicle-SDV security.
- **Cymotive Technologies:** co-founded by **Volkswagen's CARIAD** with former Israeli intelligence leadership; being acquired by India's KPIT for up to **$120 million** (May 2026) — VW's software-defined-vehicle security is Israeli-built.
- **C2A Security, GuardKnox:** Israeli automotive-cyber startups. PlaxidityX (the ex-Argus team) also found the EVerest charger vulnerability (Part 9).

The plain-language summary: **the locks on the car's doors are largely made in Israel.** Under this investigation's criterion that is the decisive layer — and it cannot be optioned out of a new car.

## 6. The Data Layer

- **Otonomo (Herzliya, 2015):** the pioneering connected-car data marketplace — ingesting **4 billion data points daily from more than 40 million vehicles**, with OEM customers including Daimler, BMW, and Mitsubishi; SPAC-listed at $1.4 billion in 2021, collapsed to roughly $70 million by 2023, and acquired by Urgent.ly in October 2023 — after weathering a documented scandal in which the startup Smartcar showed Otonomo's technical materials had copied its own. For years, the broker between your car's telemetry and its commercial buyers was an Israeli-founded platform. The category it founded now runs through larger brokers and OEM in-house programs — the data still flows; the HQ changed.
- **NissanConnect runs on Microsoft Azure** — inheriting the laptop investigation's Azure/Unit 8200 record — with **Valens Semiconductor** (Israeli; also a MediaTek portfolio company) chipsets validated into its architecture.
- **Stellantis** expanded its **Palantir** partnership (five years, March 2026) — Palantir holds Israeli R&D and Israeli military contracts (per the apps investigation).
- The **telecommunications pipes:** Harman (Samsung) builds Ready Connect 5G TCUs on **Qualcomm** modems; SiriusXM's connected-vehicle services layer serves Stellantis-era fleets (and surfaced in the hacking record, Part 8).

## 7. The OEM Ledger

| OEM | Documented position |
|---|---|
| **General Motors** | OnStar in-house (12M subscribers); Who Profits profile; Karamba security partner; Cruise employs Chris Valasek as director of cybersecurity |
| **Ford** | Who Profits profile; a Tel Aviv research center is reported but unverified in this investigation — flagged |
| **Volkswagen** | Cymotive JV (Israeli-built SDV security); Who Profits profile |
| **Toyota** | Electreon (Israeli wireless-charging) partnership, March 2025; Who Profits profile |
| **Mercedes-Benz / BMW** | Mobileye partnerships; Mercedes holds a Who Profits profile |
| **Hyundai** | **CRADEL Tel Aviv** (2018) — venture ties incl. Autotalks, Allegro.ai, Percepto, OPSYS, D-ID; on-record praise of Israel's automotive sector |
| **Stellantis** | Palantir expansion (2026); Qualcomm connected-tech rollout; no Who Profits profile (per the Maserati audit's negative finding) |
| **Nissan** | Azure telematics; Valens chipsets; Alliance Tel Aviv innovation lab; Mobileye-powered ProPilot |

**The mirror-image finding:** Israel's own military now excludes Chinese connected vehicles — the IDF's November 2025 tender for 10,000 leased vehicles excluded Chinese brands (Chery was dropped from contention) on the same supply-chain logic this series applies outward. The principle is universal; the application is selective.

## 8. The Documented Hacking Record

- **2011 — the academic foundation:** University of Washington and UC San Diego researchers (Koscher, Czeskis, Roesner, Patel, Kohno) published the first comprehensive experimental analysis of a modern automobile, demonstrating that internally compromised components could commandeer brakes and engine — the paper that created automotive cybersecurity as a field.
- **2015 — the highway demonstration:** Charlie Miller and Chris Valasek remotely hijacked a **Jeep Cherokee** through its Uconnect head unit: an unauthenticated service on the Sprint-connected infotainment computer reached the CAN bus, letting them cut the transmission on a live highway (with a Wired reporter at the wheel), later steering and braking at low speed. **Fiat Chrysler recalled 1.4 million vehicles** — the first cybersecurity-driven vehicle recall — while maintaining "no defect" in the traditional sense. The industry response was to hire the hackers: Valasek became Cruise's director of cybersecurity; Miller went to GM. A ten-year retrospective (VehicleSec, 2025) marked how far the field has come — UNECE regulations R155/R156 (July 2024) now make cybersecurity and OTA-management systems legally mandatory for new vehicle types, a direct descendant of this work.
- **2017 — Vault 7:** the CIA's files described vehicle-systems access enabling "nearly undetectable assassinations" — the capability statement that frames every later car-hacking headline.
- **2023 — the telematics-broker flaw:** a vulnerability in SiriusXM's connected-vehicle services allowed remote unlock and engine start on multiple brands (Honda, Nissan, Acura, Infiniti reported) via nothing but the VIN — B-grade sourcing, flagged; and Nissan separately surfaced an unauthenticated-API exposure of vehicle data (B-grade). The lesson of both: the *broker layer* between you and the car is itself attack surface.
- **The everyday epidemic — relay theft:** the most common car "hack" needs no malware at all: two criminals with a signal-amplifying relay box extend your key fob's sleeping radio to the parked car, open it, and drive off in under a minute. ADAC testing found only **about 15% of vehicles** resisted the technique; in the Netherlands, **59% of 2025's stolen cars** were taken keylessly. Defenses: Faraday pouches for keys at home, OBD-port locks, software immobilizers (e.g., xProtect), kill switches, trackers, and — simplest — a physical steering lock.

## 9. The EV Charging Layer

The charger is the car's strangest appendage — a 240-volt, internet-connected computer on your wall. Its protocol, **OCPP**, has shipped with plaintext communications and weak authentication; six OCPP zero-days surfaced in April 2024; the UK suspended a Spanish-made charger from sale in February 2024 over security; 116,000 user records were breached in November 2024. **Pwn2Own Automotive** made it a contest: the 2025 edition produced 49 flaws (Tesla's Wall Connector hacked five ways; the Ubiquiti EV Station shipped with its cryptographic key extractable from firmware; a Phoenix Contact chain earned $91,750), and the 2026 Tokyo edition produced 76 zero-days including full control of Alpitronic's HYC50. In the wild, **CVE-2026-4156** grants root over ChargePoint's Home Flex via its OCPP interface, and **CVE-2024-37310** (EVerest, found by PlaxidityX — the Israeli ex-Argus firm) shows the open charger stack needs its own guardians. Researchers have demonstrated grid-destabilization scenarios — mass synchronized demand spikes — turning home chargers into infrastructure weapons. Israeli firms (C2A's EVSec, PlaxidityX's AutoTester) are, again, prominent in the defense of this layer.

## 10. The Privacy Verdict

Mozilla's *Privacy Not Included* reviewed 25 car brands in September 2023 and failed **all of them** — calling cars "the worst product category we have ever reviewed," worse than mental-health apps: every brand collects more data than needed, 84% share or sell it, Tesla scored worst, and the data flows through sensors, paired phones, navigation, and third parties (SiriusXM, Google Maps). The car is the most data-hungry consumer device in this series — and, unlike the phone, it cannot be carried into a Faraday pouch.

## 11. The Protections Chapter

What a driver can actually do, in order of impact:

1. **Buy less connected car.** Trim levels matter: decline connected-services subscriptions, navigation packages with modems, and in-car commerce. The simplest drivetrain that meets your needs is the strongest privacy decision available.
2. **Harden the keys.** Faraday pouch at home; store keys away from doors; consider an OBD lock and software immobilizer in relay-theft hotspots; a $30 steering lock defeats the entire relay industry.
3. **Audit the account.** Factory app accounts: minimize permissions, decline marketing consent, request data deletion where offered (84% of brands share data; deletion policies vary).
4. **Keep software current** — now a legal requirement for makers (UNECE R155/R156) and a real defense for you.
5. **Don't jailbreak or plug untrusted devices into the OBD port**; the port is the master key.
6. **For the threat-model-extreme:** the used, pre-connectivity car (roughly pre-2014 for minimal attack surface) is the maximal-clean answer — with the honest tradeoff of losing modern safety systems.

## 12. The Minimum-Entanglement Configuration

There is no zero-ties new car: Mobileye's eyes, Qualcomm's dashboards, and the Israeli-built security backbone come with the territory. The realistic floor: the least-connected trim of a chosen model; keys in a Faraday box; no telematics subscriptions; OBD port locked; steering lock if local theft rates warrant; safety systems left intact (they are the QNX-hosted, Canadian-authored layer and should never be disabled). For the strictest criterion, the pre-connected used car remains the only true exit — accepting older crash-safety economics as the price.

---

## 13. Methodology and Evidence Grading

Four research passes: corporate and silicon; the security and data clusters; the hacking record and relay epidemic; EV charging and privacy. Grades: audit-grade (OpenIntel references where they exist), S/A-grade (UNECE texts, Pwn2Own results, UW/UCSD and Miller/Valasek work), B-grade flagged (SiriusXM VIN flaw, Nissan API, Ford Tel Aviv center), no-evidence-found (QNX/BlackBerry corporate), and on-record quotes preserved verbatim.

## 14. What Remains Unresolved

1. Ford's Tel Aviv research center: reported, unverified here.
2. The SiriusXM connected-vehicle flaw's full brand list: B-grade.
3. OEM in-house data platforms' current suppliers (post-Otonomo): partially opaque by design.
4. Chinese OEMs (BYD et al.): outside US-market scope, unverified.
5. Whether Cymotive's sale to KPIT completes: pending at compilation.

## 15. Key Figures at a Glance

| Figure | Value | Context |
|---|---|---|
| Mobileye voting control | 96.9% Intel | ADAS in a majority of new cars |
| Argus/Continental | ~$430M (2017) | Three Unit 8200 founders |
| Cymotive/KPIT | Up to $120M (2026) | VW's SDV security, Israeli-built |
| Jeep recall | 1.4M vehicles | First cybersecurity-driven recall, 2015 |
| Relay-theft protection rate | ~15% (ADAC) | 59% of 2025 Dutch thefts keyless |
| Pwn2Own Automotive 2026 | 76 zero-days | Tokyo; incl. Alpitronic full control |
| QNX share | 38.2%; 235M vehicles | Clean Canadian safety OS |
| Otonomo | 4B data points/day, 40M vehicles | Collapsed $1.4B → ~$70M → Urgent.ly |

## 16. Glossary

- **TCU:** telematics control unit — the car's cellular modem.
- **ADAS:** advanced driver assistance — cameras/radar/lane-keeping.
- **CAN bus:** the car's internal network connecting its computers.
- **OBD port:** the diagnostic port under the dash — the master key.
- **QNX/AAOS/AGL:** the car's operating systems (Canadian/Google/open).
- **UNECE R155/R156:** 2024 mandates requiring cybersecurity and OTA-management systems.
- **Relay theft:** keyless entry defeated by radio extension — no malware, under a minute.
- **V2X:** vehicle-to-everything communication (Autotalks' domain).
- **OCPP:** the charger network protocol with the checkered security record.
- **Who Profits:** the Israeli-occupation corporate database referenced for OEM profiles.

## 17. The Conclusion, in One Paragraph

The car inherits everything this series established about phones and doubles it: a single fused architecture, a privileged second computer (the TCU, the modem of the road), an attack surface documented from the university lab to the CIA's own files, and — uniquely — an entanglement so structural that no option sheet escapes it: the eyes (Mobileye), the dashboards (Qualcomm), the locks (Argus/Continental, Karamba/GM, Cymotive/VW), and for years the data broker (Otonomo) are all Israeli-built, and every major OEM's ledger carries a documented tie. The protections that remain are real but modest: the least-connected trim, hardened keys against the relay epidemic, locked OBD ports, kept-current software, and — for the strictest criterion — the pre-connected used car as the only true exit. The same pattern that closed the Lebanon file closes this one: when the holder cannot verify the authorship of the layers beneath them, the rational response is minimization — shorter wires, fewer radios, older simplicity — and the car, more than any device yet audited, punishes the alternative. Everything above is sourced, graded, and gap-marked; the open questions are listed in Part 14, and nothing unresolved is presented as resolved.

---

*Compiled 2026-09-21. Four research passes; B-grade items flagged; on-record quotes verbatim; the Ford Tel Aviv center and SiriusXM flaw explicitly bounded.*
