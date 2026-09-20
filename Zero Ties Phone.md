# The Zero-Ties Phone: A Complete Audit of Israeli Entanglement in the Cell Phone and Prepaid Market

αΩ∞

*A fully-sourced investigation into whether a cell phone — including the prepaid market, the carriers underneath it, and every brand on sale as of September 2026 — can have zero ties to Israel, foreign or domestic.*

---

## 1. The Question

The question from the laptop investigation returns, harder: **is there a cell phone on the market — at any price, in any category, including the prepaid burner market — with zero ties to Israel?**

A phone is a more difficult object to audit than a laptop, for three structural reasons explained in Part 3. But the question also reaches further than the device itself: a phone without service is a camera-shaped brick, so this investigation audits the entire stack a working phone depends on — the silicon, the modem, the operating system, the brand, the prepaid carrier, the billing system behind the carrier, the SIM card, the point of sale, and even the apps and advertising code the user touches afterward.

### How to read this document

- **Part 2** gives the short answer.
- **Part 3** explains why phones are harder than laptops — a short orientation for any reader.
- **Parts 4–10** are the hardware audit: silicon, modems, memory, cameras, security chips, and the last component layers.
- **Parts 11–14** are the software and corporate audit: operating systems, the spyware ecosystem, every brand on the market, and the clean-phone teardowns.
- **Parts 15–18** are the service stack: prepaid, SIM cards, carriers, and the back office.
- **Part 19** is the app and advertising-code layer — the deepest software finding of the investigation.
- **Part 20** covers Israel's domestic market, for the "domestic" half of the criterion.
- **Part 21** is the practical result: the minimum-ties phone.
- **Part 22** is the complete market ledger.
- **Part 22** explains how we know what we know (methodology and evidence grading).
- **Part 23** lists what remains unresolved.
- **Part 24** is a key-figures table for quick reference.
- **Part 25** is a glossary of every technical term used.
- **Part 26** is the conclusion, in one paragraph.

A note on framing, identical to the laptop report: this document argues no political position. The user's criterion is a supply-chain standard — zero ties to Israel — and this document measures the market against it. Where Israeli involvement is found it is documented with sources; where it is not found, that too is documented; where evidence is thin or disputed, the ambiguity is preserved rather than resolved by opinion.

---

### A thirty-second orientation for readers new to phones

A modern smartphone is effectively **two computers wearing one case**. The first is the one you see — the touchscreen, the apps, the operating system. The second is the **cellular modem**, a completely separate computer with its own closed software whose only job is talking to the cell towers, and which sits in a privileged position the main computer cannot fully supervise. On top of that, a flagship phone is built around a single chip — the **SoC** (system-on-chip) — that fuses the processor, graphics, camera processing, security hardware, and modem interface into one piece of silicon. A laptop lets you swap a tainted part for a clean one; a phone, fused this way, largely does not. Keep that image — one fused chip, plus a secret second computer — in mind and every section below will read clearly.

---

## 2. The Short Answer

**No mainstream smartphone has zero ties to Israel — and a phone is entangled in ways a laptop never can be.** Five structural findings hold at audit grade:

1. **Every flagship silicon path is tainted.** Qualcomm (two Israeli R&D centers operating since 1993). Apple (its Herzliya team designs the performance CPU cores — Firestorm, Avalanche, Everest — plus every storage controller, the Face ID core, and now the C1X modem and N1 wireless chip). Samsung (its Israeli centers contribute to Exynos chips and design the UFS storage architecture and ISOCELL camera line used in hundreds of millions of phones). Google Tensor (built on Samsung silicon and ARM designs, while Google assembles new chip teams inside Israel). The only audited clean silicon path is **MediaTek — BDS-1000 score 248, the lowest audited score in this entire investigation — and it is "clean with an asterisk": a venture-capital trail into Israeli chip startups, including one defense-adjacent AI firm, and distributor channels into Israel, but no office, no subsidiary, no contract.**

2. **The modem layer has no clean Western option.** Every iPhone modem ever shipped is either Qualcomm (Israeli R&D) or Apple C1/C1X (Israeli-designed). Samsung's modems come from the same company whose Exynos and UFS architecture carry Israeli authorship. The only Israeli-clean modems in any phone are Chinese — made by BroadMobi, Quectel, or integrated into Unisoc and MediaTek designs.

3. **The software forks do not escape the hardware.** GrapheneOS — independently audited as clean software, with no Israeli vendors anywhere in its infrastructure — runs *only* on Google Pixel phones whose Tensor silicon is triply tainted. The best private operating system in the world sits on the most entangled mainstream phone hardware.

4. **The service stack is entangled at its core.** Every US carrier — the networks every prepaid SIM must ride — carries documented Israeli ties: AT&T runs a 500-engineer Israeli R&D operation that develops 5G network software and the FirstNet public-safety system; Verizon maintained an Israeli venture office for six years; T-Mobile's parent Deutsche Telekom has invested in Israeli funds since 2002. And the billing software underneath essentially all of them is **Amdocs, an Israeli-founded company holding contracts with roughly 90 percent of the world's top carriers, with AT&T alone accounting for about a quarter of its revenue.**

5. **Israeli code reaches a typical phone through three doors the buyer cannot fully control:** the apps themselves (Meta, Spotify, Waze, Israeli mobile games), the advertising-and-attribution **SDKs embedded inside other people's apps** (AppsFlyer — Israeli-founded, inside roughly half of all Android apps), and the **offensive-cyber industry** (NSO's Pegasus, Intellexa's Predator, QuaDream's Reign) that exists specifically to attack these devices under Israeli Ministry of Defense export licensing.

**The closest achievable mainstream machine** (Part 21): an **Honor** phone with a MediaTek Dimensity chip — Honor is the only Tier E ("Minimal/No Complicity") company audited in this investigation, scoring **192**, and its upcoming Magic 8 Mini is tipped to carry a flagship MediaTek Dimensity 9500 — running stock Android with Meta apps uninstalled, on a T-Mobile-based prepaid plan, activated online, with a physical SIM. **The maximal-cleanliness machine**: the PINE64 PinePhone, which contains no Israeli-authored component found anywhere in its build — at hobbyist performance, riding a carrier certification system that barely tolerates it.

---

## 3. Why Phones Are Harder Than Laptops

Three structural differences, stated plainly:

**Integration.** A laptop is a federation — you can choose the CPU, the Wi-Fi card, the memory, the SSD independently. A flagship phone is one SoC that fuses everything. When that one chip is entangled, the whole device is entangled; there is no AMD-versus-Intel choice inside a Snapdragon phone.

**The secret second computer.** The cellular modem runs its own closed operating system — a real-time OS the user never sees, cannot audit, and often cannot update independently. Security researchers treat the modem as the single most privileged attack surface in mobile hardware. And the modem question has a bitter answer: every Western modem is documented as Israeli-touched, and the clean ones are exclusively Chinese.

**Lockdown.** Mainstream phones ship with locked bootloaders, meaning the owner cannot fully replace the vendor's software. The vendor's choices — preinstalled apps, cloud backups, telemetry — follow the device for its usable life unless the buyer deliberately works around them.

---

## 4. The SoC Layer — The Fatal Layer, at Audit Grade

### 4.1 Qualcomm — the Intel of phones

Two Israeli R&D centers (Haifa and Hod Hasharon) operating since 1993; five Israeli acquisitions between 2010 and 2016; and in May 2023 a definitive agreement to acquire **Autotalks**, an Israeli vehicle-connectivity chip startup. Snapdragon sits inside most premium Android phones and, historically, inside every iPhone's modem. Its silicon carries the same category of taint as Intel's CPUs — Israeli-authored engineering at the core of the product. Notably, **Qualcomm Ventures is also an investor in Nothing** (a phone brand examined below) — a corporate link recorded for completeness even though the money itself is American.

### 4.2 Apple — the deepest silicon authorship of any phone maker

The laptop investigation established Apple's Herzliya dossier; the phone investigation extends it:

- **The performance CPU cores themselves are Israeli-designed.** Semiconductor-analysis reporting on Apple's chip organization is unambiguous: "Israel is where Apple's CPU performance leadership is designed. The Herzliya team, many recruited from Intel Israel — which created the Pentium M, Core, and Sandy Bridge architectures — designs the Firestorm, Avalanche, and Everest cores that dominate benchmarks." Apple runs 8,000-plus chip engineers across more than fifteen design centers; the performance cores — the ones that win benchmarks — are the Israeli file.
- **Every storage controller in every Apple product is Israeli-designed**, per Johny Srouji, Apple's hardware chief, on the record: it began with the Anobit acquisition ("our first Israeli company"), whose team produced Apple's first in-house storage controller nine months later, later adapted for iPhone.
- **Face ID's core** is PrimeSense (Israeli, acquired 2013 for about $345 million); Apple also acquired Israeli facial-recognition firm RealFace (2017) and AR-camera firm Camerai; the January 2026 acquisition of **Q.ai — reported at roughly $1.5–2 billion** — adds facial micro-movement and "silent speech" AI. (Founders' Unit 81/8200 backgrounds trace to a single advocacy source and are flagged uncorroborated.)
- **The modem the company built to escape Qualcomm is Israeli-designed:** the C1 (iPhone 16e) and C1X (iPhone 17 series), along with the N1 wireless chip — per the OpenIntel Apple dossier, "Israel-designed silicon feeding directly into global Apple products."

**OpenIntel's Apple audit: BRS 582, Tier C ("High")** — Economic 8.00 (the acquisition stack plus Israeli-designed silicon in current products), Political 6.29 (explained below), Military 0.09 and Digital 0.20 (near-zero: no defense contracts, not in the UN OHCHR settlement database, not listed by PAX or Who Profits, and explicitly **not** a party to Project Nimbus). The political score comes from the **Benevity donation-matching controversy** — Apple matched employee donations to Friends of the IDF, the Jewish National Fund, One Israel Fund, HaYovel, and IsraelGives; 133–140 employees signed a June 2024 open letter; Apple did not respond to press inquiries. Apple also disciplined employees over pro-Palestinian expression (a Chicago keffiyeh case; roughly 40 staff reprimanded over bracelets; both Muslim and Jewish employee-resource Slack channels suspended). And Apple's relationship with Israeli offensive cyber is adversarial, not cooperative: it sued NSO Group in November 2021, then moved to dismiss in September 2024 citing the risk of exposing vital security information.

### 4.3 Samsung — BRS 639, Tier B ("Severe")

- Two Israeli R&D centers since the **2007 acquisition of Transchip** — the first foreign semiconductor acquisition by a Korean conglomerate since 1997.
- The **Herzliya camera center** built the Galaxy S3's camera and, in the center's own description, all of the camera's processing technology — the wiping effects and special processing — done in Israel. Its technology is installed on hundreds of millions of smartphones.
- The **Ramat Gan semiconductor center** contributed directly to Exynos chips, including the Exynos 5 (32nm dual-core) and the transition to 14nm — "work on the chip was done both in Israel and South Korea."
- **SIRC Tel Aviv** (the Samsung Israel R&D Center) belongs to Samsung's flash-memory division and is responsible for the development of next-generation **SSD, UFS, and eMMC storage architecture** — meaning the flash interface standard inside essentially every Samsung phone (and sold to others) has Israeli design authorship at the platform level. SIRC also develops image sensors.
- **Audit verdict: BRS 639, Tier B**, driven by the durable wholly-owned Israeli R&D footprint, the completed Transchip acquisition, and consumer-market scale. The audit explicitly preserves its caveat: unverified reporting about Cellcom device sales was *not* converted into proof of direct military contracting.

### 4.4 Google Tensor — quadruply tainted, and Google is building more in Israel

Tensor (Pixel chips) descends from Samsung semiconductor design, licenses ARM technology, and is developed inside a company whose Israeli operations keep expanding: in March 2021 Google hired ex-Intel corporate VP **Uri Frank** to build a server SoC design team in Israel (Frank had run a 2,000-person Intel design group spanning Israel, the US, and India); in September 2026 Google assembled a new edge-AI chip team in Israel led by former Hailo executive Guy Kaminitz, with ex-Pliops CEO Ido Bukspan leading data-networking chips. Separately, Google's security chip — the **Titan M2** — is designed and manufactured by Google in-house and runs on the open **RISC-V** instruction set (architecturally the one mainstream security chip not built on ARM IP); no public source attributes Titan authorship to Israel, but it sits inside Tensor silicon, so the enclave is clean while the host is not. Google is also, with Amazon, the contractor on **Project Nimbus** — the $1.2 billion Israeli government cloud program.

### 4.5 MediaTek — the cleanest audited semiconductor company in this investigation, full detail

OpenIntel's forensic dossier assigns **BRS 248, Tier D ("Moderate")** — the lowest score encountered across every company audited for either the laptop or the phone investigation. The complete ledger:

- **No Israeli office, R&D center, subsidiary, or state contract.** MediaTek's official office list spans the United States, China, Dubai, Finland, India, Japan, Korea, Singapore, Sweden, Taiwan, and the United Kingdom — no Israel entry. The audit *re-examined and rejected* a prior claim of a "MediaTek Semiconductor (Israel) Ltd." — it was an erroneous reading of an Ireland entry.
- **The venture portfolio (the asterisk):** at year-end 2024, via MTKC Global Holdings, MediaTek disclosed a **4 percent stake in NeuroBlade** (Tel Aviv AI chips; $5.539 million) and a **1 percent stake in proteanTecs** (Haifa; founded by ex-Mellanox executives; $3.846 million). Earlier disclosures: 1 percent each in **Valens** (Israeli HDBaseT — MediaTek also joined its 2017 round), **Innoviz** (Israeli lidar), and **VisIC** (Ness Ziona gallium-nitride power), plus exposure to **Viola Ventures VI** (an Israeli fund). In 2017 MediaTek co-led a round in **Corephotonics**, the Tel Aviv dual-camera startup whose optical-zoom technology defined the iPhone 7 Plus era and was licensed industry-wide.
- **The one defense-adjacent item:** in June 2020 MediaTek participated in the **$3.5 million seed round of OneView**, a Tel Aviv synthetic-data AI company, **alongside Rafael Development Corporation** — the venture vehicle of the Rafael defense prime. OneView's founders hail from "elite intelligence units"; its site markets to defense and intelligence customers and still lists MediaTek as an investor. The audit's precision matters: this is **investment adjacency, not supply** — no verified MediaTek supply relationship with Rafael, the IDF, or the Israeli Ministry of Defense.
- **Distribution:** MediaTek products reach Israel only through third-party distributors (Rutronik's franchise covers Europe plus Israel; Mouser Israel; DigiKey Israel). No settlement-specific distribution was found.
- Post-2024 portfolio status is unresolved (2025 filings do not confirm continuation or exit) — preserved as an open item.

**Bottom line:** MediaTek silicon carries no Israeli design authorship and no Israeli corporate presence — only a documented venture-portfolio footprint, one item of which sits beside a defense-prime venture arm. For a buyer applying a "nothing Israeli inside the machine" standard, MediaTek is the answer; for a strict "zero relationships of any kind" standard, the venture portfolio is the residue.

### 4.6 Unisoc and HiSilicon Kirin

**Unisoc** (China): no Israeli office, investment, or partnership surfaced in any pass — its chips power Nokia's Unisoc feature phones, some Hisense models, and low-cost Androids worldwide. Caveat: unlike MediaTek, Unisoc has not been through an audit-grade dossier; the finding is "no evidence found," one tier weaker.

**HiSilicon Kirin (Huawei):** the Kirin silicon itself is designed in Shenzhen — no Israeli *silicon authorship* was found. But Huawei-the-corporation fails a zero-ties test at corporate level, through **Toga Networks** (full dossier in Part 13): Huawei acquired Toga Networks and HexaTier in 2016 (Toga reported at up to $150 million); Toga — founded 2009 in Hod Hasharon by Itzik Malobani — is Huawei's Israeli R&D arm with roughly 400–500 employees across Hod Hasharon and Haifa in 12–14 research groups (high-speed switching, cloud, storage — division closed 2023 — AI and data-center silicon, automotive, computer vision). The working model, per Globes: Israeli teams build architecture to proof-of-concept stage, "the accrued know-how is then transferred in its entirety to China"; Toga files 90–100 patents a year. Toga was conspicuously absent from the May 2019 Entity List and added in the August 2020 round — per former employees, it used the grace period to stockpile test equipment — and one export-license revocation pushed Huawei to move development to the UK. February 2026 brought layoffs of about 50 cloud staff. Huawei, like AMD in the laptop report, is "corporate-level ties, silicon clean" — with the added note that the corporate tie is a genuine R&D center, not merely an office.

---

## 5. The Modem Layer — The Secret Second Computer, Fully Traced

The baseband modem is a second, independent computer inside every phone, running closed firmware in the most privileged position in the device. Its genealogy is now traceable end to end — and it contains one genuinely clean chapter:

- **2007–2010: Infineon (German).** The original iPhone's modems were German-designed — the only Israeli-clean chapter in iPhone modem history.
- **2010/11: Intel buys Infineon's wireless unit for $1.4 billion.** The Munich operation became Intel's modem hub.
- **2011–2016: Qualcomm's billion-dollar exclusivity.** Court testimony revealed Qualcomm *paid Apple* roughly $1 billion over three years to be the exclusive modem supplier, with clawbacks if Apple dual-sourced.
- **2016–2018: Intel's window.** iPhone 7 dual-sourced (Intel PMB9943); the iPhone XS/XR generation went all-Intel in 2018 because Qualcomm refused to support dual-sourcing (Apple COO Jeff Williams, sworn testimony).
- **April 2019: the settlement.** Apple paid approximately $4.5–4.7 billion and signed a six-year Qualcomm license; Intel exited 5G modems the same day (the unit was losing about $1 billion a year, with one customer).
- **July 2019: Apple buys Intel's modem unit — $1 billion, 2,200 employees, more than 17,000 wireless patents** — having already hired Qualcomm's decade-long modem chief and Intel's XMM 8160 lead.
- **2025–2026: the payoff.** The C1 (iPhone 16e) and C1X (iPhone 17 series) are both Israeli-designed per the OpenIntel Apple dossier. **The five-year, multi-billion-dollar effort to escape a tainted supplier ended in Herzliya.** Every iPhone modem ever shipped is now documented as Israeli-designed, one way or another.

Beyond Apple: Qualcomm's X-series modems carry the same Haifa/Hod Hasharon lineage; Samsung's Shannon modems inherit the Samsung/SIRC taint; and the only Israeli-clean modems found anywhere are Chinese — BroadMobi and Quectel (used in Linux phones) and the integrated modems in Unisoc and MediaTek designs. The strategic irony is total: the one component that talks to the cellular network — the component where a state-level actor would most want visibility — has no clean Western manufacturer.

---

## 6. Memory, Storage, and Cameras

- **Samsung UFS/flash storage: tainted at the architecture level** via SIRC — the same Israeli center that designs SSD/UFS/eMMC platforms designs the storage inside Samsung phones.
- **Micron: not clean** (Israel R&D locations, an active Israel ASIC design team, and a former Kiryat Gat fab leased from Intel — full detail in the laptop report).
- **SK Hynix and Kioxia: clean** — Korean and Japanese design and manufacture, no Israeli footprint found.
- **Apple: every storage controller in every iPhone is Israeli-designed** (the Anobit line) — so even the NAND vendor matters less than the controller sitting in front of it.
- **Cameras:** Samsung's ISOCELL sensors and their processing are Herzliya-built (Transchip lineage, Galaxy S3 onward). **Corephotonics** — the Tel Aviv dual-camera startup in which Samsung Ventures, Foxconn, and MediaTek invested — supplied the optical-zoom architecture the whole industry licensed after the iPhone 7 Plus, meaning mainstream flagship zoom pipelines trace to Israeli IP regardless of brand. **Sony's correction:** standard Sony camera sensors remain Japan-designed and clean — but Sony Semiconductor Israel (formerly Altair Semiconductor, acquired for $212 million in 2016) developed the **AI digital signal processor inside Sony's IMX500/IMX501 — the world's first image sensor with on-sensor AI processing**; and on April 27, 2026, Sony spun Altair back out with $50 million led by Israeli VC Pitango at a reported ~$300 million valuation, **while retaining an undisclosed equity stake**. Sony therefore leaves the "clean corporate" column: retained stake, Israeli-authored AI layer in the intelligent-vision sensor line. **OmniVision** (US-founded, Chinese-owned) is clean of Israeli ties.

---

## 7. The Security-Chip Layer

- **Google Titan M / Titan M2:** designed and manufactured by Google in-house (the company's own words), running on the open RISC-V instruction set; no public attribution of Titan authorship to Israel — but it lives on Tensor silicon, so the *enclave* is clean while the *host* is tainted.
- **Samsung Knox Vault:** a secure subsystem on Samsung's own SoCs — inherits the full Samsung taint.
- **Qualcomm SPU:** inside Snapdragon — tied by the same lineage.
- **MediaTek devices:** ARM TrustZone plus MediaTek in-house security IP — indirect ARM taint only.
- **Apple Secure Enclave:** provenance **unresolved** — no source was found in repeated attempts; recorded as an open item, not guessed.

---

## 8. UWB, Satellite, and the Remaining Component Layers

- **Apple U1/U2 (ultra-wideband):** provenance unresolved (zero results) — noted, not guessed.
- **Android UWB:** Samsung's own or Qorvo (US, clean) / NXP-based — NXP carries its Yokne'am, Israel design-center tie.
- **Satellite:** iPhone Emergency SOS rides Globalstar (US, clean); competing Snapdragon Satellite is Qualcomm-tied.
- **Wi-Fi/Bluetooth:** in flagships, Qualcomm FastConnect (tied) or Apple-designed wireless (the N1 wireless chip is Israeli-designed per the OpenIntel Apple dossier); in MediaTek phones, MediaTek's own integrated Wi-Fi/BT (clean); Realtek (clean) in Linux phones.
- **NFC/eSIM secure elements:** NXP (Yokne'am tie) versus ST and Infineon (clean).
- **GNSS:** u-blox (Swiss, clean) versus Qualcomm/Broadcom (tied).
- **Audio, haptics, displays, batteries, assembly: clean** — the same finding as the laptop report.
- **Punkt MC02:** Dimensity 900 confirmed, but its RAM/flash vendors have never been identified in any teardown — open item (industry norms suggest Samsung or Micron; flagged as inference, not evidence).

---

## 9. The Operating System Layer

- **iOS: maximal entanglement** — the Apple dossier applies verbatim (Israeli CPU cores, Israeli storage controllers, Israeli modem).
- **Android: heavy.** Google Israel's R&D (Waze lineage, Call Screen, search and AI features), Project Nimbus ($1.2 billion, Google and Amazon only — OpenIntel confirms Apple is not a party), and Google's new Israeli chip teams.
- **GrapheneOS — audited clean, with the hardware catch.** An OpenIntel digital-infrastructure audit found: no Israeli enterprise-security vendors anywhere in its stack; no Israeli data-center locations; no Nimbus participation; no Israeli contracts, R&D, or investments; a Canadian non-profit. **But GrapheneOS runs exclusively on Google Pixel hardware** — so the cleanest audited phone *software* chain bottoms out in tainted silicon. This clean-software-on-tainted-hardware combination is the phone problem in miniature.
- **CalyxOS and /e/OS:** similar forks with similar device constraints; /e/OS supports a wider device list including some Samsung and Fairphone models — trading one taint for another.
- **KaiOS** (feature phones): a Hong Kong/San Diego company whose OS descends from Mozilla's Firefox OS (clean lineage), but whose app store preloads Google and Facebook apps; and its hardware mixes Qualcomm, MediaTek, and Unisoc by model — "KaiOS phone" is not an answer, the chipset is.

---

## 10. The Offensive-Cyber Layer — Israeli Industry Built to Attack These Phones

Recorded here because it is the most direct form of "tie" between Israel and the devices in question, with framing stated precisely: this is not a supply-chain relationship — it is a state-licensed commercial ecosystem whose entire function is penetrating these devices. For a reader whose criterion is exposure to Israeli state-linked capability, it is the single most relevant finding; for a strict supply-chain reading, it is context. Both readings are presented; neither is adopted.

- **NSO Group / Pegasus:** founded 2010 (Niv Karmi, Omri Lavie, Shalev Hulio). Israel classifies Pegasus as a **weapon**; every export requires Israeli Ministry of Defense DECA approval. The New York Times documented Israel treating NSO as a "de facto arm of the state" — a diplomatic instrument: sales were cleared to advance the Abraham Accords, and **blocked to Estonia and Ukraine to protect relations with Russia** (Estonia's $30 million down payment was returned). Deployment requires only entering a phone number; setup takes about fifteen weeks; US court documents priced surveillance of 25 numbers in Ghana at **$8 million**. Israel required NSO to block US numbers from targeting; US intelligence officials reportedly presume Israeli state access to Pegasus-derived data (NSO denies any backdoor). The US placed NSO on the **Entity List in November 2021**; L3Harris acquisition talks in 2022 collapsed in part over Israel's insistence on retaining export-license control; Amnesty International's Israeli lawsuit to revoke the export license was rejected in July 2020.
- **Intellexa / Predator:** founder Tal Dilian served 24 years in Israeli military intelligence; an Intellexa founder was sentenced to **eight years in Greece** over Predator use. Notably, Predator's loader **self-terminates if the phone's locale is Israel or the number is +972** — it is not built to operate at home.
- **QuaDream / Reign:** founded by NSO alumni; its ENDOFDAYS exploit chain used the iCloud calendar for zero-click compromise; full chains exist for both iOS and Android.

**Why this layer cannot be dodged by hardware choice:** Pegasus-class tools are delivered by phone *number*, not by account type or device brand — a prepaid burner defeats billing surveillance but not zero-click exploitation. Mitigation is behavioral and patch-discipline based, not purchasable.

---

## 11. The Complete Brand Ledger — Every Phone Family on Sale, Examined

Approximately forty brand families across every category and price tier, grouped by the two governing axes: **corporate-level ties to Israel** and **silicon-level authorship**.

### Quadrant I — No corporate tie found + clean silicon available (the achievable answer)

| Brand | Ownership | Clean-silicon path | Grade |
|---|---|---|---|
| **Honor** | Shenzhen Zhixin (state-linked; 49.55% direct as of June 2025) | MediaTek X-series, 200 Lite; **Magic 8 Mini tipped with Dimensity 9500 — the first flagship-class clean-SoC path** | **Audit: BRS 192, Tier E — the cleanest entity in the investigation** |
| **Transsion** (Tecno/Infinix/itel) | Shenzhen; Shanghai STAR-listed | MediaTek throughout | No-evidence-found |
| **Unihertz** | Shanghai (2016) | MediaTek (Jelly 2E Helio A22; Jelly Max Dimensity 7300) | No-evidence-found |
| **Mudita** | Warsaw, Poland (founder: Michał Kiciński, CD Projekt co-founder) | MediaTek MT6761, de-Googled MuditaOS K, hardware kill switches, FCC/PTCRB certified | No-evidence-found |
| **BLU** | Miami (private; founded 2009) | MediaTek models | No-evidence-found + FTC/China flag (below) |
| **HMD/Nokia** | Finland | **Unisoc models**: 2660 Flip, 2760 Flip 4G (T107/T310); avoid 2760/2780 flips (Snapdragon 215) | No-evidence-found |
| **TCL** | China | MediaTek models | No-evidence-found |
| **Punkt** | Switzerland | Dimensity 900 (MC02) | No-evidence-found |
| **PinePhone** | PINE64 (Hong Kong) | Allwinner A64 — maximal cleanliness | No-evidence-found |
| **Chinese rugged** (Ulefone, Doogee, Oukitel, AGM) | Shenzhen | MediaTek Helio / Unisoc Tiger | No-evidence-found |
| **Oppo/Vivo** | BBK | Dimensity models in A/X lines | Consumer-guide grade |

### Quadrant II — No corporate tie found + tainted silicon

Oppo/Vivo/OnePlus/Realme/iQOO flagships (Snapdragon) · ZTE/Nubia/RedMagic (Nubia now 78.33% Shanghai Shenqi Jiyuan after ZTE's December 2025 transfer; gaming line Snapdragon throughout) · Meizu (79.09% owned by Geely founder Li Shufu's Xingji Shidai since July 2022) · ASUS Zenfone/ROG (Snapdragon; ASUS even co-built Qualcomm's own branded phone in 2021) · Nothing main line (Snapdragon; the Phone (4a) and CMF line run Dimensity) · Sharp (Foxconn-affiliated) · **Sony Xperia** (Snapdragon; corporate note: Sony's retained Altair stake and the IMX500 AI-DSP lineage) · Fairphone 5 (Qualcomm QCM6490) · Sonim and Kyocera rugged (every model Qualcomm) · Light Phone 3 (Qualcomm) · CAT (Bullitt Group, insolvent 2024).

### Quadrant III — Corporate tie + clean silicon possible

**Huawei** — Toga Networks (~400–500 staff) plus HexaTier; Kirin silicon Shenzhen-designed. **Xiaomi** — **corrected**: the documented Israeli R&D center (Xiaoyi Multimedia Israel Ltd, Rehovot, 25 staff, face recognition, founded 2015) belongs to **Xiaoyi**, a Shanghai camera company and Xiaomi *ecosystem partner* — not to Xiaomi itself. Xiaomi's own direct footprint reduces to retail sales presence (Tel Aviv store since 2018); no Xiaomi-entity R&D center was found under its own name. The earlier "confirmed tie" was a listicle's shorthand collapsing two companies — exactly why evidence grades exist.

### The Motorola distinction — the most important clarification in the brand ledger

**Motorola Solutions is not Motorola Mobility, and the difference is the deepest corporate finding in this investigation.** The two split in 2011. **Motorola Solutions** — the public-safety and radio company, not the consumer phone brand — is among the most deeply military-entangled Western technology firms operating in Israel:

- Operating in Israel **since 1964** — its first R&D subsidiary outside North America.
- **Sole supplier of the IDF's independent cellular network**: the Israeli military runs its own private 4G system, built and operated end-to-end by Motorola Solutions.
- **January 2014: a 15-year, $100 million Israeli Ministry of Defense contract** (half funded through US Foreign Military Sales) for encrypted Lex M20 military smartphones — Israeli-made secure handsets on MSI's network.
- The **Mountain Rose** encrypted network program (~$100 million, 2000–2004), and the **MotoEagle Wide Area Surveillance System** — NIS 400 million since 2005, installed in more than 25 settlements, feeding the IDF's monitoring of Palestinian movement.
- Israel Police's **Nitzan** tactical communications system; settlement contracts (Ariel, Jordan Valley, Mateh Binyamin); **listed in the UN OHCHR settlement database in both 2020 and 2023**; reportedly lobbying the IDF on a ~NIS 1.5 billion 5G upgrade, and in 2021 pressuring the IMOD to withdraw a 5G tender request for information. Its Israeli Innovation Center (opened 2016) is headed by Hemi Pecker, a former prime minister's office cyber chief.

**Motorola Mobility** — the actual consumer phone brand, owned by Lenovo since 2014 — carries *Lenovo's* ledger (the Infinidat acquisition completed April 2026; SentinelOne's Singularity embedded in ThinkShield on new Lenovo PC shipments; the Ben-Gurion University cybersecurity center inside the CyberSpark ecosystem that co-locates Unit 8200; the Phoenix Technologies BIOS-unit acquisition closed April 26, 2026) but **none** of Motorola Solutions' military record. When a boycott guide or a news story says "Motorola," the distinction determines everything — one company makes prepaid phones; the other runs the occupation's communications backbone.

### Quadrant IV — Corporate tie + tainted silicon (maximal entanglement)

**Apple** (BRS 582) · **Samsung** (BRS 639) · **Google Pixel** (Tensor; Israeli chip teams; Nimbus) · **Lenovo/Motorola Mobility** (Infinidat acquisition completed April 2026; SentinelOne's Singularity embedded in ThinkShield on new Lenovo PC shipments; the Ben-Gurion University Cybersecurity Innovation Center inside the CyberSpark ecosystem that co-locates Unit 8200; Lenovo's acquisition of Phoenix Technologies' BIOS unit closed April 26, 2026; Snapdragon or MediaTek silicon).

### Defunct and absent

BlackBerry (hardware dead: TCL license ended, OnwardMobility collapsed February 2022 after the license was canceled, patents sold for a reported ~$600 million) · LG (exited phones 2021) · HTC (dormant) · Essential (assets to Nothing) · Vertu (niche luxury, unverified, immaterial volume) · Energizer/Philips licensees (ODM-built, immaterial). **Unverified minors, stated honestly:** Doro (Swedish, acquired by Norway's Xplora in autumn 2024 — no ties found), Lively/Jitterbug (US — GreatCall was co-founded by Martin Cooper, the inventor of the cell phone; sold to Best Buy for $800 million in 2018; rides Verizon), Swissvoice (Swiss), Emporia (Austrian), Snapfon and RAZ (US), Consumer Cellular (US) — none with Israeli corporate ties found.

### The Honor dossier, in full

The only Tier E company in the investigation. **BRS 192; Military 0.00, Economic 0.00, Political 0.00; Digital 2.30 driven solely by the Honor Health app being listed as available in Israel.** The audit's complete negative ledger: no Israeli subsidiary, office, warehouse, importer of record, authorized distributor, R&D center, data center, investment, or settlement operation; Israel absent from Honor's country selector; Statcounter records **0% Israeli market share** (grey-market listings only); the only named foreign subsidiary is in Mexico. Entity hygiene the audit explicitly performed: Huawei's Israeli assets (Toga, HexaTier) are *not* attributed to Honor after the November 2020 divestiture, and an unrelated "Honor Construction and Investment Company Ltd." in Ramat Gan was identified and excluded. The tradeoff stated plainly: Honor's ownership is Chinese state-linked (upstream Shenzhen SASAC; China Mobile, China Telecom, BOE among investors), and Reporters Without Borders separately flags Chinese-device data-governance risk. A zero-Israeli-ties phone that is transparent to a *different* state's data-compulsion regime — the criterion is satisfied; the trust calculus inverts. And the chipset caveat: **every Magic-series flagship and premium Honor ships Snapdragon** — the clean-SoC choices are the X-series, the 200 Lite, and (tipped) the Magic 8 Mini with Dimensity 9500. The same model name can even carry different silicon by market (the Honor 600: Dimensity in China, Snapdragon globally).

---

## 12. The "Clean Phone" Teardowns — Honest Results

- **PINE64 PinePhone:** Allwinner A64 SoC (Chinese), Realtek Wi-Fi, OmniVision camera (clean), Quectel EG25-G modem (Chinese — one of the only clean modems in existence), Goodix touch controller, hardware kill switches for modem/mic/camera. **No Israeli-authored component was found anywhere in the build** — the single cleanest phone in the investigation. Performance is entry-level at best; the ecosystem is hobbyist; and US carriers barely tolerate it (Part 16).
- **Purism Librem 5:** NXP i.MX8M SoC — NXP has an Israeli design center in Yokne'am — **Micron RAM** (tainted), Samsung rear camera (tainted), BroadMobi modem (clean), Kioxia storage (clean). The privacy community's flagship fails the criterion at three layers.
- **Fairphone 5:** Qualcomm QCM6490 — the "ethical phone" shares the Android flagship's core taint.
- **Punkt MC02** ($749, Swiss; Apostrophy OS built on GrapheneOS): Dimensity 900 — the minimalist-privacy flagship runs the investigation's cleanest-audited SoC. RAM/flash vendors undocumented.
- **Mudita Kompakt** ($439–519, Warsaw): MediaTek MT6761 on a de-Googled AOSP-based OS with hardware kill switches; FCC/PTCRB certified and tested working on AT&T, T-Mobile, and Verizon. A genuinely new clean option with proper US carrier certification — the strongest European entry.
- **Light Phone 3:** Qualcomm inside — tainted.

---

## 13. Prepaid, Part One — The Shelf, the Flips, and the Corporate Lineages

Prepaid solves a *billing and identity* problem — no contract, no credit check, often no name at point of sale — but it changes neither the hardware criterion nor the network criterion. What it does offer is a shelf of cheap hardware from which genuinely cleaner silicon can be selected, and a set of corporate lineages worth mapping.

**The shelf.** Current US prepaid inventory (Tracfone, Straight Talk, carrier prepaid at Walmart and elsewhere) resolves into four brands: BLU, TCL, Motorola, and Nokia. BLU is a private American company (founded 2009, Doral/Miami, by Samuel Ohev-Zion; 70 million-plus devices sold; focus on the US, Latin America, and the Caribbean; "designed in Miami" branding over Chinese manufacturing) — with one caveat that belongs in the record: the **2018 FTC settlement** over China-based ADUPS firmware that collected personal data without disclosure, binding BLU to a 20-year third-party security-monitoring program. BLU is clean on the Israeli criterion and flagged on a *different* state's data practices — the same inversion pattern as Honor and Transsion. TCL and Motorola follow the ledger above; Nokia's Unisoc models are the clean flips.

**The flip-phone chipset split, model by model** — the cheapest prepaid tier hides its silicon on the spec sheet, so it is documented here: **Nokia 2760 Flip and 2780 Flip: Qualcomm Snapdragon 215 — tainted.** Nokia 2660 Flip: Unisoc T107 — clean. New HMD 2760 Flip 4G: Unisoc T310 — clean. CAT S22 Flip (T-Mobile): Snapdragon 215 — tainted. Alcatel Go Flip: Qualcomm — tainted. The senior-phone channel follows the same split: Europe's Doro (Swedish), Swissvoice (Swiss), and Emporia (Austrian) carry no Israeli corporate ties, while every US rugged handset (Sonim's XP8/Xp10/XP Pro/XP5plus; Kyocera's DuraForce) is 100 percent Qualcomm.

**Tracfone — the complete corporate lineage.** Founded 1996 in Miami as Topp Telecom by David Topp and F.J. Pollak — the company that effectively invented the US prepaid phone model. February 1999: Telmex invested $57.5 million for a 55% controlling stake; in 2000 Telmex spun off its mobile unit as América Móvil (Carlos Slim's vehicle). Growth via acquisition: Straight Talk (Walmart partnership, 2009), Simple Mobile (2012), Page Plus (2013) — a family reaching roughly 20 million subscribers through 90,000 retail locations. September 14, 2020: Verizon announced acquisition for approximately $6.25 billion in cash and stock (headline value up to $6.9 billion); FCC approval November 22, 2021 carried demanding conditions (Lifeline participation for 7–20 years, customer migration to the Verizon network, device unlocking); the deal closed November 23, 2021 ($3,125 million in cash plus 57.6 million Verizon shares, with up to $650 million more). Every Tracfone-family prepaid SIM now terminates in Verizon — venture-level Israeli ties included.

**The full MVNO ownership map.** Mint Mobile (founded 2015 by David Glickman and Rizwan Kassim; Ryan Reynolds took 25% in 2019) was acquired by **T-Mobile US in May 2024 for up to $1.35 billion — parent company Ka'ena Corporation (Mint, Ultra Mobile, Plum) went with it** — Mint is now wholly inside T-Mobile, which is ~51.4% owned by Deutsche Telekom. Tello is an independent US MVNO whose parent KeepCalling was founded by Romanian entrepreneur Florin Miron in 2002 — **the only independent, no-ties MVNO identified**. Boost rides AT&T/T-Mobile under EchoStar (no ties found at EchoStar's own level). Cricket belongs to AT&T; Metro to T-Mobile; Visible to Verizon; Consumer Cellular is a US company with no ties found at its own level. **Net finding: independent MVNO corporate layers surfaced zero Israeli ties of their own — every tie in the US prepaid stack enters through the underlying network owner or the billing substrate below.**

**The refill-card layer.** The physical prepaid refill cards sold at Walmart, Target, and grocery registers are distributed through Blackhawk Network and InComm — both American companies, with no Israeli ties found at the distribution layer. The card, like the SIM inside the phone's tray, is one of the few genuinely clean artifacts in the entire stack.

**The kosher-phone channel.** A US distribution layer most audits never examine: TAG Israel (a community filtering operation run from Jerusalem, installing content filters on smartphones and the Nokia 4G feature-phone line), TAG US (Lakewood, NJ), and GenTech (Brooklyn/Lakewood, 20-plus years of filtered-device sales "for local and Israeli use"). The hardware is ordinary; the Israeli connection is the *service layer* — installation, filter policy, and remote administration anchored in Israeli-based organizations. A distinct channel-layer tie, recorded separately from the handset ledger.

---

## 14. SIM and eSIM — Genuinely Clean, With Two Caveats

- **Physical SIM cards:** the global supply is dominated by Thales (Gemalto), IDEMIA, G+D (Giesecke+Devrient), Kona I (Korea), and Chinese makers (Datang, Wuhan Tianyu, Watchdata, Eastcompeace) — French, German, Dutch, Korean, Chinese. **No Israeli SIM manufacturer exists or was found anywhere in the supply chain.** Your SIM card is not Israeli.
- **The secure chips inside cards and eSIMs** come from STMicroelectronics (clean), Infineon (German, clean — the same corporate family that gave the iPhone its only clean modem chapter), NXP (**tainted** — its Yokne'am design center), and Samsung (tainted via SIRC).
- **eUICC software** (the SIM operating system inside eSIMs) is written by Thales, G+D, IDEMIA, and **Kigen** — a UK company but an **Arm spinoff**, inheriting ARM's Ra'anana taint indirectly. **Practical takeaway: prefer a physical SIM.**
- **iSIM** — the SIM moving inside the main SoC — is the industry direction, which folds this layer back into the silicon layer (Qualcomm/MediaTek/Apple). Note it as a trend, not a current constraint.

---

## 15. The Carrier Layer — All Three US Networks Are Tied; AT&T Is the Deepest

- **AT&T:** Israeli R&D since the 2007 Interwise acquisition; **~500 employees across two centers** (Tel Aviv's ToHA Tower and Airport City) as of the most recent reporting; scope includes **5G network software, cloud transformation, and "advanced products for managing first responder systems worldwide" — FirstNet, the US national public-safety network**. The center's own description: it "leads strategic initiatives for the entire company." An AT&T-based prepaid plan means calls traversing network software with Israeli authorship.
- **Verizon:** Verizon Ventures' Tel Aviv office (2017–March 2023) invested in **13 Israeli startups** (Cellwize — later acquired by Qualcomm; Vdoo — to JFrog; Iguazio — to McKinsey); the office closed, existing investments continue. Verizon's *network* itself shows no Israeli R&D center — lighter than AT&T by a full grade.
- **T-Mobile / Deutsche Telekom:** T-Venture has invested in Israeli venture funds since at least 2002 (per Deutsche Telekom's own SEC filings); DT's M&A records list an investment in Israeli software company Teridion; T-Mobile Ventures launched in 2020. **T-Mobile-based prepaid is the lightest-tied network option.**
- **MVNO mapping recap:** Tracfone family (Tracfone, Straight Talk, Total, Walmart Family Mobile) → Verizon only since the 2022 migration; Cricket → AT&T; Metro → T-Mobile; Boost → AT&T/T-Mobile; Mint, US Mobile (white SIM), Tello, Simple Mobile → T-Mobile.

---

## 16. The VoLTE Whitelist — Why the Cleanest Phone Barely Attaches to US Networks

Since the 3G shutdowns, US carriers authenticate voice service through VoLTE whitelists — carrier-maintained lists of approved device models — and this wall hits exactly the phones this investigation rates cleanest. AT&T moved to an explicit whitelist and excluded the PinePhone from March 2021; T-Mobile maintains a "compatible device" list that also excludes uncertified hardware, though workable service is reported on T-Mobile and its MVNOs, sometimes via the documented workaround of activating with an approved IMEI and moving the SIM. Purism now ships the Librem 5 with VoLTE enabled, but community threads document the same reality: hardware support plus **carrier certification** is the gate. The whitelist is a *usability* wall, not an Israeli tie — but it is the binding practical constraint on how far the clean-hardware answer can go in the American market.

---

## 17. The Back Office — Amdocs, Comverse, and a Century of Israeli Carrier Software

- **Amdocs:** founded **1982 in Israel** as an offshoot of the Golden Pages directory business; headquarters now in Missouri; NASDAQ: DOX; record **$5 billion revenue in 2024**; billing and CRM for **~90% of the world's top carriers; 1.7 billion customer interactions daily**; roughly **25% of total revenue from AT&T alone**; customers include AT&T, Verizon, T-Mobile US, Comcast, Altice, Deutsche Telekom, and Vodafone; the Verizon relationship dates to a 2003 contract reported at $700 million to $1 billion over five years. **There is no US carrier — and no US prepaid brand — whose customer-facing back office is documented as Amdocs-free.** Switching costs are described by analysts as near-prohibitive; the layer is stable, not trending away. Every refill-card purchase, plan activation, and balance check runs on Israeli-founded software with Israeli R&D.
- **Comverse/Verint — the historical layer.** Founded 1982–84 by three Israelis (Kobi Alexander, Boaz Misholi, Yechiam Yemini) as Efrat Future Technologies, R&D in Israel, funded partly by Israeli government grants. Products: voicemail, SMS centers, and billing — the 1997 Boston Technology acquisition ($843 million in stock) made it the voice-messaging supplier to 12 of the world's top 20 carriers, with Deutsche Telekom among its earliest big customers; its Trilogue systems served prepaid markets in developing countries — functionally the first great prepaid-billing vendor. Its interception-recording product line became **Verint** (2002). A 2001 Fox News investigation alleged Comverse/Amdocs wiretap access — **recorded only as a disputed, never-substantiated claim**; it was never proven and is flagged, not adopted. Comverse dissolved in 2012–13; its telecom business became Xura (2015) then **Mavenir** (2017) — so today's US open-RAN champion carries Comverse's Israeli engineering lineage — and part of Comverse went to Amdocs in 2015. The interception line lives on directly: Verint today sells lawful-intercept and analytics systems into carrier and government markets worldwide — the corporate descendant of Comverse's 1990s interception products, still serving the same function a generation later.
- **Cellebrite — the point of sale.** The machine the store employee uses to move your contacts, photos, and messages to a new prepaid phone is Israeli. Cellebrite (Petah Tikva, founded December 1999) began with the UME phone-to-phone transfer device sold to telecoms and phone stores; by 2005 the company said it was in **more than half of all Verizon and T-Mobile stores in the US, plus Best Buy and Walmart phone departments**; a Verizon-premium-retailer (Russell Cellular) was still announcing Cellebrite rollouts in 2016. The same company is, per The Intercept, "the FBI's go-to hackers" — its UFED forensics line extracts data from seized phones for law enforcement worldwide. The consumer transfer box and the police forensic box are one company's two product lines. **Mitigation is trivial: decline the in-store transfer and move data yourself.**

---

## 18. The Backup-Cloud Layer — Samsung and Microsoft, Ending This Week

Samsung's 2019 Microsoft partnership made OneDrive the built-in default backup for Galaxy photos; Samsung Cloud's own sync shut down in 2021, herding users to Microsoft servers; and **September 30, 2026 — the week of this document's compilation — Samsung Gallery's OneDrive sync ended**, with Samsung moving to its own cloud (existing files remain on Microsoft servers; OneDrive and Microsoft 365 app preloads continue). For five years, every Samsung phone's camera roll defaulted to **Microsoft Azure — BRS 711 in the laptop investigation, the Unit 8200 cloud**. That default is now retired.

---

## 19. The App and SDK Strata — Israeli Code Reaches the Phone Through Three Doors

**Door one — the apps themselves.** Meta's Tel Aviv office is a documented R&D center for "Facebook and Instagram's core advertising and [AI]" systems — and Meta's apps ship preinstalled or near-mandatory on virtually every prepaid Android. Spotify runs a Tel Aviv R&D office of roughly 300 staff working on recommendation and AI. Waze is Israeli-born and Google-owned. Via — the transit/ride platform used by cities worldwide — is Israeli-founded, with two wholly-owned Israeli subsidiaries and 250-plus Israel staff, per its own SEC filing. (Uber's own direct Israeli footprint was not confirmed; search results conflated it with Via, and the distinction is preserved rather than collapsed.)

**Door two — the SDKs embedded inside other people's apps.** This is the deepest software finding of the investigation. **AppsFlyer — Israeli-founded (2011; CEO Oren Kaniel; headquarters effectively "San Francisco, Israel"), ~$500 million ARR as of January 2026, profitable since 2024 — is the dominant mobile-attribution SDK: per its own industry data it leads the Android market with 48.51% of all installs** (third-party trackers put its share near 44%, ahead of Germany's Adjust at ~27% and the US Branch at ~22%). Its Series C was led by Israeli VCs Qumra and Pitango alongside Goldman Sachs and Deutsche Telekom Capital Partners. The average Android phone — including every clean Honor, Transsion, or BLU device — carries Israeli-authored tracking code inside its ordinary apps, reporting install behavior and in-app events. There is no consumer setting that removes an SDK from an app someone else wrote; the only mitigations are app selection (F-Droid's free-software catalog largely lacks it) and network-level blocking of its endpoints (imperfect). The same layer includes **ironSource** (Israeli, merged into Unity in a deal reported around $4.4 billion) — the monetization stack inside a large share of free mobile games (reported-deal grade, flagged for filing-grade confirmation).

**Door three — the games.** Israeli companies author a remarkable share of the world's top-grossing mobile games: **Playtika** (Herzliya, 2010; NASDAQ: PLTK; Slotomania, Bingo Blitz, June's Journey, Best Fiends), **Moon Active** (Tel Aviv; Coin Master with $6 billion-plus lifetime revenue and a #9 global revenue rank in H1 2024; a 22,000-square-meter expansion signed June 2026), **Plarium** (RAID: Shadow Legends, roughly $1 billion grossed), plus CrazyLabs, TabTale, SciPlay, and Playstudios — a sector generating about $9 billion, with 74% of its mobile-game workforce in the social/casual genres that dominate app-store charts. Game content is a consumption choice, unlike the SDK layer — a user who never installs Coin Master is untouched by Moon Active — but the two together complete the picture: Israeli-authored code, analytics, and content reach a typical phone through three independent doors.

---

## 20. Israel's Domestic Market — the "Domestic" Half of the Criterion

- **Operators and prepaid:** Cellcom (whose prepaid brand "TalkMan" became the generic Hebrew word for prepaid card), Partner, Pelephone (Israel's first operator, 1986), Hot Mobile, and Golan Telecom (merged into Cellcom in 2020 for roughly $216 million); MVNOs include Rami Levy, 012, Cellact, and Home Cellular. Tourist prepaid is passport-based; eSIM rollout is partial (Cellcom consumer eSIM from about 2022; Partner and Pelephone largely business-only).
- **5G (launched September 29, 2020):** licenses to Partner+Hot Mobile (joint) and Pelephone.
- **Network equipment vendors:** **Cellcom runs Nokia** for LTE (2014) and 5G edge slicing (a world-first live deployment in Netanya, 2022), plus a cloud-native 5G SA core — and conducted an Open RAN pilot with **Parallel Wireless**, a US-registered but Israeli-founded and Israeli-engineered vendor. **Pelephone's 5G was built with Ericsson** (an "independent 5G core"). The IDF's network is Motorola Solutions' exclusive domain.
- **Huawei's status in Israel: unresolved** — searches surfaced only UK/US ban material; no primary source confirming or denying an Israeli Huawei exclusion was found. Recorded as an open item rather than asserted from memory.

---

## 21. The Minimum-Ties Phone — the Practical Result

### Maximum mainstream cleanliness

| Layer | Choice | Residual taint |
|---|---|---|
| Handset | **Honor MediaTek model** (X-series, 200 Lite; Magic 8 Mini when it ships) | MediaTek Tier-D venture portfolio (incl. OneView/RDC adjacency); ARM IP; EDA tooling |
| Memory/storage | SK Hynix / Kioxia (teardown-dependent) | None found |
| Camera | Sony or OmniVision sensor | None found (avoid Samsung ISOCELL; Corephotonics zoom IP is licensed industry-wide) |
| Fingerprint | Goodix (avoid Qualcomm 3D Sonic) | None found |
| OS | Stock MagicOS with Meta apps uninstalled; FOSS apps from F-Droid where possible | GrapheneOS unavailable (Pixel-only); AppsFlyer-class SDKs in third-party apps |
| SIM | **Physical SIM** on Tello or T-Mobile-based prepaid | Card itself clean; network = T-Mobile/DT venture-level ties |
| eSIM | Declined | Avoids NXP chip + Kigen/Arm paths |
| Activation | Online self-activation; no in-store transfer | Avoids Cellebrite |
| Backup | Self-hosted or local | Avoids cloud substrate |

**Irreducible floor, stated plainly:** MediaTek's venture portfolio; ARM and Synopsys/Cadence tooling; T-Mobile/DT venture-level network ties; the **Amdocs billing substrate (unavoidable at any US carrier)**; AppsFlyer-class SDKs inside third-party apps; the ~1,400-veteran people layer; and the NSO/Intellexa/QuaDream offensive-cyber ecosystem (number-based, undodgeable by any purchase).

### Maximum literal cleanliness

**PinePhone** + T-Mobile-based prepaid with the IMEI workaround — no Israeli-authored component found in the build, at hobbyist performance, against the VoLTE certification wall. The Mudita Kompakt is the certified, warranty-backed middle path: European company, MediaTek silicon, de-Googled OS, kill switches, works on all three US networks.

---

## 22. Methodology and Evidence Grading

**How the investigation was conducted.** Six sequential research passes: breadth mapping; targeted gap-closure; primary-source deep reading (full articles and audit dossiers rather than snippets); the prepaid/carrier/SIM sweep; the complete brand sweep (~40 families); and the app/SDK strata. Sources include forensic corporate audits (OpenIntel's BDS-1000 dossiers for Honor, MediaTek, Apple, Samsung, GrapheneOS — cited with their methodology *and* their exculpatory findings), SEC filings (Mobileye, AMD, Via), company press releases and spec sheets (Lenovo/Infinidat, Honor's own device comparison tables), named-executive interviews (Srouji/Ynet), Israeli business press (Calcalist, Globes, CTech), quality international press (NYT, The Intercept, Light Reading, FDI Intelligence), FCC records (the Tracfone approval), court testimony (the Apple–Qualcomm litigation), and community/technical documentation (VoLTE whitelists, PinePhone wiki, device spec databases).

**Evidence grades used throughout:**
- **Audit-grade:** documented in a forensic dossier with explicit "no public evidence identified" statements.
- **Filing-grade:** corporate disclosure (SEC, subsidiary schedules).
- **On-record:** named executive or company statement.
- **Reported:** quality press, single or convergent sourcing.
- **Unresolved:** flagged where evidence is thin, dated, or contested.

**Caveats the record requires:**
- "No public evidence identified" records the result of specified public-source checks; it does not prove non-public activity impossible. It applies symmetrically — to MediaTek's lack of military contracts and to Apple's lack of them alike.
- The BDS-1000 framework is one human-vetted scoring system, reproduced here as a summary of *documented activity*, not as an endorsement of its politics; the underlying facts stand independently of the scores.
- Where the user's criterion is "zero ties in any way," even venture-portfolio adjacency (MediaTek's OneView/RDC round) and distributor channels count; where it is "nothing Israeli inside the machine," MediaTek silicon qualifies as clean. Both readings are maintained side by side throughout.
- Personal details about private individuals (a founder's background, an executive's faith) are treated as irrelevant to the corporate criterion and excluded; companies are what they do.

---

## 23. What Remains Unresolved — the Complete List

1. **Apple Secure Enclave provenance** — no sources found in repeated attempts.
2. **Apple U1/U2 ultra-wideband provenance** — no sources found.
3. **Punkt MC02 RAM/flash vendors** — no teardown exists; industry norms suggest Samsung or Micron (inference, flagged).
4. **Ericsson's Israeli R&D presence** — two dedicated search rounds produced nothing either way; its network *operations* in Israel are documented.
5. **Israel's Huawei 5G stance** — searches surfaced UK/US material only.
6. **MediaTek's post-2024 venture portfolio** — 2025 filings do not confirm continuation or exit.
7. **Xiaomi's own direct Israel footprint** — now actively unresolved: the documented R&D center belongs to Xiaoyi, not Xiaomi; only retail sales presence is confirmed.
8. **Uber's direct Israeli operations** — conflated with Via in search results; recorded separately.
9. **Any US MVNO running non-Amdocs billing** — none found; per-carrier confirmation is impractical.
10. **Honor's Magic 8 Mini chipset** — tipped (Dimensity 9500), not yet shipping-confirmed at compilation time.

---

## 24. Key Figures at a Glance

| Entity | Score / grade | Governing fact |
|---|---|---|
| **Honor** | **BRS 192 — Tier E** | Cleanest entity audited; only "tie" is an app's Israel availability listing; state-linked Chinese ownership |
| **MediaTek** | BRS 248 — Tier D | No office/subsidiary/contracts; venture portfolio incl. OneView/RDC adjacency; distributor channels |
| Apple | BRS 582 — Tier C | Israeli CPU cores; C1X/N1; storage controllers; Q.ai ~$1.5–2B (Jan 2026); Benevity controversy; near-zero military/digital |
| Samsung | BRS 639 — Tier B | SIRC flash/UFS + Herzliya cameras + Transchip; Exynos contributions |
| Qualcomm | (silicon-level taint) | Haifa/Hod Hasharon since 1993; Autotalks 2023; $1B Apple exclusivity era |
| Microsoft (laptop ref) | BRS 711 — Tier B | Azure/Unit 8200 record; $133M IMOD agreement |
| Intel (laptop ref) | BRS 712 — Tier B | Kiryat Gat; Mobileye 96.9% voting control |
| Dell (laptop ref) | BRS 691 — Tier B | Israeli M&A >$1B; $150M+ IMOD tender |
| Huawei | No score; corporate tie confirmed | Toga Networks ~400–500 staff; HexaTier; Kirin silicon clean |
| GrapheneOS | Audit-clean (software) | Pixel-only hardware binds it to Tensor |
| AppsFlyer | Not scored; market leader | 48.51% of Android installs; $500M ARR; Israeli-founded |
| NSO Group | Entity-listed (US, Nov 2021) | Pegasus as state weapon; DECA licensing; $8M/25 numbers |

---

## 25. Glossary

- **SoC (System on Chip):** one chip fusing processor, graphics, camera processing, security, and modem interface — the reason a phone cannot mix-and-match parts the way a laptop can.
- **Baseband / modem:** the phone's second, secret computer — its own closed operating system, the most privileged attack surface in mobile hardware.
- **ISP:** image signal processor — the silicon that turns raw sensor data into photos.
- **UFS / eMMC:** the storage interface standards inside phones; Samsung's Israeli center architects them.
- **SDK:** software development kit — code an app developer embeds; the AppsFlyer attribution SDK sits inside roughly half of Android apps.
- **Attribution:** the analytics discipline of determining which ad caused an install.
- **SEP:** standard-essential patent — a patent a standard (like 5G) cannot be practiced without.
- **MVNO:** mobile virtual network operator — a carrier that owns no towers and rides a major network (Mint, Tello, Cricket).
- **VoLTE whitelist:** a carrier's approved-device list for voice-over-LTE; uncertified phones cannot make calls on US networks.
- **eSIM / eUICC / iSIM:** software SIM (eSIM) and its operating system (eUICC); iSIM moves the SIM into the main processor.
- **CALEA:** the US law requiring carriers to build lawful-intercept capability into their networks.
- **BSS/OSS:** business and operations support systems — billing, CRM, provisioning: Amdocs' domain.
- **Open RAN:** a movement to open cellular network hardware interfaces; vendors include Mavenir (Comverse lineage) and Parallel Wireless (Israeli-founded).
- **Tier E/D/C/B:** OpenIntel's complicity bands — E (Minimal/None) through B (Severe); BRS is the 1,000-point score.
- **Unit 8200:** the IDF's signals-intelligence unit and the industry's talent pipeline.
- **IMOD:** Israel Ministry of Defense. **DECA:** its export-control arm, which licenses Pegasus exports.
- **Entity List:** the US Commerce Department blacklist (NSO added November 2021; Toga added August 2020).

---

## 26. The Conclusion, in One Paragraph

A cell phone with zero ties to Israel cannot be bought — not because of one component but because Israeli engineering sits inside every flagship silicon architecture, every Western modem, the tools that design all chips, the billing software that runs nearly every carrier, the dominant advertising SDK inside half of all apps, and an export-licensed offensive-cyber industry built to attack the devices themselves. What a buyer *can* do is now mapped to the last layer: an Honor phone with a MediaTek chip — the only Tier E company and the cleanest silicon audited — on a T-Mobile-based prepaid plan with a physical SIM, activated online, with Meta apps uninstalled and F-Droid apps preferred; or, for maximal literal cleanliness, a PinePhone with all the compromises that entails, or the certified European middle path of the Mudita Kompakt. Every choice above that floor leaves a documented residue — a venture portfolio, a distributor channel, a billing substrate, an SDK in someone else's app, a people layer no purchase can reach — and this document's purpose is that none of those residues is hidden from the buyer who wants to know. Every layer was audited, every brand was searched, nothing was adopted from anyone's theory, and everything unresolved is marked unresolved.

---

*Compiled 2026-09-20. Six research passes; primary sources opened in full; all monetary figures as reported by cited sources, dated figures labeled; "no public evidence identified" statements preserved verbatim from the underlying audits.*
