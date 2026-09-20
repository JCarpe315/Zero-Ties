# The Zero-Ties Implant: A Complete Audit of Israeli Entanglement in Connected Medical Devices

αΩ∞

*A fully-sourced investigation into the devices we cannot switch off — pacemakers, defibrillators, insulin pumps, continuous glucose monitors — their Israeli corporate apparatus, the hacking record from Barnaby Jack to the FDA's recall files, and the honest limits of what a patient can do, as of September 2026.*

---

## 1. Why Medical Devices Are the Hardest Target in This Series

Every device audited so far — laptop, phone, router, car — shares one mercy: you can put it down. A pacemaker, an insulin pump, an implanted defibrillator cannot be switched off, Faraday-pouched, or left in a drawer. It is inside you, its radio is always near, and the person who might care most about its vulnerabilities is also the person least able to do anything about them: the patient, who chose it in a clinic, under time pressure, from a shortlist written by someone else.

This document therefore has two duties the others did not: to map the entanglement completely, and to be brutally honest about the protection ceiling — because in this category, more than any other, the honest answer to "how do I protect myself" is partly "you cannot, fully — but here is everything that does work."

### How to read this document

- **Part 2** — the short answer. **Part 3** — orientation for patients and families.
- **Parts 4–7** — the audit: cardiac devices, diabetes devices, the hack record, and the regulatory bedrock.
- **Part 8** — the patient-defense ecosystem (the people doing this work for free).
- **Part 9** — protections: what actually works and what does not.
- **Part 10** — minimum-entanglement choices by device type.
- **Parts 11–15** — method, open questions, key figures, glossary, conclusion.

---

## 2. The Short Answer

**The cardiac-device corporate ledger is dominated by Medtronic — whose Israeli apparatus is the largest of any medical company in this series — while the diabetes-device stack is, remarkably, the cleanest major hardware category yet found.** Medtronic operates roughly **1,200 employees across eight Israeli sites** (Jerusalem, Yokneam, Herzliya) and built its surgical-robotics, respiratory-monitoring, transcatheter-valve, and capsule-endoscopy businesses on Israeli acquisitions — Mazor Robotics ($1.6 billion, 2018, the largest medtech acquisition in Israeli history), Oridion ($346 million), Ventor ($325 million, plus a court-ordered NIS 674 million tax ruling finding its IP had effectively transferred to Medtronic without full compensation), Given Imaging's PillCam (via Covidien, 2014), CathWorks, and a $20 million stake in Israeli insulin-pump startup Triple Jump — active and growing through 2025–2026 under Medtronic Israel CEO Arik Corcos. Boston Scientific holds an Israeli tie (SoniVie, up to $540 million, March 2025). **Biotronik — the Berlin company whose home-monitoring data flows to Germany — is the cleanest corporate in the cardiac stack.** Abbott's St. Jude business owns the largest device-cybersecurity recall on record. The diabetes stack — Dexcom, Tandem, Insulet, Abbott's Libre, Beta Bionics — surfaced no Israeli corporate ties at all. And the open-source Tidepool Loop pathway offers something no other category in this series has: a community-built, FDA-cleared algorithm the patient can actually read.

## 3. A Thirty-Second Orientation for Patients and Families

An implanted cardiac device — pacemaker, ICD (implantable cardioverter-defibrillator), or ILR (implantable loop recorder, a long-term heart monitor) — contains a radio. At home, a **transmitter or monitor** (a bedside box or a smartphone app) reads it regularly and forwards the data to the manufacturer, who forwards it to your clinic. None of these systems can change your device's programming remotely — by design, implant programming happens only in the clinic, with a wand on the skin. That design boundary is the single most important safety fact in this document: every documented attack could *read* data or, in the worst theoretical case, exhaust a battery or deliver an inappropriate shock — appalling possibilities — but no one has ever changed a device's pacing prescription from across the internet. Hold that fact; it bounds everything else.

## 4. The Cardiac Ledger

- **Medtronic — the entangled giant.** Beyond the Israeli apparatus in Part 2, the cardiac-specific facts: the **Reveal LINQ** loop recorder pairs with a proprietary cellular bedside monitor (MyCareLink) that uploads nightly; its pacemakers and ICDs pair with the CareLink ecosystem. Medtronic's devices have also been the community's benchmark target: the DEF CON BioHacking Village has tested Medtronic devices three years running, with Medtronic reporting "zero vulnerabilities discovered" — a claim the Village's coordinated-disclosure culture neither confirms nor disputes publicly.
- **Abbott (St. Jude Medical) — the recall record.** In August 2016 the short-seller Muddy Waters published a report (commissioned from the security firm MedSec) alleging the Merlin@home RF communicator could be attacked; in January 2017 the FDA issued a safety communication and ICS-CERT an advisory, and Abbott pushed an automatic patch to nearly all units; in April 2017 the FDA sent Abbott a warning letter over its cybersecurity risk-assessment process; and in **August 2017 came the largest device-cybersecurity recalls in history: a firmware update for ~465,000 US implanted RF-enabled pacemakers** (requiring an in-person clinic visit, ~3 minutes) **and a recall of ~495,000 Merlin@Home transmitters.** The stated attack consequences: rapid battery depletion and inappropriate pacing or shocks. The system's defense history since: no public exploitation.
- **Boston Scientific — the SoniVie tie.** Acquired Israeli Renal-denervation firm SoniVie (Rehovot) for up to $540 million, March 2025 ($360 million plus milestones); its LATITUDE home-monitoring ecosystem otherwise clean.
- **Biotronik — the clean standard.** Berlin-based; its **Home Monitoring** system (CardioMessenger GSM unit, data to a center in **Germany**) pioneered remote cardiac monitoring (FDA clearance 2001) and remains the most privacy-preserving major platform. No Israeli corporate ties surfaced in any pass.
- **The home-monitoring layer, mapped:** four manufacturer ecosystems — Biotronik (GSM to Germany), Medtronic CareLink, Boston Scientific LATITUDE, Abbott Merlin.net — all manufacturer-tied, none permitting remote programming, with Abbott's holding the incident record. Device choice at implant time is, functionally, a choice among these four data paths.

## 5. The Diabetes Ledger — the Clean Corner

- **Continuous glucose monitors:** **Dexcom** (San Diego — no Israeli ties surfaced; note its own FDA warning letter of March 2025 and a Class I recall of one Android app build — an app-layer defect, fixed; acquired Nutrisense in 2026), **Abbott FreeStyle Libre** (US; corporate history in Part 4), **Medtronic's CGM** (inherits the Part 4 apparatus).
- **Insulin pumps:** **Tandem** (San Diego; SEC-grade corporate, no ties found), **Insulet's Omnipod** (Massachusetts; tubeless; no ties found), **Medtronic MiniMed** (Ireland/US operating history; Medtronic corporate apparatus), **Ypsomed** (Swiss; partners with Cambridge's CamDiab on the MyLife Loop — the Swiss-British clean path), **Beta Bionics' iLet** (US, rising fast).
- **The open-source pathway:** the DIY closed-loop movement (#WeAreNotWaiting, 2013) built **Loop** (an iPhone app connecting pump and CGM over Bluetooth LE), which the non-profit **Tidepool** (backed by the Helmsley Charitable Trust and JDRF, $6 million) carried through the FDA — cleared **January 23, 2023**, the first open-source algorithm and the first interoperable automated-insulin-dosing app ever authorized; partners include Insulet's Omnipod and (future) Medtronic Bluetooth pumps, with Dexcom G6 as CGM. The caveat, consistent with this whole series: the open algorithm runs on an iPhone — the cleanest software on the most audited-tainted host. It is the only category where the patient can read the code that keeps them alive.

## 6. The Hack Record — from Demonstration to Regulation

- **Barnaby Jack, the founding dossier.** In 2011, the New Zealand hacker demonstrated at McAfee's FOCUS conference a wireless takeover of an insulin pump: **no serial number needed** (improving on Jay Radcliffe's 2011 Black Hat work, which had required one), a range of ~300 feet with a high-gain antenna, commanding maximum 25-unit doses repeatedly until the 300-unit reservoir ran dry — multiple lethal doses, delivered by radio. In 2012, at BreakPoint in Melbourne, he went after a pacemaker: querying the device returned its model and serial number, and he delivered an **830-volt shock** to a test unit — and showed the attack could propagate, device to same-vendor device. He was scheduled to present "Implantable Medical Devices: Hacking Humans" at Black Hat 2013; **he died on July 25, 2013**, a week before the talk (a coroner ruled accidental drug overdose; he was 35). The FDA's device-safety leadership publicly credited his demonstrations with forcing the issue; the FDA's first cybersecurity guidance followed in 2013. DHS analyses separately noted implant vulnerability to strong electromagnetic pulses.
- **The St. Jude sequence** (Part 4) — the market's stress test.
- **The infrastructure flaws:** URGENT/11 (VxWorks TCP/IP) and Ripple20 (Treck TCP/IP) — bugs in the third-party network stacks buried inside medical devices — drove recalls and advisories across the industry, motivating the SBOM regime below.
- **The DEF CON record:** the BioHacking Village has tested hundreds of devices across a decade; at DEF CON 34 (August 2026) researchers found **68 vulnerabilities** across medical devices, all under coordinated disclosure — "zero headlines," which is the point.

## 7. The Regulatory Bedrock

The **PATCH Act's Section 524B** (enacted in the Consolidated Appropriations Act, 2023; effective March 29, 2023) made medical devices **the first product category in the world with a mandatory Software Bill of Materials** — manufacturers must submit an SBOM (SPDX or CycloneDX formats, per NTIA minimum elements), maintain a vulnerability-monitoring and patching plan with defined cadence, offer coordinated vulnerability disclosure, and (per the June 2025 guidance) notify customers of exploitable vulnerabilities within 30 days; FDA guidance has iterated (September 2023 → June 2025 → February 2026, aligning with the quality-management overhaul QMSR/ISO 13485). The EU's Cyber Resilience Act (2024) converges on the same architecture. From patch-or-perish to paper-or-RTA (refuse-to-accept enforcement began October 2023): the industry that Barnaby Jack embarrassed in 2011 now has the strictest software-supply-chain market entry on earth.

## 8. The Patient-Defense Ecosystem

The people protecting patients without being asked: the **BioHacking Village** (DEF CON's medical arm, run by Nina Alli; 5,000-plus hackers trained; its #WeHeartHackers coordinated-disclosure program partnered with the FDA itself in 2019); **I Am The Cavalry** (the grassroots human-safety initiative whose volunteer researchers forced manufacturers to the table); the **Hippocratic Oath for Connected Medical Devices** (3,274 signatures from researchers pledging responsible disclosure); and the **2016 DMCA exemption** that legalized good-faith medical-device security research — won, in part, by that community. Medtronic, Philips, Abbott, BD, and Roche now send engineers to the Village. The inside of the industry has quietly adopted its adversaries' methods; patients are the beneficiaries.

## 9. Protections — What Works and What Does Not

**What does not work, said plainly:** no RF-shielding pouch, bag, or garment is a recognized mitigation for an implanted device's radio (searched across rounds; no standard exists, and strong magnets near some devices are themselves contraindicated). You cannot firewall an implant. Anyone selling implant "EMF protection" is selling comfort.

**What does work:**

1. **The pre-implant conversation** — the only true choice point. Ask the cardiologist or endocrinologist: what radio does this device have, what is its range, what is the home-monitor path, and which manufacturer ecosystem does it join? Where the clinical options are equivalent, the ledger is a legitimate tiebreaker: **Biotronik for cardiac remote-monitoring; the Tandem/Insulet/Omnipod/Dexcom stack or Ypsomed-CamDiab for diabetes; Loop/Tidepool for algorithm transparency** (accepting the iPhone caveat).
2. **Attend every recall and firmware update.** The 2017 Abbott recall was resolved in ~3-minute clinic visits; the population-level defense is procedural, and it works — treat recall letters like prescriptions.
3. **Register the device** with the manufacturer so advisories reach you.
4. **Use only the manufacturer's transmitter/app** for home monitoring; the phone inherits its own ledger (per the phone investigation), so the app choice is a second, quieter decision.
5. **Clinic checks on schedule** — interrogation sessions confirm battery and settings regardless of the network.
6. **For the threat-model-extreme** (a handful of public figures, abuse survivors, journalists): discuss with the care team whether a device with wireless functionality disabled or minimized is clinically appropriate — some devices support clinician-controlled RF limits, and the question costs one appointment.

## 10. Minimum-Entanglement Choices by Device Type

| Need | Cleanest mainstream option | Residual |
|---|---|---|
| Pacemaker/ICD + remote monitoring | **Biotronik** (Berlin; data to Germany) | Clinic decision governs; silicon supply chain universal |
| Heart rhythm monitoring (ILR) | Abbott Confirm Rx (runs through *your* phone — choose the phone per the phone report) or Biotronik | Phone-ledger inheritance |
| CGM | **Dexcom** or Abbott Libre | App-layer; Dexcom's own 2025 FDA letter noted |
| Insulin pump (tubed) | **Tandem** | — |
| Insulin delivery (tubeless) | **Insulet Omnipod** | — |
| Automated insulin dosing | **Tidepool Loop** (open source, FDA-cleared) on the cleanest available phone | iPhone caveat |
| Emergency (AED, public) | **Philips HeartStart** (offline, no connectivity) vs WiFi-enabled rivals | — |

**Irreducible floor:** the silicon and supply chain inside any implant (the Lebanon file's lesson applies in its darkest form here — authorship of the thing inside you); the clinic's formulary; the regulatory regime that now at least forces disclosure; and the fact that in this category, unlike every other in this series, the final choice is made with a physician, not a shopping cart.

---

## 11. Methodology and Evidence Grading

Four research passes: corporate (manufacturer by manufacturer), the security-research record, the regulatory layer, and protections. Grades: S-grade (peer-reviewed clinical reviews of the monitoring ecosystems, FDA texts), A-grade (Calcalist/CTech for Medtronic's Israeli operations; AP; Reuters), on-record (FDA officials' statements on Jack; corporate DEF CON participants), B-grade flagged (Ypsomed inferred via MyLife Loop; Dexcom recall details). Searched-and-not-found items are stated as such (RF shielding).

## 12. What Remains Unresolved

1. **RF-shielding for implants:** no recognized mitigation exists; the honest floor is procedural.
2. Ypsomed corporate: Swiss, inferred via partnership; unverified independently.
3. Cochlear implants and deep-brain stimulators: category noted; manufacturer-level audit incomplete (Medtronic DBS inherits the corporate ledger).
4. The 2022-protesters medical-sanctions thread: outside scope, noted once, not pursued.
5. Whether Tidepool adds Android hosting: open at compilation.

## 13. Key Figures at a Glance

| Figure | Value | Context |
|---|---|---|
| Medtronic Israel | ~1,200 staff, 8 sites | Mazor $1.6B; Ventor $325M + NIS 674M ruling; PillCam; CathWorks; Triple Jump |
| SoniVie/Boston Scientific | Up to $540M (Mar 2025) | Renal denervation, Rehovot |
| Abbott recalls | 465,000 implants + 495,000 transmitters | Aug 2017; largest device-cyber recalls |
| Barnaby Jack | Insulin pump 2011; pacemaker 830V 2012; died July 2013 | Forced FDA's first cyber guidance |
| Tidepool Loop | FDA-cleared Jan 23, 2023 | First open-source AID algorithm |
| Section 524B | Effective Mar 29, 2023 | World's first mandatory SBOM |
| DEF CON 34 | 68 vulnerabilities, coordinated | Aug 2026; "zero headlines" |
| Biotronik | Berlin; GSM data to Germany | Cleanest cardiac corporate |

## 14. Glossary

- **Pacemaker/ICD/ILR:** rhythm devices; ILR = long-term monitor.
- **Home monitor/transmitter:** bedside box or app forwarding device data to the clinic.
- **Interrogation:** the clinic wand-session that reads (and only in-clinic can program) the device.
- **CGM:** continuous glucose monitor; **AID:** automated insulin dosing (the "artificial pancreas").
- **SBOM:** software bill of materials — the ingredient list the FDA now requires.
- **Coordinated disclosure:** the researcher-to-manufacturer reporting pipeline (the BioHacking Village's model).
- **DMCA exemption:** the 2016 legal carve-out permitting good-faith implant research.
- **RTA:** FDA refuse-to-accept — the enforcement teeth behind 524B.

## 15. The Conclusion, in One Paragraph

A medical device is the only object in this series that the owner cannot put down, cannot shield, and mostly did not choose alone — and that asymmetry defines everything the audit found. The corporate map splits cleanly: one giant built substantially in Israel (Medtronic's eight sites, its robotics and valves and capsules and insulin stakes), one giant holding the industry's cybersecurity scar tissue (Abbott's 2017 recalls), one acquisition-marked newcomer (Boston Scientific–SoniVie), and one quiet German standard for the privacy-conscious (Biotronik); while the diabetes stack — Dexcom, Tandem, Insulet, Beta Bionics — emerged as the cleanest hardware category this series has examined, crowned by the only FDA-cleared open-source therapy algorithm on earth. The hack record runs from a New Zealander's 300-foot insulin-pump takeover through an 830-volt pacemaker shock to a recall of nearly half a million implanted hearts — and its product, finally, is the strictest software-disclosure regime in any industry, defended nightly by volunteers at DEF CON. The protections, stated without decoration: choose at the implant conversation when the choice exists; keep every firmware appointment; register the device; ask the one hard question about radios. And the shadow over all of it, from the Lebanon file: the day supply-chain authorship becomes lethality, the devices that cannot be put down are the ones that matter most — which is why this document, like the implant itself, keeps working after you stop thinking about it. Everything above is sourced, graded, and gap-marked; Part 12 lists what could not be resolved, and nothing there is presented otherwise.

---

*Compiled 2026-09-21. Four research passes; clinical reviews and FDA texts at S-grade; corporate reporting at A-grade; no recognized shielding mitigation exists and none is claimed.*
